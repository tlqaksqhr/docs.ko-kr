---
title: 가비지 컬렉션 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 13f7e935ab999ccc3cd3ea1e308e8d686bed4171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396937"
---
# <a name="garbage-collection-etw-events"></a><span data-ttu-id="a3210-102">가비지 컬렉션 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-102">Garbage Collection ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="a3210-103">이들 이벤트는 가비지 수집과 관련된 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-103">These events collect information pertaining to garbage collection.</span></span> <span data-ttu-id="a3210-104">가비지 수집 수행 횟수, 가비지 수집 중에 해제된 메모리 양 등을 판별하는 작업을 포함하여 진단과 디버깅에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-104">They help in diagnostics and debugging, including determining how many times garbage collection was performed, how much memory was freed during garbage collection, and so on.</span></span>  
  
 <span data-ttu-id="a3210-105">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-105">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="a3210-106">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-106">GCStart_V1 Event</span></span>](#gcstart_v1_event)  
  
-   [<span data-ttu-id="a3210-107">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-107">GCEnd_V1 Event</span></span>](#gcend_v1_event)  
  
-   [<span data-ttu-id="a3210-108">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-108">GCHeapStats_V1 Event</span></span>](#gcheapstats_v1_event)  
  
-   [<span data-ttu-id="a3210-109">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-109">GCCreateSegment_V1 Event</span></span>](#gccreatesegment_v1_event)  
  
-   [<span data-ttu-id="a3210-110">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-110">GCFreeSegment_V1 Event</span></span>](#gcfreesegment_v1_event)  
  
-   [<span data-ttu-id="a3210-111">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-111">GCRestartEEBegin_V1 Event</span></span>](#gcrestarteebegin_v1_event)  
  
-   [<span data-ttu-id="a3210-112">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-112">GCRestartEEEnd_V1 Event</span></span>](#gcrestarteeend_v1_event)  
  
-   [<span data-ttu-id="a3210-113">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-113">GCSuspendEE_V1 Event</span></span>](#gcsuspendee_v1_event)  
  
-   [<span data-ttu-id="a3210-114">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-114">GCSuspendEEEnd_V1 Event</span></span>](#gcsuspendeeend_v1_event)  
  
-   [<span data-ttu-id="a3210-115">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-115">GCAllocationTick_V2 Event</span></span>](#gcallocationtick_v2_event)  
  
-   [<span data-ttu-id="a3210-116">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-116">GCFinalizersBegin_V1 Event</span></span>](#gcfinalizersbegin_v1_event)  
  
-   [<span data-ttu-id="a3210-117">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-117">GCFinalizersEnd_V1 Event</span></span>](#gcfinalizersend_v1_event)  
  
-   [<span data-ttu-id="a3210-118">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-118">GCCreateConcurrentThread_V1 Event</span></span>](#gccreateconcurrentthread_v1_event)  
  
-   [<span data-ttu-id="a3210-119">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-119">GCTerminateConcurrentThread_V1 Event</span></span>](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a><span data-ttu-id="a3210-120">GCStart_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-120">GCStart_V1 Event</span></span>  
 <span data-ttu-id="a3210-121">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-121">The following table shows the keyword and level.</span></span> <span data-ttu-id="a3210-122">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a3210-122">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="a3210-123">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-123">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-124">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-124">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-125">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-125">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-126">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-126">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-127">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-127">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-128">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-128">Event</span></span>|<span data-ttu-id="a3210-129">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-129">Event ID</span></span>|<span data-ttu-id="a3210-130">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-130">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|<span data-ttu-id="a3210-131">1</span><span class="sxs-lookup"><span data-stu-id="a3210-131">1</span></span>|<span data-ttu-id="a3210-132">가비지 수집이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-132">A garbage collection has started.</span></span>|  
  
 <span data-ttu-id="a3210-133">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-133">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3210-134">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a3210-134">Field name</span></span>|<span data-ttu-id="a3210-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a3210-135">Data type</span></span>|<span data-ttu-id="a3210-136">설명</span><span class="sxs-lookup"><span data-stu-id="a3210-136">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3210-137">개수</span><span class="sxs-lookup"><span data-stu-id="a3210-137">Count</span></span>|<span data-ttu-id="a3210-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-138">win:UInt32</span></span>|<span data-ttu-id="a3210-139">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-139">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="a3210-140">깊이</span><span class="sxs-lookup"><span data-stu-id="a3210-140">Depth</span></span>|<span data-ttu-id="a3210-141">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-141">win:UInt32</span></span>|<span data-ttu-id="a3210-142">수집되고 있는 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-142">The generation that is being collected.</span></span>|  
|<span data-ttu-id="a3210-143">이유</span><span class="sxs-lookup"><span data-stu-id="a3210-143">Reason</span></span>|<span data-ttu-id="a3210-144">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-144">win:UInt32</span></span>|<span data-ttu-id="a3210-145">가비지 수집이 트리거된 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-145">Why the garbage collection was triggered:</span></span><br /><br /> <span data-ttu-id="a3210-146">0x0 - 작은 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="a3210-146">0x0 - Small object heap allocation.</span></span><br /><br /> <span data-ttu-id="a3210-147">0x1 - 발생됨.</span><span class="sxs-lookup"><span data-stu-id="a3210-147">0x1 - Induced.</span></span><br /><br /> <span data-ttu-id="a3210-148">0x2 - 메모리 부족.</span><span class="sxs-lookup"><span data-stu-id="a3210-148">0x2 - Low memory.</span></span><br /><br /> <span data-ttu-id="a3210-149">0x3 - 비어 있음.</span><span class="sxs-lookup"><span data-stu-id="a3210-149">0x3 - Empty.</span></span><br /><br /> <span data-ttu-id="a3210-150">0x4 - 큰 개체 힙 할당.</span><span class="sxs-lookup"><span data-stu-id="a3210-150">0x4 - Large object heap allocation.</span></span><br /><br /> <span data-ttu-id="a3210-151">0x5 - 공간 부족(작은 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="a3210-151">0x5 - Out of space (for small object heap).</span></span><br /><br /> <span data-ttu-id="a3210-152">0x6 - 공간 부족(큰 개체 힙용).</span><span class="sxs-lookup"><span data-stu-id="a3210-152">0x6 - Out of space (for large object heap).</span></span><br /><br /> <span data-ttu-id="a3210-153">0x7 - 발생하지만 차단으로 강제 적용되지 않음.</span><span class="sxs-lookup"><span data-stu-id="a3210-153">0x7 - Induced but not forced as blocking.</span></span>|  
|<span data-ttu-id="a3210-154">형식</span><span class="sxs-lookup"><span data-stu-id="a3210-154">Type</span></span>|<span data-ttu-id="a3210-155">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-155">win:UInt32</span></span>|<span data-ttu-id="a3210-156">0x0 - 가비지 수집 차단이 백그라운드 가비지 수집 외부에서 발생함.</span><span class="sxs-lookup"><span data-stu-id="a3210-156">0x0 - Blocking garbage collection occurred outside background garbage collection.</span></span><br /><br /> <span data-ttu-id="a3210-157">0x1 - 백그라운드 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="a3210-157">0x1 - Background garbage collection.</span></span><br /><br /> <span data-ttu-id="a3210-158">0x2 - 가비지 수집 차단이 백그라운드 가비지 수집 중에 발생함.</span><span class="sxs-lookup"><span data-stu-id="a3210-158">0x2 - Blocking garbage collection occurred during background garbage collection.</span></span>|  
|<span data-ttu-id="a3210-159">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3210-159">ClrInstanceID</span></span>|<span data-ttu-id="a3210-160">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3210-160">win:UInt16</span></span>|<span data-ttu-id="a3210-161">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-161">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3210-162">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-162">Back to top</span></span>](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a><span data-ttu-id="a3210-163">GCEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-163">GCEnd_V1 Event</span></span>  
 <span data-ttu-id="a3210-164">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-164">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-165">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-165">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-166">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-166">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-167">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-167">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-168">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-168">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-169">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-169">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-170">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-170">Event</span></span>|<span data-ttu-id="a3210-171">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-171">Event ID</span></span>|<span data-ttu-id="a3210-172">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-172">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|<span data-ttu-id="a3210-173">2</span><span class="sxs-lookup"><span data-stu-id="a3210-173">2</span></span>|<span data-ttu-id="a3210-174">가비지 수집이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-174">The garbage collection has ended.</span></span>|  
  
 <span data-ttu-id="a3210-175">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-175">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3210-176">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a3210-176">Field name</span></span>|<span data-ttu-id="a3210-177">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a3210-177">Data type</span></span>|<span data-ttu-id="a3210-178">설명</span><span class="sxs-lookup"><span data-stu-id="a3210-178">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3210-179">개수</span><span class="sxs-lookup"><span data-stu-id="a3210-179">Count</span></span>|<span data-ttu-id="a3210-180">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-180">win:UInt32</span></span>|<span data-ttu-id="a3210-181">*n*번째 가비지 수집입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-181">The *n*th garbage collection.</span></span>|  
|<span data-ttu-id="a3210-182">깊이</span><span class="sxs-lookup"><span data-stu-id="a3210-182">Depth</span></span>|<span data-ttu-id="a3210-183">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-183">win:UInt32</span></span>|<span data-ttu-id="a3210-184">수집된 세대입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-184">The generation that was collected.</span></span>|  
|<span data-ttu-id="a3210-185">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3210-185">ClrInstanceID</span></span>|<span data-ttu-id="a3210-186">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3210-186">win:UInt16</span></span>|<span data-ttu-id="a3210-187">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-187">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3210-188">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-188">Back to top</span></span>](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a><span data-ttu-id="a3210-189">GCHeapStats_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-189">GCHeapStats_V1 Event</span></span>  
 <span data-ttu-id="a3210-190">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-190">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-191">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-191">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-192">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-192">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-193">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-193">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-194">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-194">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-195">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-195">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-196">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-196">Event</span></span>|<span data-ttu-id="a3210-197">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-197">Event ID</span></span>|<span data-ttu-id="a3210-198">설명</span><span class="sxs-lookup"><span data-stu-id="a3210-198">Description</span></span>|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|<span data-ttu-id="a3210-199">4</span><span class="sxs-lookup"><span data-stu-id="a3210-199">4</span></span>|<span data-ttu-id="a3210-200">각 가비지 수집 종료 시 힙 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-200">Shows the heap statistics at the end of each garbage collection.</span></span>|  
  
 <span data-ttu-id="a3210-201">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-201">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3210-202">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a3210-202">Field name</span></span>|<span data-ttu-id="a3210-203">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a3210-203">Data type</span></span>|<span data-ttu-id="a3210-204">설명</span><span class="sxs-lookup"><span data-stu-id="a3210-204">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3210-205">GenerationSize0</span><span class="sxs-lookup"><span data-stu-id="a3210-205">GenerationSize0</span></span>|<span data-ttu-id="a3210-206">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-206">win:UInt64</span></span>|<span data-ttu-id="a3210-207">0세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-207">The size, in bytes, of generation 0 memory.</span></span>|  
|<span data-ttu-id="a3210-208">TotalPromotedSize0</span><span class="sxs-lookup"><span data-stu-id="a3210-208">TotalPromotedSize0</span></span>|<span data-ttu-id="a3210-209">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-209">win:UInt64</span></span>|<span data-ttu-id="a3210-210">0세대에서 1세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-210">The number of bytes that are promoted from generation 0 to generation 1.</span></span>|  
|<span data-ttu-id="a3210-211">GenerationSize1</span><span class="sxs-lookup"><span data-stu-id="a3210-211">GenerationSize1</span></span>|<span data-ttu-id="a3210-212">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-212">win:UInt64</span></span>|<span data-ttu-id="a3210-213">1세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-213">The size, in bytes, of generation 1 memory.</span></span>|  
|<span data-ttu-id="a3210-214">TotalPromotedSize1</span><span class="sxs-lookup"><span data-stu-id="a3210-214">TotalPromotedSize1</span></span>|<span data-ttu-id="a3210-215">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-215">win:UInt64</span></span>|<span data-ttu-id="a3210-216">1세대에서 2세대로 수준이 올려진 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-216">The number of bytes that are promoted from generation 1 to generation 2.</span></span>|  
|<span data-ttu-id="a3210-217">GenerationSize2</span><span class="sxs-lookup"><span data-stu-id="a3210-217">GenerationSize2</span></span>|<span data-ttu-id="a3210-218">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-218">win:UInt64</span></span>|<span data-ttu-id="a3210-219">2세대 메모리의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-219">The size, in bytes, of generation 2 memory.</span></span>|  
|<span data-ttu-id="a3210-220">TotalPromotedSize2</span><span class="sxs-lookup"><span data-stu-id="a3210-220">TotalPromotedSize2</span></span>|<span data-ttu-id="a3210-221">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-221">win:UInt64</span></span>|<span data-ttu-id="a3210-222">마지막 수집 후에 2세대에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-222">The number of bytes that survived in generation 2 after the last collection.</span></span>|  
|<span data-ttu-id="a3210-223">GenerationSize3</span><span class="sxs-lookup"><span data-stu-id="a3210-223">GenerationSize3</span></span>|<span data-ttu-id="a3210-224">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-224">win:UInt64</span></span>|<span data-ttu-id="a3210-225">큰 개체 힙의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-225">The size, in bytes, of the large object heap.</span></span>|  
|<span data-ttu-id="a3210-226">TotalPromotedSize3</span><span class="sxs-lookup"><span data-stu-id="a3210-226">TotalPromotedSize3</span></span>|<span data-ttu-id="a3210-227">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-227">win:UInt64</span></span>|<span data-ttu-id="a3210-228">마지막 수집 후에 큰 개체 힙에 남아 있는 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-228">The number of bytes that survived in the large object heap after the last collection.</span></span>|  
|<span data-ttu-id="a3210-229">FinalizationPromotedSize</span><span class="sxs-lookup"><span data-stu-id="a3210-229">FinalizationPromotedSize</span></span>|<span data-ttu-id="a3210-230">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-230">win:UInt64</span></span>|<span data-ttu-id="a3210-231">종료 준비가 된 개체의 전체 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-231">The total size, in bytes, of the objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="a3210-232">FinalizationPromotedCount</span><span class="sxs-lookup"><span data-stu-id="a3210-232">FinalizationPromotedCount</span></span>|<span data-ttu-id="a3210-233">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-233">win:UInt64</span></span>|<span data-ttu-id="a3210-234">종료 준비가 된 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-234">The number of objects that are ready for finalization.</span></span>|  
|<span data-ttu-id="a3210-235">PinnedObjectCount</span><span class="sxs-lookup"><span data-stu-id="a3210-235">PinnedObjectCount</span></span>|<span data-ttu-id="a3210-236">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-236">win:UInt32</span></span>|<span data-ttu-id="a3210-237">고정된(제거할 수 없는) 개체 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-237">The number of pinned (unmovable) objects.</span></span>|  
|<span data-ttu-id="a3210-238">SinkBlockCount</span><span class="sxs-lookup"><span data-stu-id="a3210-238">SinkBlockCount</span></span>|<span data-ttu-id="a3210-239">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-239">win:UInt32</span></span>|<span data-ttu-id="a3210-240">사용 중인 동기화 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-240">The number of synchronization blocks in use.</span></span>|  
|<span data-ttu-id="a3210-241">GCHandleCount</span><span class="sxs-lookup"><span data-stu-id="a3210-241">GCHandleCount</span></span>|<span data-ttu-id="a3210-242">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-242">win:UInt32</span></span>|<span data-ttu-id="a3210-243">사용 중인 가비지 수집 핸들 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-243">The number of garbage collection handles in use.</span></span>|  
|<span data-ttu-id="a3210-244">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3210-244">ClrInstanceID</span></span>|<span data-ttu-id="a3210-245">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3210-245">win:UInt16</span></span>|<span data-ttu-id="a3210-246">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-246">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3210-247">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-247">Back to top</span></span>](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a><span data-ttu-id="a3210-248">GCCreateSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-248">GCCreateSegment_V1 Event</span></span>  
 <span data-ttu-id="a3210-249">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-249">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-250">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-250">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-251">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-251">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-252">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-252">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-253">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-253">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-254">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-254">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-255">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-255">Event</span></span>|<span data-ttu-id="a3210-256">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-256">Event ID</span></span>|<span data-ttu-id="a3210-257">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-257">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|<span data-ttu-id="a3210-258">5</span><span class="sxs-lookup"><span data-stu-id="a3210-258">5</span></span>|<span data-ttu-id="a3210-259">새 가비지 수집 세그먼트가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-259">A new garbage collection segment has been created.</span></span> <span data-ttu-id="a3210-260">또한 이미 실행 중인 프로세스에서 추적 기능이 사용되면 각 기존 세그먼트에 대해 이 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-260">In addition, when tracing is enabled on a process that is already running, this event is raised for each existing segment.</span></span>|  
  
 <span data-ttu-id="a3210-261">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-261">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3210-262">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a3210-262">Field name</span></span>|<span data-ttu-id="a3210-263">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a3210-263">Data type</span></span>|<span data-ttu-id="a3210-264">설명</span><span class="sxs-lookup"><span data-stu-id="a3210-264">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3210-265">주소</span><span class="sxs-lookup"><span data-stu-id="a3210-265">Address</span></span>|<span data-ttu-id="a3210-266">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-266">win:UInt64</span></span>|<span data-ttu-id="a3210-267">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-267">The address of the segment.</span></span>|  
|<span data-ttu-id="a3210-268">크기</span><span class="sxs-lookup"><span data-stu-id="a3210-268">Size</span></span>|<span data-ttu-id="a3210-269">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-269">win:UInt64</span></span>|<span data-ttu-id="a3210-270">세그먼트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-270">The size of the segment.</span></span>|  
|<span data-ttu-id="a3210-271">형식</span><span class="sxs-lookup"><span data-stu-id="a3210-271">Type</span></span>|<span data-ttu-id="a3210-272">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-272">win:UInt32</span></span>|<span data-ttu-id="a3210-273">0x0 - 작은 개체 힙.</span><span class="sxs-lookup"><span data-stu-id="a3210-273">0x0 - Small object heap.</span></span><br /><br /> <span data-ttu-id="a3210-274">0x1 - 큰 개체 힙</span><span class="sxs-lookup"><span data-stu-id="a3210-274">0x1 - Large object heap.</span></span><br /><br /> <span data-ttu-id="a3210-275">0x2 - 읽기 전용 힙.</span><span class="sxs-lookup"><span data-stu-id="a3210-275">0x2 - Read-only heap.</span></span>|  
|<span data-ttu-id="a3210-276">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3210-276">ClrInstanceID</span></span>|<span data-ttu-id="a3210-277">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3210-277">win:UInt16</span></span>|<span data-ttu-id="a3210-278">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-278">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 <span data-ttu-id="a3210-279">가비지 수집기에서 할당되는 세그먼트 크기는 구현에 따라 다르며 정기적인 업데이트를 포함하여 언제든지 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-279">Note that the size of segments allocated by the garbage collector is implementation-specific and is subject to change at any time, including in periodic updates.</span></span> <span data-ttu-id="a3210-280">앱에서 특정 세그먼트 크기를 가정하거나 의존해서는 안 되며, 세그먼트 할당에 사용할 수 있는 메모리 크기를 구성하려고 해서도 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-280">Your app should never make assumptions about or depend on a particular segment size, nor should it attempt to configure the amount of memory available for segment allocations.</span></span>  
  
 [<span data-ttu-id="a3210-281">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-281">Back to top</span></span>](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a><span data-ttu-id="a3210-282">GCFreeSegment_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-282">GCFreeSegment_V1 Event</span></span>  
 <span data-ttu-id="a3210-283">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-283">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-284">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-284">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-285">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-285">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-286">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-286">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-287">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-287">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-288">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-288">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-289">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-289">Event</span></span>|<span data-ttu-id="a3210-290">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-290">Event ID</span></span>|<span data-ttu-id="a3210-291">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-291">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|<span data-ttu-id="a3210-292">6</span><span class="sxs-lookup"><span data-stu-id="a3210-292">6</span></span>|<span data-ttu-id="a3210-293">가비지 수집 세그먼트가 해제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-293">A garbage collection segment has been released.</span></span>|  
  
 <span data-ttu-id="a3210-294">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-294">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3210-295">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a3210-295">Field name</span></span>|<span data-ttu-id="a3210-296">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a3210-296">Data type</span></span>|<span data-ttu-id="a3210-297">설명</span><span class="sxs-lookup"><span data-stu-id="a3210-297">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3210-298">주소</span><span class="sxs-lookup"><span data-stu-id="a3210-298">Address</span></span>|<span data-ttu-id="a3210-299">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-299">win:UInt64</span></span>|<span data-ttu-id="a3210-300">세그먼트 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-300">The address of the segment.</span></span>|  
|<span data-ttu-id="a3210-301">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3210-301">ClrInstanceID</span></span>|<span data-ttu-id="a3210-302">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3210-302">win:UInt16</span></span>|<span data-ttu-id="a3210-303">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-303">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3210-304">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-304">Back to top</span></span>](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a><span data-ttu-id="a3210-305">GCRestartEEBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-305">GCRestartEEBegin_V1 Event</span></span>  
 <span data-ttu-id="a3210-306">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-306">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-307">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-307">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-308">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-308">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-309">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-309">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-310">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-310">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-311">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-311">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-312">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-312">Event</span></span>|<span data-ttu-id="a3210-313">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-313">Event ID</span></span>|<span data-ttu-id="a3210-314">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-314">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|<span data-ttu-id="a3210-315">7</span><span class="sxs-lookup"><span data-stu-id="a3210-315">7</span></span>|<span data-ttu-id="a3210-316">공용 언어 런타임 일시 중단에서 다시 시작이 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-316">Resumption from common language runtime suspension has begun.</span></span>|  
  
 <span data-ttu-id="a3210-317">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-317">No event data.</span></span>  
  
 [<span data-ttu-id="a3210-318">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-318">Back to top</span></span>](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a><span data-ttu-id="a3210-319">GCRestartEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-319">GCRestartEEEnd_V1 Event</span></span>  
 <span data-ttu-id="a3210-320">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-320">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-321">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-321">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-322">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-322">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-323">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-323">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-324">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-324">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-325">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-325">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-326">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-326">Event</span></span>|<span data-ttu-id="a3210-327">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-327">Event Id</span></span>|<span data-ttu-id="a3210-328">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-328">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|<span data-ttu-id="a3210-329">3</span><span class="sxs-lookup"><span data-stu-id="a3210-329">3</span></span>|<span data-ttu-id="a3210-330">공용 언어 런타임 일시 중단에서 다시 시작이 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-330">Resumption from common language runtime suspension has ended.</span></span>|  
  
 <span data-ttu-id="a3210-331">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-331">No event data.</span></span>  
  
 [<span data-ttu-id="a3210-332">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-332">Back to top</span></span>](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a><span data-ttu-id="a3210-333">GCSuspendEE_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-333">GCSuspendEE_V1 Event</span></span>  
 <span data-ttu-id="a3210-334">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-334">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-335">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-335">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-336">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-336">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-337">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-337">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-338">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-338">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-339">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-339">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-340">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-340">Event</span></span>|<span data-ttu-id="a3210-341">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-341">Event ID</span></span>|<span data-ttu-id="a3210-342">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-342">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|<span data-ttu-id="a3210-343">10</span><span class="sxs-lookup"><span data-stu-id="a3210-343">9</span></span>|<span data-ttu-id="a3210-344">가비지 수집에 대한 실행 엔진의 일시 중단이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-344">Start of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="a3210-345">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-345">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3210-346">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a3210-346">Field name</span></span>|<span data-ttu-id="a3210-347">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a3210-347">Data type</span></span>|<span data-ttu-id="a3210-348">설명</span><span class="sxs-lookup"><span data-stu-id="a3210-348">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3210-349">이유</span><span class="sxs-lookup"><span data-stu-id="a3210-349">Reason</span></span>|<span data-ttu-id="a3210-350">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3210-350">win:UInt16</span></span>|<span data-ttu-id="a3210-351">0x0 - 기타.</span><span class="sxs-lookup"><span data-stu-id="a3210-351">0x0 - Other.</span></span><br /><br /> <span data-ttu-id="a3210-352">0x1 - 가비지 수집.</span><span class="sxs-lookup"><span data-stu-id="a3210-352">0x1 - Garbage collection.</span></span><br /><br /> <span data-ttu-id="a3210-353">0x2 - 응용 프로그램 도메인 중지.</span><span class="sxs-lookup"><span data-stu-id="a3210-353">0x2 - Application domain shutdown.</span></span><br /><br /> <span data-ttu-id="a3210-354">0x3 - 코드 피칭.</span><span class="sxs-lookup"><span data-stu-id="a3210-354">0x3 - Code pitching.</span></span><br /><br /> <span data-ttu-id="a3210-355">0x4 - 종료.</span><span class="sxs-lookup"><span data-stu-id="a3210-355">0x4 - Shutdown.</span></span><br /><br /> <span data-ttu-id="a3210-356">0x5 - 디버거.</span><span class="sxs-lookup"><span data-stu-id="a3210-356">0x5 - Debugger.</span></span><br /><br /> <span data-ttu-id="a3210-357">0x6 - 가비지 수집 준비.</span><span class="sxs-lookup"><span data-stu-id="a3210-357">0x6 - Preparation for garbage collection.</span></span>|  
|<span data-ttu-id="a3210-358">개수</span><span class="sxs-lookup"><span data-stu-id="a3210-358">Count</span></span>|<span data-ttu-id="a3210-359">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-359">win:UInt32</span></span>|<span data-ttu-id="a3210-360">해당 시점의 GC 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-360">The GC count at the time.</span></span> <span data-ttu-id="a3210-361">일반적으로 이 이벤트 뒤에 후속 GC 시작 이벤트가 확인되고 가비지 수집 중에 GC 인덱스를 늘리면 해당 개수는 이 개수 + 1이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-361">Usually, you would see a subsequent GC Start event after this, and its Count would be this Count + 1 as we increase the GC index during a garbage collection.</span></span>|  
|<span data-ttu-id="a3210-362">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3210-362">ClrInstanceID</span></span>|<span data-ttu-id="a3210-363">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3210-363">win:UInt16</span></span>|<span data-ttu-id="a3210-364">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-364">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3210-365">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-365">Back to top</span></span>](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a><span data-ttu-id="a3210-366">GCSuspendEEEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-366">GCSuspendEEEnd_V1 Event</span></span>  
 <span data-ttu-id="a3210-367">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-367">The following table shows the keyword and level:</span></span>  
  
|<span data-ttu-id="a3210-368">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-368">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-369">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-369">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-370">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-370">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-371">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-371">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-372">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-372">The following table shows the event information:</span></span>  
  
|<span data-ttu-id="a3210-373">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-373">Event</span></span>|<span data-ttu-id="a3210-374">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-374">Event ID</span></span>|<span data-ttu-id="a3210-375">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-375">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|<span data-ttu-id="a3210-376">8</span><span class="sxs-lookup"><span data-stu-id="a3210-376">8</span></span>|<span data-ttu-id="a3210-377">가비지 수집에 대한 실행 엔진의 일시 중단이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-377">End of suspension of the execution engine for garbage collection.</span></span>|  
  
 <span data-ttu-id="a3210-378">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-378">No event data.</span></span>  
  
 [<span data-ttu-id="a3210-379">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-379">Back to top</span></span>](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a><span data-ttu-id="a3210-380">GCAllocationTick_V2 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-380">GCAllocationTick_V2 Event</span></span>  
 <span data-ttu-id="a3210-381">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-381">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-382">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-382">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-383">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-383">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-384">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-384">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-385">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-385">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-386">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-386">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-387">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-387">Event</span></span>|<span data-ttu-id="a3210-388">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-388">Event ID</span></span>|<span data-ttu-id="a3210-389">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-389">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|<span data-ttu-id="a3210-390">10</span><span class="sxs-lookup"><span data-stu-id="a3210-390">10</span></span>|<span data-ttu-id="a3210-391">매번 100KB 정도가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-391">Each time approximately 100 KB is allocated.</span></span>|  
  
 <span data-ttu-id="a3210-392">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-392">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3210-393">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a3210-393">Field name</span></span>|<span data-ttu-id="a3210-394">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a3210-394">Data type</span></span>|<span data-ttu-id="a3210-395">설명</span><span class="sxs-lookup"><span data-stu-id="a3210-395">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3210-396">AllocationAmount</span><span class="sxs-lookup"><span data-stu-id="a3210-396">AllocationAmount</span></span>|<span data-ttu-id="a3210-397">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-397">win:UInt32</span></span>|<span data-ttu-id="a3210-398">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-398">The allocation size, in bytes.</span></span> <span data-ttu-id="a3210-399">이 값은 ULONG 길이(4,294,967,295바이트)보다 적은 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-399">This value is accurate for allocations that are less than the length of a ULONG (4,294,967,295 bytes).</span></span> <span data-ttu-id="a3210-400">할당이 더 크면 이 필드에 잘린 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-400">If the allocation is greater, this field contains a truncated value.</span></span> <span data-ttu-id="a3210-401">매우 큰 할당에 대해서는 `AllocationAmount64` 를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="a3210-401">Use `AllocationAmount64` for very large allocations.</span></span>|  
|<span data-ttu-id="a3210-402">AllocationKind</span><span class="sxs-lookup"><span data-stu-id="a3210-402">AllocationKind</span></span>|<span data-ttu-id="a3210-403">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-403">win:UInt32</span></span>|<span data-ttu-id="a3210-404">0x0 - 작은 개체 할당(할당이 작은 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="a3210-404">0x0 - Small object allocation (allocation is in small object heap).</span></span><br /><br /> <span data-ttu-id="a3210-405">0x1 - 큰 개체 할당(할당이 큰 개체 힙에 포함됨).</span><span class="sxs-lookup"><span data-stu-id="a3210-405">0x1 - Large object allocation (allocation is in large object heap).</span></span>|  
|<span data-ttu-id="a3210-406">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3210-406">ClrInstanceID</span></span>|<span data-ttu-id="a3210-407">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3210-407">win:UInt16</span></span>|<span data-ttu-id="a3210-408">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-408">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
|<span data-ttu-id="a3210-409">AllocationAmount64</span><span class="sxs-lookup"><span data-stu-id="a3210-409">AllocationAmount64</span></span>|<span data-ttu-id="a3210-410">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="a3210-410">win:UInt64</span></span>|<span data-ttu-id="a3210-411">할당 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-411">The allocation size, in bytes.</span></span> <span data-ttu-id="a3210-412">이 값은 매우 큰 할당에 대해 정확합니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-412">This value is accurate for very large allocations.</span></span>|  
|<span data-ttu-id="a3210-413">TypeId</span><span class="sxs-lookup"><span data-stu-id="a3210-413">TypeId</span></span>|<span data-ttu-id="a3210-414">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="a3210-414">win:Pointer</span></span>|<span data-ttu-id="a3210-415">MethodTable 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-415">The address of the MethodTable.</span></span> <span data-ttu-id="a3210-416">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)에 해당하는 MethodTable의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-416">When there are several types of objects that were allocated during this event, this is the address of the MethodTable that corresponds to the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="a3210-417">TypeName</span><span class="sxs-lookup"><span data-stu-id="a3210-417">TypeName</span></span>|<span data-ttu-id="a3210-418">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="a3210-418">win:UnicodeString</span></span>|<span data-ttu-id="a3210-419">할당된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-419">The name of the type that was allocated.</span></span> <span data-ttu-id="a3210-420">이 이벤트 중에 여러 가지 개체 형식이 할당되었으면 이 항목은 할당된 마지막 개체(100KB 임계값을 초과한 개체)의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-420">When there are several types of objects that were allocated during this event, this is the type of the last object allocated (the object that caused the 100 KB threshold to be exceeded).</span></span>|  
|<span data-ttu-id="a3210-421">HeapIndex</span><span class="sxs-lookup"><span data-stu-id="a3210-421">HeapIndex</span></span>|<span data-ttu-id="a3210-422">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-422">win:UInt32</span></span>|<span data-ttu-id="a3210-423">개체가 할당된 힙입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-423">The heap where the object was allocated.</span></span> <span data-ttu-id="a3210-424">워크스테이션 가비지 수집에서 실행될 때 이 값은 0(영)입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-424">This value is 0 (zero) when running with workstation garbage collection.</span></span>|  
  
 [<span data-ttu-id="a3210-425">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-425">Back to top</span></span>](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a><span data-ttu-id="a3210-426">GCFinalizersBegin_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-426">GCFinalizersBegin_V1 Event</span></span>  
 <span data-ttu-id="a3210-427">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-427">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-428">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-428">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-429">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-429">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-430">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-430">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-431">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-431">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-432">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-432">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-433">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-433">Event</span></span>|<span data-ttu-id="a3210-434">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-434">Event ID</span></span>|<span data-ttu-id="a3210-435">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-435">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|<span data-ttu-id="a3210-436">14</span><span class="sxs-lookup"><span data-stu-id="a3210-436">14</span></span>|<span data-ttu-id="a3210-437">종료자 실행이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-437">The start of running finalizers.</span></span>|  
  
 <span data-ttu-id="a3210-438">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-438">No event data.</span></span>  
  
 [<span data-ttu-id="a3210-439">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-439">Back to top</span></span>](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a><span data-ttu-id="a3210-440">GCFinalizersEnd_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-440">GCFinalizersEnd_V1 Event</span></span>  
 <span data-ttu-id="a3210-441">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-441">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-442">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-442">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-443">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-443">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-444">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-444">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-445">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-445">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-446">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-446">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-447">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-447">Event</span></span>|<span data-ttu-id="a3210-448">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-448">Event ID</span></span>|<span data-ttu-id="a3210-449">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-449">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|<span data-ttu-id="a3210-450">13</span><span class="sxs-lookup"><span data-stu-id="a3210-450">13</span></span>|<span data-ttu-id="a3210-451">종료자 실행이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-451">The end of running finalizers.</span></span>|  
  
 <span data-ttu-id="a3210-452">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-452">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="a3210-453">필드 이름</span><span class="sxs-lookup"><span data-stu-id="a3210-453">Field name</span></span>|<span data-ttu-id="a3210-454">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a3210-454">Data type</span></span>|<span data-ttu-id="a3210-455">설명</span><span class="sxs-lookup"><span data-stu-id="a3210-455">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="a3210-456">개수</span><span class="sxs-lookup"><span data-stu-id="a3210-456">Count</span></span>|<span data-ttu-id="a3210-457">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="a3210-457">win:UInt32</span></span>|<span data-ttu-id="a3210-458">실행된 종료자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-458">The number of finalizers that were run.</span></span>|  
|<span data-ttu-id="a3210-459">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="a3210-459">ClrInstanceID</span></span>|<span data-ttu-id="a3210-460">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="a3210-460">win:UInt16</span></span>|<span data-ttu-id="a3210-461">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-461">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="a3210-462">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-462">Back to top</span></span>](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a><span data-ttu-id="a3210-463">GCCreateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-463">GCCreateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="a3210-464">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-464">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-465">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-465">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-466">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-466">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-467">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-467">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-468">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-468">Informational (4)</span></span>|  
|<span data-ttu-id="a3210-469">`ThreadingKeyword`(0x10000)</span><span class="sxs-lookup"><span data-stu-id="a3210-469">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a3210-470">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-470">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-471">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-471">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-472">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-472">Event</span></span>|<span data-ttu-id="a3210-473">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-473">Event ID</span></span>|<span data-ttu-id="a3210-474">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-474">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|<span data-ttu-id="a3210-475">11</span><span class="sxs-lookup"><span data-stu-id="a3210-475">11</span></span>|<span data-ttu-id="a3210-476">동시 가비지 수집 스레드가 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-476">Concurrent garbage collection thread was created.</span></span>|  
  
 <span data-ttu-id="a3210-477">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-477">No event data.</span></span>  
  
 [<span data-ttu-id="a3210-478">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="a3210-478">Back to top</span></span>](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a><span data-ttu-id="a3210-479">GCTerminateConcurrentThread_V1 Event</span><span class="sxs-lookup"><span data-stu-id="a3210-479">GCTerminateConcurrentThread_V1 Event</span></span>  
 <span data-ttu-id="a3210-480">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-480">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="a3210-481">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="a3210-481">Keyword for raising the event</span></span>|<span data-ttu-id="a3210-482">수준</span><span class="sxs-lookup"><span data-stu-id="a3210-482">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="a3210-483">`GCKeyword` (0x1)</span><span class="sxs-lookup"><span data-stu-id="a3210-483">`GCKeyword` (0x1)</span></span>|<span data-ttu-id="a3210-484">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-484">Informational (4)</span></span>|  
|<span data-ttu-id="a3210-485">`ThreadingKeyword`(0x10000)</span><span class="sxs-lookup"><span data-stu-id="a3210-485">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="a3210-486">정보(4)</span><span class="sxs-lookup"><span data-stu-id="a3210-486">Informational (4)</span></span>|  
  
 <span data-ttu-id="a3210-487">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-487">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="a3210-488">이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-488">Event</span></span>|<span data-ttu-id="a3210-489">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="a3210-489">Event ID</span></span>|<span data-ttu-id="a3210-490">발생 시기</span><span class="sxs-lookup"><span data-stu-id="a3210-490">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|<span data-ttu-id="a3210-491">12</span><span class="sxs-lookup"><span data-stu-id="a3210-491">12</span></span>|<span data-ttu-id="a3210-492">동시 가비지 수집 스레드가 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-492">Concurrent garbage collection thread was terminated.</span></span>|  
  
 <span data-ttu-id="a3210-493">이벤트 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a3210-493">No event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3210-494">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3210-494">See Also</span></span>  
 [<span data-ttu-id="a3210-495">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="a3210-495">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
