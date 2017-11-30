---
title: CountdownEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9f953f6477abf1f4e0d6aaf79e67005172ff1144
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="countdownevent"></a><span data-ttu-id="e5672-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="e5672-102">CountdownEvent</span></span>
<span data-ttu-id="e5672-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType>신호를 특정 횟수를 지정한 후에 대기 중인 스레드를 차단 해제 하는 동기화 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="e5672-104"><xref:System.Threading.CountdownEvent>있는 그렇지 않은 경우 사용 해야 하는 시나리오를 위한는 <xref:System.Threading.ManualResetEvent> 또는 <xref:System.Threading.ManualResetEventSlim> 및 이벤트 신호를 보내기 전에 변수를 수동으로 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="e5672-105">예를 들어 분기/조인 시나리오에서 만들 수 있습니다만 <xref:System.Threading.CountdownEvent> 신호 수가 5, 있고 스레드에서 시작 5 개 작업 항목 풀 및 각 작업 항목 통화는 다음 <xref:System.Threading.CountdownEvent.Signal%2A> 완료 될 때입니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="e5672-106">호출할 때마다 <xref:System.Threading.CountdownEvent.Signal%2A> 신호 카운트가 1 씩 감소 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="e5672-107">주 스레드에서 호출 <xref:System.Threading.CountdownEvent.Wait%2A> 신호 0이 될 때까지 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5672-108">.NET Framework 동기화 레거시 Api와 상호 작용할 수 없는 코드를 사용 하는 것이 좋습니다 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체 또는 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 분기-조인 병렬 처리 표현 하는 보다 편리 하 게 방식에 대 한 메서드.</span><span class="sxs-lookup"><span data-stu-id="e5672-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="e5672-109"><xref:System.Threading.CountdownEvent>이러한 추가 기능에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
-   <span data-ttu-id="e5672-110">취소 토큰을 사용 하 여 대기 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
-   <span data-ttu-id="e5672-111">인스턴스가 만들어진 후에 신호 수가 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-111">Its signal count can be incremented after the instance is created.</span></span>  
  
-   <span data-ttu-id="e5672-112">후 인스턴스를 다시 사용할 수 <xref:System.Threading.CountdownEvent.Wait%2A> 가 호출 하 여 반환 되는 <xref:System.Threading.CountdownEvent.Reset%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="e5672-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
-   <span data-ttu-id="e5672-113">인스턴스를 노출 한 <xref:System.Threading.WaitHandle> 다른.NET Framework 동기화 Api와의 통합에 대 한 같은 <xref:System.Threading.WaitHandle.WaitAll%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="e5672-114">기본 사용</span><span class="sxs-lookup"><span data-stu-id="e5672-114">Basic Usage</span></span>  
 <span data-ttu-id="e5672-115">다음 예제에서는 사용 하는 <xref:System.Threading.CountdownEvent> 와 <xref:System.Threading.ThreadPool> 작업 항목.</span><span class="sxs-lookup"><span data-stu-id="e5672-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="e5672-116">취소를 지 원하는 CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="e5672-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="e5672-117">다음 예제에서 대기 작업을 취소 하는 방법을 보여 줍니다 <xref:System.Threading.CountdownEvent> 취소 토큰을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="e5672-118">기본 패턴에서 도입 된 통합 된 취소에 대 한 모델을 따르며 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-118">The basic pattern follows the model for unified cancellation, which is introduced in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="e5672-119">자세한 내용은 참조 [관리 되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-119">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="e5672-120">참고 대기 작업 신호를 보내는 하는 스레드의 취소 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="e5672-121">일반적으로 취소 논리 연산에 적용 되 고 대기 하는 이벤트 뿐만 아니라 대기를 동기화 하는 모든 작업 항목에 포함할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="e5672-122">이 예제에서는 취소 요청에 응답할 수 있도록 각 작업 항목에서 동일한 취소 토큰 복사본에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5672-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5672-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5672-123">See Also</span></span>  
 [<span data-ttu-id="e5672-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="e5672-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
