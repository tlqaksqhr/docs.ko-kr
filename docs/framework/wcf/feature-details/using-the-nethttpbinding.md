---
title: "NetHttpBinding 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 56528078895ea7c624afaf716e9a26eabe335d69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-nethttpbinding"></a>NetHttpBinding 사용
<xref:System.ServiceModel.NetHttpBinding>은 HTTP 또는 WebSocket 서비스를 사용하도록 디자인된 바인딩이며 기본적으로 이진 인코딩을 사용합니다. <xref:System.ServiceModel.NetHttpBinding>은 해당 바인딩이 HTTP 요청-회신 계약에 사용되는지 이중 계약에 사용되는지를 검색하고 그에 맞게 동작을 변경합니다. 요청-회신 계약에는 HTTP가 사용되고 이중 계약에는 WebSocket이 사용됩니다. 사용 하 여이 동작을 재정의할 수 있습니다는 <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A> --> `WebSocketTransportUsage` 설정:  
  
1.  Always - 이 설정은 요청-회신 계약의 경우에도 WebSocket이 사용되도록 합니다.  
  
2.  Never - 이 설정은 WebSocket이 사용되지 않도록 합니다. 이 설정 상태에서 이중 계약을 사용하려고 시도하면 예외가 발생합니다.  
  
3.  WhenDuplex - 이 설정은 기본값이며 위에 설명된 대로 동작합니다.  
  
 <xref:System.ServiceModel.NetHttpBinding>은 HTTP 모드 및 WebSocket 모드에서 신뢰할 수 있는 세션을 지원합니다. WebSocket 모드에서는 세션이 전송에 의해 제공됩니다.  
  
> [!WARNING]
>  <xref:System.ServiceModel.NetHttpBinding>이 사용되고 바인딩의 TransferMode가 TransferMode.Streamed로 설정된 경우 큰 스트림으로 인해 교착 상태가 발생하고 호출이 시간 초과될 수 있습니다. 이 문제를 해결하려면 보다 작은 메시지를 보내거나 TransferMode.Buffered를 사용하세요.  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a>NetHttpBinding을 사용하도록 서비스 구성  
 다른 바인딩과 동일하게 <xref:System.ServiceModel.NetHttpBinding>을 구성할 수 있습니다. 다음 구성 조각에서는 <xref:System.ServiceModel.NetHttpBinding>을 사용하여 WCF 서비스를 구성하는 방법을 보여 줍니다.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    <!- ... -->   
  </system.serviceModel>  
```  
  
 다음 코드 조각에서는 코드로 <xref:System.ServiceModel.NetHttpBinding>을 추가하는 방법을 보여 줍니다.  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);   
        }  
```  
  
## <a name="see-also"></a>참고 항목  
 [서비스에 대한 바인딩 구성](../../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 [바인딩](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [이중 서비스](../../../../docs/framework/wcf/feature-details/duplex-services.md)
