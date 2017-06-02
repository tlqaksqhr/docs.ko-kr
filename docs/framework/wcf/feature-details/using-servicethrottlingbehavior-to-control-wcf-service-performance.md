---
title: "ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "동작 [WCF] 서비스 성능"
ms.assetid: f9dc120c-dc24-49d5-930e-b22f5bc73423
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ServiceThrottlingBehavior를 사용하여 WCF 서비스 성능 제어
<xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 클래스 인스턴스 수를 제한 하는 데 사용할 수 또는 세션 응용 프로그램 수준에서 생성 되는 속성을 노출 합니다. 이 동작을 사용하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램의 성능을 세밀하게 조정할 수 있습니다.  
  
## <a name="controlling-service-instances-and-concurrent-calls"></a>서비스 인스턴스 및 동시 호출 제어  
 사용 하 여는 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A> 속성을 통해 처리 중인 메시지의 최대 수를 지정는 <xref:System.ServiceModel.ServiceHost> 클래스 및 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> 속성의 최대 수를 지정 하려면 <xref:System.ServiceModel.InstanceContext> 서비스에서 개체입니다.  
  
 에 대 한 응용 프로그램을 실행 하는 실제 경험 이후에 발생 하는 일반적으로 이러한 속성에 대 한 설정을 결정 하기 때문에 로드에 대 한 설정을 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 속성은 일반적으로 사용 하면 응용 프로그램 구성 파일에 지정 됩니다는 [ <> \> ](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md) 요소입니다.  
  
 다음 코드 예제에서는 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior> 설정 하는 응용 프로그램 구성 파일에서 클래스는 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentSessions%2A>, <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, 및 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A> 속성을 1로는 간단한 예입니다. 실제 경험을 통해 특정 응용 프로그램에 대한 최적의 설정을 결정합니다.  
  
 <!-- TODO: review snippet reference [!code-csharp[ServiceThrottlingBehavior#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/servicethrottlingbehavior/cs/hostapplication.exe.config#3)]  -->  
  
 정확한 런타임 동작은 값에 따라 달라 집니다는 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> 및 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 메시지 수는 작업 실행 한 번에 서비스의 수명을 제어 하는 속성 <xref:System.ServiceModel.InstanceContext> 수신 채널 기준으로 세션을 각각.  
  
 자세한 내용은 다음을 참조 하십시오. <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentCalls%2A>, 및 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior.MaxConcurrentInstances%2A>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>   
 <xref:System.ServiceModel.NetTcpBinding.MaxConnections%2A>