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
# <a name="how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications"></a><span data-ttu-id="44e4b-102">방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="44e4b-102">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>
<span data-ttu-id="44e4b-103">MSMQ 통합 바인딩을 통해 기존 메시지 큐(MSMQ) 응용 프로그램을 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 응용 프로그램과 통합하여 MSMQ 메시지와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지를 서로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-103">You can integrate existing Message Queuing (MSMQ) applications with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] applications by using the MSMQ integration binding to convert MSMQ messages to and from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] messages.</span></span> <span data-ttu-id="44e4b-104">그러면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 MSMQ 수신자 응용 프로그램을 호출할 수 있을 뿐 아니라 MSMQ 발신자 응용 프로그램에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-104">This allows you to call into MSMQ receiver applications from [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients as well as call into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services from MSMQ sender applications.</span></span>  
  
 <span data-ttu-id="44e4b-105">이 단원에서는 (1) System.Messaging을 사용하여 작성된 MSMQ 응용 프로그램 서비스와 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 클라이언트 간 및 (2) MSMQ 응용 프로그램 클라이언트와 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 간에 대기 중인 통신에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-105">In this section, we explain how to use <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> for queued communication between (1) a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and an MSMQ application service written using System.Messaging and (2) an MSMQ application client and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 <span data-ttu-id="44e4b-106">MSMQ 수신자 응용 프로그램을 호출 하는 방법을 보여 주는 전체 샘플는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 참조는 [메시지 큐에 Windows Communication Foundation](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="44e4b-106">For a complete sample that demonstrates how to call a MSMQ receiver application from a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, see the [Windows Communication Foundation to Message Queuing](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) sample.</span></span>  
  
 <span data-ttu-id="44e4b-107">호출 하는 방법을 보여 주는 전체 샘플에 대 한는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] MSMQ 클라이언트로부터 서비스, 참조는 [Windows Communication Foundation에 메시지 큐](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="44e4b-107">For a complete sample that demonstrates how to call a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from a MSMQ client, see the [Message Queuing to Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) sample.</span></span>  
  
### <a name="to-create-a-wcf-service-that-receives-messages-from-a-msmq-client"></a><span data-ttu-id="44e4b-108">MSMQ 클라이언트로부터 메시지를 수신하는 WCF 서비스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="44e4b-108">To create a WCF service that receives messages from a MSMQ client</span></span>  
  
1.  <span data-ttu-id="44e4b-109">다음 예제 코드에 표시된 것처럼 MSMQ 발신자 응용 프로그램으로부터 대기 중인 메시지를 수신하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 대한 서비스 계약을 정의하는 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-109">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service that receives queued messages from a MSMQ sender application, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#1)]
     [!code-vb[S_MsmqToWcf#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#1)]  
  
2.  <span data-ttu-id="44e4b-110">다음 예제 코드에 표시된 것처럼 인터페이스를 구현하고 <xref:System.ServiceModel.ServiceBehaviorAttribute> 특성을 클래스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-110">Implement the interface and apply the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute to the class, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_MsmqToWcf#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmqtowcf/cs/service.cs#2)]
     [!code-vb[S_MsmqToWcf#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmqtowcf/vb/service.vb#2)]  
  
3.  <span data-ttu-id="44e4b-111"><xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>을 지정하는 구성 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-111">Create a configuration file that specifies the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>.</span></span>  
  
  
  
4.  <span data-ttu-id="44e4b-112">구성된 바인딩을 사용하는 <xref:System.ServiceModel.ServiceHost> 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-112">Instantiate a <xref:System.ServiceModel.ServiceHost> object that uses the configured binding.</span></span>  
  
  
  
### <a name="to-create-a-wcf-client-that-sends-messages-to-a-msmq-receiver-application"></a><span data-ttu-id="44e4b-113">MSMQ 수신자 응용 프로그램에 메시지를 보내는 WCF 클라이언트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="44e4b-113">To create a WCF client that sends messages to a MSMQ receiver application</span></span>  
  
1.  <span data-ttu-id="44e4b-114">다음 예제 코드에 표시된 것처럼 대기 중인 메시지를 MSMQ 수신기에 보내는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에 대한 서비스 계약을 정의하는 인터페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-114">Define an interface that defines the service contract for the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that sends queued messages to the MSMQ receiver, as shown in the following example code.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/proxy.cs#6)]
     [!code-vb[S_WcfToMsmq#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/proxy.vb#6)]  
  
2.  <span data-ttu-id="44e4b-115">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트에서 MSMQ 수신자를 호출하는 데 사용할 클라이언트 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-115">Define a client class that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client uses to call the MSMQ receiver.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#2)]
     [!code-vb[S_WcfToMsmq#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#2)]  
  
3.  <span data-ttu-id="44e4b-116">MsmqIntegrationBinding 바인딩을 사용하도록 지정하는 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-116">Create a configuration that specifies use of the MsmqIntegrationBinding binding.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/snippets.cs#3)]
     [!code-vb[S_WcfToMsmq#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_wcftomsmq/vb/snippets.vb#3)]  
  
4.  <span data-ttu-id="44e4b-117">클라이언트 클래스의 인스턴스를 만들고 메시지 수신 서비스에 의해 정의된 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="44e4b-117">Create an instance of the client class and call the method defined by the message receiving service.</span></span>  
  
     [!code-csharp[S_WcfToMsmq#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wcftomsmq/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="44e4b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44e4b-118">See Also</span></span>  
 [<span data-ttu-id="44e4b-119">큐 개요</span><span class="sxs-lookup"><span data-stu-id="44e4b-119">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="44e4b-120">방법: 대기 중인 WCF 끝점으로 메시지를 교환</span><span class="sxs-lookup"><span data-stu-id="44e4b-120">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 [<span data-ttu-id="44e4b-121">메시지 큐에 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="44e4b-121">Windows Communication Foundation to Message Queuing</span></span>](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md)  
 [<span data-ttu-id="44e4b-122">메시지 큐 (MSMQ) 설치</span><span class="sxs-lookup"><span data-stu-id="44e4b-122">Installing Message Queuing (MSMQ)</span></span>](../../../../docs/framework/wcf/samples/installing-message-queuing-msmq.md)  
 [<span data-ttu-id="44e4b-123">Windows Communication Foundation로 메시지 큐</span><span class="sxs-lookup"><span data-stu-id="44e4b-123">Message Queuing to Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md)  
 [<span data-ttu-id="44e4b-124">메시지 큐에 대 한 메시지 보안</span><span class="sxs-lookup"><span data-stu-id="44e4b-124">Message Security over Message Queuing</span></span>](../../../../docs/framework/wcf/samples/message-security-over-message-queuing.md)
