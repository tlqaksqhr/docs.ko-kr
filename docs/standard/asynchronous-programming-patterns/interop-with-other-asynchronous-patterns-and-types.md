---
title: "다른 비동기 패턴 및 형식과의 Interop"
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
helpviewer_keywords:
- .NET Framework, and TAP
- asynchronous design patterns, .NET Framework
- TAP, .NET Framework support for
- Task-based Asynchronous Pattern, .NET Framework support for
- .NET Framework, asynchronous design patterns
ms.assetid: f120a5d9-933b-4d1d-acb6-f034a57c3749
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e30b562b4795717df526c143df96607686a7582
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="interop-with-other-asynchronous-patterns-and-types"></a><span data-ttu-id="d57c7-102">다른 비동기 패턴 및 형식과의 Interop</span><span class="sxs-lookup"><span data-stu-id="d57c7-102">Interop with Other Asynchronous Patterns and Types</span></span>
<span data-ttu-id="d57c7-103">.NET Framework 1.0에서는 <xref:System.IAsyncResult> 또는 [Begin/End](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md)패턴이라고도 하는 `Begin/End` 패턴이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-103">The .NET Framework 1.0 introduced the <xref:System.IAsyncResult> pattern, otherwise known as the [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md), or the `Begin/End` pattern.</span></span>  <span data-ttu-id="d57c7-104">.NET Framework 2.0에서는 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-104">The .NET Framework 2.0 added the [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  <span data-ttu-id="d57c7-105">.NET Framework 4부터 [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) 이 APM과 EAP를 둘 다 대체하지만 이전 패턴에서 마이그레이션 루틴을 쉽게 빌드할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-105">Starting with the .NET Framework 4, the [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md) supersedes both APM and EAP, but provides the ability to easily build migration routines from the earlier patterns.</span></span>  
  
 <span data-ttu-id="d57c7-106">항목 내용</span><span class="sxs-lookup"><span data-stu-id="d57c7-106">In this topic:</span></span>  
  
-   <span data-ttu-id="d57c7-107">[작업 및 APM](#APM) ([APM에서 TAP로](#ApmToTap) 또는 [TAP에서 APM으로](#TapToApm))</span><span class="sxs-lookup"><span data-stu-id="d57c7-107">[Tasks and APM](#APM) ([from APM to TAP](#ApmToTap) or [from TAP to APM](#TapToApm))</span></span>  
  
-   [<span data-ttu-id="d57c7-108">작업 및 EAP</span><span class="sxs-lookup"><span data-stu-id="d57c7-108">Tasks and EAP</span></span>](#EAP)  
  
-   <span data-ttu-id="d57c7-109">[작업 및 대기 핸들](#WaitHandles) ([대기 핸들에서 TAP로](#WHToTap) 또는 [TAP에서 대기 핸들로](#TapToWH))</span><span class="sxs-lookup"><span data-stu-id="d57c7-109">[Tasks and wait handles](#WaitHandles) ([from wait handles to TAP](#WHToTap) or [from TAP to wait handles](#TapToWH))</span></span>  
  
<a name="APM"></a>   
## <a name="tasks-and-the-asynchronous-programming-model-apm"></a><span data-ttu-id="d57c7-110">작업 및 APM(비동기 프로그래밍 모델)</span><span class="sxs-lookup"><span data-stu-id="d57c7-110">Tasks and the Asynchronous Programming Model (APM)</span></span>  
  
<a name="ApmToTap"></a>   
### <a name="from-apm-to-tap"></a><span data-ttu-id="d57c7-111">APM에서 TAP로</span><span class="sxs-lookup"><span data-stu-id="d57c7-111">From APM to TAP</span></span>  
 <span data-ttu-id="d57c7-112">[Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) 패턴은 매우 구조적이므로 APM 구현을 TAP 구현으로 노출하는 래퍼를 쉽게 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-112">Because the [Asynchronous Programming Model (APM)](../../../docs/standard/asynchronous-programming-patterns/asynchronous-programming-model-apm.md) pattern is very structured, it is quite easy to build a wrapper to expose an APM implementation as a TAP implementation.</span></span> <span data-ttu-id="d57c7-113">사실상, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터 .NET Framework에 이 변환을 제공하는 도우미 루틴이 <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> 메서드 오버로드의 형태로 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-113">In fact, the .NET Framework, starting with [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], includes helper routines in the form of <xref:System.Threading.Tasks.TaskFactory.FromAsync%2A> method overloads to provide this translation.</span></span>  
  
 <span data-ttu-id="d57c7-114">동기 <xref:System.IO.Stream> 메서드에 해당하는 APM 항목을 나타내는 <xref:System.IO.Stream.BeginRead%2A> 클래스와 해당 <xref:System.IO.Stream.EndRead%2A> 및 <xref:System.IO.Stream.Read%2A> 메서드를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-114">Consider the <xref:System.IO.Stream> class and its <xref:System.IO.Stream.BeginRead%2A> and <xref:System.IO.Stream.EndRead%2A> methods, which represent the APM counterpart to the synchronous <xref:System.IO.Stream.Read%2A> method:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#1)]
 [!code-vb[Conceptual.AsyncInterop#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#1)]  
[!code-csharp[Conceptual.AsyncInterop#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#2)]
[!code-vb[Conceptual.AsyncInterop#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#2)]  
[!code-csharp[Conceptual.AsyncInterop#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Stream1.cs#3)]
[!code-vb[Conceptual.AsyncInterop#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/stream1.vb#3)]  
  
 <span data-ttu-id="d57c7-115">사용할 수는 <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> 다음과 같이이 작업에 대 한 TAP 래퍼를 구현 하려면 메서드:</span><span class="sxs-lookup"><span data-stu-id="d57c7-115">You can use the <xref:System.Threading.Tasks.TaskFactory%601.FromAsync%2A?displayProperty=nameWithType> method to implement a TAP wrapper for this operation as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap1.cs#4)]
 [!code-vb[Conceptual.AsyncInterop#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap1.vb#4)]  
  
 <span data-ttu-id="d57c7-116">구현은 다음과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-116">This implementation is similar to the following:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wrap2.cs#5)]
 [!code-vb[Conceptual.AsyncInterop#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wrap2.vb#5)]  
  
<a name="TapToApm"></a>   
### <a name="from-tap-to-apm"></a><span data-ttu-id="d57c7-117">TAP에서 APM으로</span><span class="sxs-lookup"><span data-stu-id="d57c7-117">From TAP to APM</span></span>  
 <span data-ttu-id="d57c7-118">기존 인프라에 APM 패턴이 필요한 경우 TAP 구현을 가져와 APM 구현이 필요한 곳에서 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-118">If your existing infrastructure expects the APM pattern, you'll also want to take a TAP implementation and use it where an APM implementation is expected.</span></span>  <span data-ttu-id="d57c7-119">작업이 구성되고 <xref:System.Threading.Tasks.Task> 클래스가 <xref:System.IAsyncResult>를 구현하기 때문에 간단한 도우미 함수를 사용하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-119">Because tasks can be composed and  the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, you can use a straightforward helper function to do this.</span></span> <span data-ttu-id="d57c7-120">다음 코드에서는 <xref:System.Threading.Tasks.Task%601> 클래스 확장을 사용하지만 제네릭이 아닌 작업에 대해 거의 동일한 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-120">The following code uses an extension of the <xref:System.Threading.Tasks.Task%601> class, but you can use an almost identical function for non-generic tasks.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM1.cs#6)]
 [!code-vb[Conceptual.AsyncInterop#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM1.vb#6)]  
  
 <span data-ttu-id="d57c7-121">이제 다음 TAP 구현이 있는 경우를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="d57c7-121">Now, consider a case where you have the following TAP implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#7)]
 [!code-vb[Conceptual.AsyncInterop#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#7)]  
  
 <span data-ttu-id="d57c7-122">다음 APM 구현을 제공하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-122">and you want to provide this APM implementation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#8)]
 [!code-vb[Conceptual.AsyncInterop#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#8)]  
[!code-csharp[Conceptual.AsyncInterop#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#9)]
[!code-vb[Conceptual.AsyncInterop#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#9)]  
  
 <span data-ttu-id="d57c7-123">다음 예제에서는 APM으로 마이그레이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-123">The following example demonstrates one migration to APM:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/APM2.cs#10)]
 [!code-vb[Conceptual.AsyncInterop#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/APM2.vb#10)]  
  
<a name="EAP"></a>   
## <a name="tasks-and-the-event-based-asynchronous-pattern-eap"></a><span data-ttu-id="d57c7-124">작업 및 EAP(이벤트 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="d57c7-124">Tasks and the Event-based Asynchronous Pattern (EAP)</span></span>  
 <span data-ttu-id="d57c7-125">EAP 패턴에는 APM 패턴보다 더 많은 변형과 더 적은 구조가 있기 때문에 [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) 구현 래핑이 APM 패턴 래핑보다 훨씬 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-125">Wrapping an [Event-based Asynchronous Pattern (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md) implementation is more involved than wrapping an APM pattern, because the EAP pattern has more variation and less structure than the APM pattern.</span></span>  <span data-ttu-id="d57c7-126">이를 보여 주기 위해 다음 코드에서는 `DownloadStringAsync` 메서드를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-126">To demonstrate, the following code wraps the `DownloadStringAsync` method.</span></span>  <span data-ttu-id="d57c7-127">`DownloadStringAsync` 는 URI를 수락하고 진행 중인 여러 통계를 보고하기 위해 다운로드하는 동안 `DownloadProgressChanged` 이벤트를 발생시키며 완료되면 `DownloadStringCompleted` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-127">`DownloadStringAsync` accepts a URI, raises the `DownloadProgressChanged` event while downloading in order to report multiple statistics on progress, and raises the `DownloadStringCompleted` event when it's done.</span></span>  <span data-ttu-id="d57c7-128">최종 결과는 지정된 URI에 있는 페이지의 내용이 포함된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-128">The final result is a string that contains the contents of the page at the specified URI.</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/EAP1.cs#11)]
 [!code-vb[Conceptual.AsyncInterop#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/EAP1.vb#11)]  
  
<a name="WaitHandles"></a>   
## <a name="tasks-and-wait-handles"></a><span data-ttu-id="d57c7-129">작업 및 대기 핸들</span><span class="sxs-lookup"><span data-stu-id="d57c7-129">Tasks and Wait Handles</span></span>  
  
<a name="WHToTap"></a>   
### <a name="from-wait-handles-to-tap"></a><span data-ttu-id="d57c7-130">대기 핸들에서 TAP로</span><span class="sxs-lookup"><span data-stu-id="d57c7-130">From Wait Handles to TAP</span></span>  
 <span data-ttu-id="d57c7-131">대기 핸들은 비동기 패턴을 구현 하지 않지만 고급 개발자가 사용할 수는 <xref:System.Threading.WaitHandle> 클래스 및 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> 메서드를 비동기 알림에 대기 핸들을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-131">Although wait handles don't implement an asynchronous pattern, advanced developers may use the <xref:System.Threading.WaitHandle> class and the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method for asynchronous notifications when a wait handle is set.</span></span>  <span data-ttu-id="d57c7-132"><xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> 메서드를 래핑하여 대기 핸들의 동기 대기에 대해 작업 기반 대체 항목을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-132">You can wrap the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> method to enable a task-based alternative to any synchronous wait on a wait handle:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#12)]
 [!code-vb[Conceptual.AsyncInterop#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#12)]  
  
 <span data-ttu-id="d57c7-133">이 메서드를 통해 비동기 메서드에서 기존 <xref:System.Threading.WaitHandle> 구현을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-133">With this method, you can use existing <xref:System.Threading.WaitHandle> implementations in asynchronous methods.</span></span>  <span data-ttu-id="d57c7-134">예를 들어 특정 시간에 실행 되는 비동기 작업의 수를 제한 하려는 경우 세마포 활용할 수 있습니다 (한 <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> 개체).</span><span class="sxs-lookup"><span data-stu-id="d57c7-134">For example, if you want to throttle the number of asynchronous operations that are executing at any particular time, you can utilize a semaphore (a <xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType> object).</span></span>  <span data-ttu-id="d57c7-135">세마포 개수를 *N* 으로 초기화하고, 작업을 수행하려는 시간 동안 세마포에서 대기한 다음 작업이 완료되면 세마포를 해제하여 동시에 실행되는 작업 수를 *N*개로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-135">You can throttle to *N* the number of operations that run concurrently by initializing the semaphore’s count to *N*, waiting on the semaphore any time you want to perform an operation, and releasing the semaphore when you’re done with an operation:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Semaphore1.cs#13)]
 [!code-vb[Conceptual.AsyncInterop#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Semaphore1.vb#13)]  
  
 <span data-ttu-id="d57c7-136">대기 핸들에 의존하지 않고 완전히 작업으로 작동하는 비동기 세마포를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-136">You can also build an asynchronous semaphore that does not rely on wait handles and instead works completely with tasks.</span></span> <span data-ttu-id="d57c7-137">이렇게 하려면 [Consuming the Task-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md) 에 설명된 <xref:System.Threading.Tasks.Task>이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-137">To do this, you can use techniques such as those discussed in [Consuming the Task-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md) for building data structures on top of <xref:System.Threading.Tasks.Task>.</span></span>  
  
<a name="TapToWH"></a>   
### <a name="from-tap-to-wait-handles"></a><span data-ttu-id="d57c7-138">TAP에서 대기 핸들로</span><span class="sxs-lookup"><span data-stu-id="d57c7-138">From TAP to Wait Handles</span></span>  
 <span data-ttu-id="d57c7-139">앞에서 설명한 대로 <xref:System.Threading.Tasks.Task> 클래스는 <xref:System.IAsyncResult>를 구현하고, 해당 구현에서 <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> 가 완료될 때 설정되는 대기 핸들을 반환하는 <xref:System.Threading.Tasks.Task> 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-139">As previously mentioned, the <xref:System.Threading.Tasks.Task> class implements <xref:System.IAsyncResult>, and that implementation exposes an <xref:System.Threading.Tasks.Task.System%23IAsyncResult%23AsyncWaitHandle%2A> property that returns a wait handle that will be set when the <xref:System.Threading.Tasks.Task> completes.</span></span>  <span data-ttu-id="d57c7-140">다음과 같이 <xref:System.Threading.WaitHandle> 에 대한 <xref:System.Threading.Tasks.Task> 을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d57c7-140">You can get a <xref:System.Threading.WaitHandle> for a <xref:System.Threading.Tasks.Task> as follows:</span></span>  
  
 [!code-csharp[Conceptual.AsyncInterop#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.AsyncInterop/cs/Wait1.cs#14)]
 [!code-vb[Conceptual.AsyncInterop#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.AsyncInterop/vb/Wait1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="d57c7-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d57c7-141">See Also</span></span>  
 [<span data-ttu-id="d57c7-142">TAP(작업 기반 비동기 패턴)</span><span class="sxs-lookup"><span data-stu-id="d57c7-142">Task-based Asynchronous Pattern (TAP)</span></span>](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)  
 [<span data-ttu-id="d57c7-143">작업 기반 비동기 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="d57c7-143">Implementing the Task-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/implementing-the-task-based-asynchronous-pattern.md)  
 [<span data-ttu-id="d57c7-144">작업 기반 비동기 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="d57c7-144">Consuming the Task-based Asynchronous Pattern</span></span>](../../../docs/standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)
