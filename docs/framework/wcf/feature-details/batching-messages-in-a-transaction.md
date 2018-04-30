---
title: 트랜잭션에서 메시지 일괄 처리
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching messages [WCF]
ms.assetid: 53305392-e82e-4e89-aedc-3efb6ebcd28c
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 17d9bd3b58e8320bfe1f62ac56aff59ba52f4374
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="batching-messages-in-a-transaction"></a><span data-ttu-id="f2b92-102">트랜잭션에서 메시지 일괄 처리</span><span class="sxs-lookup"><span data-stu-id="f2b92-102">Batching Messages in a Transaction</span></span>
<span data-ttu-id="f2b92-103">대기 중인 응용 프로그램은 트랜잭션을 사용하여 정확하고 안정적인 메시지 배달을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-103">Queued applications use transactions to ensure correctness and reliable delivery of messages.</span></span> <span data-ttu-id="f2b92-104">트랜잭션은 비용이 많이 드는 작업이나 메시지 처리량을 상당히 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-104">Transactions, however, are expensive operations and can dramatically reduce message throughput.</span></span> <span data-ttu-id="f2b92-105">메시지 처리량을 향상시키기 위한 한가지 방법은 응용 프로그램이 단일 트랜잭션 내에서 여러 메시지를 읽고 처리하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-105">One way to improve message throughput is to have an application read and process multiple messages within a single transaction.</span></span> <span data-ttu-id="f2b92-106">성능이 좋아질수록 복구 작업도 늘어납니다. 즉, 일괄 처리하는 메시지 수가 증가하면 트랜잭션이 롤백 되는 경우 필요한 복구 작업의 크기도 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-106">The trade-off is between performance and recovery: as the number of messages in a batch increases, so does the amount of recovery work that required if transactions are rolled back.</span></span> <span data-ttu-id="f2b92-107">트랜잭션 및 세션에서 일괄 처리하는 메시지 사이에는 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-107">It is important to note the difference between batching messages in a transaction and sessions.</span></span> <span data-ttu-id="f2b92-108">A *세션* 은 단일 응용 프로그램에 의해 처리 되 고 하나의 단위로 커밋되는 관련된 메시지의 그룹화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-108">A *session* is a grouping of related messages that are processed by a single application and committed as a single unit.</span></span> <span data-ttu-id="f2b92-109">세션은 일반적으로 관련 메시지 그룹을 함께 처리해야 하는 경우 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-109">Sessions are generally used when a group of related messages must be processed together.</span></span> <span data-ttu-id="f2b92-110">이러한 예로 온라인 쇼핑 웹 사이트를 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-110">An example of this is an online shopping Web site.</span></span> <span data-ttu-id="f2b92-111">*일괄 처리* 관련 없는 메시지를 메시지 처리량을 증가 하는 방법, 여러 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-111">*Batches* are used to process multiple, unrelated messages in a way that increases message throughput.</span></span> <span data-ttu-id="f2b92-112">세션에 대 한 자세한 내용은 참조 [세션의 대기 중인 메시지 그룹화](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-112">For more information about sessions, see [Grouping Queued Messages in a Session](../../../../docs/framework/wcf/feature-details/grouping-queued-messages-in-a-session.md).</span></span> <span data-ttu-id="f2b92-113">또한 일괄 처리하는 메시지는 하나의 응용 프로그램에 의해 처리되고 하나의 단위로 커밋되지만 일괄 처리하는 메시지 간에 관계가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-113">Messages in a batch are also processed by a single application and committed as a single unit, but there may be no relationship between the messages in the batch.</span></span> <span data-ttu-id="f2b92-114">한 트랜잭션의 메시지를 일괄 처리하는 것이 응용 프로그램이 실행되는 방법을 변경하지 않는 가장 적절한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-114">Batching messages in a transaction is an optimization that does not change how the application runs.</span></span>  
  
## <a name="entering-batching-mode"></a><span data-ttu-id="f2b92-115">일괄 처리 모드 시작</span><span class="sxs-lookup"><span data-stu-id="f2b92-115">Entering Batching Mode</span></span>  
 <span data-ttu-id="f2b92-116"><xref:System.ServiceModel.Description.TransactedBatchingBehavior> 끝점 동작은 일괄 처리를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-116">The <xref:System.ServiceModel.Description.TransactedBatchingBehavior> endpoint behavior controls batching.</span></span> <span data-ttu-id="f2b92-117">이 끝점 동작을 서비스 끝점에 추가하면 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]가 하나의 트랜잭션에서 메시지를 일괄 처리하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-117">Adding this endpoint behavior to a service endpoint tells [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to batch messages in a transaction.</span></span> <span data-ttu-id="f2b92-118">트랜잭션이 필요한 메시지만 일괄 처리에 배치 됩니다 일부 메시지에 트랜잭션이 필요 하 고로 표시 된 작업에서 보낸 메시지만 `TransactionScopeRequired`  =  `true` 및 `TransactionAutoComplete`  =  `true` 됩니다 일괄 처리에 대 한 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-118">Not all messages require a transaction, so only messages that require a transaction are placed in a batch, and only messages sent from operations marked with `TransactionScopeRequired` = `true` and `TransactionAutoComplete` = `true` are considered for a batch.</span></span> <span data-ttu-id="f2b92-119">경우에 서비스 계약에 대 한 모든 작업으로 표시 되어 `TransactionScopeRequired`  =  `false` 및 `TransactionAutoComplete`  =  `false`, 다음 일괄 처리 모드 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-119">If all operations on the service contract are marked with `TransactionScopeRequired` = `false` and `TransactionAutoComplete` = `false`, then batching mode is never entered.</span></span>  
  
## <a name="committing-a-transaction"></a><span data-ttu-id="f2b92-120">트랜잭션 커밋</span><span class="sxs-lookup"><span data-stu-id="f2b92-120">Committing a Transaction</span></span>  
 <span data-ttu-id="f2b92-121">일괄 처리된 트랜잭션은 다음을 기준으로 커밋됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-121">A batched transaction is committed based on the following:</span></span>  
  
-   <span data-ttu-id="f2b92-122">`MaxBatchSize`.</span><span class="sxs-lookup"><span data-stu-id="f2b92-122">`MaxBatchSize`.</span></span> <span data-ttu-id="f2b92-123"><xref:System.ServiceModel.Description.TransactedBatchingBehavior> 동작의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-123">A property of the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> behavior.</span></span> <span data-ttu-id="f2b92-124">이 속성은 일괄 처리로 배치되는 최대 메시지 수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-124">This property determines the maximum number of messages that are placed into a batch.</span></span> <span data-ttu-id="f2b92-125">이 값에 도달하면 일괄 처리가 커밋됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-125">When this number is reached, the batch is committed.</span></span> <span data-ttu-id="f2b92-126">값은 엄격하게 제한하지 않으며 이 값의 메시지를 받기 전에 일괄 처리를 커밋할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-126">This is value is not a strict limit, it is possible to commit a batch before receiving this number of messages.</span></span>  
  
-   <span data-ttu-id="f2b92-127">`Transaction Timeout`.</span><span class="sxs-lookup"><span data-stu-id="f2b92-127">`Transaction Timeout`.</span></span> <span data-ttu-id="f2b92-128">트랜잭션 시간 제한의 80%가 경과한 후, 일괄 처리가 커밋되고 새 일괄 처리가 만들어 집니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-128">After 80 percent of the transaction's time-out has elapsed, the batch is committed and a new batch is created.</span></span> <span data-ttu-id="f2b92-129">이는 완료할 트랜잭션의 지정된 시간이 20% 이하로 남은 경우, 일괄 처리가 커밋된다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-129">This means that if 20 percent or less of the time given for a transaction to complete remains, the batch is committed.</span></span>  
  
-   <span data-ttu-id="f2b92-130">`TransactionScopeRequired`.</span><span class="sxs-lookup"><span data-stu-id="f2b92-130">`TransactionScopeRequired`.</span></span> <span data-ttu-id="f2b92-131">일괄 처리 메시지를 처리할 때 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 발견 된 `TransactionScopeRequired`  =  `false`, 첫 번째 메시지 수신 시 새 일괄 처리를 다시 열를 일괄 처리를 커밋하고 `TransactionScopeRequired`  =  `true` 및 `TransactionAutoComplete` = `true`.</span><span class="sxs-lookup"><span data-stu-id="f2b92-131">When processing a batch of messages, if [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] finds one that has `TransactionScopeRequired` = `false`, it commits the batch and reopens a new batch on receipt of the first message with `TransactionScopeRequired` = `true` and `TransactionAutoComplete` = `true`.</span></span>  
  
-   <span data-ttu-id="f2b92-132">메시지가 더 이상 큐에 없는 경우 `MaxBatchSize`에 도달하지 않았거나 트랜잭션 시간 제한의 80%가 경과하지 않았더라도 현재 일괄 처리가 커밋됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-132">If no more messages exist in the queue, then the current batch is committed, even if the `MaxBatchSize` has not been reached or 80 percent of the transaction's time-out has not elapsed.</span></span>  
  
## <a name="leaving-batching-mode"></a><span data-ttu-id="f2b92-133">일괄 처리 모드 종료</span><span class="sxs-lookup"><span data-stu-id="f2b92-133">Leaving Batching Mode</span></span>  
 <span data-ttu-id="f2b92-134">일괄 처리 메시지로 인해 트랜잭션이 중단되는 경우 다음 단계가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-134">If a message in a batch causes the transaction to abort, the following steps occur:</span></span>  
  
1.  <span data-ttu-id="f2b92-135">전체 일괄 처리 메시지가 롤백됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-135">The entire batch of messages is rolled back.</span></span>  
  
2.  <span data-ttu-id="f2b92-136">읽는 메시지 수가 최대 일괄 처리 크기의 두 배를 초과할 때까지 메시지를 한 번에 하나씩 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-136">Messages are read one at a time until the number of messages read exceeds twice the maximum batch size.</span></span>  
  
3.  <span data-ttu-id="f2b92-137">일괄 처리 모드가 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-137">Batch mode is re-entered.</span></span>  
  
## <a name="choosing-the-batch-size"></a><span data-ttu-id="f2b92-138">일괄 처리 크기 선택</span><span class="sxs-lookup"><span data-stu-id="f2b92-138">Choosing the Batch Size</span></span>  
 <span data-ttu-id="f2b92-139">일괄 처리 크기는 응용 프로그램에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-139">The size of a batch is application-dependent.</span></span> <span data-ttu-id="f2b92-140">응용 프로그램의 최적 일괄 처리 크기를 결정하는 데 가장 적절한 방법은 직접 경험하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-140">The empirical method is the best way to arrive at an optimal batch size for the application.</span></span> <span data-ttu-id="f2b92-141">일괄 처리 크기 선택 시 응용 프로그램의 실제 배포 모델에 따라 크기를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-141">It is important to remember when choosing a batch size to choose the size according to your application's actual deployment model.</span></span> <span data-ttu-id="f2b92-142">예를 들어, 응용 프로그램을 배포할 때 원격 시스템에서 SQL Server가 필요하고 큐 및 SQL Server가 포함된 트랜잭션이 필요한 경우 이 구성을 실제로 실행하여 일괄 처리 크기를 결정하는 것이 가장 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-142">For example, when deploying the application, if you need an SQL server on a remote machine and a transaction that spans the queue and the SQL server, then the batch size is best determined by running this exact configuration.</span></span>  
  
## <a name="concurrency-and-batching"></a><span data-ttu-id="f2b92-143">동시성 및 일괄 처리</span><span class="sxs-lookup"><span data-stu-id="f2b92-143">Concurrency and Batching</span></span>  
 <span data-ttu-id="f2b92-144">처리량을 증가시키기 위해 여러 일괄 처리를 동시에 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-144">To increase throughput, you can also have many batches run concurrently.</span></span> <span data-ttu-id="f2b92-145">`ConcurrencyMode.Multiple`에서 `ServiceBehaviorAttribute`을 설정하여 동시 일괄 처리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-145">By setting `ConcurrencyMode.Multiple` in `ServiceBehaviorAttribute`, you enable concurrent batching.</span></span>  
  
 <span data-ttu-id="f2b92-146">*서비스 스로틀* 최대 동시 호출 수는 서비스에서 수행할 수를 나타내는 데 사용 되는 서비스 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-146">*Service throttling* is a service behavior that is used to indicate how many maximum concurrent calls can be made on the service.</span></span> <span data-ttu-id="f2b92-147">일괄 처리에서 사용하는 경우 이 동작은 동시에 실행할 수 있는 일괄 처리 수로 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-147">When used with batching, this is interpreted as how many concurrent batches can be run.</span></span> <span data-ttu-id="f2b92-148">서비스 스로틀을 설정하지 않을 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 기본적으로 최대 동시 호출을 16으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-148">If the service throttling is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] defaults the maximum concurrent calls to 16.</span></span> <span data-ttu-id="f2b92-149">따라서 기본적으로 일괄 처리 동작이 추가된 경우, 동시에 최대 16개의 일괄 처리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-149">Thus, if batching behavior were added by default, a maximum of 16 batches can be active at the same time.</span></span> <span data-ttu-id="f2b92-150">사용자 성능을 기준으로 서비스 스로틀 및 일괄 처리를 조정하는 것이 가장 바람직합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-150">It is best to tune the service throttling and batching based on your capacity.</span></span> <span data-ttu-id="f2b92-151">예를 들어, 큐에 100개의 메시지가 있고 20개를 일괄 처리하려는 경우 처리량에 따라 일괄 처리를 조정하지 않은 것처럼 16개의 트랜잭션을 수행할 수 있기 때문에, 최대 동시 호출을 16으로 설정하는 것이 유용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-151">For example, if the queue has 100 messages and a batch of 20 is desired, having the maximum concurrent calls set to 16 is not useful because, depending on throughput, 16 transactions could be active, similar to not having batching turned on.</span></span> <span data-ttu-id="f2b92-152">따라서 성능을 세부적으로 조정하는 경우 동시 일괄 처리를 설정하지 않거나 올바른 서비스 스로틀 크기로 동시 일괄 처리를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-152">Therefore, when fine-tuning for performance, either do not have concurrent batching or have concurrent batching with the correct service throttle size.</span></span>  
  
## <a name="batching-and-multiple-endpoints"></a><span data-ttu-id="f2b92-153">일괄 처리 및 여러 끝점</span><span class="sxs-lookup"><span data-stu-id="f2b92-153">Batching and Multiple Endpoints</span></span>  
 <span data-ttu-id="f2b92-154">끝점은 주소 및 계약으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-154">An endpoint is composed of an address and a contract.</span></span> <span data-ttu-id="f2b92-155">동일한 바인딩을 공유하는 여러 끝점이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-155">There may be multiple endpoints that share the same binding.</span></span> <span data-ttu-id="f2b92-156">두 개의 끝점이 동일한 바인딩을 공유하고 URI(Uniform Resource Identifier) 또는 큐 주소를 수신 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-156">It is possible for two endpoints to share the same binding and listen Uniform Resource Identifier (URI), or queue address.</span></span> <span data-ttu-id="f2b92-157">두 개의 끝점을 동일한 큐에서 읽는 경우, 트랜잭션된 일괄 처리 동작이 양쪽 끝점에 추가되고 지정된 일괄 처리 크기 간에 충돌될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-157">If two endpoints are reading from the same queue, and transacted batching behavior is added to both endpoints, a conflict in the batch sizes specified could arise.</span></span> <span data-ttu-id="f2b92-158">이러한 동작은 두 개의 트랜잭션된 일괄 처리 동작 간에 지정된 최소 일괄 처리 크기로 일괄 처리를 구현하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-158">This is resolved by implementing batching using the minimal batch size specified between the two transacted batching behaviors.</span></span> <span data-ttu-id="f2b92-159">이 시나리오에서 끝점 중 하나가 트랜잭션된 일괄 처리를 지정하지 않은 경우, 양쪽 끝점 모두 일괄 처리를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-159">In this scenario, if one of the endpoints does not specify transacted batching, then both endpoints would not use batching.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2b92-160">예제</span><span class="sxs-lookup"><span data-stu-id="f2b92-160">Example</span></span>  
 <span data-ttu-id="f2b92-161">다음 예제에서는 구성 파일에서 `TransactedBatchingBehavior`를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-161">The following example shows how to specify the `TransactedBatchingBehavior` in a configuration file.</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="TransactedBatchingBehavior"
              maxBatchSize="100" />
  </endpointBehaviors>
</behaviors>
```  
  
 <span data-ttu-id="f2b92-162">다음 예제에서는 코드에서 <xref:System.ServiceModel.Description.TransactedBatchingBehavior>를 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f2b92-162">The following example shows how to specify the <xref:System.ServiceModel.Description.TransactedBatchingBehavior> in code.</span></span>  
  
```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
     ServiceEndpoint sep = ServiceHost.AddServiceEndpoint(typeof(IOrderProcessor), new NetMsmqBinding(), "net.msmq://localhost/private/ServiceModelSamplesTransacted");
     sep.Behaviors.Add(new TransactedBatchingBehavior(100));
     
     // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();
  
    // The service can now be accessed.
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.WriteLine();
    Console.ReadLine();
  
    // Close the ServiceHostB to shut down the service.
    serviceHost.Close();
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2b92-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2b92-163">See Also</span></span>  
 [<span data-ttu-id="f2b92-164">큐 개요</span><span class="sxs-lookup"><span data-stu-id="f2b92-164">Queues Overview</span></span>](../../../../docs/framework/wcf/feature-details/queues-overview.md)  
 [<span data-ttu-id="f2b92-165">WCF의 큐</span><span class="sxs-lookup"><span data-stu-id="f2b92-165">Queuing in WCF</span></span>](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)
