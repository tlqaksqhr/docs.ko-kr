---
title: 장벽(.NET Framework)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 392e975f6bf566c2ba36290940eb0daee03f004f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="barrier-net-framework"></a><span data-ttu-id="1f767-102">장벽(.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="1f767-102">Barrier (.NET Framework)</span></span>
<span data-ttu-id="1f767-103">‘장벽’은 여러 스레드(‘참가자’라고 함)가 단계별로 알고리즘에서 동시에 작동할 수 있게 해주는 사용자 정의 동기화 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-103">A *barrier* is a user-defined synchronization primitive that enables multiple threads (known as *participants*) to work concurrently on an algorithm in phases.</span></span> <span data-ttu-id="1f767-104">각 참가자는 코드의 장벽 지점에 도달할 때까지 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-104">Each participant executes until it reaches the barrier point in the code.</span></span> <span data-ttu-id="1f767-105">장벽은 한 작업 단계의 끝을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-105">The barrier represents the end of one phase of work.</span></span> <span data-ttu-id="1f767-106">참가자가 장벽에 도달하면 모든 참가자가 동일한 장벽에 도달할 때까지 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-106">When a participant reaches the barrier, it blocks until all participants have reached the same barrier.</span></span> <span data-ttu-id="1f767-107">모든 참가자가 장벽에 도달한 후 사후 단계 작업을 필요에 따라 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-107">After all participants have reached the barrier, you can optionally invoke a post-phase action.</span></span> <span data-ttu-id="1f767-108">이 사후 단계 작업을 사용하여 다른 모든 스레드는 여전히 차단하는 동시에 단일 스레드에서 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-108">This post-phase action can be used to perform actions by a single thread while all other threads are still blocked.</span></span> <span data-ttu-id="1f767-109">작업이 실행된 후 모든 참가자가 차단 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-109">After the action has been executed, the participants are all unblocked.</span></span>  
  
 <span data-ttu-id="1f767-110">다음 코드 조각에서는 기본 장벽 패턴을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-110">The following code snippet shows a basic barrier pattern.</span></span>  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 <span data-ttu-id="1f767-111">전체 예제는 [방법: 동시 작업을 장벽과 동기화](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f767-111">For a complete example, see [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).</span></span>  
  
## <a name="adding-and-removing-participants"></a><span data-ttu-id="1f767-112">참가자 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="1f767-112">Adding and Removing Participants</span></span>  
 <span data-ttu-id="1f767-113"><xref:System.Threading.Barrier>를 만들 때 참가자 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-113">When you create a <xref:System.Threading.Barrier>, specify the number of participants.</span></span> <span data-ttu-id="1f767-114">언제든지 참가자를 동적으로 추가 또는 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-114">You can also add or remove participants dynamically at any time.</span></span> <span data-ttu-id="1f767-115">예를 들어 한 참가자가 문제의 해당 부분을 해결하는 경우 결과를 저장하고 해당 스레드에서 실행을 중지한 다음, <xref:System.Threading.Barrier.RemoveParticipant%2A>를 호출하여 장벽의 참가자 수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-115">For example, if one participant solves its part of the problem, you can store the result, stop execution on that thread, and call <xref:System.Threading.Barrier.RemoveParticipant%2A> to decrement the number of participants in the barrier.</span></span> <span data-ttu-id="1f767-116"><xref:System.Threading.Barrier.AddParticipant%2A>를 호출하여 참가자를 추가하는 경우 반환 값은 새 참가자의 작업을 초기화하는 데 유용할 수 있는 현재 단계 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-116">When you add a participant by calling <xref:System.Threading.Barrier.AddParticipant%2A>, the return value specifies the current phase number, which may be useful in order to initialize the work of the new participant.</span></span>  
  
## <a name="broken-barriers"></a><span data-ttu-id="1f767-117">손상된 장벽</span><span class="sxs-lookup"><span data-stu-id="1f767-117">Broken Barriers</span></span>  
 <span data-ttu-id="1f767-118">한 참가자가 장벽에 도달하지 못할 경우 교착 상태가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-118">Deadlocks can occur if one participant fails to reach the barrier.</span></span> <span data-ttu-id="1f767-119">이러한 교착 상태를 방지하려면 <xref:System.Threading.Barrier.SignalAndWait%2A> 메서드의 오버로드를 사용하여 시간 제한 기간 및 취소 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-119">To avoid these deadlocks, use the overloads of the <xref:System.Threading.Barrier.SignalAndWait%2A> method to specify a time-out period and a cancellation token.</span></span> <span data-ttu-id="1f767-120">이러한 오버로드는 다음 단계로 넘어가기 전에 각 참가자가 확인할 수 있는 부울 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-120">These overloads return a Boolean value that every participant can check before it continues to the next phase.</span></span>  
  
## <a name="post-phase-exceptions"></a><span data-ttu-id="1f767-121">사후 단계 예외</span><span class="sxs-lookup"><span data-stu-id="1f767-121">Post-Phase Exceptions</span></span>  
 <span data-ttu-id="1f767-122">사후 단계 대리자에서 예외가 발생하는 경우 <xref:System.Threading.BarrierPostPhaseException> 개체에 래핑된 다음 모든 참가자에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-122">If the post-phase delegate throws an exception, it is wrapped in a <xref:System.Threading.BarrierPostPhaseException> object which is then propagated to all participants.</span></span>  
  
## <a name="barrier-versus-continuewhenall"></a><span data-ttu-id="1f767-123">장벽과 ContinueWhenAll 비교</span><span class="sxs-lookup"><span data-stu-id="1f767-123">Barrier Versus ContinueWhenAll</span></span>  
 <span data-ttu-id="1f767-124">장벽은 스레드가 루프로 여러 단계를 수행할 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-124">Barriers are especially useful when the threads are performing multiple phases in loops.</span></span> <span data-ttu-id="1f767-125">코드에 한두 개의 작업 단계만 필요한 경우 다음을 포함하여 임의 종류의 암시적 조인과 함께 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체를 사용할지 여부를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="1f767-125">If your code requires only one or two phases of work, consider whether to use <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects with any kind of implicit join, including:</span></span>  
  
-   <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.Invoke%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.ForEach%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.For%2A>  
  
 <span data-ttu-id="1f767-126">자세한 내용은 [연속 작업을 사용하여 작업 연결](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1f767-126">For more information, see [Chaining Tasks by Using Continuation Tasks](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f767-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f767-127">See Also</span></span>  
 [<span data-ttu-id="1f767-128">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="1f767-128">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="1f767-129">방법: 동시 작업을 배리어와 동기화</span><span class="sxs-lookup"><span data-stu-id="1f767-129">How to: Synchronize Concurrent Operations with a Barrier</span></span>](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)
