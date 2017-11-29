---
title: "방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지 교환"
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
ms.assetid: 62210fd8-a372-4d55-ab9b-c99827d1885e
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d09b8e662b2876fa5d5c5246ea7e7a4998cde9ea
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a>방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지 교환
MSMQ 통합 바인딩을 통해 기존 메시지 큐(MSMQ) 응용 프로그램을 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램과 통합하여 MSMQ 메시지와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지를 서로 변환할 수 있습니다. 그러면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 MSMQ 수신자 응용 프로그램을 호출할 수 있을 뿐 아니라 MSMQ 발신자 응용 프로그램에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호출할 수 있습니다.  
  
 이 단원에서는 (1) System.Messaging을 사용하여 작성된 MSMQ 응용 프로그램 서비스와 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 클라이언트 간 및 (2) MSMQ 응용 프로그램 클라이언트와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 간에 대기 중인 통신에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]을 사용하는 방법에 대해 설명합니다.  
  
 MSMQ 수신자 응용 프로그램을 호출 하는 방법을 보여 주는 전체 샘플는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 참조는 [메시지 큐에 Windows Communication Foundation](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) 샘플.  
  
 호출 하는 방법을 보여 주는 전체 샘플에 대 한는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] MSMQ 클라이언트로부터 서비스, 참조는 [Windows Communication Foundation에 메시지 큐](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) 샘플.  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a>MSMQ 클라이언트로부터 메시지를 수신하는 WCF 서비스를 만들려면  
  
1.  다음 예제 코드에 표시된 것처럼 MSMQ 발신자 응용 프로그램으로부터 대기 중인 메시지를 수신하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 서비스 계약을 정의하는 인터페이스를 정의합니다.  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  다음 예제 코드에 표시된 것처럼 인터페이스를 구현하고 <xref:System.ServiceModel.ServiceBehaviorAttribute> 특성을 클래스에 적용합니다.  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>을 지정하는 구성 파일을 만듭니다.  
  
  
  
4.  구성된 바인딩을 사용하는 <xref:System.ServiceModel.ServiceHost> 개체를 인스턴스화합니다.  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a>MSMQ 수신자 응용 프로그램에 메시지를 보내는 WCF 클라이언트를 만들려면  
  
1.  다음 예제 코드에 표시된 것처럼 대기 중인 메시지를 MSMQ 수신기에 보내는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에 대한 서비스 계약을 정의하는 인터페이스를 정의합니다.  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 MSMQ 수신자를 호출하는 데 사용할 클라이언트 클래스를 정의합니다.  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  MsmqIntegrationBinding 바인딩을 사용하도록 지정하는 구성을 만듭니다.  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  클라이언트 클래스의 인스턴스를 만들고 메시지 수신 서비스에 의해 정의된 메서드를 호출합니다.  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a>참고 항목  
 [큐 개요](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [방법: 대기 중인 WCF 끝점으로 메시지를 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [메시지 큐에 Windows Communication Foundation](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [메시지 큐 (MSMQ) 설치](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [Windows Communication Foundation로 메시지 큐](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [메시지 큐에 대 한 메시지 보안](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
