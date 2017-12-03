---
title: HttpCookieSession
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 101cb624-8303-448a-a3af-933247c1e109
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 72d6dcef2ac59fd63706d8d8c843f739575cf5cc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="httpcookiesession"></a>HttpCookieSession
이 샘플에서는 세션 관리에 HTTP 쿠키를 사용하기 위해 사용자 지정 프로토콜 채널을 빌드하는 방법을 보여 줍니다. 이 채널은 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스와 ASMX 클라이언트 또는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 ASMX 서비스 사이의 통신을 가능하게 합니다.  
  
 클라이언트가 세션 기반의 ASMX 웹 서비스에 있는 웹 메서드를 호출하면 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 엔진은 다음 작업을 수행합니다.  
  
-   고유 ID(세션 ID)를 생성합니다.  
  
-   세션 개체를 생성하여 고유 ID에 연결합니다.  
  
-   고유 ID를 Set-Cookie HTTP 응답 헤더에 추가하여 클라이언트로 보냅니다.  
  
-   클라이언트로 보내는 세션 ID를 기반으로 이후의 호출에서 클라이언트를 식별합니다.  
  
 클라이언트는 이후에 서버로 보내는 요청에 이 세션 ID를 포함합니다. 서버는 클라이언트가 보낸 세션 ID를 사용하여 현재 HTTP 컨텍스트에 적절한 세션 개체를 로드합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\HttpCookieSession`  
  
## <a name="httpcookiesession-channel-message-exchange-pattern"></a>HttpCookieSession 채널 메시지 교환 패턴  
 이 샘플에서는 ASMX와 같은 시나리오에 대해 세션을 사용하도록 설정합니다. 채널 스택의 맨 아래에는 <xref:System.ServiceModel.Channels.IRequestChannel> 및 <xref:System.ServiceModel.Channels.IReplyChannel>을 지원하는 HTTP 전송이 있습니다. 채널은 채널 스택의 상위 수준에 세션을 제공합니다. 이 샘플에서는 세션을 지원하는 두 개의 채널(<xref:System.ServiceModel.Channels.IRequestSessionChannel> 및 <xref:System.ServiceModel.Channels.IReplySessionChannel>)을 구현합니다.  
  
## <a name="service-channel"></a>서비스 채널  
 이 샘플은 `HttpCookieReplySessionChannelListener` 클래스에 서비스 채널을 제공합니다. 이 클래스는 <xref:System.ServiceModel.Channels.IChannelListener> 인터페이스를 구현하고 채널 스택의 하위 수준에 있는 <xref:System.ServiceModel.Channels.IReplyChannel> 채널을 <xref:System.ServiceModel.Channels.IReplySessionChannel>로 변환합니다. 이 프로세스는 다음과 같이 나눌 수 있습니다.  
  
-   채널 수신기가 열리면 채널 수신기는 내부 수신기로부터 내부 채널을 받습니다. 내부 수신기는 데이터그램 수신기이고 받은 채널의 수명은 수신기의 수명에서 분리되므로 내부 수신기를 닫고 내부 채널만 유지할 수 있습니다.  
  
    ```  
                this.innerChannelListener.Open(timeoutHelper.RemainingTime());  
    this.innerChannel = this.innerChannelListener.AcceptChannel(timeoutHelper.RemainingTime());  
    this.innerChannel.Open(timeoutHelper.RemainingTime());  
    this.innerChannelListener.Close(timeoutHelper.RemainingTime());  
    ```  
  
-   열기 프로세스가 완료되면 내부 채널에서 메시지를 받도록 메시지 루프를 설정합니다.  
  
    ```  
    IAsyncResult result = BeginInnerReceiveRequest();  
    if (result != null && result.CompletedSynchronously)  
    {  
       // do not block the user thread  
       if (this.completeReceiveCallback == null)  
       {  
          this.completeReceiveCallback = new WaitCallback(CompleteReceiveCallback);  
       }  
       ThreadPool.QueueUserWorkItem(this.completeReceiveCallback, result);  
    }  
    ```  
  
-   메시지가 도착하면 서비스 채널은 세션 식별자를 확인하고 적절한 세션 채널로 디멀티플렉싱됩니다. 채널 수신기는 세션 식별자를 세션 채널 인스턴스에 매핑하는 사전을 유지 관리합니다.  
  
    ```  
    Dictionary<string, IReplySessionChannel> channelMapping;  
    ```  
  
 `HttpCookieReplySessionChannel` 클래스는 <xref:System.ServiceModel.Channels.IReplySessionChannel>을 구현합니다. 채널 스택의 상위 수준에서는 <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> 메서드를 호출하여 이 세션에 대한 요청을 읽습니다. 각 세션 채널에는 서비스 채널에서 채우는 개인 메시지 큐가 있습니다.  
  
```  
InputQueue<RequestContext> requestQueue;  
```  
  
 누군가가 <xref:System.ServiceModel.Channels.IReplyChannel.ReceiveRequest%2A> 메서드를 호출했지만 메시지 큐에 메시지가 없는 경우 채널은 지정된 시간 동안 대기한 후에 종료됩니다. 그러면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 이외의 클라이언트에 대해 생성된 세션 채널이 정리됩니다.  
  
 `channelMapping`을 사용하여 `ReplySessionChannels`를 추적하며, 받은 채널이 모두 닫힐 때까지 기본 `innerChannel`을 닫지 않습니다. 이렇게 하면 `HttpCookieReplySessionChannel`이 `HttpCookieReplySessionChannelListener`의 수명보다 오래 유지될 수 있습니다. 받은 채널은 `OnClosed` 콜백을 통해 수신기에 대한 참조를 유지하므로 수신기에서 수행되는 가비지 수집에 대해 걱정할 필요가 없습니다.  
  
## <a name="client-channel"></a>클라이언트 채널  
 해당 클라이언트 채널은 `HttpCookieSessionChannelFactory` 클래스에 있습니다. 채널을 만드는 동안 채널 팩터리는 내부 요청 채널을 `HttpCookieRequestSessionChannel`로 래핑합니다. `HttpCookieRequestSessionChannel` 클래스는 호출을 기본 요청 채널로 전달합니다. 클라이언트가 프록시를 닫으면 `HttpCookieRequestSessionChannel`은 채널이 닫히는 것을 알리는 메시지를 서비스로 보냅니다. 따라서 서비스 채널 스택은 사용 중인 세션 채널을 정상적으로 종료할 수 있습니다.  
  
## <a name="binding-and-binding-element"></a>바인딩 및 바인딩 요소  
 서비스 및 클라이언트 채널을 만든 다음에는 이 채널을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 런타임에 통합해야 합니다. 채널은 바인딩 및 바인딩 요소를 통해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에 노출됩니다. 이 바인딩은 하나 또는 여러 개의 바인딩 요소로 구성됩니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 BasicHttpBinding 또는 WSHttpBinding과 같은 여러 가지 시스템 정의 바인딩을 제공합니다. `HttpCookieSessionBindingElement` 클래스에는 바인딩 요소의 구현이 포함되어 있습니다. 이 클래스는 채널 수신기 및 채널 팩터리 만들기 메서드를 재정의하여 필요한 채널 수신기 또는 채널 팩터리 인스턴스화를 수행합니다.  
  
 이 샘플에서는 서비스 설명에 정책 어설션을 사용합니다. 따라서 이 샘플을 사용하면 서비스를 사용할 수 있는 다른 클라이언트에 채널 요구 사항을 게시할 수 있습니다. 예를 들어 이 바인딩 요소는 정책 어설션을 게시하여 세션을 지원함을 잠재적 클라이언트에게 알립니다. 이 샘플에서는 바인딩 요소 구성에서 `ExchangeTerminateMessage` 속성을 사용하도록 설정하므로 서비스가 세션 대화를 종료하기 위한 추가 메시지 교환 작업을 지원하는 것을 보여 주기 위해 필요한 어설션을 추가합니다. 그런 다음 클라이언트는 이 작업을 사용할 수 있습니다. 다음 WSDL 코드는 `HttpCookieSessionBindingElement`에서 만든 정책 어설션을 보여 줍니다.  
  
```xml  
<wsp:Policy wsu:Id="HttpCookieSessionBinding_IWcfCookieSessionService_policy" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
<wsp:ExactlyOne>  
<wsp:All>  
<wspe:Utf816FFFECharacterEncoding xmlns:wspe="http://schemas.xmlsoap.org/ws/2004/09/policy/encoding"/>  
<mhsc:httpSessionCookie xmlns:mhsc="http://samples.microsoft.com/wcf/mhsc/policy"/>  
</wsp:All>  
</wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 `HttpCookieSessionBinding` 클래스는 이전에 설명한 바인딩 요소를 사용하는 시스템 제공 바인딩입니다.  
  
## <a name="adding-the-channel-to-the-configuration-system"></a>구성 시스템에 채널 추가  
 이 샘플에서는 구성을 통해 샘플 채널을 노출하는 두 개의 클래스를 제공합니다. 첫 번째 클래스는 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>의 `HttpCookieSessionBindingElement`입니다 대량의 구현은 `HttpCookieSessionBindingConfigurationElement`로부터 파생되는 <xref:System.ServiceModel.Configuration.StandardBindingElement>에 위임됩니다. `HttpCookieSessionBindingConfigurationElement`에는 `HttpCookieSessionBindingElement`의 속성에 대응하는 속성이 있습니다.  
  
### <a name="binding-element-extension-section"></a>바인딩 요소 확장 섹션  
 `HttpCookieSessionBindingElementSection` 섹션은 구성 시스템에 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>을 노출하는 `HttpCookieSessionBindingElement`입니다. 몇 가지 재정의를 통해 구성 섹션 이름, 바인딩 요소의 형식 및 바인딩 요소를 만드는 방법을 정의합니다. 그러면 다음과 같이 구성 파일의 확장 섹션을 등록할 수 있습니다.  
  
```xml  
<configuration>        
    <system.serviceModel>        
      <extensions>          
        <bindingElementExtensions>            
          <add name="httpCookieSession"   
               type=  
"Microsoft.ServiceModel.Samples.HttpCookieSessionBindingElementElement,   
                    HttpCookieSessionExtension, Version=1.0.0.0,   
                    Culture=neutral, PublicKeyToken=null"/>  
        </bindingElementExtensions >  
      </extensions>  
  
      <bindings>  
      <customBinding>  
        <binding name="allowCookiesBinding">  
          <textMessageEncoding messageVersion="Soap11WSAddressing10" />  
          <httpCookieSession sessionTimeout="10" exchangeTerminateMessage="true" />  
          <httpTransport allowCookies="true" />  
        </binding>  
      </customBinding>  
      </bindings>        
    </system.serviceModel>    
</configuration>  
```  
  
## <a name="test-code"></a>테스트 코드  
 이 샘플 전송을 사용하기 위한 테스트 코드는 Client 및 Service 디렉터리에 있습니다. 두 개의 테스트 구성-하나의 테스트 된 바인딩을 사용 `allowCookies` 로 설정 `true` 클라이언트에서. 두 번째 테스트에서는 종료 메시지 교환을 사용하여 바인딩에서 명시적인 종료를 사용하도록 설정합니다.  
  
 샘플을 실행하면 다음 출력이 표시됩니다.  
  
```  
Simple binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
Smart binding:  
AddItem(10000,2): ItemCount=2  
AddItem(10550,5): ItemCount=7  
RemoveItem(10550,2): ItemCount=5  
Items  
10000, 2  
10550, 3  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
3.  지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
4.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
## <a name="see-also"></a>참고 항목
