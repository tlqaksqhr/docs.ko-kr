---
title: "세션의 대기 중인 메시지 그룹화"
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
helpviewer_keywords: queues [WCF]. grouping messages
ms.assetid: 63b23b36-261f-4c37-99a2-cc323cd72a1a
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b5817ded29836bcc6c998aaf293a7b2fd99170c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="grouping-queued-messages-in-a-session"></a><span data-ttu-id="a71b5-102">세션의 대기 중인 메시지 그룹화</span><span class="sxs-lookup"><span data-stu-id="a71b5-102">Grouping Queued Messages in a Session</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="a71b5-103">에서는 단일 수신 응용 프로그램에서 처리하도록 관련 메시지 집합을 그룹화할 수 있는 세션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-103"> provides a session that allows you to group a set of related messages together for processing by a single receiving application.</span></span> <span data-ttu-id="a71b5-104">세션의 일부인 메시지는 동일한 트랜잭션의 일부여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-104">Messages that are part of a session must be part of the same transaction.</span></span> <span data-ttu-id="a71b5-105">모든 메시지가 동일한 트랜잭션의 일부이므로, 하나의 메시지가 처리되지 않으면 전체 세션이 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-105">Because all messages are part of the same transaction, if one message fails to be processed the entire session is rolled back.</span></span> <span data-ttu-id="a71b5-106">세션은 배달 못 한 편지 큐 및 포이즌 큐와 관련하여 유사하게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-106">Sessions have similar behaviors with regard to dead-letter queues and poison queues.</span></span> <span data-ttu-id="a71b5-107">세션에 대해 구성된 대기 중인 바인딩에 대해 설정된 TTL(Time to Live) 속성은 세션에 전체적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-107">The Time to Live (TTL) property set on a queued binding configured for sessions is applied to the session as a whole.</span></span> <span data-ttu-id="a71b5-108">TTL이 만료되기 전에 세션에 있는 메시지 중 일부만 전송된 경우 전체 세션이 배달 못 한 편지 큐에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-108">If only some of the messages in the session are sent before the TTL expires, the entire session is placed in the dead-letter queue.</span></span> <span data-ttu-id="a71b5-109">마찬가지로 세션에 있는 메시지가 응용 프로그램 큐에서 응용 프로그램으로 전송되지 못하면 전체 세션이 포이즌 큐(사용 가능한 경우)에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-109">Similarly, when messages in a session fail to be sent to an application from the application queue, the entire session is placed in the poison queue (if available).</span></span>  
  
## <a name="message-grouping-example"></a><span data-ttu-id="a71b5-110">메시지 그룹화 예제</span><span class="sxs-lookup"><span data-stu-id="a71b5-110">Message Grouping Example</span></span>  
 <span data-ttu-id="a71b5-111">메시지 그룹화가 유용한 한 가지 예는 주문 처리 응용 프로그램을 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스로 구현하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-111">One example where grouping messages is helpful is when implementing an order-processing application as a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="a71b5-112">예를 들어 클라이언트가 많은 항목을 포함하는 주문을 이 응용 프로그램에 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-112">For instance, a client submits an order to this application that contains a number of items.</span></span> <span data-ttu-id="a71b5-113">각 항목에 대해 클라이언트가 서비스를 호출하고, 그 결과 메시지가 개별적으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-113">For each item, the client makes a call to the service, which results in a separate message being sent.</span></span> <span data-ttu-id="a71b5-114">서버 A가 첫 번째 항목을 수신하고 서버 B가 두 번째 항목을 수신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-114">It is possible for serve A to receive the first item, and server B to receive the second item.</span></span> <span data-ttu-id="a71b5-115">항목이 추가될 때마다 해당 항목을 처리하는 서버는 해당 주문을 찾아서 항목을 추가해야 하므로 매우 비효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-115">Each time an item is added, the server processing that item has to find the appropriate order and add the item to it, which is highly inefficient.</span></span> <span data-ttu-id="a71b5-116">서버에서 현재 처리 중인 모든 주문을 추적하여 새 항목이 속하는 주문을 확인해야 하기 때문에 단일 서버에서 모든 요청을 처리하는 이런 비효율성이 여전히 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-116">You still run into such inefficiencies with only a single server handling all requests, because the server must keep track of all orders currently being processed and determine which one the new item belongs to.</span></span> <span data-ttu-id="a71b5-117">단일 주문에 대한 모든 요청을 그룹화하면 이러한 응용 프로그램의 구현이 크게 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-117">Grouping all requests for a single order greatly simplifies implementation of such an application.</span></span> <span data-ttu-id="a71b5-118">클라이언트 응용 프로그램이 세션에 있는 단일 주문에 대한 모든 항목을 보내기 때문에 서비스에서 주문을 처리할 때 전체 세션을 한 번에 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-118">The client application sends all items for a single order in a session, so when the service processes the order, it processes the entire session at once.</span></span> \  
  
## <a name="procedures"></a><span data-ttu-id="a71b5-119">절차</span><span class="sxs-lookup"><span data-stu-id="a71b5-119">Procedures</span></span>  
  
#### <a name="to-set-up-a-service-contract-to-use-sessions"></a><span data-ttu-id="a71b5-120">세션을 사용하도록 서비스 계약을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a71b5-120">To set up a service contract to use sessions</span></span>  
  
1.  <span data-ttu-id="a71b5-121">세션이 필요한 서비스 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-121">Define a service contract that requires a session.</span></span> <span data-ttu-id="a71b5-122">이 작업은 <xref:System.ServiceModel.OperationContractAttribute> 특성을 사용하고 다음을 지정하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-122">Do this with the <xref:System.ServiceModel.OperationContractAttribute> attribute and by specifying:</span></span>  
  
    ```  
    SessionMode=SessionMode.Required  
    ```  
  
2.  <span data-ttu-id="a71b5-123">이러한 메서드는 아무것도 반환하지 않기 때문에 계약의 작업을 단방향으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-123">Mark the operations in the contract as one-way, because these methods do not return anything.</span></span> <span data-ttu-id="a71b5-124">이 작업은 <xref:System.ServiceModel.OperationContractAttribute> 특성을 사용하고 다음을 지정하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-124">This is done with the <xref:System.ServiceModel.OperationContractAttribute> attribute and by specifying:</span></span>  
  
    ```  
    [OperationContract(IsOneWay = true)]  
    ```  
  
3.  <span data-ttu-id="a71b5-125">서비스 계약을 구현하고 `InstanceContextMode`의 `PerSession`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-125">Implement the service contract and specify an `InstanceContextMode` of `PerSession`.</span></span> <span data-ttu-id="a71b5-126">그러면 각 세션에 대해 서비스가 한 번씩만 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-126">This instantiates the service only once for each session.</span></span>  
  
    ```  
    [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
    ```  
  
4.  <span data-ttu-id="a71b5-127">서비스 작업마다 하나의 트랜잭션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-127">Each service operation requires a transaction.</span></span> <span data-ttu-id="a71b5-128"><xref:System.ServiceModel.OperationBehaviorAttribute> 특성을 사용하여 이를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-128">Specify this with the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="a71b5-129">트랜잭션을 완료하는 작업에서는 `TransactionAutoComplete`를 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-129">The operation that completes the transaction should also set `TransactionAutoComplete` to `true`.</span></span>  
  
    ```  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]   
    ```  
  
5.  <span data-ttu-id="a71b5-130">시스템 제공 `NetMsmqBinding` 바인딩을 사용하는 끝점을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-130">Configure an endpoint that uses the system-provided `NetMsmqBinding` binding.</span></span>  
  
6.  <span data-ttu-id="a71b5-131"><xref:System.Messaging>을 사용하여 트랜잭션 큐를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-131">Create a transactional queue using <xref:System.Messaging>.</span></span> <span data-ttu-id="a71b5-132">메시지 큐(MSMQ) 또는 MMC를 사용하여 큐를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-132">You can also create the queue by using Message Queuing (MSMQ) or MMC.</span></span> <span data-ttu-id="a71b5-133">그러면 트랜잭션 큐가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-133">If you do, create a transactional queue.</span></span>  
  
7.  <span data-ttu-id="a71b5-134"><xref:System.ServiceModel.ServiceHost>를 사용하여 서비스에 대한 서비스 호스트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-134">Create a service host for the service by using <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
8.  <span data-ttu-id="a71b5-135">서비스를 사용할 수 있도록 서비스 호스트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-135">Open the service host to make the service available.</span></span>  
  
9. <span data-ttu-id="a71b5-136">서비스 호스트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-136">Close the service host.</span></span>  
  
#### <a name="to-set-up-a-client"></a><span data-ttu-id="a71b5-137">클라이언트를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="a71b5-137">To set up a client</span></span>  
  
1.  <span data-ttu-id="a71b5-138">트랜잭션 큐에 쓸 트랜잭션 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-138">Create a transaction scope to write to the transactional queue.</span></span>  
  
2.  <span data-ttu-id="a71b5-139">만들기는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 사용 하 여 클라이언트는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-139">Create the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool.</span></span>  
  
3.  <span data-ttu-id="a71b5-140">주문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-140">Place the order.</span></span>  
  
4.  <span data-ttu-id="a71b5-141">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-141">Close the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a71b5-142">예제</span><span class="sxs-lookup"><span data-stu-id="a71b5-142">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a71b5-143">설명</span><span class="sxs-lookup"><span data-stu-id="a71b5-143">Description</span></span>  
 <span data-ttu-id="a71b5-144">다음 예제에서는 `IProcessOrder` 서비스와 이 서비스를 사용하는 클라이언트에 대한 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-144">The following example provides the code for the `IProcessOrder` service and for a client that uses this service.</span></span> <span data-ttu-id="a71b5-145">또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 대기 중인 세션을 사용하여 그룹화 동작을 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a71b5-145">It shows how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses queued sessions to provide the grouping behavior.</span></span>  
  
### <a name="code-for-the-service"></a><span data-ttu-id="a71b5-146">서비스 코드</span><span class="sxs-lookup"><span data-stu-id="a71b5-146">Code for the Service</span></span>  
 [!code-csharp[S_Msmq_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/service.cs#1)]
 [!code-vb[S_Msmq_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/service.vb#1)]  
  
  
  
### <a name="code-for-the-client"></a><span data-ttu-id="a71b5-147">클라이언트 코드</span><span class="sxs-lookup"><span data-stu-id="a71b5-147">Code for the Client</span></span>  
 [!code-csharp[S_Msmq_Session#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_msmq_session/cs/client.cs#3)]
 [!code-vb[S_Msmq_Session#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_msmq_session/vb/client.vb#3)]  
  
  
  
## <a name="see-also"></a><span data-ttu-id="a71b5-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a71b5-148">See Also</span></span>  
 [<span data-ttu-id="a71b5-149">세션 및 큐</span><span class="sxs-lookup"><span data-stu-id="a71b5-149">Sessions and Queues</span></span>](../../../../docs/framework/wcf/samples/sessions-and-queues.md)  
 [<span data-ttu-id="a71b5-150">큐 개요</span><span class="sxs-lookup"><span data-stu-id="a71b5-150">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)
