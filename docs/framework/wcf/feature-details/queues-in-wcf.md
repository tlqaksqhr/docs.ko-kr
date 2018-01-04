---
title: "Windows Communication Foundation의 큐"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: queues [WCF]
ms.assetid: 43008409-1bb4-4bd4-85d7-862c8f10ae20
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c87e384b3186a1dd4b53ba6c21d92bf4d0e6a8c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="queues-in-windows-communication-foundation"></a><span data-ttu-id="a0c99-102">Windows Communication Foundation의 큐</span><span class="sxs-lookup"><span data-stu-id="a0c99-102">Queues in Windows Communication Foundation</span></span>
<span data-ttu-id="a0c99-103">이 단원의 항목에서는 큐에 대한 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-103">The topics in this section discuss [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] support for queues.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a0c99-104">는 Microsoft Message Queuing(이전에 MSMQ라고 함)을 전송으로 사용하여 큐에 대한 지원을 제공하고 다음 시나리오를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-104"> provides support for queuing by leveraging Microsoft Message Queuing (previously known as MSMQ) as a transport and enables the following scenarios:</span></span>  
  
-   <span data-ttu-id="a0c99-105">느슨하게 결합된 응용 프로그램.</span><span class="sxs-lookup"><span data-stu-id="a0c99-105">Loosely coupled applications.</span></span> <span data-ttu-id="a0c99-106">송신 응용 프로그램은 수신 응용 프로그램이 메시지를 처리할 수 있는지 여부를 확인할 필요 없이 큐에 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-106">Sending applications can send messages to queues without needing to know whether the receiving application is available to process the message.</span></span> <span data-ttu-id="a0c99-107">큐는 수신 응용 프로그램이 메시지를 처리할 수 있는 속도에 따라 변경되지 않는 일정한 속도로 송신 응용 프로그램이 메시지를 큐에 보낼 수 있는 독립적인 프로세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-107">The queue provides processing independence that allows a sending application to send messages to the queue at a rate that does not depend on how fast the receiving applications can process the messages.</span></span> <span data-ttu-id="a0c99-108">큐에 메시지를 보내는 작업이 메시지 처리 작업과 밀접하게 연결되지 않을 경우 전반적인 시스템 가용성이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-108">Overall system availability increases when sending messages to a queue is not tightly coupled to message processing.</span></span>  
  
-   <span data-ttu-id="a0c99-109">실패 격리.</span><span class="sxs-lookup"><span data-stu-id="a0c99-109">Failure isolation.</span></span> <span data-ttu-id="a0c99-110">메시지를 큐에 보내거나 받는 응용 프로그램이 서로 간에 영향을 주지 않고 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-110">Applications sending or receiving messages to a queue can fail without affecting each other.</span></span> <span data-ttu-id="a0c99-111">예를 들어 수신 응용 프로그램이 실패하더라도 송신 응용 프로그램은 계속해서 큐에 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-111">If, for example, the receiving application fails, the sending application can continue to send messages to the queue.</span></span> <span data-ttu-id="a0c99-112">수신 응용 프로그램이 다시 활성화되면 큐에서 메시지를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-112">When the receiver is up again, it can process the messages from the queue.</span></span> <span data-ttu-id="a0c99-113">실패 격리는 전체 시스템 안정성 및 가용성을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-113">Failure isolation increases the overall system reliability and availability.</span></span>  
  
-   <span data-ttu-id="a0c99-114">로드 조정.</span><span class="sxs-lookup"><span data-stu-id="a0c99-114">Load leveling.</span></span> <span data-ttu-id="a0c99-115">송신 응용 프로그램이 수신 응용 프로그램을 메시지로 가득 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-115">Sending applications can overwhelm receiving applications with messages.</span></span> <span data-ttu-id="a0c99-116">큐는 수신 응용 프로그램이 과부하가 걸리지 않도록 일치하지 않는 메시지 작성 및 사용률을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-116">Queues can manage mismatched message production and consumption rates so that a receiver is not overwhelmed.</span></span>  
  
-   <span data-ttu-id="a0c99-117">연결이 끊긴 작업.</span><span class="sxs-lookup"><span data-stu-id="a0c99-117">Disconnected operations.</span></span> <span data-ttu-id="a0c99-118">송신, 수신 및 처리 작업은 모바일 장치의 경우처럼 대기 시간이 긴 네트워크 또는 가용성이 제한된 네트워크에서 통신하는 경우 연결이 끊어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-118">Sending, receiving, and processing operations can become disconnected when communicating over high-latency networks or limited-availability networks, such as in the case of mobile devices.</span></span> <span data-ttu-id="a0c99-119">큐를 사용하면 끝점의 연결이 끊어지더라도 이러한 작업을 계속 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-119">Queues allow these operations to continue, even when the endpoints are disconnected.</span></span> <span data-ttu-id="a0c99-120">다시 연결이 되면 큐가 메시지를 수신 응용 프로그램으로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-120">When the connection is reestablished, the queue forwards messages to the receiving application.</span></span>  
  
 <span data-ttu-id="a0c99-121">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에서 큐 기능을 사용하기 위해 표준 바인딩 중 하나를 사용하거나 표준 바인딩 중 하나가 요구 사항을 충족하지 못하는 경우 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-121">To use the queues feature in a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, you can use one of the standard bindings, or you can create a custom binding if one of the standard bindings does not satisfy your requirements.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a0c99-122">하나를 선택 하는 방법 및 관련 된 표준 바인딩 참조 [하는 방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지를 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-122"> relevant standard bindings and how to choose one, see [How to: Exchange Messages with WCF Endpoints and Message Queuing Applications](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a0c99-123">사용자 지정 바인딩을 만들 참조 [사용자 지정 바인딩을](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-123"> creating custom bindings, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0c99-124">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a0c99-124">In This Section</span></span>  
 [<span data-ttu-id="a0c99-125">큐 개요</span><span class="sxs-lookup"><span data-stu-id="a0c99-125">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 <span data-ttu-id="a0c99-126">메시지 큐 개념의 개요.</span><span class="sxs-lookup"><span data-stu-id="a0c99-126">An overview of message queuing concepts.</span></span>  
  
 [<span data-ttu-id="a0c99-127">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="a0c99-127">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 <span data-ttu-id="a0c99-128">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 큐 지원의 개요.</span><span class="sxs-lookup"><span data-stu-id="a0c99-128">An overview of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] queue support.</span></span>  
  
 [<span data-ttu-id="a0c99-129">방법: 대기 중인 메시지와 WCF 끝점 교환</span><span class="sxs-lookup"><span data-stu-id="a0c99-129">How to: Exchange Queued Messages with WCF Endpoints</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)  
 <span data-ttu-id="a0c99-130"><xref:System.ServiceModel.NetMsmqBinding> 클래스를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 및 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 사이에서 통신하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-130">Explains how to use the <xref:System.ServiceModel.NetMsmqBinding> class to communicate between a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
 [<span data-ttu-id="a0c99-131">방법: WCF 끝점 및 메시지 큐 응용 프로그램과 메시지 교환</span><span class="sxs-lookup"><span data-stu-id="a0c99-131">How to: Exchange Messages with WCF Endpoints and Message Queuing Applications</span></span>](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 <span data-ttu-id="a0c99-132"><xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>을 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 메시지 큐 응용 프로그램 사이에서 통신하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-132">Explains how to use the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> to communicate between [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and Message Queuing applications.</span></span>  
  
 [<span data-ttu-id="a0c99-133">세션의 대기 중인 메시지 그룹화</span><span class="sxs-lookup"><span data-stu-id="a0c99-133">Grouping Queued Messages in a Session</span></span>](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)  
 <span data-ttu-id="a0c99-134">단일 수신 응용 프로그램으로 상호 관련된 메시지 처리를 용이하게 하기 위해 큐의 메시지를 그룹화하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-134">Explains how to group messages in a queue to facilitate correlated message processing by a single receiving application.</span></span>  
  
 [<span data-ttu-id="a0c99-135">트랜잭션에서 메시지 일괄 처리</span><span class="sxs-lookup"><span data-stu-id="a0c99-135">Batching Messages in a Transaction</span></span>](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
 <span data-ttu-id="a0c99-136">메시지를 트랜잭션으로 일괄 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-136">Explains how to batch messages in a transaction.</span></span>  
  
 [<span data-ttu-id="a0c99-137">배달 못 한 편지 큐를 사용하여 메시지 전송 오류 처리</span><span class="sxs-lookup"><span data-stu-id="a0c99-137">Using Dead-Letter Queues to Handle Message Transfer Failures</span></span>](../../../../docs/framework/wcf/feature-details/using-dead-letter-queues-to-handle-message-transfer-failures.md)  
 <span data-ttu-id="a0c99-138">배달 못 한 편지 큐를 사용하여 메시지 전송 및 배달 실패를 처리하고 배달 못 한 편지 큐에서 메시지를 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-138">Explains how to handle message transfer and delivery failures using dead letter queues and how to process messages from the dead letter queue.</span></span>  
  
 [<span data-ttu-id="a0c99-139">포이즌 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="a0c99-139">Poison Message Handling</span></span>](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)  
 <span data-ttu-id="a0c99-140">포이즌 메시지(수신 응용 프로그램에 전달하는 최대 배달 시도 횟수를 초과한 메시지)를 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-140">Explains how to handle poison messages (messages that have exceeded the maximum number of delivery attempts to the receiving application).</span></span>  
  
 [<span data-ttu-id="a0c99-141">Windows Vista, Windows Server 2003 및 Windows XP의 큐 기능 차이점</span><span class="sxs-lookup"><span data-stu-id="a0c99-141">Differences in Queuing Features in Windows Vista, Windows Server 2003, and Windows XP</span></span>](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)  
 <span data-ttu-id="a0c99-142">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], [!INCLUDE[wv](../../../../includes/wv-md.md)] 및 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 간 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 큐 기능의 차이점에 대해 요약합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-142">Summarizes the differences in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] queues feature between [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], and [!INCLUDE[wxp](../../../../includes/wxp-md.md)].</span></span>  
  
 [<span data-ttu-id="a0c99-143">전송 보안을 사용하여 메시지에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a0c99-143">Securing Messages Using Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)  
 <span data-ttu-id="a0c99-144">전송 보안을 사용하여 대기 중인 메시지의 보안을 유지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-144">Describes how to use transport security to secure queued messages.</span></span>  
  
 [<span data-ttu-id="a0c99-145">메시지 보안을 사용하여 메시지에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="a0c99-145">Securing Messages Using Message Security</span></span>](../../../../docs/framework/wcf/feature-details/securing-messages-using-message-security.md)  
 <span data-ttu-id="a0c99-146">메시지 보안을 사용하여 대기 중인 메시지의 보안을 유지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-146">Describes how to use message security to secure queued messages.</span></span>  
  
 [<span data-ttu-id="a0c99-147">대기 중인 메시지 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a0c99-147">Troubleshooting Queued Messaging</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-queued-messaging.md)  
 <span data-ttu-id="a0c99-148">일반적인 큐 문제를 해결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-148">Explains how to troubleshoot common queuing problems.</span></span>  
  
 [<span data-ttu-id="a0c99-149">대기 중인 통신을 위한 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="a0c99-149">Best Practices for Queued Communication</span></span>](../../../../docs/framework/wcf/feature-details/best-practices-for-queued-communication.md)  
 <span data-ttu-id="a0c99-150">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 대기 중인 통신 사용에 대한 최선의 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0c99-150">Explains best practices for using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] queued communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c99-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0c99-151">See Also</span></span>  
 [<span data-ttu-id="a0c99-152">메시지 큐</span><span class="sxs-lookup"><span data-stu-id="a0c99-152">Message Queuing</span></span>](http://msdn.microsoft.com/en-us/ff917e87-05d5-478f-9430-0f560675ece1)
