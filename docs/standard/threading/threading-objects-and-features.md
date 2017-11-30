---
title: "스레딩 개체 및 기능"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a73e5c60a661c171e9e46e6307484cf5e0e6b80
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="threading-objects-and-features"></a><span data-ttu-id="2453a-102">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="2453a-102">Threading Objects and Features</span></span>
<span data-ttu-id="2453a-103">.NET Framework에서는 다중 스레드 응용 프로그램을 만들고 관리하는 데 도움이 되는 많은 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-103">The .NET Framework provides a number of objects that help you create and manage multithreaded applications.</span></span> <span data-ttu-id="2453a-104">관리되는 스레드는 <xref:System.Threading.Thread> 클래스를 통해 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-104">Managed threads are represented by the <xref:System.Threading.Thread> class.</span></span> <span data-ttu-id="2453a-105"><xref:System.Threading.ThreadPool> 클래스는 다중 스레드 백그라운드 작업을 쉽게 만들고 관리할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-105">The <xref:System.Threading.ThreadPool> class provides easy creation and management of multithreaded background tasks.</span></span> <span data-ttu-id="2453a-106"><xref:System.ComponentModel.BackgroundWorker> 클래스는 사용자 인터페이스와 상호 작용하는 작업에 대해 동일한 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-106">The <xref:System.ComponentModel.BackgroundWorker> class does the same for tasks that interact with the user interface.</span></span> <span data-ttu-id="2453a-107"><xref:System.Threading.Timer> 클래스는 정해진 간격마다 백그라운드 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-107">The <xref:System.Threading.Timer> class executes background tasks at timed intervals.</span></span>  
  
 <span data-ttu-id="2453a-108">또한 .NET Framework 버전 2.0에서 도입된 <xref:System.Threading.Semaphore> 및 <xref:System.Threading.EventWaitHandle> 클래스를 포함하여 스레드 작업을 동기화하는 많은 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-108">In addition, there are a number of classes that synchronize activities of threads, including the <xref:System.Threading.Semaphore> and <xref:System.Threading.EventWaitHandle> classes introduced in the .NET Framework version 2.0.</span></span> <span data-ttu-id="2453a-109">이러한 클래스의 기능은 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)에서 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-109">The features of these classes are compared in [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2453a-110">단원 내용</span><span class="sxs-lookup"><span data-stu-id="2453a-110">In This Section</span></span>  
 [<span data-ttu-id="2453a-111">관리되는 스레드 풀</span><span class="sxs-lookup"><span data-stu-id="2453a-111">The Managed Thread Pool</span></span>](../../../docs/standard/threading/the-managed-thread-pool.md)  
 <span data-ttu-id="2453a-112">직접 스레드 관리를 수행할 필요 없이 스레드에 작업을 실행하도록 요청할 수 있게 해주는 **ThreadPool** 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-112">Explains the **ThreadPool** class, which enables you to request a thread to execute a task without having to do any thread management yourself.</span></span>  
  
 [<span data-ttu-id="2453a-113">타이머</span><span class="sxs-lookup"><span data-stu-id="2453a-113">Timers</span></span>](../../../docs/standard/threading/timers.md)  
 <span data-ttu-id="2453a-114">**Timer**를 사용하여 대리자가 지정된 시간에 호출되도록 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-114">Explains how to use a **Timer** to specify a delegate to be called at a specified time.</span></span>  
  
 [<span data-ttu-id="2453a-115">모니터</span><span class="sxs-lookup"><span data-stu-id="2453a-115">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 <span data-ttu-id="2453a-116">**Monitor** 클래스를 사용하여 멤버에 대한 액세스를 동기화하거나 고유한 스레드 관리 유형을 빌드하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-116">Explains how to use the **Monitor** class to synchronize access to a member or to build your own thread management types.</span></span>  
  
 [<span data-ttu-id="2453a-117">대기 핸들</span><span class="sxs-lookup"><span data-stu-id="2453a-117">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="2453a-118">이벤트 대기 핸들, 뮤텍스 및 세마포에 대한 추상 기본 클래스로 여러 동기화 이벤트를 대기할 수 있게 해주는 <xref:System.Threading.WaitHandle> 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-118">Describes the <xref:System.Threading.WaitHandle> class, the abstract base class for event wait handles, mutexes, and semaphores, which enables waiting for multiple synchronization events.</span></span>  
  
 [<span data-ttu-id="2453a-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="2453a-119">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 <span data-ttu-id="2453a-120">신호 전송 및 신호 대기를 통해 스레드 작업을 동기화하는 데 사용되는 관리되는 이벤트 대기 핸들을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-120">Describes managed event wait handles, which are used to synchronize thread activities by signaling and waiting for signals.</span></span>  
  
 [<span data-ttu-id="2453a-121">뮤텍스</span><span class="sxs-lookup"><span data-stu-id="2453a-121">Mutexes</span></span>](../../../docs/standard/threading/mutexes.md)  
 <span data-ttu-id="2453a-122">사용 하는 방법에 설명 된 <xref:System.Threading.Mutex> 개체에 대 한 액세스를 동기화 하거나 고유한 동기화 메커니즘을 구축 합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-122">Explains how to use a <xref:System.Threading.Mutex> to synchronize access to an object or to build your own synchronization mechanisms.</span></span>  
  
 [<span data-ttu-id="2453a-123">연동 작업</span><span class="sxs-lookup"><span data-stu-id="2453a-123">Interlocked Operations</span></span>](../../../docs/standard/threading/interlocked-operations.md)  
 <span data-ttu-id="2453a-124"><xref:System.Threading.Interlocked> 클래스를 사용하여 값을 증가 또는 감소시키고 단일 원자성 작업에 값을 저장하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-124">Explains how to use the <xref:System.Threading.Interlocked> class to increment or decrement a value and store the value in a single atomic operation.</span></span>  
  
 [<span data-ttu-id="2453a-125">판독기 및 작성기 잠금</span><span class="sxs-lookup"><span data-stu-id="2453a-125">Reader-Writer Locks</span></span>](../../../docs/standard/threading/reader-writer-locks.md)  
 <span data-ttu-id="2453a-126">단일 작성기/다중 판독기 의미 체계를 구현하는 잠금을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-126">Defines a lock that implements single-writer/multiple-reader semantics.</span></span>  
  
 [<span data-ttu-id="2453a-127">세마포 및 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="2453a-127">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 <span data-ttu-id="2453a-128"><xref:System.Threading.Semaphore> 개체 및 이 개체를 사용하여 제한된 리소스에 대한 액세스를 제어하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-128">Describes <xref:System.Threading.Semaphore> objects and explains how to use them to control access to limited resources.</span></span>  
  
 [<span data-ttu-id="2453a-129">동기화 기본 형식 개요</span><span class="sxs-lookup"><span data-stu-id="2453a-129">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="2453a-130">관리되는 스레드 잠금 및 동기화를 위해 제공되는 .NET Framework 클래스의 기능을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-130">Compares the features of the .NET Framework classes provided for locking and synchronizing managed threads.</span></span>  
  
 [<span data-ttu-id="2453a-131">장벽</span><span class="sxs-lookup"><span data-stu-id="2453a-131">Barrier</span></span>](../../../docs/standard/threading/barrier.md)  
 <span data-ttu-id="2453a-132">단계별 작업에서 스레드를 조정하기 위해 장벽 패턴을 구현하는 <xref:System.Threading.Barrier> 개체를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-132">Describes <xref:System.Threading.Barrier> objects that implement the barrier pattern for coordination of threads in phased operations.</span></span>  
  
 [<span data-ttu-id="2453a-133">스핀 잠금</span><span class="sxs-lookup"><span data-stu-id="2453a-133">SpinLock</span></span>](../../../docs/standard/threading/spinlock.md)  
 <span data-ttu-id="2453a-134">특정 하위 수준 시나리오에 대한 Monitor 클래스의 경량 대체 항목인 <xref:System.Threading.SpinLock>을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-134">Describes <xref:System.Threading.SpinLock>, a lightweight alternative to the Monitor class for certain low-level scenarios.</span></span>  
  
 [<span data-ttu-id="2453a-135">스핀 대기</span><span class="sxs-lookup"><span data-stu-id="2453a-135">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 <span data-ttu-id="2453a-136">커널 기반 대기를 시작하기 전에 사용 중인 회전을 수행하는 낮은 수준의 동기화 기본 형식인 <xref:System.Threading.SpinWait>를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-136">Describes <xref:System.Threading.SpinWait>, a low level synchronization primitive that performs busy spinning prior to initiating a kernel-based wait.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2453a-137">참조</span><span class="sxs-lookup"><span data-stu-id="2453a-137">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="2453a-138">비관리 코드에서 가져왔는지 또는 관리되는 응용 프로그램에서 만들어졌는지에 관계없이 관리되는 스레드를 나타내는 **Thread** 클래스에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-138">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="2453a-139">사용자 인터페이스 스레드에서 발생하는 이벤트를 통해 통신하여 사용자 인터페이스와 상호 작용하는 백그라운드 작업을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-139">Enables background tasks that interact with the user interface, communicating via events raised on the user-interface thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2453a-140">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2453a-140">Related Sections</span></span>  
 [<span data-ttu-id="2453a-141">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="2453a-141">Asynchronous File I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)  
 <span data-ttu-id="2453a-142">I/O 비동기 완료 포트가 스레드 풀을 사용하여 입출력 작업이 완료된 경우에만 처리를 요청하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-142">Describes how I/O asynchronous completion ports use the thread pool to require processing only when an input/output operation completes.</span></span>  
  
 [<span data-ttu-id="2453a-143">TPL(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="2453a-143">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 <span data-ttu-id="2453a-144">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 이상에서 다중 스레드 프로그래밍에 권장되는 접근 방식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2453a-144">Describes the recommended approach for multithreaded programming in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and later.</span></span>
