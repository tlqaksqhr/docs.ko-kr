---
title: Discovery 바인딩 Element 샘플
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af513015-85bf-417b-8729-1bdff77ff6d6
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 624209221dc8c2745afa6b4db20df6e47c7374f1
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="discovery-binding-element-sample"></a>Discovery 바인딩 Element 샘플
이 샘플에서는 검색 클라이언트 바인딩 요소를 사용하여 서비스를 검색하는 방법을 보여 줍니다. 개발자는 이 기능을 사용하여 기존 클라이언트 채널 스택에 검색 클라이언트 채널을 추가할 수 있으므로 프로그래밍 모델을 매우 직관적으로 만들 수 있습니다. 연결된 채널이 열리면 검색을 사용하여 서비스의 주소가 확인됩니다. 이 샘플은 다음 프로젝트로 구성되어 있습니다.  
  
-   **CalculatorService**: 검색 가능한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.  
  
-   **CalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] discovery 클라이언트 채널을 사용 하 여 검색 하 고 CalculatorService를 호출 하는 클라이언트 응용 프로그램입니다.  
  
-   **DynamicCalculatorClient**: A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 동적 끝점을 사용 하 여 검색 하 고 CalculatorService를 호출 하는 클라이언트 응용 프로그램입니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryBindingElement`  
  
## <a name="calculatorservice"></a>CalculatorService  
 이 프로젝트에는 `ICalculatorService` 계약을 구현하는 간단한 계산기 서비스가 포함되어 있습니다.  
  
 다음 App.config 파일은 서비스 동작과 검색 끝점에 `<serviceDiscovery>` 동작을 추가하는 데 사용됩니다.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
        <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <!--Enable discovery through configuration.-->  
      <serviceBehaviors>  
        <behavior name="CalculatorBehavior">  
          <serviceDiscovery>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 이렇게 하면 서비스와 해당 끝점이 검색 가능하게 됩니다. CalculatorService는 NetTcpBinding 바인딩을 사용하여 하나의 끝점을 추가하는 자체 호스팅 서비스입니다. 또한 다음 코드와 같이 끝점에 `EndpointDiscoveryBehavior`를 추가하고 범위를 지정합니다.  
  
```  
// Add a NET.TCP endpoint and add a scope to that endpoint.  
ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new NetTcpBinding(), netTcpAddress);  
EndpointDiscoveryBehavior netTctEndpointBehavior = new EndpointDiscoveryBehavior();  
netTctEndpointBehavior.Scopes.Add(new Uri("ldap:///ou=engineering,o=exampleorg,c=us"));  
netTcpEndpoint.Behaviors.Add(netTctEndpointBehavior);  
serviceHost.Open();  
```  
  
## <a name="calculatorclient"></a>CalculatorClient  
 이 프로젝트에는 CalculatorService에 메시지를 보내는 클라이언트 구현이 포함되어 있습니다. 이 프로그램에서는 `CreateCustomBindingWithDiscoveryElement()` 메서드를 사용하여 검색 클라이언트 채널을 사용하는 사용자 지정 바인딩을 만듭니다.  
  
```  
static CustomBinding CreateCustomBindingWithDiscoveryElement()  
 {  
      DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
            // Provide the search criteria and the endpoint over which the probe is sent  
            discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
            discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
            CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
            // Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
            // An exception is thrown if this binding element is not at the top  
            customBinding.Elements.Insert(0, discoveryBindingElement);  
  
            return customBinding; }  
```  
  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>가 인스턴스화된 후 개발자는 서비스를 검색할 때 사용할 조건을 지정합니다. 이 경우 검색 찾기 조건은 `ICalculatorService` 형식입니다. 또한 개발자는 서비스를 찾을 위치를 지정하는 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>를 반환하는 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>를 지정합니다. <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>는 새 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> 인스턴스를 반환합니다. 자세한 내용은 참조 [사용자 지정 바인딩을 사용 하 여 검색 클라이언트 채널](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md)합니다.  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
    // to the DiscoveryClientBindingElement. The Discovery ClientChannel   
    // uses this endpoint to send Probe message.  
    public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
    {  
        public override DiscoveryEndpoint GetDiscoveryEndpoint()  
        {  
            return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
        }  
    }  
```  
  
 이 경우 클라이언트에서는 검색 프로토콜에 의해 정의된 UDP 멀티캐스트 메커니즘을 사용하여 로컬 서브넷의 서비스를 검색합니다. 메서드의 나머지 부분에서는 사용자 지정 바인딩을 만들고 스택의 맨 위에 검색 바인딩 요소를 삽입합니다.  
  
> [!NOTE]
>  <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>는 바인딩 스택의 맨 위에 있어야 합니다. 실제 주소는 검색 클라이언트 채널에만 있으므로 <xref:System.ServiceModel.Channels.BindingElement>의 맨 위에 있는 모든 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>는 만드는 채널 팩터리나 채널에서 `EndpointAddress` 또는 `Via` 속성을 사용하지 않는지 확인해야 합니다.  
  
 그런 다음 이 사용자 지정 바인딩과 끝점 주소를 전달하여 `CalculatorClient`를 인스턴스화할 수 있습니다.  
  
```  
CalculatorServiceClient client = new CalculatorServiceClient(CreateCustomBindingWithDiscoveryElement(), DiscoveryClientBindingElement.DiscoveryEndpointAddress);  
```  
  
 Discovery 클라이언트 채널을 사용하는 경우 이전에 지정한 상수 끝점 주소가 전달됩니다. 이제 런타임 시 Discovery 클라이언트 채널이 검색 조건으로 지정한 서비스를 찾아서 연결해 줍니다. 서비스 및 클라이언트에서 연결을 설정하려면 동일한 기본 바인딩 스택도 있어야 합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 솔루션을 엽니다.  
  
2.  솔루션을 빌드합니다.  
  
3.  서비스 응용 프로그램과 각 클라이언트 응용 프로그램을 실행합니다.  
  
4.  클라이언트에서 주소를 모르고도 서비스를 찾을 수 있는지 확인합니다.  
  
## <a name="see-also"></a>참고 항목
