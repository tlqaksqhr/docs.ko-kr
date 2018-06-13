---
title: CountdownEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, CountdownEvent
ms.assetid: eec3812a-e20f-4ecd-bfef-6921d508b708
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f98e2388cb31e62d974c8b0bae0bdf833f5963a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585362"
---
# <a name="countdownevent"></a><span data-ttu-id="20b51-102">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="20b51-102">CountdownEvent</span></span>
<span data-ttu-id="20b51-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType>는 특정 횟수만큼 신호를 받은 후 대기 스레드를 차단 해제하는 동기화 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-103"><xref:System.Threading.CountdownEvent?displayProperty=nameWithType> is a synchronization primitive that unblocks its waiting threads after it has been signaled a certain number of times.</span></span> <span data-ttu-id="20b51-104"><xref:System.Threading.CountdownEvent>는 <xref:System.Threading.ManualResetEvent> 또는 <xref:System.Threading.ManualResetEventSlim>을 사용하여 이벤트에 신호를 보내기 전에 변수를 수동으로 감소시켜야 하는 시나리오를 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-104"><xref:System.Threading.CountdownEvent> is designed for scenarios in which you would otherwise have to use a <xref:System.Threading.ManualResetEvent> or <xref:System.Threading.ManualResetEventSlim> and manually decrement a variable before signaling the event.</span></span> <span data-ttu-id="20b51-105">예를 들어, 포크/조인 시나리오에서 신호 수가 5인 <xref:System.Threading.CountdownEvent>을 생성한 다음, 스레드 풀에서 5개의 작업 항목을 시작하고 완료될 때 각 작업 항목이 <xref:System.Threading.CountdownEvent.Signal%2A>을 호출하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-105">For example, in a fork/join scenario, you can just create a <xref:System.Threading.CountdownEvent> that has a signal count of 5, and then start five work items on the thread pool and have each work item call <xref:System.Threading.CountdownEvent.Signal%2A> when it completes.</span></span> <span data-ttu-id="20b51-106"><xref:System.Threading.CountdownEvent.Signal%2A>을 호출할 때마다 신호 수가 1씩 감소됩니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-106">Each call to <xref:System.Threading.CountdownEvent.Signal%2A> decrements the signal count by 1.</span></span> <span data-ttu-id="20b51-107">주 스레드에서 <xref:System.Threading.CountdownEvent.Wait%2A>에 대한 호출은 신호 수가 0일 때까지 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-107">On the main thread, the call to <xref:System.Threading.CountdownEvent.Wait%2A> will block until the signal count is zero.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20b51-108">레거시 .NET Framework 동기화 API와 상호 작용할 필요가 없는 코드의 경우, 포크-조인 병렬 처리를 더 쉽게 표현할 수 있도록 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 개체 또는 <xref:System.Threading.Tasks.Parallel.Invoke%2A> 메서드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-108">For code that does not have to interact with legacy .NET Framework synchronization APIs, consider using <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> objects or the <xref:System.Threading.Tasks.Parallel.Invoke%2A> method for an even easier approach to expressing fork-join parallelism.</span></span>  
  
 <span data-ttu-id="20b51-109"><xref:System.Threading.CountdownEvent>에는 다음과 같은 추가 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-109"><xref:System.Threading.CountdownEvent> has these additional features:</span></span>  
  
-   <span data-ttu-id="20b51-110">취소 토큰을 사용하여 대기 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-110">The wait operation can be canceled by using cancellation tokens.</span></span>  
  
-   <span data-ttu-id="20b51-111">인스턴스가 생성된 후에는 신호 수가 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-111">Its signal count can be incremented after the instance is created.</span></span>  
  
-   <span data-ttu-id="20b51-112"><xref:System.Threading.CountdownEvent.Wait%2A>가 <xref:System.Threading.CountdownEvent.Reset%2A> 메서드를 호출하여 반환한 후 인스턴스를 재사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-112">Instances can be reused after <xref:System.Threading.CountdownEvent.Wait%2A> has returned by calling the <xref:System.Threading.CountdownEvent.Reset%2A> method.</span></span>  
  
-   <span data-ttu-id="20b51-113">인스턴스는 <xref:System.Threading.WaitHandle.WaitAll%2A>와 같은 다른 .NET Framework 동기화 API와의 통합을 위해 <xref:System.Threading.WaitHandle>을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-113">Instances expose a <xref:System.Threading.WaitHandle> for integration with other .NET Framework synchronization APIs such as <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span>  
  
## <a name="basic-usage"></a><span data-ttu-id="20b51-114">기본 사용</span><span class="sxs-lookup"><span data-stu-id="20b51-114">Basic Usage</span></span>  
 <span data-ttu-id="20b51-115">다음 예제는 <xref:System.Threading.ThreadPool> 작업 항목에 <xref:System.Threading.CountdownEvent>를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-115">The following example demonstrates how to use a <xref:System.Threading.CountdownEvent> with <xref:System.Threading.ThreadPool> work items.</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#01)]
 [!code-vb[CDS_CountdownEvent#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/module1.vb#01)]  
  
## <a name="countdownevent-with-cancellation"></a><span data-ttu-id="20b51-116">취소를 사용하는 CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="20b51-116">CountdownEvent With Cancellation</span></span>  
 <span data-ttu-id="20b51-117">다음 예제는 취소 토큰을 사용하여 <xref:System.Threading.CountdownEvent>에서 대기 작업을 취소하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-117">The following example shows how to cancel the wait operation on <xref:System.Threading.CountdownEvent> by using a cancellation token.</span></span> <span data-ttu-id="20b51-118">기본 패턴은 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에 도입된 통합 취소를 위한 모델을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-118">The basic pattern follows the model for unified cancellation, which is introduced in [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="20b51-119">자세한 내용은 [관리되는 스레드의 취소](../../../docs/standard/threading/cancellation-in-managed-threads.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20b51-119">For more information, see [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md).</span></span>  
  
 [!code-csharp[CDS_CountdownEvent#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_countdownevent/cs/countdownevent.cs#02)]
 [!code-vb[CDS_CountdownEvent#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_countdownevent/vb/canceleventwait.vb#02)]  
  
 <span data-ttu-id="20b51-120">대기 작업은 해당 작업에 신호를 보내는 스레드를 취소하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-120">Note that the wait operation does not cancel the threads that are signaling it.</span></span> <span data-ttu-id="20b51-121">일반적으로 취소는 논리 연산에 적용되며, 이벤트에 대한 대기뿐만 아니라 대기가 동기화 중인 모든 작업 항목도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-121">Typically, cancellation is applied to a logical operation, and that can include waiting on the event as well as all the work items that the wait is synchronizing.</span></span> <span data-ttu-id="20b51-122">이 예제에서는 취소 요청에 응답할 수 있도록 작업 항목에 동일한 취소 토큰의 사본이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="20b51-122">In this example, each work item is passed a copy of the same cancellation token so that it can respond to the cancellation request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b51-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20b51-123">See Also</span></span>  
 [<span data-ttu-id="20b51-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="20b51-124">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
