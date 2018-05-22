---
title: Windows 시스템의 큰 개체 힙
ms.date: 05/02/2018
helpviewer_keywords:
- large object heap (LOH)"
- LOH
- garbage collection, large object heap
- GC [.NET ], large object heap
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 68513d2535ea9e19a42f9e58b9d423e17008f9de
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
---
# <a name="the-large-object-heap-on-windows-systems"></a><span data-ttu-id="2a812-102">Windows 시스템의 큰 개체 힙</span><span class="sxs-lookup"><span data-stu-id="2a812-102">The large object heap on Windows systems</span></span>

<span data-ttu-id="2a812-103">.NET GC(가비지 수집기)는 개체를 큰 개체 및 작은 개체로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-103">The .NET Garbage Collector (GC) divides objects up into small and large objects.</span></span> <span data-ttu-id="2a812-104">개체가 크면 그 특성 중 일부는 개체가 작을 때보다 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-104">When an object is large, some of its attributes become more significant than if the object is small.</span></span> <span data-ttu-id="2a812-105">예를 들어 개체 압축, 즉 힙의 다른 위치에서 메모리에 복사하는 경우 비용이 많이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-105">For instance, compacting it -- that is, copying it in memory elsewhere on the heap -- can be expensive.</span></span> <span data-ttu-id="2a812-106">이로 인해 .NET 가비지 수집기는 LOH(큰 개체 힙)에 큰 개체를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-106">Because of this, the .NET Garbage Collector places large objects on the large object heap (LOH).</span></span> <span data-ttu-id="2a812-107">이 항목에서는 큰 개체 힙에 대해 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-107">In this topic, we'll look at the large object heap in depth.</span></span> <span data-ttu-id="2a812-108">즉 개체가 큰 개체로 정규화하는 기능, 이러한 큰 개체를 수집하는 방법 및 큰 개체에서 이용하는 성능에 대한 함축적 유형에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-108">We'll discuss what qualifies an object as a large object, how these large objects are collected, and what kind of performance implications large objects impose.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a812-109">이 항목에서는 Windows 시스템에서만 실행되는 .NET Framework 및 .NET Core의 큰 개체 힙에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-109">This topic discusses the large object heap in the .NET Framework and .NET Core running on Windows systems only.</span></span> <span data-ttu-id="2a812-110">다른 플랫폼의 .NET 구현에서 실행되는 LOH는 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-110">It does not cover the LOH running on .NET implementations on other platforms.</span></span>

## <a name="how-an-object-ends-up-on-the-large-object-heap-and-how-gc-handles-them"></a><span data-ttu-id="2a812-111">개체가 큰 개체 힙에서 종료하는 방법 및 GC에서 처리하는 방법</span><span class="sxs-lookup"><span data-stu-id="2a812-111">How an object ends up on the large object heap and how GC handles them</span></span>

<span data-ttu-id="2a812-112">개체는 85,000바이트 이상이면 큰 개체로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-112">If an object is greater than or equal to 85,000 bytes, it’s considered a large object.</span></span> <span data-ttu-id="2a812-113">이 숫자는 성능 튜닝으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-113">This number was determined by performance tuning.</span></span> <span data-ttu-id="2a812-114">개체 할당 요청이 85,000바이트 이상이면 런타임에서 이를 큰 개체 힙에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-114">When an object allocation request is for 85,000 or more bytes, the runtime allocates it on the large object heap.</span></span>

<span data-ttu-id="2a812-115">이 의미를 이해하려면 .NET GC에 대한 몇 가지 기본 사항을 검토하는 것이 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-115">To understand what this means, it's useful to examine some fundamentals about the .NET GC.</span></span>

<span data-ttu-id="2a812-116">.NET 가비지 수집기는 세대 수집기입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-116">The .NET Garbage Collector is a generational collector.</span></span> <span data-ttu-id="2a812-117">세 개의 세대, 즉 0세대, 1세대 및 2세대가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-117">It has three generations: generation 0, generation 1, and generation 2.</span></span> <span data-ttu-id="2a812-118">세 개의 세대가 있는 이유는 잘 조정된 응용 프로그램에서 대부분의 개체가 0세대에서 소멸된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-118">The reason for having 3 generations is that, in a well-tuned app, most objects die in gen0.</span></span> <span data-ttu-id="2a812-119">예를 들어 서버 응용 프로그램에서는 요청이 완료되면 각 요청과 관련된 할당이 소멸되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-119">For example, in a server app, the allocations associated with each request should die after the request is finished.</span></span> <span data-ttu-id="2a812-120">진행 중인 할당 요청은 1세대가 되고 여기서 소멸됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-120">The in-flight allocation requests will make it into gen1 and die there.</span></span> <span data-ttu-id="2a812-121">기본적으로 1세대는 최근에 생성된 개체 영역과 수명이 긴 개체 영역 간의 버퍼 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-121">Essentially, gen1 acts as a buffer between young object areas and long-lived object areas.</span></span>

<span data-ttu-id="2a812-122">작은 개체는 항상 0세대에 할당되며 수명에 따라 1세대 또는 2세대로 승격될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-122">Small objects are always allocated in generation 0 and, depending on their lifetime, may be promoted to generation 1 or generation2.</span></span> <span data-ttu-id="2a812-123">큰 개체는 항상 2세대에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-123">Large objects are always allocated in generation 2.</span></span>

<span data-ttu-id="2a812-124">큰 개체는 2세대 수집 동안에만 수집되므로 2세대에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-124">Large objects belong to generation 2 because they are collected only during a generation 2 collection.</span></span> <span data-ttu-id="2a812-125">특정 세대가 수집되면 그 이전 세대도 모두 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-125">When a generation is collected, all its younger generation(s) are also collected.</span></span> <span data-ttu-id="2a812-126">예를 들어 1세대 GC가 수행되면 0세대와 1세대가 모두 수집되고,</span><span class="sxs-lookup"><span data-stu-id="2a812-126">For example, when a generation 1 GC happens, both generation 1 and 0 are collected.</span></span> <span data-ttu-id="2a812-127">2세대 GC가 수행되면 전체 힙이 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-127">And when a generation 2 GC happens, the whole heap is collected.</span></span> <span data-ttu-id="2a812-128">이러한 이유로 2세대 GC는 *전체 GC*라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-128">For this reason, a generation 2 GC is also called a *full GC*.</span></span> <span data-ttu-id="2a812-129">이 문서에서는 전체 GC 대신 2세대 GC를 언급하지만 용어는 서로 바꿔 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-129">This article refers to generation 2 GC instead of full GC, but the terms are interchangeable.</span></span>

<span data-ttu-id="2a812-130">세대는 GC 힙의 논리적 뷰를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-130">Generations provide a logical view of the GC heap.</span></span> <span data-ttu-id="2a812-131">실제로 개체는 관리되는 힙 세그먼트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-131">Physically, objects live in managed heap segments.</span></span> <span data-ttu-id="2a812-132">*관리되는 힙 세그먼트*는 GC에서 관리 코드 대신 [VirtualAlloc 함수](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx)를 호출하여 OS로부터 예약하는 메모리 청크입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-132">A *managed heap segment* is a chunk of memory that the GC reserves from the OS by calling the [VirtualAlloc function](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) on behalf of managed code.</span></span> <span data-ttu-id="2a812-133">CLR이 로드되면 GC에서 작은 개체(SOH 또는 작은 개체 힙)와 큰 개체(큰 개체 힙)에 대해 하나씩 두 개의 초기 힙 세그먼트를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-133">When the CLR is loaded, the GC allocates two initial heap segments: one for small objects (the Small Object Heap, or SOH), and one for large objects (the Large Object Heap).</span></span>

<span data-ttu-id="2a812-134">그런 다음, 이러한 관리되는 힙 세그먼트에 관리되는 개체를 배치하여 할당 요청이 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-134">The allocation requests are then satisfied by putting managed objects on these managed heap segments.</span></span> <span data-ttu-id="2a812-135">개체가 85,000바이트보다 작으면 SOH용 세그먼트에 배치되며, 그렇지 않으면 LOH 세그먼트에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-135">If the object is less than 85,000 bytes, it is put on the segment for the SOH; otherwise, it is put on an LOH segment.</span></span> <span data-ttu-id="2a812-136">세그먼트에 더 많은 개체가 할당됨에 따라 세그먼트가 더 작은 청크로 커밋됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-136">Segments are committed (in smaller chunks) as more and more objects are allocated onto them.</span></span>
<span data-ttu-id="2a812-137">SOH의 경우 GC에 남아 있는 개체는 다음 세대로 승격됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-137">For the SOH, objects that survive a GC are promoted to the next generation.</span></span> <span data-ttu-id="2a812-138">0세대 수집에서 남아 있는 개체는 이제 1세대 개체로 간주되는 방식 등으로 승격됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-138">Objects that survive a generation 0 collection are now considered generation 1 objects, and so on.</span></span> <span data-ttu-id="2a812-139">그러나 가장 오래된 세대에 남아 있는 개체는 여전히 가장 오래된 세대로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-139">However, objects that survive the oldest generation are still considered to be in the oldest generation.</span></span> <span data-ttu-id="2a812-140">즉 2세대에 남아 있는 개체는 2세대 개체가 되고, LOH에 남아 있는 개체는 LOH 개체가 됩니다(2세대와 함께 수집됨).</span><span class="sxs-lookup"><span data-stu-id="2a812-140">In other words, survivors from generation 2 are generation 2 objects; and survivors from the LOH are LOH objects (which are collected with gen2).</span></span> 

<span data-ttu-id="2a812-141">사용자 코드에서는 0세대(작은 개체) 또는 LOH(큰 개체)만 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-141">User code can only allocate in generation 0 (small objects) or the LOH (large objects).</span></span> <span data-ttu-id="2a812-142">GC만이 0세대에 남아 있는 개체를 승격하여 1세대에, 1세대와 2세대에 남아 있는 개체를 승격하여 2세대에 "할당"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-142">Only the GC can “allocate” objects in generation 1 (by promoting survivors from generation 0) and generation 2 (by promoting survivors from generations 1 and 2).</span></span>

<span data-ttu-id="2a812-143">가비지 수집이 트리거되면 GC에서 남아 있는 개체를 모두 추적하여 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-143">When a garbage collection is triggered, the GC traces through the live objects and compacts them.</span></span> <span data-ttu-id="2a812-144">그러나 압축하는 데 비용이 많이 들므로 GC는 LOH를 *정리*합니다. 이 경우 나중에 큰 개체 할당 요청을 충족하는 데 다시 사용할 수 있는 소멸된 개체에서 사용 가능한 개체 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-144">But because compaction is expensive, the GC *sweeps* the LOH; it makes a free list out of dead objects that can be reused later to satisfy large object allocation requests.</span></span> <span data-ttu-id="2a812-145">인접한 소멸된 개체는 하나의 사용 가능한 개체가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-145">Adjacent dead objects are made into one free object.</span></span>

<span data-ttu-id="2a812-146">.NET Core 및 .NET Framework(.NET Framework 4.5.1 이상)에는 사용자가 다음 번의 전체 GC 차단 중에 LOH를 압축해야 한다고 지정할 수 있는 <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?displayProperty="fullname"> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-146">.NET Core and .NET Framework (starting with .NET Framework 4.5.1) include the <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?displayProperty="fullname"> property that allows users to specify that the LOH should be compacted during the next full blocking GC.</span></span> <span data-ttu-id="2a812-147">그리고 앞으로는 .NET에서 LOH를 자동으로 압축하도록 결정할 수 있을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-147">And in the future, .NET may decide to compact the LOH automatically.</span></span> <span data-ttu-id="2a812-148">즉, 큰 개체를 할당하고 이동하지 못하도록 하려면 해당 개체를 고정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-148">This means that, if you allocate large objects and want to make sure that they don’t move, you should still pin them.</span></span>

<span data-ttu-id="2a812-149">그림 1에서는 GC에서 `Obj1`과 `Obj3`이 소멸된 첫 번째 0세대 GC 이후에 1세대를 형성하고, `Obj2`와 `Obj5`가 소멸된 첫 번째 1세대 이후에 2세대를 형성하는 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-149">Figure 1 illustrates a scenario where the GC forms generation 1 after the first generation 0 GC where `Obj1` and `Obj3` are dead, and it forms generation 2 after the first generation 1 GC where `Obj2` and `Obj5` are dead.</span></span> <span data-ttu-id="2a812-150">이 그림과 다음 그림은 설명을 위한 것입니다. 여기에는 힙에서 발생하는 작업을 더 잘 보여 주기 위해 매우 적은 수의 개체가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-150">Note that this and the following figures are only for illustration purposes; they contain very few objects to better show what happens on the heap.</span></span> <span data-ttu-id="2a812-151">실제로 더 많은 개체가 일반적으로 GC에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-151">In reality, many more objects are typically involved in a GC.</span></span>

![그림 1: 0세대 GC 및 1세대 GC](media/loh/loh-figure-1.jpg)   
<span data-ttu-id="2a812-153">그림 1: 0세대 및 1세대 GC</span><span class="sxs-lookup"><span data-stu-id="2a812-153">Figure 1: A generation 0 and a generation 1 GC.</span></span>

<span data-ttu-id="2a812-154">그림 2에서는 `Obj1`과 `Obj2`가 소멸되었음을 확인한 2세대 GC 이후에 GC가 `Obj1`과 `Obj2`에서 점유하는 데 사용한 메모리에서 연속적인 사용 가능한 공간을 형성하여 `Obj4`에 대한 할당 요청을 충족하는 데 사용했음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-154">Figure 2 shows that after a generation 2 GC which saw that `Obj1` and `Obj2` are dead, the GC forms contiguous free space out of memory that used to be occupied by `Obj1` and `Obj2`, which then was used to satisfy an allocation request for `Obj4`.</span></span> <span data-ttu-id="2a812-155">마지막 개체인 `Obj3` 뒤에서 세그먼트 끝까지의 공간도 할당 요청을 충족하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-155">The space after the last object, `Obj3`, to end of the segment can also be used to satisfy allocation requests.</span></span>
 
![그림 2: 2세대 GC 이후](media/loh/loh-figure-2.jpg)  
<span data-ttu-id="2a812-157">그림 2: 2세대 GC 이후</span><span class="sxs-lookup"><span data-stu-id="2a812-157">Figure 2: After a generation 2 GC</span></span>

<span data-ttu-id="2a812-158">큰 개체 할당 요청을 수용할 사용 가능한 공간이 부족한 경우 GC는 먼저 OS에서 더 많은 세그먼트를 획득하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-158">If there isn't enough free space to accommodate the large object allocation requests, the GC first attempts to acquire more segments from the OS.</span></span> <span data-ttu-id="2a812-159">이 작업이 실패하면 일부 공간을 확보하기 위해 2세대 GC가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-159">If that fails, it triggers a generation 2 GC in the hope of freeing up some space.</span></span>

<span data-ttu-id="2a812-160">1세대 또는 2세대 GC 동안 가비지 수집기는 [VirtualFree 함수](https://msdn.microsoft.com/library/windows/desktop/aa366892(v=vs.85).aspx)를 호출하여 남아 있는 개체가 없는 세그먼트를 OS에 다시 릴리스합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-160">During a generation 1 or generation 2 GC, the garbage collector releases segments that have no live objects on them back to the OS by calling the [VirtualFree function](https://msdn.microsoft.com/library/windows/desktop/aa366892(v=vs.85).aspx).</span></span> <span data-ttu-id="2a812-161">마지막 남아 있는 개체 뒤에서 세그먼트 끝까지의 공간은 커밋 해제됩니다(응용 프로그램이 즉시 할당되기 때문에 가비지 수집기에서 커밋된 일부 개체를 유지하는 0세대/1세대가 남아 있는 임시 세그먼트는 제외).</span><span class="sxs-lookup"><span data-stu-id="2a812-161">Space after the last live object to the end of the segment is decommitted (except on the ephemeral segment where gen0/gen1 live, where the garbage collector does keep some committed because your application will be allocating in it right away).</span></span> <span data-ttu-id="2a812-162">그리고 사용 가능한 공간은 다시 설정되어도 커밋된 상태로 유지되므로 OS에서 데이터를 디스크에 다시 쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-162">And the free spaces remain committed though they are reset, meaning that the OS doesn’t need to write data in them back to disk.</span></span>

<span data-ttu-id="2a812-163">LOH는 2세대 GC 동안에만 수집되므로 LOH 세그먼트는 이러한 GC 동안에만 해제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-163">Since the LOH is only collected during generation 2 GCs, the LOH segment can only be freed during such a GC.</span></span> <span data-ttu-id="2a812-164">그림 3에서는 가비지 수집기에서 한 세그먼트(세그먼트 2)를 OS로 다시 릴리스하고, 나머지 세그먼트에 대해 더 많은 공간을 커밋 해제하는 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-164">Figure 3 illustrates a scenario where the garbage collector releases one segment (segment 2) back to the OS and decommits more space on the remaining segments.</span></span> <span data-ttu-id="2a812-165">큰 개체 할당 요청을 충족하기 위해 세그먼트 끝에 있는 커밋 해제된 공간을 사용해야 하는 경우 메모리를 다시 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-165">If it needs to use the decommitted space at the end of the segment to satisfy large object allocation requests, it commits the memory again.</span></span> <span data-ttu-id="2a812-166">커밋/커밋 해제에 대한 설명은 [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx)에 대한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a812-166">(For an explanation of commit/decommit, see the documentation for [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx).</span></span>
 
![그림 3: 2세대 GC 이후의 LOH](media/loh/loh-figure-3.jpg)  
<span data-ttu-id="2a812-168">그림 3: 2세대 GC 이후의 LOH</span><span class="sxs-lookup"><span data-stu-id="2a812-168">Figure 3: The LOH after a generation 2 GC</span></span>

## <a name="when-is-a-large-object-collected"></a><span data-ttu-id="2a812-169">큰 개체가 수집되는 경우</span><span class="sxs-lookup"><span data-stu-id="2a812-169">When is a large object collected?</span></span>

<span data-ttu-id="2a812-170">일반적으로 다음 3가지 조건 중 하나가 발생하면 GC가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-170">In general, a GC occurs when one of the following following 3 conditions happens:</span></span>

- <span data-ttu-id="2a812-171">할당이 0세대 또는 큰 개체 임계값을 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-171">Allocation exceeds the generation 0 or large object threshold.</span></span>

   <span data-ttu-id="2a812-172">임계값은 세대의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-172">The threshold is a property of a generation.</span></span> <span data-ttu-id="2a812-173">세대에 대한 임계값은 가비지 수집기에서 개체를 할당할 때 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-173">A threshold for a generation is set when the garbage collector allocates objects into it.</span></span> <span data-ttu-id="2a812-174">임계값이 초과되면 해당 세대에서 GC가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-174">When the threshold is exceeded, a GC is triggered on that generation.</span></span> <span data-ttu-id="2a812-175">작은 개체 또는 큰 개체를 할당할 때 0세대 및 LOH의 임계값을 각각 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-175">When you allocate small or large objects, you consume generation 0 and the LOH’s thresholds, respectively.</span></span> <span data-ttu-id="2a812-176">가비지 수집기에서 1세대와 2세대에 할당하는 경우 해당 임계값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-176">When the garbage collector allocates into generation 1 and 2, it consumes their thresholds.</span></span> <span data-ttu-id="2a812-177">이러한 임계값은 프로그램이 실행될 때 동적으로 튜닝됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-177">These thresholds are dynamically tuned as the program runs.</span></span>

   <span data-ttu-id="2a812-178">이는 일반적인 경우입니다. 대부분의 GC는 관리되는 힙에 대한 할당으로 인해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-178">This is the typical case; most GCs happen because of allocations on the managed heap.</span></span>

- <span data-ttu-id="2a812-179"><xref:System.GC.Collect%2A?displayProperty=nameWithType> 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-179">The <xref:System.GC.Collect%2A?displayProperty=nameWithType> method is called.</span></span>

   <span data-ttu-id="2a812-180">매개 변수가 없는 <xref:System.GC.Collect?displayProperty=nameWithType> 메서드가 호출되거나 다른 오버로드에서 인수로 <xref:System.GC.MaxGeneration?displayProperty=nameWithType>을 전달하면 LOH가 나머지 관리되는 힙과 함께 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-180">If the parameterless <xref:System.GC.Collect?displayProperty=nameWithType> method is called or another overload is passed <xref:System.GC.MaxGeneration?displayProperty=nameWithType> as an argument, the LOH is collected along with the rest of the managed heap.</span></span>

- <span data-ttu-id="2a812-181">시스템 메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-181">The system is in low memory situation.</span></span>

   <span data-ttu-id="2a812-182">이는 가비지 수집기에서 OS로부터 높은 메모리 알림을 받을 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-182">This occurs when the garbage collector receives a high memory notification from the OS.</span></span> <span data-ttu-id="2a812-183">가비지 수집기에서 2세대 GC 작업이 생산적이라고 인식하면 해당 GC를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-183">If the garbage collector thinks that doing a generation 2 GC will be productive, it triggers one.</span></span>

## <a name="loh-performance-implications"></a><span data-ttu-id="2a812-184">LOH 성능의 함축적 의미</span><span class="sxs-lookup"><span data-stu-id="2a812-184">LOH Performance Implications</span></span>

<span data-ttu-id="2a812-185">큰 개체 힙에 대한 할당은 다음과 같은 방식으로 성능에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-185">Allocations on the large object heap impact performance in the following ways.</span></span>

- <span data-ttu-id="2a812-186">할당 비용</span><span class="sxs-lookup"><span data-stu-id="2a812-186">Allocation cost.</span></span>

   <span data-ttu-id="2a812-187">CLR은 제공하는 모든 새 개체에 대한 메모리를 지울 수 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-187">The CLR makes the guarantee that the memory for every new object it gives out is cleared.</span></span> <span data-ttu-id="2a812-188">즉, 큰 개체의 할당 비용은 GC를 트리거하지 않는 한 메모리 지우기를 통해 완전히 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-188">This means the allocation cost of a large object is completely dominated by memory clearing (unless it triggers a GC).</span></span> <span data-ttu-id="2a812-189">1바이트를 비우는 데 2회의 주기가 걸리는 경우 가장 작은 큰 개체를 지우는 데 170,000회의 주기가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-189">If it takes 2 cycles to clear one byte, it takes 170,000 cycles to clear the smallest large object.</span></span> <span data-ttu-id="2a812-190">2GHz 컴퓨터에서 16MB 개체의 메모리를 지우는 데 약 16ms가 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-190">Clearing the memmory of a 16MB object on a 2GHz machine takes approximately 16ms.</span></span> <span data-ttu-id="2a812-191">이는 다소 큰 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-191">That's a rather large cost.</span></span>

- <span data-ttu-id="2a812-192">수집 비용</span><span class="sxs-lookup"><span data-stu-id="2a812-192">Collection cost.</span></span>

   <span data-ttu-id="2a812-193">LOH와 2세대가 함께 수집되므로 어느 하나의 임계값이 초과되면 2세대 수집이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-193">Because the LOH and generation 2 are collected together, if either one's threshold is exceeded, a generation 2 collection is triggered.</span></span> <span data-ttu-id="2a812-194">LOH로 인해 2세대 수집이 트리거되면 GC 이후에 2세대가 반드시 더 작아질 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-194">If a generation 2 collection is triggered because of the LOH, generation 2 won't necessarily be much smaller after the GC.</span></span> <span data-ttu-id="2a812-195">2세대에 대한 데이터가 많지 않으면 이로 인한 영향을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-195">If there's not much data on generation 2, this has minimal impact.</span></span> <span data-ttu-id="2a812-196">그러나 2세대가 큰 경우 2세대 GC가 많이 트리거되면 성능 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-196">But if generation 2 is large, it can cause performance problems if many generation 2 GCs are triggered.</span></span> <span data-ttu-id="2a812-197">큰 개체가 아주 일시적으로 많이 할당되고 SOH가 큰 경우 GC를 수행하는 데 너무 많은 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-197">If many large objects are allocated on a very temporary basis and you have a large SOH, you could be spending too much time doing GCs.</span></span> <span data-ttu-id="2a812-198">또한 할당 비용은 정말로 큰 개체를 계속 할당하고 내보내는 경우 크게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-198">In addition, the allocation cost can really add up if you keep allocating and letting go of really large objects.</span></span>

- <span data-ttu-id="2a812-199">참조 형식이 있는 배열 요소</span><span class="sxs-lookup"><span data-stu-id="2a812-199">Array elements with reference types.</span></span>

   <span data-ttu-id="2a812-200">LOH의 매우 큰 개체는 일반적으로 배열이며, 실제로 큰 인스턴스 개체는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-200">Very large objects on the LOH are usually arrays (it's very rare to have an instance object that's really large).</span></span> <span data-ttu-id="2a812-201">참조가 많은 배열 요소인 경우 참조가 많지 않은 요소에 존재하지 않는 비용이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-201">If the elements of an array are reference-rich, it incurs a cost that is not present if the elements are not reference-rich.</span></span> <span data-ttu-id="2a812-202">참조가 없는 요소인 경우 배열을 가비지 수집기에서 배열을 거칠 필요가 전혀 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-202">If the element doesn’t contain any references, the garbage collector doesn’t need to go through the array at all.</span></span> <span data-ttu-id="2a812-203">예를 들어 배열을 사용하여 노드를 이진 트리에 저장하는 경우, 이를 구현하는 한 가지 방법은 다음과 같이 실제 노드를 통해 오른쪽 노드와 왼쪽 노드를 참조하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-203">For example, if you use an array to store nodes in a binary tree, one way to implement it is to refer to a node’s right and left node by the actual nodes:</span></span>

   ```csharp
   class Node
   {
      Data d;
      Node left;
      Node right;
   };

   Node[] binary_tr = new Node [num_nodes];
   ```

   <span data-ttu-id="2a812-204">`num_nodes`가 큰 경우 가비지 수집기는 요소당 둘 이상의 참조를 거쳐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-204">If `num_nodes` is large, the garbage collector needs to go through at least two references per element.</span></span> <span data-ttu-id="2a812-205">또 다른 방법은 다음과 같이 오른쪽 노드와 왼쪽 노드의 인덱스를 저장하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-205">An alternative approach is to store the index of the right and the left nodes:</span></span>

   ```csharp
   class Node
   {
      Data d;
      uint left_index;
      uint right_index;
   } ;
   ```

   <span data-ttu-id="2a812-206">왼쪽 노드의 데이터를 `left.d`로 참조하는 대신 `binary_tr[left_index].d`로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-206">Instead of referring the left node’s data as `left.d`, you refer to it as `binary_tr[left_index].d`.</span></span> <span data-ttu-id="2a812-207">그리고 가비지 수집기에서는 왼쪽 노드와 오른쪽 노드에 대한 참조를 확인할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-207">And the garbage collector doesn’t need to look at any references for the left and right node.</span></span>

<span data-ttu-id="2a812-208">세 가지 요소 중 처음 두 가지는 일반적으로 세 번째 요소보다 더 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-208">Out of the three factors, the first two are usually more significant than the third.</span></span> <span data-ttu-id="2a812-209">이에 따라 임시 개체를 할당하는 대신 다시 사용하는 큰 개체의 풀을 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-209">Because of this, we recommend that you allocate a pool of large objects that you reuse instead of allocating temporary ones.</span></span> 

## <a name="collecting-performance-data-for-the-loh"></a><span data-ttu-id="2a812-210">LOH에 대한 성능 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="2a812-210">Collecting performance data for the LOH</span></span>

<span data-ttu-id="2a812-211">특정 영역에 대한 성능 데이터를 수집하려면 다음 작업을 이미 완료했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-211">Before you collect performance data for a specific area, you should already have done the following:</span></span>

1. <span data-ttu-id="2a812-212">해당 영역을 검토했다는 증명 정보를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-212">Found evidence that you should be looking at this area.</span></span>

1. <span data-ttu-id="2a812-213">확인한 성능 문제를 설명할 수 있는 항목을 찾지 못한 채 알고 있는 다른 영역을 모두 소진했습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-213">Exhausted other areas that you know of without finding anything that could explain the performance problem you saw.</span></span>

<span data-ttu-id="2a812-214">메모리 및 CPU의 기본 사항에 대한 자세한 내용은 [문제를 파악한 후 해결 방법 찾기](https://blogs.msdn.microsoft.com/maoni/2006/09/01/understand-the-problem-before-you-try-to-find-a-solution/) 블로그를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a812-214">See the blog [Understand the problem before you try to find a solution](https://blogs.msdn.microsoft.com/maoni/2006/09/01/understand-the-problem-before-you-try-to-find-a-solution/) for more information on the fundamentals of memory and the CPU.</span></span>

<span data-ttu-id="2a812-215">LOH 성능에 대한 데이터를 수집하는 데 사용할 수 있는 도구는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-215">You can use the following tools to collect data on LOH performance:</span></span>

- [<span data-ttu-id="2a812-216">.NET CLR 메모리 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="2a812-216">.NET CLR memory performance counters</span></span>](#net-clr-memory-performance-counters)

- [<span data-ttu-id="2a812-217">ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="2a812-217">ETW events</span></span>](#etw-events)

- [<span data-ttu-id="2a812-218">디버거</span><span class="sxs-lookup"><span data-stu-id="2a812-218">A debugger</span></span>](#a-debugger)

### <a name="net-clr-memory-performance-counters"></a><span data-ttu-id="2a812-219">.NET CLR 메모리 성능 카운터</span><span class="sxs-lookup"><span data-stu-id="2a812-219">.NET CLR Memory Performance counters</span></span>

<span data-ttu-id="2a812-220">이러한 성능 카운터는 일반적으로 성능 문제를 조사하는 데 유용한 첫 번째 단계입니다(하지만 [ETW 이벤트](#etw) 사용이 권장됨).</span><span class="sxs-lookup"><span data-stu-id="2a812-220">These performance counters are usually a good first step in investigating performance issues (although we recommend that you use [ETW events](#etw)).</span></span> <span data-ttu-id="2a812-221">그림 4와 같이 원하는 카운터를 추가하여 성능 모니터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-221">You configure Performance Monitor by adding the counters that you want, as Figure 4 shows.</span></span> <span data-ttu-id="2a812-222">LOH와 관련된 카운터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-222">The ones that are relevant for the LOH are:</span></span>

- <span data-ttu-id="2a812-223">**2세대 수집 \#**</span><span class="sxs-lookup"><span data-stu-id="2a812-223">**\# Gen 2 Collections**</span></span>

   <span data-ttu-id="2a812-224">프로세스가 시작된 이후 수행된 2세대 GC 횟수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-224">Displays the number of times generation 2 GCs have occurred since the process started.</span></span> <span data-ttu-id="2a812-225">이 카운터는 2세대 수집(전체 가비지 수집이라고도 함)이 끝날 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-225">The counter is incremented at the end of a generation 2 collection (also called a full garbage collection).</span></span> <span data-ttu-id="2a812-226">이 카운터는 마지막으로 관찰된 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-226">This counter displays the last observed value.</span></span>

- <span data-ttu-id="2a812-227">**Large Object Heap size**</span><span class="sxs-lookup"><span data-stu-id="2a812-227">**Large Object Heap size**</span></span>

   <span data-ttu-id="2a812-228">사용 가능한 공간을 포함하여 LOH의 현재 크기(바이트)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-228">Displays the current size, in bytes, including free space, of the LOH.</span></span> <span data-ttu-id="2a812-229">이 카운터는 각 할당이 아니라 가비지 컬렉션이 끝날 때 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-229">This counter is updated at the end of a garbage collection, not at each allocation.</span></span>

<span data-ttu-id="2a812-230">성능 카운터를 확인하는 일반적인 방법은 성능 모니터(perfmon.exe)를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-230">A common way to look at performance counters is with Performance Monitor (perfmon.exe).</span></span> <span data-ttu-id="2a812-231">"카운터 추가" 명령을 사용하여 관심 있는 프로세스에 대해 원하는 카운터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-231">Use “Add Counters” to add the interesting counter for processes that you care about.</span></span> <span data-ttu-id="2a812-232">그림 4와 같이 성능 카운터 데이터를 로그 파일에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-232">You can save the performance counter data to a log file, as Figure 4 shows.</span></span>

![그림 4: 성능 카운터 추가](media/loh/perfcounter.png)    
<span data-ttu-id="2a812-234">그림 4: 2세대 GC 이후의 LOH</span><span class="sxs-lookup"><span data-stu-id="2a812-234">Figure 4: The LOH after a generation 2 GC</span></span>

<span data-ttu-id="2a812-235">또한 성능 카운터는 프로그래밍 방식으로 쿼리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-235">Performance counters can also be queried programmatically.</span></span> <span data-ttu-id="2a812-236">많은 사람들이 일상적인 테스트 프로세스의 일환으로 이러한 방식으로 성능 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-236">Many people collect them this way as part of their routine testing process.</span></span> <span data-ttu-id="2a812-237">정상적이지 않은 값이 있는 카운터가 검색되면 다른 방법을 사용하여 조사하는 데 유용한 더 자세한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-237">When they spot counters with values that are out of the ordinary, they use other means to get more detailed data to help with the investigation.</span></span>

> [!NOTE]
> <span data-ttu-id="2a812-238">ETW에서 훨씬 더 많은 정보를 제공하므로 성능 카운터 대신 ETW 이벤트를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-238">We recommend that you to use ETW events instead of performance counters, because ETW provides much richer information.</span></span>

### <a name="etw"></a><span data-ttu-id="2a812-239">ETW</span><span class="sxs-lookup"><span data-stu-id="2a812-239">ETW</span></span>

<span data-ttu-id="2a812-240">가비지 수집기는 힙에서 수행하는 작업과 그 이유를 파악하는 데 도움이 되는 다양한 ETW 이벤트 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-240">The garbage collector provides a rich set of ETW events to help you understand what the heap is doing and why.</span></span> <span data-ttu-id="2a812-241">다음 블로그 게시물에서는 ETW를 통해 GC 이벤트를 수집하고 파악하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-241">The following blog posts show how to collect and understand GC events with ETW:</span></span>

- [<span data-ttu-id="2a812-242">GC ETW 이벤트 - 1</span><span class="sxs-lookup"><span data-stu-id="2a812-242">GC ETW Events - 1 </span></span>](http://blogs.msdn.com/b/maoni/archive/2014/12/22/gc-etw-events.aspx)

- [<span data-ttu-id="2a812-243">GC ETW 이벤트 - 2</span><span class="sxs-lookup"><span data-stu-id="2a812-243">GC ETW Events - 2</span></span>](http://blogs.msdn.com/b/maoni/archive/2014/12/25/gc-etw-events-2.aspx)

- [<span data-ttu-id="2a812-244">GC ETW 이벤트 - 3</span><span class="sxs-lookup"><span data-stu-id="2a812-244">GC ETW Events - 3</span></span>](http://blogs.msdn.com/b/maoni/archive/2014/12/25/gc-etw-events-3.aspx) 

- [<span data-ttu-id="2a812-245">GC ETW 이벤트 - 4</span><span class="sxs-lookup"><span data-stu-id="2a812-245">GC ETW Events - 4</span></span>](http://blogs.msdn.com/b/maoni/archive/2014/12/30/gc-etw-events-4.aspx)

<span data-ttu-id="2a812-246">임시 LOH 할당으로 인해 발생된 과도한 2세대 GC를 확인하려면 GC에 대한 트리거 이유 열을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-246">To identify excessive generation 2 GCs caused by temporary LOH allocations, look at the Trigger Reason column for GCs.</span></span> <span data-ttu-id="2a812-247">임시 큰 개체만 할당하는 간단한 테스트의 경우 다음 [PerfView](https://www.microsoft.com/download/details.aspx?id=28567) 명령줄을 사용하여 ETW 이벤트에 대한 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-247">For a simple test that only allocates temporary large objects, you can collect information on ETW events with the following [PerfView](https://www.microsoft.com/download/details.aspx?id=28567) command line:</span></span>

```console
perfview /GCCollectOnly /AcceptEULA /nogui collect
```

<span data-ttu-id="2a812-248">결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-248">The result is something like this:</span></span>
 
![그림 5: PerfView를 사용하여 ETW 이벤트 검사](media/loh/perfview.png)  
<span data-ttu-id="2a812-250">그림 5: PerfView를 사용하여 표시된 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="2a812-250">Figure 5: ETW events shown using PerfView</span></span>

<span data-ttu-id="2a812-251">여기서 알 수 있듯이, 모든 GC는 2세대 GC이며 AllocLarge를 통해 모두 트리거됩니다. 즉, 큰 개체를 할당하면 이 GC가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-251">As you can see, all GCs are generation 2 GCs, and they are all triggered by AllocLarge, which means that allocating a large object triggered this GC.</span></span> <span data-ttu-id="2a812-252">**LOH 잔존율 %** 열이 1%라고 표시되므로 이러한 할당은 일시적입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-252">We know that these allocations are temporary because the **LOH Survival Rate %** column says 1%.</span></span>

<span data-ttu-id="2a812-253">이러한 큰 개체를 할당한 사람을 알려주는 추가 ETW 이벤트를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-253">You can collect additional ETW events that tell you who allocated these large objects.</span></span> <span data-ttu-id="2a812-254">다음과 같은 명령줄이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-254">The following command line:</span></span>

```console
perfview /GCOnly /AcceptEULA /nogui collect
```

<span data-ttu-id="2a812-255">이 명령은 대략 100,000개의 할당마다 실행되는 AllocationTick 이벤트를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-255">collects an AllocationTick event which is fired approximately every 100k worth of allocations.</span></span> <span data-ttu-id="2a812-256">즉, 큰 개체가 할당될 때마다 이벤트가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-256">In other words, an event is fired each time a large object is allocated.</span></span> <span data-ttu-id="2a812-257">큰 개체를 할당한 호출 스택을 보여 주는 GC 힙 할당 보기 중 하나를 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-257">You can then look at one of the GC Heap Alloc views which show you the callstacks that allocated large objects:</span></span>
 
![그림 6: GC 힙 할당 보기](media/loh/perfview2.png)  
<span data-ttu-id="2a812-259">그림 6: GC 힙 할당 보기</span><span class="sxs-lookup"><span data-stu-id="2a812-259">Figure 6: A GC Heap Alloc view</span></span>
 
<span data-ttu-id="2a812-260">여기서 알 수 있듯이, 이는 `Main` 메서드에서 큰 개체를 할당하는 매우 간단한 테스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-260">As you can see, this is a very simple test that just allocates large objects from its `Main` method.</span></span>

### <a name="a-debugger"></a><span data-ttu-id="2a812-261">디버거</span><span class="sxs-lookup"><span data-stu-id="2a812-261">A debugger</span></span>

<span data-ttu-id="2a812-262">메모리 덤프만 있고 실제로 LOH에 있는 개체를 확인해야 하는 경우 .NET에서 제공하는 [SoS 디버거 확장](http://msdn2.microsoft.com/ms404370.aspx)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-262">If all you have is a memory dump and you need to look at what objects are actually on the LOH, you can use the [SoS debugger extension](http://msdn2.microsoft.com/ms404370.aspx) provided by .NET.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a812-263">이 섹션에서 설명하는 디버깅 명령은 [Windows 디버거](http://www.microsoft.com/whdc/devtools/debugging/default.mspx)에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-263">The debugging commands mentioned in this section are applicable to the [Windows Debuggers](http://www.microsoft.com/whdc/devtools/debugging/default.mspx).</span></span>

<span data-ttu-id="2a812-264">다음은 LOH 분석에서 나오는 출력 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-264">The following shows sample output from analyzing the LOH:</span></span>

```
0:003> .loadby sos mscorwks
0:003> !eeheap -gc
Number of GC Heaps: 1
generation 0 starts at 0x013e35ec
sdgeneration 1 starts at 0x013e1b6c
generation 2 starts at 0x013e1000
ephemeral segment allocation context: none
segment   begin allocated     size
0018f2d0 790d5588 790f4b38 0x0001f5b0(128432)
013e0000 013e1000 013e35f8 0x000025f8(9720)
Large object heap starts at 0x023e1000
segment   begin allocated     size
023e0000 023e1000 033db630 0x00ffa630(16754224)
033e0000 033e1000 043cdf98 0x00fecf98(16699288)
043e0000 043e1000 05368b58 0x00f87b58(16284504)
Total Size 0x2f90cc8(49876168)
------------------------------
GC Heap Size 0x2f90cc8(49876168)
0:003> !dumpheap -stat 023e1000 033db630
total 133 objects
Statistics:
MT   Count   TotalSize Class Name
001521d0       66     2081792     Free
7912273c       63     6663696 System.Byte[]
7912254c       4     8008736 System.Object[]
Total 133 objects
```

<span data-ttu-id="2a812-265">LOH 힙 크기는 (16,754,224 + 16,699,288 + 16,284,504) = 49,738,016바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-265">The LOH heap size is (16,754,224 + 16,699,288 + 16,284,504) = 49,738,016 bytes.</span></span> <span data-ttu-id="2a812-266">023e1000과 033db630 주소 사이에서 <xref:System.Object?displayProperty=fullName> 개체의 배열에서 8,008,736바이트, <xref:System.Byte?displayProperty=nameWithType> 개체의 배열에서 6,663,696바이트 및 사용 가능한 공간으로 2,081,792바이트를 차지합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-266">Between addresses 023e1000 and 033db630, 8,008,736 bytes are occupied by an array of <xref:System.Object?displayProperty=fullName> objects, 6,663,696 bytes are occupied by an array of <xref:System.Byte?displayProperty=nameWithType>  objects, and 2,081,792 bytes are occupied by free space.</span></span>

<span data-ttu-id="2a812-267">경우에 따라 디버거에서 LOH의 전체 크기가 85,000바이트 미만임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-267">Sometimes, the debugger shows that the total size of the LOH is less than 85,000 bytes.</span></span> <span data-ttu-id="2a812-268">이는 런타임 자체에서 LOH를 사용하여 큰 개체보다 작은 일부 개체를 할당하기 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-268">This happens because the runtime itself uses the LOH to allocate some objects that are smaller than a large object.</span></span>

<span data-ttu-id="2a812-269">LOH는 압축되지 않으므로 LOH가 조각화의 원인으로 간주되는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-269">Because the LOH is not compacted, sometimes the LOH is thoought to be the source of fragmentation.</span></span> <span data-ttu-id="2a812-270">조각화의 의미는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-270">Fragmentation means:</span></span>

- <span data-ttu-id="2a812-271">관리되는 힙의 조각화 - 관리되는 개체 간에 사용 가능한 공간 크기로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-271">Fragmentation of the managed heap, which is indicated by the amount of free space between managed objects.</span></span> <span data-ttu-id="2a812-272">SoS에서 `!dumpheap –type Free` 명령은 관리되는 개체 간에 사용 가능한 공간 크기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-272">In SoS, the `!dumpheap –type Free` command displays the amount of free space between managed objects.</span></span>

- <span data-ttu-id="2a812-273">VM(가상 메모리) 주소 공간의 조각화 - `MEM_FREE`로 표시되는 메모리입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-273">Fragmentation of the virtual memory (VM) address space, which is the memory marked as `MEM_FREE`.</span></span> <span data-ttu-id="2a812-274">windbg에서 다양한 디버거 명령을 사용하여 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-274">You can get it by using various debugger commands in windbg.</span></span>

   <span data-ttu-id="2a812-275">다음 예제에서는 VM 공간의 조각화를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-275">The following example shows fragmentation in the VM space:</span></span>

   ```
   0:000> !address
   00000000 : 00000000 - 00010000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   00010000 : 00010000 - 00002000
   Type     00020000 MEM_PRIVATE
   Protect 00000004 PAGE_READWRITE
   State   00001000 MEM_COMMIT
   Usage   RegionUsageEnvironmentBlock
   00012000 : 00012000 - 0000e000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   … [omitted]
   -------------------- Usage SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Pct(Busy)   Usage
   701000 (   7172) : 00.34%   20.69%   : RegionUsageIsVAD
   7de15000 ( 2062420) : 98.35%   00.00%   : RegionUsageFree
   1452000 (   20808) : 00.99%   60.02%   : RegionUsageImage
   300000 (   3072) : 00.15%   08.86%   : RegionUsageStack
   3000 (     12) : 00.00%   00.03%   : RegionUsageTeb
   381000 (   3588) : 00.17%   10.35%   : RegionUsageHeap
   0 (       0) : 00.00%   00.00%   : RegionUsagePageHeap
   1000 (       4) : 00.00%   00.01%   : RegionUsagePeb
   1000 (       4) : 00.00%   00.01%   : RegionUsageProcessParametrs
   2000 (       8) : 00.00%   00.02%   : RegionUsageEnvironmentBlock
   Tot: 7fff0000 (2097088 KB) Busy: 021db000 (34668 KB)

   -------------------- Type SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   7de15000 ( 2062420) : 98.35%   : <free>
   1452000 (   20808) : 00.99%   : MEM_IMAGE
   69f000 (   6780) : 00.32%   : MEM_MAPPED
   6ea000 (   7080) : 00.34%   : MEM_PRIVATE

   -------------------- State SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   1a58000 (   26976) : 01.29%   : MEM_COMMIT
   7de15000 ( 2062420) : 98.35%   : MEM_FREE
   783000 (   7692) : 00.37%   : MEM_RESERVE

   Largest free region: Base 01432000 - Size 707ee000 (1843128 KB)
   ```

<span data-ttu-id="2a812-276">가비지 수집기에서 자주 OS로부터 새 관리되는 힙 세그먼트를 얻고 빈 세그먼트를 OS로 릴리스하는 데 필요한 임시 큰 개체로 인해 가상 메모리 조각화가 발생하는 경우가 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-276">It’s more common to see VM fragmentation caused by temporary large objects that require the garbage collector to frequently acquire new managed heap segments from the OS and to release empty ones back to the OS.</span></span>

<span data-ttu-id="2a812-277">LOH로 인해 VM 조각화가 발생하는지 확인하려면 [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) 및 [VirtualFree](https://msdn.microsoft.com/library/windows/desktop/aa366892(v=vs.85).aspx)에 중단점을 설정하고 이를 호출하는 사람을 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-277">To verify whether the LOH is causing VM fragmentation, you can set a breakpoint on [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) and [VirtualFree](https://msdn.microsoft.com/library/windows/desktop/aa366892(v=vs.85).aspx) to see who call them.</span></span> <span data-ttu-id="2a812-278">예를 들어 OS에서 8MB보다 큰 가상 메모리 청크를 할당하려고 한 사람을 확인하려면 다음과 같이 중단점을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-278">For example, to see who tried to allocate virtual memory chunks larger than 8MBB from the OS, you can set a breakpoint like this:</span></span>

```console
bp kernel32!virtualalloc "j (dwo(@esp+8)>800000) 'kb';'g'"
```

<span data-ttu-id="2a812-279">이 명령은 디버거를 시작하고 8MB(0x800000)보다 큰 할당 크기로 인해 [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx)가 호출되는 경우에만 호출 스택을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-279">This command breaks into the debugger and shows the callstack only if [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) is called with an allocation size greater than 8MB (0x800000).</span></span>

<span data-ttu-id="2a812-280">CLR 2.0에는 크고 작은 개체 힙에 포함되는 세그먼트를 자주 획득하고 릴리스하는 시나리오에 유용할 수 있는 *VM Hoarding*(VM 비축)이라는 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-280">CLR 2.0 added a feature called *VM Hoarding* that can be useful for scenarious where segments (including on the large and small object heaps) are frequently acquired and released.</span></span> <span data-ttu-id="2a812-281">VM Hoarding을 지정하려면 호스팅 API를 통해 `STARTUP_HOARD_GC_VM`이라는 시작 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-281">To specify VM Hoarding, you specify a startup flag called `STARTUP_HOARD_GC_VM` via the hosting API.</span></span> <span data-ttu-id="2a812-282">CLR은 빈 세그먼트를 OS로 다시 릴리스하는 대신, 이러한 세그먼트의 메모리를 커밋 해제하고 대기 목록에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-282">Instead of releasing empty segments back to the OS, the CLR decommits the memory on these segments and puts them on a standby list.</span></span> <span data-ttu-id="2a812-283">(CLR은 너무 큰 세그먼트에 대해 이 작업을 수행하지 않습니다.) CLR은 나중에 새 세그먼트 요청을 충족하는 데 이러한 세그먼트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-283">(Note that the CLR doesn't do this for segments that are too large.) The CLR later uses those segments to satisfy new segment requests.</span></span> <span data-ttu-id="2a812-284">다음에 응용 프로그램에 새 세그먼트가 필요할 때 CLR에서 충분히 큰 세크먼트를 찾을 수 있으면 이 대기 목록에 있는 세그먼트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-284">The next time that your app needs a new segment, the CLR uses one from this standby list if it can find one that’s big enough.</span></span>

<span data-ttu-id="2a812-285">또한 VM Hoarding은 메모리 부족 예외를 방지하기 위해 이미 획득한 세그먼트를 유지하려는 응용 프로그램(예 시스템에서 실행되는 주요 응용 프로그램인 일부 서버 응용 프로그램)에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-285">VM hoarding is also useful for applications that want to hold onto the segments that they already acquired, such as some server apps that are the dominant apps running on the system, to avoid out of memory exceptions.</span></span>

<span data-ttu-id="2a812-286">이 기능을 사용할 때 응용 프로그램을 주의 깊게 테스트하여 응용 프로그램에서 메모리 사용을 매우 안정적으로 유지하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a812-286">We strongly recommend that you carefully test your application when you use this feature to ensure your application has fairly stable memory usage.</span></span>
<span data-ttu-id="2a812-287">bp kernel32!virtualalloc "j (dwo(@esp+8)>800000) 'kb';'g'"</span><span class="sxs-lookup"><span data-stu-id="2a812-287">bp kernel32!virtualalloc "j (dwo(@esp+8)>800000) 'kb';'g'"</span></span>
```

This command breaks into the debugger and shows the callstack only if [VirtualAlloc](https://msdn.microsoft.com/library/windows/desktop/aa366887(v=vs.85).aspx) is called with an allocation size greater than 8MB (0x800000).

CLR 2.0 added a feature called *VM Hoarding* that can be useful for scenarious where segments (including on the large and small object heaps) are frequently acquired and released. To specify VM Hoarding, you specify a startup flag called `STARTUP_HOARD_GC_VM` via the hosting API. Instead of releasing empty segments back to the OS, the CLR decommits the memory on these segments and puts them on a standby list. (Note that the CLR doesn't do this for segments that are too large.) The CLR later uses those segments to satisfy new segment requests. The next time that your app needs a new segment, the CLR uses one from this standby list if it can find one that’s big enough.

VM hoarding is also useful for applications that want to hold onto the segments that they already acquired, such as some server apps that are the dominant apps running on the system, to avoid out of memory exceptions.

We strongly recommend that you carefully test your application when you use this feature to ensure your application has fairly stable memory usage.
