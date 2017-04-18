---
title: "방법: 대기 중인 메시지와 WCF 끝점 교환 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 938e7825-f63a-4c3d-b603-63772fabfdb3
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# 방법: 대기 중인 메시지와 WCF 끝점 교환
큐를 사용하면 통신하는 동안 서비스를 사용할 수 없는 경우에도 클라이언트와 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 간의 메시징을 신뢰할 수 있는지 확인할 수 있습니다. 다음 절차에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 구현할 때 대기 중인 표준 바인딩을 사용하여 클라이언트와 서비스 간의 통신을 지속하는 방법을 보여 줍니다.  
  
 이 섹션에서는 사용 하는 방법에 설명 <xref:System.ServiceModel.NetMsmqBinding> 간의 대기 중인된 통신에는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.  
  
### <a name="to-use-queuing-in-a-wcf-service"></a>WCF 서비스에서 큐를 사용하려면  
  
1.  으로 표시 한 인터페이스를 사용 하 여 서비스 계약 정의 <xref:System.ServiceModel.ServiceContractAttribute>합니다. 인터페이스의 작업을 사용 하 여 서비스 계약의 일부인 표시는 <xref:System.ServiceModel.OperationContractAttribute> 메서드에 대 한 응답이 반환 되기 때문에 단방향으로 지정 합니다. 다음 코드에서는 예제 서비스 계약 및 작업 정의를 제공합니다.  
  
     [!code-csharp[S_Msmq_Transacted#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#1)]
     [!code-vb[S_Msmq_Transacted#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#1)]  
  
2.  서비스 계약에서 사용자 정의 형식을 전달하는 경우 해당 형식의 데이터 계약을 정의해야 합니다. 다음 코드에서는 `PurchaseOrder` 및 `PurchaseOrderLineItem`의 두 데이터 계약을 보여 줍니다. 이 두 형식은 서비스로 전송되는 데이터를 정의합니다. 또한 이 데이터 계약을 정의하는 클래스에서 여러 메서드도 정의합니다. 이러한 메서드는 데이터 계약의 일부로 간주되지 않습니다. `DataMember` 특성을 사용하여 선언된 해당 멤버만이 데이터 계약의 일부가 됩니다.  
  
     [!code-csharp[S_Msmq_Transacted#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#2)]
     [!code-vb[S_Msmq_Transacted#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#2)]  
  
3.  클래스에서 인터페이스에 정의된 서비스 계약의 메서드를 구현합니다.  
  
     [!code-csharp[S_Msmq_Transacted#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#3)]
     [!code-vb[S_Msmq_Transacted#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#3)]  
  
     공지는 <xref:System.ServiceModel.OperationBehaviorAttribute> 에 배치 된 `SubmitPurchaseOrder` 메서드. 따라서 이 작업은 트랜잭션 내에서 호출해야 하며 메서드가 완료되면 트랜잭션도 자동으로 완료되도록 지정됩니다.  
  
4.  사용 하 여 트랜잭션 큐 만들기 <xref:System.Messaging>합니다. MSMQ(Microsoft Message Queuing) MMC(Microsoft Management Console)를 대신 사용하여 큐를 만들 수 있습니다. 이 경우에는 트랜잭션 큐를 만들어야 합니다.  
  
     [!code-csharp[S_Msmq_Transacted#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#4)]
     [!code-vb[S_Msmq_Transacted#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#4)]  
  
5.  정의 <xref:System.ServiceModel.Description.ServiceEndpoint> 서비스 주소를 지정 하는 표준 구성에서 <xref:System.ServiceModel.NetMsmqBinding> 바인딩. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]사용 하 여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 구성 참조 [Windows Communication Foundation 응용 프로그램 구성](http://msdn.microsoft.com/ko-kr/13cb368e-88d4-4c61-8eed-2af0361c6d7a)합니다.  
  
  
  
6.  에 대 한 호스트를 만드는 `OrderProcessing` 를 사용 하 여 서비스 <xref:System.ServiceModel.ServiceHost> 큐에서 메시지를 읽고 하 게 처리 합니다. 서비스를 사용할 수 있도록 서비스 호스트를 엽니다. 사용자에게 아무 키나 누르면 서비스를 종료할 수 있음을 알리는 메시지를 표시합니다. `ReadLine`을 호출하여 키를 누를 때까지 기다린 후에 서비스를 닫습니다.  
  
     [!code-csharp[S_Msmq_Transacted#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#6)]
     [!code-vb[S_Msmq_Transacted#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#6)]  
  
### <a name="to-create-a-client-for-the-queued-service"></a>대기 중인 서비스의 클라이언트를 만들려면  
  
1.  다음 예제에서는 호스팅 응용 프로그램을 실행하고 Svcutil.exe 도구를 사용해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 만드는 방법을 보여 줍니다.  
  
    ```  
    svcutil http://localhost:8000/ServiceModelSamples/service  
    ```  
  
2.  정의 <xref:System.ServiceModel.Description.ServiceEndpoint> 주소를 지정 하는 표준 구성에서 <xref:System.ServiceModel.NetMsmqBinding> 바인딩, 다음 예제와 같이 합니다.  
  
  
  
3.  다음예제와 같이 트랜잭션 큐에 쓸 트랜잭션 범위를 만들고 `SubmitPurchaseOrder` 작업을 호출한 다음 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 닫습니다.  
  
     [!code-csharp[S_Msmq_Transacted#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#8)]
     [!code-vb[S_Msmq_Transacted#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#8)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 이 예제에 포함된 서비스 코드, 호스팅 응용 프로그램, App.config 파일 및 클라이언트 코드를 보여 줍니다.  
  
 [!code-csharp[S_Msmq_Transacted#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/service.cs#9)]
 [!code-vb[S_Msmq_Transacted#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/service.vb#9)]  
  
 [!code-csharp[S_Msmq_Transacted#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/hostapp.cs#10)]
 [!code-vb[S_Msmq_Transacted#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/hostapp.vb#10)]  
  
  
  
 [!code-csharp[S_Msmq_Transacted#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_transacted/cs/client.cs#12)]
 [!code-vb[S_Msmq_Transacted#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_transacted/vb/client.vb#12)]  
  
  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.NetMsmqBinding>   
 [트랜잭션 된 MSMQ 바인딩](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md)   
 [WCF의 큐](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)   
 [방법: WCF 끝점을 사용 하 여 메시지를 교환 및 메시지 큐 응용](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)   
 [Windows Communication Foundation에서 메시지 큐로](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)   
 [메시지 큐 (MSMQ) 설치](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)   
 [메시지 큐 통합 바인딩 샘플](http://msdn.microsoft.com/ko-kr/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)   
 [Windows Communication Foundation로 메시지 큐](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)   
 [메시지 큐에 대 한 메시지 보안](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)