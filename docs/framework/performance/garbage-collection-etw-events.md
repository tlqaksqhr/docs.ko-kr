---
title: "가비지 컬렉션 ETW 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 133d48baa9613ea698b6d6a21f0dfe88a798859c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="35d26-102">가비지 컬렉션 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="35d26-103">이들 이벤트는 가비지 수집과 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="35d26-104">가비지 수집 수행 횟수, 가비지 수집 중에 해제된 메모리 양 등을 판별하는 작업을 포함하여 진단과 디버깅에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="35d26-105">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="35d26-106">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="35d26-107">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="35d26-108">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="35d26-109">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="35d26-110">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="35d26-111">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="35d26-112">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="35d26-113">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="35d26-114">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="35d26-115">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="35d26-116">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="35d26-117">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="35d26-118">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="35d26-119">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="35d26-120">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="35d26-121">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="35d26-122">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35d26-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="35d26-123">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-123">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-124">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-126">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-127">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-128">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-128">Event</span></span>|<span data-ttu-id="35d26-129">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-129">Event ID</span></span>|<span data-ttu-id="35d26-130">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="35d26-131">1</span><span class="sxs-lookup"><span data-stu-id="35d26-131">1</span></span>|<span data-ttu-id="35d26-132">가비지 수집이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="35d26-133">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="35d26-134">필드 이름</span><span class="sxs-lookup"><span data-stu-id="35d26-134">Field name</span></span>|<span data-ttu-id="35d26-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="35d26-135">Data type</span></span>|<span data-ttu-id="35d26-136">설명</span><span class="sxs-lookup"><span data-stu-id="35d26-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="35d26-137">개수</span><span class="sxs-lookup"><span data-stu-id="35d26-137">Count</span></span>|<span data-ttu-id="35d26-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-138">win:UInt32</span></span>|<span data-ttu-id="35d26-139">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="35d26-140">깊이</span><span class="sxs-lookup"><span data-stu-id="35d26-140">Depth</span></span>|<span data-ttu-id="35d26-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-141">win:UInt32</span></span>|<span data-ttu-id="35d26-142">수집되고 있는 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="35d26-143">이유</span><span class="sxs-lookup"><span data-stu-id="35d26-143">Reason</span></span>|<span data-ttu-id="35d26-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-144">win:UInt32</span></span>|<span data-ttu-id="35d26-145">가비지 수집이 트리거된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="35d26-146">0x0 - 작은 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="35d26-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="35d26-147">0x1 - 발생됨.</span><span class="sxs-lookup"><span data-stu-id="35d26-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="35d26-148">0x2 - 메모리 부족.</span><span class="sxs-lookup"><span data-stu-id="35d26-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="35d26-149">0x3 - 비어 있음.</span><span class="sxs-lookup"><span data-stu-id="35d26-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="35d26-150">0x4 - 큰 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="35d26-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="35d26-151">0x5 - 공간 부족(작은 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="35d26-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="35d26-152">0x6 - 공간 부족(큰 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="35d26-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="35d26-153">0x7 - 발생하지만 차단으로 강제 적용되지 않음.</span><span class="sxs-lookup"><span data-stu-id="35d26-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="35d26-154">형식</span><span class="sxs-lookup"><span data-stu-id="35d26-154">Type</span></span>|<span data-ttu-id="35d26-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-155">win:UInt32</span></span>|<span data-ttu-id="35d26-156">0x0 - 가비지 수집 차단이 백그라운드 가비지 수집 외부에서 발생함.</span><span class="sxs-lookup"><span data-stu-id="35d26-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="35d26-157">0x1 - 백그라운드 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="35d26-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="35d26-158">0x2 - 가비지 수집 차단이 백그라운드 가비지 수집 중에 발생함.</span><span class="sxs-lookup"><span data-stu-id="35d26-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="35d26-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="35d26-159">ClrInstanceID</span></span>|<span data-ttu-id="35d26-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="35d26-160">win:UInt16</span></span>|<span data-ttu-id="35d26-161">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="35d26-162">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="35d26-163">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="35d26-164">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-165">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-165">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-166">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-168">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-169">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-170">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-170">Event</span></span>|<span data-ttu-id="35d26-171">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-171">Event ID</span></span>|<span data-ttu-id="35d26-172">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="35d26-173">2</span><span class="sxs-lookup"><span data-stu-id="35d26-173">2</span></span>|<span data-ttu-id="35d26-174">가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="35d26-175">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="35d26-176">필드 이름</span><span class="sxs-lookup"><span data-stu-id="35d26-176">Field name</span></span>|<span data-ttu-id="35d26-177">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="35d26-177">Data type</span></span>|<span data-ttu-id="35d26-178">설명</span><span class="sxs-lookup"><span data-stu-id="35d26-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="35d26-179">개수</span><span class="sxs-lookup"><span data-stu-id="35d26-179">Count</span></span>|<span data-ttu-id="35d26-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-180">win:UInt32</span></span>|<span data-ttu-id="35d26-181">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="35d26-182">깊이</span><span class="sxs-lookup"><span data-stu-id="35d26-182">Depth</span></span>|<span data-ttu-id="35d26-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-183">win:UInt32</span></span>|<span data-ttu-id="35d26-184">수집된 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="35d26-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="35d26-185">ClrInstanceID</span></span>|<span data-ttu-id="35d26-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="35d26-186">win:UInt16</span></span>|<span data-ttu-id="35d26-187">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="35d26-188">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="35d26-189">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="35d26-190">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-191">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-191">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-192">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-194">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-195">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-196">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-196">Event</span></span>|<span data-ttu-id="35d26-197">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-197">Event ID</span></span>|<span data-ttu-id="35d26-198">설명</span><span class="sxs-lookup"><span data-stu-id="35d26-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="35d26-199">4</span><span class="sxs-lookup"><span data-stu-id="35d26-199">4</span></span>|<span data-ttu-id="35d26-200">각 가비지 수집 종료 시 힙 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="35d26-201">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="35d26-202">필드 이름</span><span class="sxs-lookup"><span data-stu-id="35d26-202">Field name</span></span>|<span data-ttu-id="35d26-203">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="35d26-203">Data type</span></span>|<span data-ttu-id="35d26-204">설명</span><span class="sxs-lookup"><span data-stu-id="35d26-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="35d26-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="35d26-205">GenerationSize0</span></span>|<span data-ttu-id="35d26-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-206">win:UInt64</span></span>|<span data-ttu-id="35d26-207">0세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="35d26-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="35d26-208">TotalPromotedSize0</span></span>|<span data-ttu-id="35d26-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-209">win:UInt64</span></span>|<span data-ttu-id="35d26-210">0세대에서 1세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="35d26-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="35d26-211">GenerationSize1</span></span>|<span data-ttu-id="35d26-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-212">win:UInt64</span></span>|<span data-ttu-id="35d26-213">1세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="35d26-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="35d26-214">TotalPromotedSize1</span></span>|<span data-ttu-id="35d26-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-215">win:UInt64</span></span>|<span data-ttu-id="35d26-216">1세대에서 2세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="35d26-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="35d26-217">GenerationSize2</span></span>|<span data-ttu-id="35d26-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-218">win:UInt64</span></span>|<span data-ttu-id="35d26-219">2세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="35d26-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="35d26-220">TotalPromotedSize2</span></span>|<span data-ttu-id="35d26-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-221">win:UInt64</span></span>|<span data-ttu-id="35d26-222">마지막 수집 후에 2세대에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="35d26-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="35d26-223">GenerationSize3</span></span>|<span data-ttu-id="35d26-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-224">win:UInt64</span></span>|<span data-ttu-id="35d26-225">큰 개체 힙의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="35d26-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="35d26-226">TotalPromotedSize3</span></span>|<span data-ttu-id="35d26-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-227">win:UInt64</span></span>|<span data-ttu-id="35d26-228">마지막 수집 후에 큰 개체 힙에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="35d26-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="35d26-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="35d26-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-230">win:UInt64</span></span>|<span data-ttu-id="35d26-231">종료 준비가 된 개체의 전체 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="35d26-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="35d26-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="35d26-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-233">win:UInt64</span></span>|<span data-ttu-id="35d26-234">종료 준비가 된 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="35d26-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="35d26-235">PinnedObjectCount</span></span>|<span data-ttu-id="35d26-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-236">win:UInt32</span></span>|<span data-ttu-id="35d26-237">고정된(제거할 수 없는) 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="35d26-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="35d26-238">SinkBlockCount</span></span>|<span data-ttu-id="35d26-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-239">win:UInt32</span></span>|<span data-ttu-id="35d26-240">사용 중인 동기화 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="35d26-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="35d26-241">GCHandleCount</span></span>|<span data-ttu-id="35d26-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-242">win:UInt32</span></span>|<span data-ttu-id="35d26-243">사용 중인 가비지 수집 핸들 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="35d26-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="35d26-244">ClrInstanceID</span></span>|<span data-ttu-id="35d26-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="35d26-245">win:UInt16</span></span>|<span data-ttu-id="35d26-246">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="35d26-247">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="35d26-248">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="35d26-249">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-250">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-250">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-251">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-253">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-254">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-255">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-255">Event</span></span>|<span data-ttu-id="35d26-256">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-256">Event ID</span></span>|<span data-ttu-id="35d26-257">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="35d26-258">5</span><span class="sxs-lookup"><span data-stu-id="35d26-258">5</span></span>|<span data-ttu-id="35d26-259">새 가비지 수집 세그먼트가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="35d26-260">또한 이미 실행 중인 프로세스에서 추적 기능이 사용되면 각 기존 세그먼트에 대해 이 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="35d26-261">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="35d26-262">필드 이름</span><span class="sxs-lookup"><span data-stu-id="35d26-262">Field name</span></span>|<span data-ttu-id="35d26-263">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="35d26-263">Data type</span></span>|<span data-ttu-id="35d26-264">설명</span><span class="sxs-lookup"><span data-stu-id="35d26-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="35d26-265">주소</span><span class="sxs-lookup"><span data-stu-id="35d26-265">Address</span></span>|<span data-ttu-id="35d26-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-266">win:UInt64</span></span>|<span data-ttu-id="35d26-267">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-267">The address of the segment.</span></span>|  
|<span data-ttu-id="35d26-268">크기</span><span class="sxs-lookup"><span data-stu-id="35d26-268">Size</span></span>|<span data-ttu-id="35d26-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-269">win:UInt64</span></span>|<span data-ttu-id="35d26-270">세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-270">The size of the segment.</span></span>|  
|<span data-ttu-id="35d26-271">형식</span><span class="sxs-lookup"><span data-stu-id="35d26-271">Type</span></span>|<span data-ttu-id="35d26-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-272">win:UInt32</span></span>|<span data-ttu-id="35d26-273">0x0 - 작은 개체 힙.</span><span class="sxs-lookup"><span data-stu-id="35d26-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="35d26-274">0x1 - 큰 개체 힙</span><span class="sxs-lookup"><span data-stu-id="35d26-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="35d26-275">0x2 - 읽기 전용 힙.</span><span class="sxs-lookup"><span data-stu-id="35d26-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="35d26-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="35d26-276">ClrInstanceID</span></span>|<span data-ttu-id="35d26-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="35d26-277">win:UInt16</span></span>|<span data-ttu-id="35d26-278">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="35d26-279">가비지 수집기에서 할당되는 세그먼트 크기는 구현에 따라 다르며 정기적인 업데이트를 포함하여 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="35d26-280">앱에서 특정 세그먼트 크기를 가정하거나 의존해서는 안 되며, 세그먼트 할당에 사용할 수 있는 메모리 크기를 구성하려고 해서도 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="35d26-281">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="35d26-282">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="35d26-283">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-284">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-284">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-285">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-287">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-288">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-289">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-289">Event</span></span>|<span data-ttu-id="35d26-290">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-290">Event ID</span></span>|<span data-ttu-id="35d26-291">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="35d26-292">6</span><span class="sxs-lookup"><span data-stu-id="35d26-292">6</span></span>|<span data-ttu-id="35d26-293">가비지 수집 세그먼트가 해제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="35d26-294">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="35d26-295">필드 이름</span><span class="sxs-lookup"><span data-stu-id="35d26-295">Field name</span></span>|<span data-ttu-id="35d26-296">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="35d26-296">Data type</span></span>|<span data-ttu-id="35d26-297">설명</span><span class="sxs-lookup"><span data-stu-id="35d26-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="35d26-298">주소</span><span class="sxs-lookup"><span data-stu-id="35d26-298">Address</span></span>|<span data-ttu-id="35d26-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-299">win:UInt64</span></span>|<span data-ttu-id="35d26-300">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-300">The address of the segment.</span></span>|  
|<span data-ttu-id="35d26-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="35d26-301">ClrInstanceID</span></span>|<span data-ttu-id="35d26-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="35d26-302">win:UInt16</span></span>|<span data-ttu-id="35d26-303">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="35d26-304">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="35d26-305">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="35d26-306">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-307">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-307">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-308">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-310">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-311">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-312">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-312">Event</span></span>|<span data-ttu-id="35d26-313">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-313">Event ID</span></span>|<span data-ttu-id="35d26-314">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="35d26-315">7</span><span class="sxs-lookup"><span data-stu-id="35d26-315">7</span></span>|<span data-ttu-id="35d26-316">공용 언어 런타임 일시 중단에서 다시 시작이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="35d26-317">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-317">No event data.</span></span>  
  
 [<span data-ttu-id="35d26-318">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="35d26-319">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="35d26-320">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-321">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-321">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-322">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-324">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-325">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-326">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-326">Event</span></span>|<span data-ttu-id="35d26-327">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-327">Event Id</span></span>|<span data-ttu-id="35d26-328">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="35d26-329">3</span><span class="sxs-lookup"><span data-stu-id="35d26-329">3</span></span>|<span data-ttu-id="35d26-330">공용 언어 런타임 일시 중단에서 다시 시작이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="35d26-331">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-331">No event data.</span></span>  
  
 [<span data-ttu-id="35d26-332">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="35d26-333">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="35d26-334">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-335">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-335">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-336">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-338">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-339">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-340">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-340">Event</span></span>|<span data-ttu-id="35d26-341">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-341">Event ID</span></span>|<span data-ttu-id="35d26-342">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="35d26-343">10</span><span class="sxs-lookup"><span data-stu-id="35d26-343">9</span></span>|<span data-ttu-id="35d26-344">가비지 수집에 대한 실행 엔진의 일시 중단이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="35d26-345">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="35d26-346">필드 이름</span><span class="sxs-lookup"><span data-stu-id="35d26-346">Field name</span></span>|<span data-ttu-id="35d26-347">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="35d26-347">Data type</span></span>|<span data-ttu-id="35d26-348">설명</span><span class="sxs-lookup"><span data-stu-id="35d26-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="35d26-349">이유</span><span class="sxs-lookup"><span data-stu-id="35d26-349">Reason</span></span>|<span data-ttu-id="35d26-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="35d26-350">win:UInt16</span></span>|<span data-ttu-id="35d26-351">0x0 - 기타.</span><span class="sxs-lookup"><span data-stu-id="35d26-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="35d26-352">0x1 - 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="35d26-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="35d26-353">0x2 - 응용 프로그램 도메인 중지.</span><span class="sxs-lookup"><span data-stu-id="35d26-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="35d26-354">0x3 - 코드 피칭.</span><span class="sxs-lookup"><span data-stu-id="35d26-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="35d26-355">0x4 - 종료.</span><span class="sxs-lookup"><span data-stu-id="35d26-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="35d26-356">0x5 - 디버거.</span><span class="sxs-lookup"><span data-stu-id="35d26-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="35d26-357">0x6 - 가비지 수집 준비.</span><span class="sxs-lookup"><span data-stu-id="35d26-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="35d26-358">개수</span><span class="sxs-lookup"><span data-stu-id="35d26-358">Count</span></span>|<span data-ttu-id="35d26-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-359">win:UInt32</span></span>|<span data-ttu-id="35d26-360">해당 시점의 GC 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-360">The GC count at the time.</span></span> <span data-ttu-id="35d26-361">일반적으로 이 이벤트 뒤에 후속 GC 시작 이벤트가 확인되고 가비지 수집 중에 GC 인덱스를 늘리면 해당 개수는 이 개수 + 1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="35d26-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="35d26-362">ClrInstanceID</span></span>|<span data-ttu-id="35d26-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="35d26-363">win:UInt16</span></span>|<span data-ttu-id="35d26-364">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="35d26-365">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="35d26-366">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="35d26-367">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="35d26-368">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-368">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-369">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-371">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-372">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="35d26-373">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-373">Event</span></span>|<span data-ttu-id="35d26-374">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-374">Event ID</span></span>|<span data-ttu-id="35d26-375">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="35d26-376">8</span><span class="sxs-lookup"><span data-stu-id="35d26-376">8</span></span>|<span data-ttu-id="35d26-377">가비지 수집에 대한 실행 엔진의 일시 중단이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="35d26-378">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-378">No event data.</span></span>  
  
 [<span data-ttu-id="35d26-379">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="35d26-380">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="35d26-381">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-382">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-382">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-383">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-385">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-386">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-387">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-387">Event</span></span>|<span data-ttu-id="35d26-388">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-388">Event ID</span></span>|<span data-ttu-id="35d26-389">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="35d26-390">10</span><span class="sxs-lookup"><span data-stu-id="35d26-390">10</span></span>|<span data-ttu-id="35d26-391">매번 100KB 정도가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="35d26-392">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="35d26-393">필드 이름</span><span class="sxs-lookup"><span data-stu-id="35d26-393">Field name</span></span>|<span data-ttu-id="35d26-394">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="35d26-394">Data type</span></span>|<span data-ttu-id="35d26-395">설명</span><span class="sxs-lookup"><span data-stu-id="35d26-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="35d26-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="35d26-396">AllocationAmount</span></span>|<span data-ttu-id="35d26-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-397">win:UInt32</span></span>|<span data-ttu-id="35d26-398">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-398">The allocation size, in bytes.</span></span> <span data-ttu-id="35d26-399">이 값은 ULONG 길이(4,294,967,295바이트)보다 적은 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="35d26-400">할당이 더 크면 이 필드에 잘린 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="35d26-401">매우 큰 할당에 대해서는 `AllocationAmount64` 를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="35d26-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="35d26-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="35d26-402">AllocationKind</span></span>|<span data-ttu-id="35d26-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-403">win:UInt32</span></span>|<span data-ttu-id="35d26-404">0x0 - 작은 개체 할당(할당이 작은 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="35d26-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="35d26-405">0x1 - 큰 개체 할당(할당이 큰 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="35d26-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="35d26-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="35d26-406">ClrInstanceID</span></span>|<span data-ttu-id="35d26-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="35d26-407">win:UInt16</span></span>|<span data-ttu-id="35d26-408">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="35d26-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="35d26-409">AllocationAmount64</span></span>|<span data-ttu-id="35d26-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="35d26-410">win:UInt64</span></span>|<span data-ttu-id="35d26-411">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-411">The allocation size, in bytes.</span></span> <span data-ttu-id="35d26-412">이 값은 매우 큰 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="35d26-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="35d26-413">TypeId</span></span>|<span data-ttu-id="35d26-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="35d26-414">win:Pointer</span></span>|<span data-ttu-id="35d26-415">MethodTable 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-415">The address of the MethodTable.</span></span> <span data-ttu-id="35d26-416">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)에 해당하는 MethodTable의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="35d26-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="35d26-417">TypeName</span></span>|<span data-ttu-id="35d26-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="35d26-418">win:UnicodeString</span></span>|<span data-ttu-id="35d26-419">할당된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-419">The name of the type that was allocated.</span></span> <span data-ttu-id="35d26-420">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="35d26-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="35d26-421">HeapIndex</span></span>|<span data-ttu-id="35d26-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-422">win:UInt32</span></span>|<span data-ttu-id="35d26-423">개체가 할당된 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-423">The heap where the object was allocated.</span></span> <span data-ttu-id="35d26-424">워크스테이션 가비지 수집에서 실행될 때 이 값은 0(영)입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="35d26-425">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="35d26-426">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="35d26-427">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-428">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-428">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-429">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-431">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-432">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-433">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-433">Event</span></span>|<span data-ttu-id="35d26-434">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-434">Event ID</span></span>|<span data-ttu-id="35d26-435">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="35d26-436">14</span><span class="sxs-lookup"><span data-stu-id="35d26-436">14</span></span>|<span data-ttu-id="35d26-437">종료자 실행이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="35d26-438">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-438">No event data.</span></span>  
  
 [<span data-ttu-id="35d26-439">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="35d26-440">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="35d26-441">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-442">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-442">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-443">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-445">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-446">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-447">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-447">Event</span></span>|<span data-ttu-id="35d26-448">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-448">Event ID</span></span>|<span data-ttu-id="35d26-449">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="35d26-450">13</span><span class="sxs-lookup"><span data-stu-id="35d26-450">13</span></span>|<span data-ttu-id="35d26-451">종료자 실행이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="35d26-452">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="35d26-453">필드 이름</span><span class="sxs-lookup"><span data-stu-id="35d26-453">Field name</span></span>|<span data-ttu-id="35d26-454">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="35d26-454">Data type</span></span>|<span data-ttu-id="35d26-455">설명</span><span class="sxs-lookup"><span data-stu-id="35d26-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="35d26-456">개수</span><span class="sxs-lookup"><span data-stu-id="35d26-456">Count</span></span>|<span data-ttu-id="35d26-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="35d26-457">win:UInt32</span></span>|<span data-ttu-id="35d26-458">실행된 종료자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="35d26-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="35d26-459">ClrInstanceID</span></span>|<span data-ttu-id="35d26-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="35d26-460">win:UInt16</span></span>|<span data-ttu-id="35d26-461">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="35d26-462">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="35d26-463">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="35d26-464">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-465">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-465">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-466">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-468">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-468">Informational (4)</span></span>|  
|<span data-ttu-id="35d26-469">`ThreadingKeyword`(0x10000)</span><span class="sxs-lookup"><span data-stu-id="35d26-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="35d26-470">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-471">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-472">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-472">Event</span></span>|<span data-ttu-id="35d26-473">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-473">Event ID</span></span>|<span data-ttu-id="35d26-474">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="35d26-475">11</span><span class="sxs-lookup"><span data-stu-id="35d26-475">11</span></span>|<span data-ttu-id="35d26-476">동시 가비지 수집 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="35d26-477">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-477">No event data.</span></span>  
  
 [<span data-ttu-id="35d26-478">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="35d26-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="35d26-479">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="35d26-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="35d26-480">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="35d26-481">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="35d26-481">Keyword for raising the event</span></span>|<span data-ttu-id="35d26-482">수준</span><span class="sxs-lookup"><span data-stu-id="35d26-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="35d26-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="35d26-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="35d26-484">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-484">Informational (4)</span></span>|  
|<span data-ttu-id="35d26-485">`ThreadingKeyword`(0x10000)</span><span class="sxs-lookup"><span data-stu-id="35d26-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="35d26-486">정보(4)</span><span class="sxs-lookup"><span data-stu-id="35d26-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="35d26-487">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="35d26-488">이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-488">Event</span></span>|<span data-ttu-id="35d26-489">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="35d26-489">Event ID</span></span>|<span data-ttu-id="35d26-490">발생 시기</span><span class="sxs-lookup"><span data-stu-id="35d26-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="35d26-491">12</span><span class="sxs-lookup"><span data-stu-id="35d26-491">12</span></span>|<span data-ttu-id="35d26-492">동시 가비지 수집 스레드가 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="35d26-493">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="35d26-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d26-494">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35d26-494">See Also</span></span>  
 [<span data-ttu-id="35d26-495">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="35d26-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
