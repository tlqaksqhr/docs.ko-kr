---
title: 관리되는 스레딩 기본 사항
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- multiple threads
- threading [.NET Framework], multiple threads
- threading [.NET Framework], about threading
- managed threading
ms.assetid: b2944911-0e8f-427d-a8bb-077550618935
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fa91bb22de6492815f79bfd50e1fefc800c6047
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="managed-threading-basics"></a><span data-ttu-id="fa014-102">관리되는 스레딩 기본 사항</span><span class="sxs-lookup"><span data-stu-id="fa014-102">Managed Threading Basics</span></span>
<span data-ttu-id="fa014-103">이 섹션의 첫 5개 항목은 관리되는 스레딩을 사용하는 시기를 결정하도록 돕고 몇 가지 기본 기능을 설명하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-103">The first five topics of this section are designed to help you determine when to use managed threading, and to explain some basic features.</span></span> <span data-ttu-id="fa014-104">추가 기능을 제공하는 클래스에 대한 내용은 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md) 및 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa014-104">For information on classes that provide additional features, see [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) and [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).</span></span>  
  
 <span data-ttu-id="fa014-105">이 섹션의 나머지 항목에서는 Windows 운영 체제와 관리되는 스레딩의 상호 작용을 비롯한 고급 주제를 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-105">The rest of the topics in this section cover advanced topics, including the interaction of managed threading with the Windows operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa014-106">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서 작업 병렬 라이브러리 및 PLINQ는 다중 스레드 프로그램에서 작업 및 데이터 병렬 처리를 위한 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-106">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], the Task Parallel Library and PLINQ provide APIs for task and data parallelism in multi-threaded programs.</span></span> <span data-ttu-id="fa014-107">자세한 내용은 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa014-107">For more information, see [Parallel Programming](../../../docs/standard/parallel-programming/index.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa014-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="fa014-108">In This Section</span></span>  
 [<span data-ttu-id="fa014-109">스레드 및 스레딩</span><span class="sxs-lookup"><span data-stu-id="fa014-109">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="fa014-110">다중 스레드의 장단점에 대해 설명하고 스레드를 만들거나 스레드 풀 스레드를 사용할 수 있는 시나리오를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-110">Discusses the advantages and drawbacks of multiple threads, and outlines the scenarios in which you might create threads or use thread pool threads.</span></span>  
  
 [<span data-ttu-id="fa014-111">관리되는 스레드의 예외</span><span class="sxs-lookup"><span data-stu-id="fa014-111">Exceptions in Managed Threads</span></span>](../../../docs/standard/threading/exceptions-in-managed-threads.md)  
 <span data-ttu-id="fa014-112">.NET Framework의 여러 버전에 대해 스레드의 처리되지 않은 예외의 동작(특히 응용 프로그램 종료를 발생시키는 상황에서)에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-112">Describes the behavior of unhandled exceptions in threads for different versions of the .NET Framework, in particular the situations in which they result in termination of the application.</span></span>  
  
 [<span data-ttu-id="fa014-113">다중 스레딩을 위한 데이터 동기화</span><span class="sxs-lookup"><span data-stu-id="fa014-113">Synchronizing Data for Multithreading</span></span>](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)  
 <span data-ttu-id="fa014-114">다중 스레드에서 사용할 클래스의 데이터를 동기화하기 위한 전략에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-114">Describes strategies for synchronizing data in classes that will be used with multiple threads.</span></span>  
  
 [<span data-ttu-id="fa014-115">관리되는 스레드 상태</span><span class="sxs-lookup"><span data-stu-id="fa014-115">Managed Thread States</span></span>](../../../docs/standard/threading/managed-thread-states.md)  
 <span data-ttu-id="fa014-116">기본 스레드 상태를 설명하고 스레드가 실행 중인지 여부를 감지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-116">Describes the basic thread states, and explains how to detect whether a thread is running.</span></span>  
  
 [<span data-ttu-id="fa014-117">포그라운드 및 백그라운드 스레드</span><span class="sxs-lookup"><span data-stu-id="fa014-117">Foreground and Background Threads</span></span>](../../../docs/standard/threading/foreground-and-background-threads.md)  
 <span data-ttu-id="fa014-118">포그라운드 스레드와 백그라운드 스레드 간의 차이점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-118">Explains the differences between foreground and background threads.</span></span>  
  
 [<span data-ttu-id="fa014-119">Windows에서 관리되는 스레딩 및 관리되지 않는 스레딩</span><span class="sxs-lookup"><span data-stu-id="fa014-119">Managed and Unmanaged Threading in Windows</span></span>](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)  
 <span data-ttu-id="fa014-120">관리되는 스레딩과 관리되지 않는 스레딩, 간의 관계에 대해 설명하고, Windows 스레딩 API에 대해 관리되는 스레딩을 나열하고, COM 아파트 및 관리되는 스레드의 상호 작용에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-120">Discusses the relationship between managed and unmanaged threading, lists managed equivalents for Windows threading APIs, and discusses the interaction of COM apartments and managed threads.</span></span>  
  
 [<span data-ttu-id="fa014-121">Thread.Suspend, 가비지 컬렉션, 안전한 시점</span><span class="sxs-lookup"><span data-stu-id="fa014-121">Thread.Suspend, Garbage Collection, and Safe Points</span></span>](../../../docs/standard/threading/thread-suspend-garbage-collection-and-safe-points.md)  
 <span data-ttu-id="fa014-122">스레드 일시중단 및 가비지 수집에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-122">Describes thread suspension and garbage collection.</span></span>  
  
 [<span data-ttu-id="fa014-123">스레드 로컬 저장소: 스레드 상대 정적 필드 및 데이터 슬롯</span><span class="sxs-lookup"><span data-stu-id="fa014-123">Thread Local Storage: Thread-Relative Static Fields and Data Slots</span></span>](../../../docs/standard/threading/thread-local-storage-thread-relative-static-fields-and-data-slots.md)  
 <span data-ttu-id="fa014-124">스레드 관련 저장소 메커니즘을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-124">Describes thread-relative storage mechanisms.</span></span>  
  
 [<span data-ttu-id="fa014-125">관리되는 스레드의 취소</span><span class="sxs-lookup"><span data-stu-id="fa014-125">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)  
 <span data-ttu-id="fa014-126">취소 토큰을 사용하여 비동기 또는 장기 실행 동기 작업을 취소할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-126">Describes how asynchronous or long-running synchronous operations can be canceled by using a cancellation token.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="fa014-127">참조</span><span class="sxs-lookup"><span data-stu-id="fa014-127">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="fa014-128">비관리 코드에서 가져왔는지 또는 관리되는 응용 프로그램에서 만들어졌는지에 관계없이 관리되는 스레드를 나타내는 **Thread** 클래스에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-128">Provides reference documentation for the **Thread** class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <span data-ttu-id="fa014-129">사용자 인터페이스 개체와 함께 다중 스레딩을 구현할 수 있는 안전한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-129">Provides a safe way to implement multithreading in conjunction with user-interface objects.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fa014-130">관련 단원</span><span class="sxs-lookup"><span data-stu-id="fa014-130">Related Sections</span></span>  
 [<span data-ttu-id="fa014-131">동기화 기본 형식 개요</span><span class="sxs-lookup"><span data-stu-id="fa014-131">Overview of Synchronization Primitives</span></span>](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 <span data-ttu-id="fa014-132">다중 스레드의 활동을 동기화하는 데 사용되는 관리되는 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-132">Describes the managed classes used to synchronize the activities of multiple threads.</span></span>  
  
 [<span data-ttu-id="fa014-133">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="fa014-133">Managed Threading Best Practices</span></span>](../../../docs/standard/threading/managed-threading-best-practices.md)  
 <span data-ttu-id="fa014-134">문제를 피할 수 있도록 다중 스레딩 및 전략에 대한 일반적인 문제를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-134">Describes common problems with multithreading and strategies for avoiding problems.</span></span>  
  
 [<span data-ttu-id="fa014-135">병렬 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fa014-135">Parallel Programming</span></span>](../../../docs/standard/parallel-programming/index.md)  
 <span data-ttu-id="fa014-136">비동기 및 다중 스레드 .NET Framework 응용 프로그램을 만드는 작업을 크게 간소화하는 작업 병렬 라이브러리 및 PLINQ에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fa014-136">Describes the Task Parallel Library and PLINQ, which greatly simplify the work of creating asynchronous and multi-threaded .NET Framework applications.</span></span>
