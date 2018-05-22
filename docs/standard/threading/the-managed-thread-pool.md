---
title: 관리되는 스레드 풀
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- thread pooling [.NET Framework]
- thread pools [.NET Framework]
- threading [.NET Framework], thread pool
- threading [.NET Framework], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3894229ff5561e50d42a36f576a89ee7bf01c067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="the-managed-thread-pool"></a><span data-ttu-id="1e509-102">관리되는 스레드 풀</span><span class="sxs-lookup"><span data-stu-id="1e509-102">The Managed Thread Pool</span></span>
<span data-ttu-id="1e509-103"><xref:System.Threading.ThreadPool> 클래스는 시스템에서 관리하는 작업자 스레드 풀을 응용 프로그램에 제공하여 스레드 관리 대신 응용 프로그램 작업에 집중할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-103">The <xref:System.Threading.ThreadPool> class provides your application with a pool of worker threads that are managed by the system, allowing you to concentrate on application tasks rather than thread management.</span></span> <span data-ttu-id="1e509-104">후순위 처리가 필요한 간단한 작업이 있는 경우 관리되는 스레드 풀을 통해 쉽게 여러 스레드를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-104">If you have short tasks that require background processing, the managed thread pool is an easy way to take advantage of multiple threads.</span></span> <span data-ttu-id="1e509-105">예를 들어 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 스레드 풀 스레드에서 비동기 작업을 수행하는 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-105">For example, beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] you can create <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> objects, which perform asynchronous tasks on thread pool threads.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e509-106">[!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)]부터 스레드 풀의 처리량이 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]의 이전 릴리스에서 병목으로 식별된 세 가지 주요 영역(큐에 작업 대기, 스레드 풀 스레드 디스패치 및 I/O 완료 스레드 디스패치)에서 크게 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-106">Starting with the [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)], the throughput of the thread pool is significantly improved in three key areas that were identified as bottlenecks in previous releases of the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]: queuing tasks, dispatching thread pool threads, and dispatching I/O completion threads.</span></span> <span data-ttu-id="1e509-107">이 기능을 사용하려면 응용 프로그램이 [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] 이상을 대상으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-107">To use this functionality, your application should target the [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] or later.</span></span>  
  
 <span data-ttu-id="1e509-108">.NET Framework version 2.0에서는 사용자 인터페이스와 상호 작용하는 백그라운드 작업을 위해 사용자 인터페이스 스레드에서 발생한 이벤트를 통해 통신하는 <xref:System.ComponentModel.BackgroundWorker> 클래스도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-108">For background tasks that interact with the user interface, the .NET Framework version 2.0 also provides the <xref:System.ComponentModel.BackgroundWorker> class, which communicates using events raised on the user interface thread.</span></span>  
  
 <span data-ttu-id="1e509-109">.NET Framework는 비동기 I/O 완료, 타이머 콜백, 등록된 대기 작업, 대리자를 사용한 비동기 메서드 호출 및 <xref:System.Net> 소켓 연결을 비롯한 다양한 용도로 스레드 풀 스레드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-109">The .NET Framework uses thread pool threads for many purposes, including asynchronous I/O completion, timer callbacks, registered wait operations, asynchronous method calls using delegates, and <xref:System.Net> socket connections.</span></span>  
  
## <a name="when-not-to-use-thread-pool-threads"></a><span data-ttu-id="1e509-110">스레드 풀 스레드를 사용하지 않아야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="1e509-110">When Not to Use Thread Pool Threads</span></span>  
 <span data-ttu-id="1e509-111">스레드 풀 스레드를 사용하는 대신 고유한 스레드를 만들고 관리하는 것이 적절한 여러 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-111">There are several scenarios in which it is appropriate to create and manage your own threads instead of using thread pool threads:</span></span>  
  
-   <span data-ttu-id="1e509-112">포그라운드 스레드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-112">You require a foreground thread.</span></span>  
  
-   <span data-ttu-id="1e509-113">스레드가 특정 우선 순위를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-113">You require a thread to have a particular priority.</span></span>  
  
-   <span data-ttu-id="1e509-114">스레드가 오랜 시간 동안 차단되게 하는 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-114">You have tasks that cause the thread to block for long periods of time.</span></span> <span data-ttu-id="1e509-115">스레드 풀에 최대 개수의 스레드가 있으므로 차단된 스레드 풀 스레드 수가 많으면 작업이 시작되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-115">The thread pool has a maximum number of threads, so a large number of blocked thread pool threads might prevent tasks from starting.</span></span>  
  
-   <span data-ttu-id="1e509-116">단일 스레드 아파트에 스레드를 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-116">You need to place threads into a single-threaded apartment.</span></span> <span data-ttu-id="1e509-117">모든 <xref:System.Threading.ThreadPool> 스레드는 다중 스레드 아파트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-117">All <xref:System.Threading.ThreadPool> threads are in the multithreaded apartment.</span></span>  
  
-   <span data-ttu-id="1e509-118">스레드와 연결된 안정적인 ID가 있거나 스레드를 작업 전용으로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-118">You need to have a stable identity associated with the thread, or to dedicate a thread to a task.</span></span>  
  
## <a name="thread-pool-characteristics"></a><span data-ttu-id="1e509-119">스레드 풀 특징</span><span class="sxs-lookup"><span data-stu-id="1e509-119">Thread Pool Characteristics</span></span>  
 <span data-ttu-id="1e509-120">스레드 풀 스레드는 백그라운드 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-120">Thread pool threads are background threads.</span></span> <span data-ttu-id="1e509-121">[포그라운드 및 백그라운드 스레드](../../../docs/standard/threading/foreground-and-background-threads.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e509-121">See [Foreground and Background Threads](../../../docs/standard/threading/foreground-and-background-threads.md).</span></span> <span data-ttu-id="1e509-122">각 스레드는 기본 스택 크기를 사용하고, 기본 우선 순위로 실행되며, 다중 스레드 아파트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-122">Each thread uses the default stack size, runs at the default priority, and is in the multithreaded apartment.</span></span>  
  
 <span data-ttu-id="1e509-123">프로세스당 하나의 스레드 풀만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-123">There is only one thread pool per process.</span></span>  
  
### <a name="exceptions-in-thread-pool-threads"></a><span data-ttu-id="1e509-124">스레드 풀 스레드의 예외</span><span class="sxs-lookup"><span data-stu-id="1e509-124">Exceptions in Thread Pool Threads</span></span>  
 <span data-ttu-id="1e509-125">스레드 풀 스레드에 처리되지 않은 예외가 있으면 프로세스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-125">Unhandled exceptions on thread pool threads terminate the process.</span></span> <span data-ttu-id="1e509-126">이 규칙에는 다음 세 가지 예외 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-126">There are three exceptions to this rule:</span></span>  
  
-   <span data-ttu-id="1e509-127"><xref:System.Threading.Thread.Abort%2A>가 호출되었으므로 스레드 풀 스레드에서 <xref:System.Threading.ThreadAbortException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-127">A <xref:System.Threading.ThreadAbortException> is thrown in a thread pool thread, because <xref:System.Threading.Thread.Abort%2A> was called.</span></span>  
  
-   <span data-ttu-id="1e509-128">응용 프로그램 도메인이 언로드되고 있으므로 스레드 풀 스레드에서 <xref:System.AppDomainUnloadedException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-128">An <xref:System.AppDomainUnloadedException> is thrown in a thread pool thread, because the application domain is being unloaded.</span></span>  
  
-   <span data-ttu-id="1e509-129">공용 언어 런타임 또는 호스트 프로세스에서 스레드를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-129">The common language runtime or a host process terminates the thread.</span></span>  
  
 <span data-ttu-id="1e509-130">자세한 내용은 [관리되는 스레드의 예외](../../../docs/standard/threading/exceptions-in-managed-threads.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e509-130">For more information, see [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e509-131">.NET Framework 버전 1.0 및 1.1에서는 공용 언어 런타임이 스레드 풀 스레드에서 처리되지 않은 예외를 자동으로 포착합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-131">In the .NET Framework versions 1.0 and 1.1, the common language runtime silently traps unhandled exceptions in thread pool threads.</span></span> <span data-ttu-id="1e509-132">이는 손상된 응용 프로그램 상태일 수 있으며 결국 응용 프로그램이 중단되게 하여 디버그하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-132">This might corrupt application state and eventually cause applications to hang, which might be very difficult to debug.</span></span>  
  
### <a name="maximum-number-of-thread-pool-threads"></a><span data-ttu-id="1e509-133">스레드 풀 스레드의 최대 개수</span><span class="sxs-lookup"><span data-stu-id="1e509-133">Maximum Number of Thread Pool Threads</span></span>  
 <span data-ttu-id="1e509-134">스레드 풀에 대기할 수 있는 작업 수는 사용 가능한 메모리에 의해서만 제한됩니다. 그러나 스레드 풀은 동시에 프로세스에서 활성화될 수 있는 스레드 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-134">The number of operations that can be queued to the thread pool is limited only by available memory; however, the thread pool limits the number of threads that can be active in the process simultaneously.</span></span> <span data-ttu-id="1e509-135">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터 프로세스에 대한 스레드 풀의 기본 크기는 가상 주소 공간의 크기와 같은 여러 요인에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-135">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the default size of the thread pool for a process depends on several factors, such as the size of the virtual address space.</span></span> <span data-ttu-id="1e509-136">프로세스에서 <xref:System.Threading.ThreadPool.GetMaxThreads%2A> 메서드를 호출하여 스레드 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-136">A process can call the <xref:System.Threading.ThreadPool.GetMaxThreads%2A> method to determine the number of threads.</span></span>  
  
 <span data-ttu-id="1e509-137"><xref:System.Threading.ThreadPool.GetMaxThreads%2A> 및 <xref:System.Threading.ThreadPool.SetMaxThreads%2A> 메서드를 사용하여 최대 스레드 수를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-137">You can control the maximum number of threads by using the <xref:System.Threading.ThreadPool.GetMaxThreads%2A> and <xref:System.Threading.ThreadPool.SetMaxThreads%2A> methods.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e509-138">.NET Framework 버전 1.0 및 1.1에서는 관리 코드에서 스레드 풀의 크기를 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-138">In the .NET Framework versions 1.0 and 1.1, the size of the thread pool cannot be set from managed code.</span></span> <span data-ttu-id="1e509-139">공용 언어 런타임을 호스트하는 코드에서 mscoree.h에 정의된 `CorSetMaxThreads`를 사용하여 크기를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-139">Code that hosts the common language runtime can set the size using `CorSetMaxThreads`, defined in mscoree.h.</span></span>  
  
### <a name="thread-pool-minimums"></a><span data-ttu-id="1e509-140">스레드 풀 최소값</span><span class="sxs-lookup"><span data-stu-id="1e509-140">Thread Pool Minimums</span></span>  
 <span data-ttu-id="1e509-141">스레드 풀은 각 범주에 대해 지정된 최소값에 도달할 때까지 요청 시 새 작업자 스레드 또는 I/O 완료 스레드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-141">The thread pool provides new worker threads or I/O completion threads on demand until it reaches a specified minimum for each category.</span></span> <span data-ttu-id="1e509-142"><xref:System.Threading.ThreadPool.GetMinThreads%2A> 메서드를 사용하여 이러한 최소값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-142">You can use the <xref:System.Threading.ThreadPool.GetMinThreads%2A> method to obtain these minimum values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1e509-143">요구가 적을 때는 실제 스레드 풀 스레드 수가 최소값보다 작을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-143">When demand is low, the actual number of thread pool threads can fall below the minimum values.</span></span>  
  
 <span data-ttu-id="1e509-144">최소값에 도달하면 스레드 풀이 추가 스레드를 만들거나 일부 작업이 완료될 때까지 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-144">When a minimum is reached, the thread pool can create additional threads or wait until some tasks complete.</span></span> <span data-ttu-id="1e509-145">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터는 스레드 풀이 시간 단위당 완료되는 작업 수로 정의된 처리량을 최적화하기 위해 작업자 스레드를 만들고 소멸시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-145">Beginning with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], the thread pool creates and destroys worker threads in order to optimize throughput, which is defined as the number of tasks that complete per unit of time.</span></span> <span data-ttu-id="1e509-146">스레드가 너무 적으면 사용 가능한 리소스가 효율적으로 사용되지 않는 반면, 너무 많으면 리소스 경합이 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-146">Too few threads might not make optimal use of available resources, whereas too many threads could increase resource contention.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="1e509-147"><xref:System.Threading.ThreadPool.SetMinThreads%2A> 메서드를 사용하여 유휴 상태 스레드의 최소 개수를 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-147">You can use the <xref:System.Threading.ThreadPool.SetMinThreads%2A> method to increase the minimum number of idle threads.</span></span> <span data-ttu-id="1e509-148">그러나 이러한 값을 불필요하게 늘리면 성능 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-148">However, unnecessarily increasing these values can cause performance problems.</span></span> <span data-ttu-id="1e509-149">너무 많은 작업이 동시에 시작되는 경우 모두 속도가 느린 것처럼 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-149">If too many tasks start at the same time, all of them might appear to be slow.</span></span> <span data-ttu-id="1e509-150">대부분의 경우 스레드 풀은 고유한 스레드 할당 알고리즘에서 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-150">In most cases the thread pool will perform better with its own algorithm for allocating threads.</span></span>  
  
## <a name="skipping-security-checks"></a><span data-ttu-id="1e509-151">보안 검사 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="1e509-151">Skipping Security Checks</span></span>  
 <span data-ttu-id="1e509-152">스레드 풀은 <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> 및 <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType> 메서드도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-152">The thread pool also provides the <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> and <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="1e509-153">호출자 스택이 큐에 대기 중인 작업을 실행하는 동안 수행되는 보안 검사와 관련이 없는 경우에만 이러한 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-153">Use these methods only when you are certain that the caller's stack is irrelevant to any security checks performed during the execution of the queued task.</span></span> <span data-ttu-id="1e509-154"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 및 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A>는 둘 다 호출자 스택을 캡처합니다. 호출자 스택은 스레드가 작업 실행을 시작할 때 스레드 풀 스레드 스택에 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-154"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> and <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> both capture the caller's stack, which is merged into the stack of the thread pool thread when the thread begins to execute a task.</span></span> <span data-ttu-id="1e509-155">보안 검사가 필요한 경우 전체 스택을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-155">If a security check is required, the entire stack must be checked.</span></span> <span data-ttu-id="1e509-156">검사를 통해 안전성이 제공되지만 성능이 저하되는 단점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-156">Although the check provides safety, it also has a performance cost.</span></span>  
  
## <a name="using-the-thread-pool"></a><span data-ttu-id="1e509-157">스레드 풀 사용</span><span class="sxs-lookup"><span data-stu-id="1e509-157">Using the Thread Pool</span></span>  
 <span data-ttu-id="1e509-158">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터 스레드 풀을 사용하는 가장 쉬운 방법은 [TPL(작업 병렬 라이브러리)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-158">Beginning with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], the easiest way to use the thread pool is to use the [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md).</span></span> <span data-ttu-id="1e509-159">기본적으로 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601>과 같은 병렬 라이브러리 형식은 스레드 풀 스레드를 사용하여 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-159">By default, parallel library types like <xref:System.Threading.Tasks.Task> and <xref:System.Threading.Tasks.Task%601> use thread pool threads to run tasks.</span></span> <span data-ttu-id="1e509-160">관리 코드에서 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType>(또는 비관리 코드에서 `CorQueueUserWorkItem`)을 호출하고 작업을 수행하는 메서드를 나타내는 <xref:System.Threading.WaitCallback> 대리자를 전달하여 스레드 풀을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-160">You can also use the thread pool by calling <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> from managed code (or `CorQueueUserWorkItem` from unmanaged code) and passing a <xref:System.Threading.WaitCallback> delegate representing the method that performs the task.</span></span> <span data-ttu-id="1e509-161">스레드 풀을 사용하는 또 다른 방법은 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> 메서드를 사용하고 신호를 받거나 시간 초과된 경우 <xref:System.Threading.WaitOrTimerCallback> 대리자가 나타내는 메서드를 호출하는 <xref:System.Threading.WaitHandle>을 전달하여 대기 작업과 관련된 작업 항목을 큐에 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-161">Another way to use the thread pool is to queue work items that are related to a wait operation by using the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method and passing a <xref:System.Threading.WaitHandle> that, when signaled or when timed out, calls the method represented by the <xref:System.Threading.WaitOrTimerCallback> delegate.</span></span> <span data-ttu-id="1e509-162">스레드 풀 스레드는 콜백 메서드를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-162">Thread pool threads are used to invoke callback methods.</span></span>  
  
## <a name="threadpool-examples"></a><span data-ttu-id="1e509-163">ThreadPool 예제</span><span class="sxs-lookup"><span data-stu-id="1e509-163">ThreadPool Examples</span></span>  
 <span data-ttu-id="1e509-164">이 섹션의 코드 예제에서는 <xref:System.Threading.Tasks.Task> 클래스, <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 메서드 및 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> 메서드를 사용하여 스레드 풀을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-164">The code examples in this section demonstrate the thread pool by using the <xref:System.Threading.Tasks.Task> class, the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method, and the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> method.</span></span>  
  
-   [<span data-ttu-id="1e509-165">작업 병렬 라이브러리를 사용하여 비동기 작업 실행</span><span class="sxs-lookup"><span data-stu-id="1e509-165">Executing Asynchronous Tasks with the Task Parallel Library</span></span>](#TaskParallelLibrary)  
  
-   [<span data-ttu-id="1e509-166">QueueUserWorkItem을 사용하여 비동기적으로 코드 실행</span><span class="sxs-lookup"><span data-stu-id="1e509-166">Executing Code Asynchronously with QueueUserWorkItem</span></span>](#ExecuteCodeWithQUWI)  
  
-   [<span data-ttu-id="1e509-167">QueueUserWorkItem에 대한 작업 데이터 제공</span><span class="sxs-lookup"><span data-stu-id="1e509-167">Supplying Task Data for QueueUserWorkItem</span></span>](#TaskDataForQUWI)  
  
-   [<span data-ttu-id="1e509-168">RegisterWaitForSingleObject 사용</span><span class="sxs-lookup"><span data-stu-id="1e509-168">Using RegisterWaitForSingleObject</span></span>](#RegisterWaitForSingleObject)  
  
<a name="TaskParallelLibrary"></a>   
### <a name="executing-asynchronous-tasks-with-the-task-parallel-library"></a><span data-ttu-id="1e509-169">작업 병렬 라이브러리를 사용하여 비동기 작업 실행</span><span class="sxs-lookup"><span data-stu-id="1e509-169">Executing Asynchronous Tasks with the Task Parallel Library</span></span>  
 <span data-ttu-id="1e509-170">다음 예제에서는 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> 메서드를 호출하여 <xref:System.Threading.Tasks.Task> 개체를 만들고 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-170">The following example shows how to create and use a <xref:System.Threading.Tasks.Task> object by calling the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="1e509-171"><xref:System.Threading.Tasks.Task%601> 클래스를 사용하여 비동기 작업의 값을 반환하는 예제는 [방법: 작업에서 값 반환](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e509-171">For an example that uses the <xref:System.Threading.Tasks.Task%601> class to return a value from an asynchronous task, see [How to: Return a Value from a Task](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md).</span></span>  
  
 [!code-csharp[System.Threading.Tasks.Task#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.task/cs/startnew.cs#01)]
 [!code-vb[System.Threading.Tasks.Task#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.task/vb/startnew.vb#01)]  
  
<a name="ExecuteCodeWithQUWI"></a>   
### <a name="executing-code-asynchronously-with-queueuserworkitem"></a><span data-ttu-id="1e509-172">QueueUserWorkItem을 사용하여 비동기적으로 코드 실행</span><span class="sxs-lookup"><span data-stu-id="1e509-172">Executing Code Asynchronously with QueueUserWorkItem</span></span>  
 <span data-ttu-id="1e509-173">다음 예제에서는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 메서드를 사용하여 `ThreadProc` 메서드가 나타내는 매우 간단한 작업을 큐에 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-173">The following example queues a very simple task, represented by the `ThreadProc` method, using the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span>  
  
 [!code-cpp[Conceptual.ThreadPool#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.ThreadPool#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source1.cs#1)]
 [!code-vb[Conceptual.ThreadPool#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source1.vb#1)]  
  
<a name="TaskDataForQUWI"></a>   
### <a name="supplying-task-data-for-queueuserworkitem"></a><span data-ttu-id="1e509-174">QueueUserWorkItem에 대한 작업 데이터 제공</span><span class="sxs-lookup"><span data-stu-id="1e509-174">Supplying Task Data for QueueUserWorkItem</span></span>  
 <span data-ttu-id="1e509-175">다음 코드 예제에서는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 메서드를 사용하여 작업을 큐에 대기하고 작업에 대한 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-175">The following code example uses the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method to queue a task and supply the data for the task.</span></span>  
  
 [!code-cpp[Conceptual.ThreadPool#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.ThreadPool#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source2.cs#2)]
 [!code-vb[Conceptual.ThreadPool#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source2.vb#2)]  
  
<a name="RegisterWaitForSingleObject"></a>   
### <a name="using-registerwaitforsingleobject"></a><span data-ttu-id="1e509-176">RegisterWaitForSingleObject 사용</span><span class="sxs-lookup"><span data-stu-id="1e509-176">Using RegisterWaitForSingleObject</span></span>  
 <span data-ttu-id="1e509-177">다음 예제에서는 여러 가지 스레딩 기능을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e509-177">The following example demonstrates several threading features.</span></span>  
  
-   <span data-ttu-id="1e509-178"><xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> 메서드를 사용하여 <xref:System.Threading.ThreadPool> 스레드에서 실행할 작업을 큐에 대기.</span><span class="sxs-lookup"><span data-stu-id="1e509-178">Queuing a task for execution by <xref:System.Threading.ThreadPool> threads, with the <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> method.</span></span>  
  
-   <span data-ttu-id="1e509-179"><xref:System.Threading.AutoResetEvent>를 사용하여 실행할 작업에 신호 보내기.</span><span class="sxs-lookup"><span data-stu-id="1e509-179">Signaling a task to execute, with <xref:System.Threading.AutoResetEvent>.</span></span> <span data-ttu-id="1e509-180">[EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e509-180">See [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md).</span></span>  
  
-   <span data-ttu-id="1e509-181"><xref:System.Threading.WaitOrTimerCallback> 대리자를 사용하여 시간 초과 및 신호 모두 처리.</span><span class="sxs-lookup"><span data-stu-id="1e509-181">Handling both time-outs and signals with a <xref:System.Threading.WaitOrTimerCallback> delegate.</span></span>  
  
-   <span data-ttu-id="1e509-182"><xref:System.Threading.RegisteredWaitHandle>을 사용하여 큐에 대기 중인 작업 취소.</span><span class="sxs-lookup"><span data-stu-id="1e509-182">Canceling a queued task with <xref:System.Threading.RegisteredWaitHandle>.</span></span>  
  
 [!code-cpp[Conceptual.ThreadPool#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.ThreadPool#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source3.cs#3)]
 [!code-vb[Conceptual.ThreadPool#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source3.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="1e509-183">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1e509-183">See Also</span></span>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.Tasks.Task>  
 <xref:System.Threading.Tasks.Task%601>  
 [<span data-ttu-id="1e509-184">TPL(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="1e509-184">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [<span data-ttu-id="1e509-185">TPL(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="1e509-185">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [<span data-ttu-id="1e509-186">방법: 작업에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="1e509-186">How to: Return a Value from a Task</span></span>](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)  
 [<span data-ttu-id="1e509-187">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="1e509-187">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="1e509-188">스레드 및 스레딩</span><span class="sxs-lookup"><span data-stu-id="1e509-188">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 [<span data-ttu-id="1e509-189">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="1e509-189">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [<span data-ttu-id="1e509-190">타이머</span><span class="sxs-lookup"><span data-stu-id="1e509-190">Timers</span></span>](../../../docs/standard/threading/timers.md)
