---
title: "방법: 포트 공유를 사용하도록 Windows Communication Foundation 서비스 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 6400bc71-a858-4ac2-8d5a-caa72d3b5482
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0086e145ca2aab325764467742a4ff2e6e3c0b5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-configure-a-windows-communication-foundation-service-to-use-port-sharing"></a>방법: 포트 공유를 사용하도록 Windows Communication Foundation 서비스 구성
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램에서 net.tcp:// 포트 공유를 사용하는 가장 쉬운 방법은 <xref:System.ServiceModel.NetTcpBinding>을 사용하여 서비스를 노출하는 것입니다.  
  
 이 바인딩에서는 이 바인딩을 사용하여 구성하는 서비스에 대해 net.tcp:// 포트 공유를 사용할지 여부를 제어하는 <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> 속성을 제공합니다.  
  
 다음 절차에서는 <xref:System.ServiceModel.NetTcpBinding> 클래스를 사용하여 URI(Uniform Resource Identifier) net.tcp://localhost/MyService에서 끝점을 여는 방법을 보여 줍니다. 코드와 구성 요소를 사용한 방법을 차례로 보여 줍니다.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-code"></a>코드로 NetTcpBinding에서 net.tcp:// 포트 공유를 사용하도록 설정하려면  
  
1.  라는 계약을 구현 하는 서비스 만들기 `IMyService` 버전을 호출 `MyService`합니다.  
  
     [!code-csharp[c_ConfigurePortSharing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#1)]
     [!code-vb[c_ConfigurePortSharing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#1)]  
  
2.  <xref:System.ServiceModel.NetTcpBinding> 클래스의 인스턴스를 만들고 <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> 속성을 `true`로 설정합니다.  
  
     [!code-csharp[c_ConfigurePortSharing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#2)]
     [!code-vb[c_ConfigurePortSharing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#2)]  
  
3.  <xref:System.ServiceModel.ServiceHost>를 만든 다음 포트 공유 사용 `MyService`을 사용하고 끝점 주소 URI "net.tcp://localhost/MyService"에서 수신 대기하는 <xref:System.ServiceModel.NetTcpBinding>에 대해 서비스 끝점을 추가합니다.  
  
     [!code-csharp[c_ConfigurePortSharing#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#3)]
     [!code-vb[c_ConfigurePortSharing#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#3)]  
  
    > [!NOTE]
    >  끝점 주소 URI에서 다른 포트 번호를 지정하지 않기 때문에 이 예제에서는 기본 TCP 포트 808을 사용합니다. 전송 바인딩에서 포트 공유가 명시적으로 사용되기 때문에 이 서비스는 다른 프로세스의 다른 서비스와 포트 808을 공유할 수 있습니다. 포트 공유가 허용되지 않고 다른 응용 프로그램에서 포트 808을 이미 사용하고 있는 경우 포트를 열면 이 서비스에서 <xref:System.ServiceModel.AddressAlreadyInUseException>을 throw합니다.  
  
### <a name="to-enable-nettcp-port-sharing-on-a-nettcpbinding-in-configuration"></a>구성을 통해 NetTcpBinding에서 net.tcp:// 포트 공유를 사용하도록 설정하려면  
  
1.  다음 예제에서는 구성 요소를 사용하여 포트 공유를 사용하도록 설정하고 서비스 끝점을 추가하는 방법을 보여 줍니다.  
  
```xml  
<system.serviceModel>  
  <bindings>  
    <netTcpBinding name="portSharingBinding"   
                   portSharingEnabled="true" />  
  </bindings>  
  <services>  
    <service name="MyService">  
        <endpoint address="net.tcp://localhost/MyService"  
                  binding="netTcpBinding"  
                  contract="IMyService"  
                  bindingConfiguration="portSharingBinding" />  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>참고 항목  
 [Net.TCP 포트 공유](http://msdn.microsoft.com/library/f13692ee-a179-4439-ae72-50db9534eded)  
 [방법: Net.TCP Port Sharing Service 사용](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)
