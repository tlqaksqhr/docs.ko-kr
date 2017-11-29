---
title: WSStreamedHttpBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97ce4d3d-ca6f-45fa-b33b-2429bb84e65b
caps.latest.revision: "27"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8238ede6fd43cc5cca2df1f8c7f9162f9c4a1302
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="wsstreamedhttpbinding"></a>WSStreamedHttpBinding
이 샘플에서는 HTTP 전송이 사용될 때 스트리밍 시나리오를 지원하도록 디자인된 바인딩을 만드는 방법을 보여 줍니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Binding\WSStreamedHttpBinding`  
  
 새 표준 바인딩을 만들고 구성하기 위한 단계는 다음과 같습니다.  
  
1.  새 표준 바인딩 만들기  
  
     basicHttpBinding 및 netTcpBinding과 같은 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 표준 바인딩은 특정 요구 사항에 맞게 기본 전송 및 채널 스택을 구성합니다. 이 샘플에서 `WSStreamedHttpBinding`은 스트리밍을 지원하도록 채널 스택을 구성합니다. 기본적으로 WS-Security 및 신뢰할 수 있는 메시징은 스트리밍에서 지원되지 않으므로 이러한 기능은 둘 다 채널 스택에 추가되지 않습니다. 새 바인딩은 `WSStreamedHttpBinding`에서 파생되는 <xref:System.ServiceModel.Channels.Binding> 클래스에서 구현됩니다. `WSStreamedHttpBinding`은 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>, <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> 및 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 바인딩 요소를 포함합니다. 다음 샘플 코드와 같이 결과 바인딩 스택을 구성하기 위해 클래스에서 `CreateBindingElements()` 메서드를 제공합니다.  
  
    ```  
    public override BindingElementCollection CreateBindingElements()  
    {  
         // return collection of BindingElements  
         BindingElementCollection bindingElements = new BindingElementCollection();  
  
        // the order of binding elements within the collection is important: layered channels are applied in the order included, followed by  
        // the message encoder, and finally the transport at the end  
        if (flowTransactions)  
        {  
            bindingElements.Add(transactionFlow);  
        }  
        bindingElements.Add(textEncoding);  
  
        // add transport (http or https)  
        bindingElements.Add(transport);  
        return bindingElements.Clone();  
    }  
    ```  
  
2.  구성 지원 추가  
  
     구성을 통해 전송을 노출하기 위해 샘플에서는 두 개의 추가 클래스인 `WSStreamedHttpBindingConfigurationElement` 및 `WSStreamedHttpBindingSection`을 구현합니다. `WSStreamedHttpBindingSection` 클래스는 <xref:System.ServiceModel.Configuration.StandardBindingCollectionElement%602> 구성 시스템에 `WSStreamedHttpBinding`을 노출하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]입니다. 대량의 구현은 `WSStreamedHttpBindingConfigurationElement`에서 파생되는 <xref:System.ServiceModel.Configuration.StandardBindingElement>에 위임됩니다. `WSStreamedHttpBindingConfigurationElement` 클래스에는 `WSStreamedHttpBinding`의 속성에 해당하는 속성과 각 구성 요소를 바인딩에 매핑하기 위한 함수가 있습니다.  
  
     서비스의 구성 파일에 다음 섹션을 추가하여 구성 시스템에 처리기를 등록합니다.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <extensions>  
          <bindingExtensions>  
            <add name="wsStreamedHttpBinding" type="Microsoft.ServiceModel.Samples.WSStreamedHttpBindingCollectionElement, WSStreamedHttpBinding, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
          </bindingExtensions>  
        </extensions>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     그런 다음 serviceModel 구성 섹션에서 처리기를 참조할 수 있습니다.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <endpoint  
                    address="https://localhost/servicemodelsamples/service.svc"  
                    bindingConfiguration="Binding"  
                    binding="wsStreamedHttpBinding"  
                    contract="Microsoft.ServiceModel.Samples.IStreamedEchoService"/>  
        </client>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  에 나열 된 단계를 수행 했는지 확인 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
3.  수행 했는지 확인 하십시오.는 [인터넷 정보 서비스 (IIS) 서버 인증서 설치 지침](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)합니다.  
  
4.  지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
5.  다중 컴퓨터 구성에서 샘플을 실행 하려면의 지침에 따라 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
6.  클라이언트 창이 표시되면 "Sample.txt"를 입력합니다. 디렉터리에서 "Copy of Sample.txt"를 볼 수 있습니다.  
  
## <a name="the-wsstreamedhttpbinding-sample-service"></a>WSStreamedHttpBinding 샘플 서비스  
 `WSStreamedHttpBinding`을 사용하는 샘플 서비스는 서비스 하위 디렉터리에 있습니다. `OperationContract` 구현에서는 `MemoryStream`을 반환하기 전에 `MemoryStream`을 사용하여 들어오는 스트림에서 모든 데이터를 검색합니다. 샘플 서비스는 IIS(인터넷 정보 서비스)에 의해 호스팅됩니다.  
  
```  
[ServiceContract]  
public interface IStreamedEchoService  
{  
    [OperationContract]  
    Stream Echo(Stream data);  
}  
  
public class StreamedEchoService : IStreamedEchoService  
{  
    public Stream Echo(Stream data)  
    {  
        MemoryStream dataStorage = new MemoryStream();  
        byte[] byteArray = new byte[8192];  
        int bytesRead = data.Read(byteArray, 0, 8192);  
        while (bytesRead > 0)  
        {  
            dataStorage.Write(byteArray, 0, bytesRead);  
            bytesRead = data.Read(byteArray, 0, 8192);  
        }  
        data.Close();  
        dataStorage.Seek(0, SeekOrigin.Begin);  
  
        return dataStorage;  
    }  
}  
```  
  
## <a name="the-wsstreamedhttpbinding-sample-client"></a>WSStreamedHttpBinding 샘플 클라이언트  
 `WSStreamedHttpBinding`을 사용하여 상호 작용하는 데 사용되는 클라이언트는 클라이언트 하위 디렉터리에 있습니다. 이 샘플에 사용된 인증서는 Makecert.exe를 사용하여 만든 테스트 인증서이므로 브라우저에서 https://localhost/servicemodelsamples/service.svc와 같은 HTTPS 주소에 액세스하려 하면 보안 경고가 나타납니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 제공되는 테스트 인증서를 사용하여 작업을 수행할 수 있도록 클라이언트에 추가 코드를 추가하여 보안 경고가 나타나지 않게 합니다. 코드 및 함께 사용되는 클래스는 프로덕션 인증서를 사용할 때에는 필요가 없습니다.  
  
```  
// WARNING: This code is only required for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
## <a name="see-also"></a>참고 항목
