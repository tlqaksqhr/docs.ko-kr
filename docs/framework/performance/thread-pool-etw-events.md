---
title: "스레드 풀 ETW 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread pool events [.NET Framework]
- ETW, thread pool events (CLR)
ms.assetid: f2a21e3a-3b6c-4433-97f3-47ff16855ecc
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3dfd8b17e4ca01802651087ff20988744a411ed2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="thread-pool-etw-events"></a><span data-ttu-id="b49a4-102">스레드 풀 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-102">Thread Pool ETW Events</span></span>
<span data-ttu-id="b49a4-103"><a name="top"></a> 이러한 이벤트는 작업자 스레드 및 I/O 스레드에 대한 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-103"><a name="top"></a> These events collect information about worker and I/O threads.</span></span>  
  
 <span data-ttu-id="b49a4-104">스레드 풀 이벤트에는 다음과 같은 두 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-104">There are two groups of thread pool events:</span></span>  
  
-   <span data-ttu-id="b49a4-105">[작업자 스레드 풀 이벤트](#worker). 이러한 스레드 풀 이벤트는 응용 프로그램에서 스레드 풀을 사용하는 방식에 대한 정보 및 작업 부하가 동시성 제어에 미치는 영향에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-105">[Worker thread pool events](#worker), which provide information about how an application uses the thread pool, and the effect of workloads on concurrency control.</span></span>  
  
-   <span data-ttu-id="b49a4-106">[I/O 스레드 풀 이벤트](#io). 이러한 스레드 풀 이벤트는 스레드 풀에서 생성되거나, 만료되거나, 만료되지 않거나, 종료된 I/O 스레드에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-106">[I/O thread pool events](#io), which provide information about I/O threads that are created, retired, unretired, or terminated in the thread pool.</span></span>  
  
<a name="worker"></a>   
## <a name="worker-thread-pool-events"></a><span data-ttu-id="b49a4-107">작업자 스레드 풀 이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-107">Worker Thread Pool Events</span></span>  
 <span data-ttu-id="b49a4-108">이러한 이벤트는 런타임의 작업자 스레드 풀과 관련이 있으며, 스레드 이벤트에 대한 알림을 제공합니다(예: 스레드가 만들어지거나 중지될 때).</span><span class="sxs-lookup"><span data-stu-id="b49a4-108">These events relate to the runtime's worker thread pool and provide notifications for thread events (for example, when a thread is created or stopped).</span></span> <span data-ttu-id="b49a4-109">작업자 스레드 풀은 동시성 제어를 위해 측정된 처리량을 기준으로 스레드 수가 계산되는 자동 선택 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-109">The worker thread pool uses an adaptive algorithm for concurrency control, where the number of threads is calculated based on the measured throughput.</span></span> <span data-ttu-id="b49a4-110">작업자 스레드 풀 이벤트는 응용 프로그램이 스레드 풀을 사용하는 방법 그리고 특정 작업 부하가 동시성 제어에 미칠 수 있는 영향을 이해하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-110">Worker thread pool events can be used to understand how an application is using the thread pool, and the effect that certain workloads may have on concurrency control.</span></span>  
  
### <a name="threadpoolworkerthreadstart-and-threadpoolworkerthreadstop"></a><span data-ttu-id="b49a4-111">ThreadPoolWorkerThreadStart 및 ThreadPoolWorkerThreadStop</span><span class="sxs-lookup"><span data-stu-id="b49a4-111">ThreadPoolWorkerThreadStart and ThreadPoolWorkerThreadStop</span></span>  
 <span data-ttu-id="b49a4-112">다음 표에서는 이러한 이벤트의 키워드 및 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-112">The following table shows the keyword and level for these events.</span></span> <span data-ttu-id="b49a4-113">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b49a4-113">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="b49a4-114">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b49a4-114">Keyword for raising the event</span></span>|<span data-ttu-id="b49a4-115">수준</span><span class="sxs-lookup"><span data-stu-id="b49a4-115">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b49a4-116">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b49a4-116">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b49a4-117">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b49a4-117">Informational (4)</span></span>|  
  
 <span data-ttu-id="b49a4-118">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-118">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b49a4-119">이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-119">Event</span></span>|<span data-ttu-id="b49a4-120">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b49a4-120">Event ID</span></span>|<span data-ttu-id="b49a4-121">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b49a4-121">Raised when</span></span>|  
|-|-|-|  
|`ThreadPoolWorkerThreadStart`|<span data-ttu-id="b49a4-122">50</span><span class="sxs-lookup"><span data-stu-id="b49a4-122">50</span></span>|<span data-ttu-id="b49a4-123">작업자 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-123">A worker thread is created.</span></span>|  
|`ThreadPoolWorkerThreadStop`|<span data-ttu-id="b49a4-124">51</span><span class="sxs-lookup"><span data-stu-id="b49a4-124">51</span></span>|<span data-ttu-id="b49a4-125">작업자 스레드가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-125">A worker thread is stopped.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStart`|<span data-ttu-id="b49a4-126">52</span><span class="sxs-lookup"><span data-stu-id="b49a4-126">52</span></span>|<span data-ttu-id="b49a4-127">작업자 스레드가 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-127">A worker thread retires.</span></span>|  
|`ThreadPoolWorkerThreadRetirementStop`|<span data-ttu-id="b49a4-128">53</span><span class="sxs-lookup"><span data-stu-id="b49a4-128">53</span></span>|<span data-ttu-id="b49a4-129">만료된 작업자 스레드가 다시 활성 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-129">A retired worker thread becomes active again.</span></span>|  
  
 <span data-ttu-id="b49a4-130">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-130">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b49a4-131">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b49a4-131">Field name</span></span>|<span data-ttu-id="b49a4-132">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b49a4-132">Data type</span></span>|<span data-ttu-id="b49a4-133">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-133">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b49a4-134">ActiveWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="b49a4-134">ActiveWorkerThreadCount</span></span>|<span data-ttu-id="b49a4-135">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b49a4-135">win:UInt32</span></span>|<span data-ttu-id="b49a4-136">이미 작업을 처리하고 있는 작업자 스레드를 포함하여 작업을 처리할 수 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-136">Number of worker threads available to process work, including those that are already processing work.</span></span>|  
|<span data-ttu-id="b49a4-137">RetiredWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="b49a4-137">RetiredWorkerThreadCount</span></span>|<span data-ttu-id="b49a4-138">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b49a4-138">win:UInt32</span></span>|<span data-ttu-id="b49a4-139">작업을 처리할 수 없지만, 나중에 더 많은 스레드가 필요할 때를 대비하여 유지하고 있는 작업자 스레드의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-139">Number of worker threads that are not available to process work, but that are being held in reserve in case more threads are needed later.</span></span>|  
|<span data-ttu-id="b49a4-140">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b49a4-140">ClrInstanceID</span></span>|<span data-ttu-id="b49a4-141">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b49a4-141">Win:UInt16</span></span>|<span data-ttu-id="b49a4-142">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-142">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="threadpoolworkerthreadadjustment"></a><span data-ttu-id="b49a4-143">ThreadPoolWorkerThreadAdjustment</span><span class="sxs-lookup"><span data-stu-id="b49a4-143">ThreadPoolWorkerThreadAdjustment</span></span>  
 <span data-ttu-id="b49a4-144">이러한 스레드 풀 이벤트는 스레드 삽입(동시성 제어) 알고리즘의 동작을 이해하고 디버깅하기 위한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-144">These thread pool events provide information for understanding and debugging the behavior of the thread injection (concurrency control) algorithm.</span></span> <span data-ttu-id="b49a4-145">이 정보는 작업자 스레드 풀에서 내부적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-145">The information is used internally by the worker thread pool.</span></span>  
  
#### <a name="threadpoolworkerthreadadjustmentsample"></a><span data-ttu-id="b49a4-146">ThreadPoolWorkerThreadAdjustmentSample</span><span class="sxs-lookup"><span data-stu-id="b49a4-146">ThreadPoolWorkerThreadAdjustmentSample</span></span>  
 <span data-ttu-id="b49a4-147">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-147">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b49a4-148">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b49a4-148">Keyword for raising the event</span></span>|<span data-ttu-id="b49a4-149">수준</span><span class="sxs-lookup"><span data-stu-id="b49a4-149">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b49a4-150">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b49a4-150">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b49a4-151">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b49a4-151">Informational (4)</span></span>|  
  
 <span data-ttu-id="b49a4-152">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-152">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b49a4-153">이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-153">Event</span></span>|<span data-ttu-id="b49a4-154">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b49a4-154">Event ID</span></span>|<span data-ttu-id="b49a4-155">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-155">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentSample`|<span data-ttu-id="b49a4-156">54</span><span class="sxs-lookup"><span data-stu-id="b49a4-156">54</span></span>|<span data-ttu-id="b49a4-157">한 샘플의 정보 컬렉션을 나타냅니다. 즉, 특정 시점에 특정 동시성 수준으로 처리량을 측정한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-157">Refers to the collection of information for one sample; that is, a measurement of throughput with a certain concurrency level, in an instant of time.</span></span>|  
  
 <span data-ttu-id="b49a4-158">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-158">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b49a4-159">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b49a4-159">Field name</span></span>|<span data-ttu-id="b49a4-160">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b49a4-160">Data type</span></span>|<span data-ttu-id="b49a4-161">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-161">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b49a4-162">처리량</span><span class="sxs-lookup"><span data-stu-id="b49a4-162">Throughput</span></span>|<span data-ttu-id="b49a4-163">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-163">win:Double</span></span>|<span data-ttu-id="b49a4-164">시간 단위당 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-164">Number of completions per unit of time.</span></span>|  
|<span data-ttu-id="b49a4-165">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b49a4-165">ClrInstanceID</span></span>|<span data-ttu-id="b49a4-166">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b49a4-166">Win:UInt16</span></span>|<span data-ttu-id="b49a4-167">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-167">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentadjustment"></a><span data-ttu-id="b49a4-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span><span class="sxs-lookup"><span data-stu-id="b49a4-168">ThreadPoolWorkerThreadAdjustmentAdjustment</span></span>  
 <span data-ttu-id="b49a4-169">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-169">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b49a4-170">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b49a4-170">Keyword for raising the event</span></span>|<span data-ttu-id="b49a4-171">수준</span><span class="sxs-lookup"><span data-stu-id="b49a4-171">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b49a4-172">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b49a4-172">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b49a4-173">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b49a4-173">Informational (4)</span></span>|  
  
 <span data-ttu-id="b49a4-174">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-174">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b49a4-175">이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-175">Event</span></span>|<span data-ttu-id="b49a4-176">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b49a4-176">Event ID</span></span>|<span data-ttu-id="b49a4-177">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-177">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|<span data-ttu-id="b49a4-178">55</span><span class="sxs-lookup"><span data-stu-id="b49a4-178">55</span></span>|<span data-ttu-id="b49a4-179">스레드 삽입(언덕 오르기) 알고리즘이 동시성 수준에서 변화를 감지할 때 제어의 변경을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-179">Records a change in control, when the thread injection (hill-climbing) algorithm determines that a change in concurrency level is in place.</span></span>|  
  
 <span data-ttu-id="b49a4-180">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-180">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b49a4-181">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b49a4-181">Field name</span></span>|<span data-ttu-id="b49a4-182">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b49a4-182">Data type</span></span>|<span data-ttu-id="b49a4-183">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-183">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b49a4-184">AverageThroughput</span><span class="sxs-lookup"><span data-stu-id="b49a4-184">AverageThroughput</span></span>|<span data-ttu-id="b49a4-185">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-185">win:Double</span></span>|<span data-ttu-id="b49a4-186">측정 샘플의 평균 처리량입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-186">Average throughput of a sample of measurements.</span></span>|  
|<span data-ttu-id="b49a4-187">NewWorkerThreadCount</span><span class="sxs-lookup"><span data-stu-id="b49a4-187">NewWorkerThreadCount</span></span>|<span data-ttu-id="b49a4-188">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b49a4-188">win:UInt32</span></span>|<span data-ttu-id="b49a4-189">새로운 활성 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-189">New number of active worker threads.</span></span>|  
|<span data-ttu-id="b49a4-190">이유</span><span class="sxs-lookup"><span data-stu-id="b49a4-190">Reason</span></span>|<span data-ttu-id="b49a4-191">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="b49a4-191">win:UInt32</span></span>|<span data-ttu-id="b49a4-192">조정의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-192">Reason for the adjustment.</span></span><br /><br /> <span data-ttu-id="b49a4-193">0x00 - 준비</span><span class="sxs-lookup"><span data-stu-id="b49a4-193">0x00 - Warmup.</span></span><br /><br /> <span data-ttu-id="b49a4-194">0x01 - 초기화 중</span><span class="sxs-lookup"><span data-stu-id="b49a4-194">0x01 - Initializing.</span></span><br /><br /> <span data-ttu-id="b49a4-195">0x02 - 무작위 이동</span><span class="sxs-lookup"><span data-stu-id="b49a4-195">0x02 - Random move.</span></span><br /><br /> <span data-ttu-id="b49a4-196">0x03 - 오르기 이동</span><span class="sxs-lookup"><span data-stu-id="b49a4-196">0x03 - Climbing move.</span></span><br /><br /> <span data-ttu-id="b49a4-197">0x04 - 포인트 변경</span><span class="sxs-lookup"><span data-stu-id="b49a4-197">0x04 - Change point.</span></span><br /><br /> <span data-ttu-id="b49a4-198">0x05 - 안정화 중</span><span class="sxs-lookup"><span data-stu-id="b49a4-198">0x05 - Stabilizing.</span></span><br /><br /> <span data-ttu-id="b49a4-199">0x06 - 고갈</span><span class="sxs-lookup"><span data-stu-id="b49a4-199">0x06 - Starvation.</span></span><br /><br /> <span data-ttu-id="b49a4-200">0x07 - 스레드 시간 초과</span><span class="sxs-lookup"><span data-stu-id="b49a4-200">0x07 - Thread timed out.</span></span>|  
|<span data-ttu-id="b49a4-201">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b49a4-201">ClrInstanceID</span></span>|<span data-ttu-id="b49a4-202">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b49a4-202">Win:UInt16</span></span>|<span data-ttu-id="b49a4-203">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-203">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
#### <a name="threadpoolworkerthreadadjustmentstats"></a><span data-ttu-id="b49a4-204">ThreadPoolWorkerThreadAdjustmentStats</span><span class="sxs-lookup"><span data-stu-id="b49a4-204">ThreadPoolWorkerThreadAdjustmentStats</span></span>  
 <span data-ttu-id="b49a4-205">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-205">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b49a4-206">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b49a4-206">Keyword for raising the event</span></span>|<span data-ttu-id="b49a4-207">수준</span><span class="sxs-lookup"><span data-stu-id="b49a4-207">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b49a4-208">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b49a4-208">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b49a4-209">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b49a4-209">Informational (4)</span></span>|  
  
 <span data-ttu-id="b49a4-210">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-210">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b49a4-211">이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-211">Event</span></span>|<span data-ttu-id="b49a4-212">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b49a4-212">Event ID</span></span>|<span data-ttu-id="b49a4-213">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-213">Description</span></span>|  
|-----------|--------------|-----------------|  
|`ThreadPoolWorkerThreadAdjustmentStats`|<span data-ttu-id="b49a4-214">56</span><span class="sxs-lookup"><span data-stu-id="b49a4-214">56</span></span>|<span data-ttu-id="b49a4-215">스레드 풀의 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-215">Gathers data on the thread pool.</span></span>|  
  
 <span data-ttu-id="b49a4-216">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-216">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b49a4-217">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b49a4-217">Field name</span></span>|<span data-ttu-id="b49a4-218">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b49a4-218">Data type</span></span>|<span data-ttu-id="b49a4-219">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-219">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b49a4-220">기간</span><span class="sxs-lookup"><span data-stu-id="b49a4-220">Duration</span></span>|<span data-ttu-id="b49a4-221">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-221">win:Double</span></span>|<span data-ttu-id="b49a4-222">이러한 통계가 수집된 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-222">Amount of time, in seconds, during which these statistics were collected.</span></span>|  
|<span data-ttu-id="b49a4-223">처리량</span><span class="sxs-lookup"><span data-stu-id="b49a4-223">Throughput</span></span>|<span data-ttu-id="b49a4-224">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-224">win:Double</span></span>|<span data-ttu-id="b49a4-225">이 간격 동안의 초당 평균 완료 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-225">Average number of completions per second during this interval.</span></span>|  
|<span data-ttu-id="b49a4-226">ThreadWave</span><span class="sxs-lookup"><span data-stu-id="b49a4-226">ThreadWave</span></span>|<span data-ttu-id="b49a4-227">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-227">win:Double</span></span>|<span data-ttu-id="b49a4-228">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-228">Reserved for internal use.</span></span>|  
|<span data-ttu-id="b49a4-229">ThroughputWave</span><span class="sxs-lookup"><span data-stu-id="b49a4-229">ThroughputWave</span></span>|<span data-ttu-id="b49a4-230">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-230">win:Double</span></span>|<span data-ttu-id="b49a4-231">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-231">Reserved for internal use.</span></span>|  
|<span data-ttu-id="b49a4-232">ThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="b49a4-232">ThroughputErrorEstimate</span></span>|<span data-ttu-id="b49a4-233">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-233">win:Double</span></span>|<span data-ttu-id="b49a4-234">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-234">Reserved for internal use.</span></span>|  
|<span data-ttu-id="b49a4-235">AverageThroughputErrorEstimate</span><span class="sxs-lookup"><span data-stu-id="b49a4-235">AverageThroughputErrorEstimate</span></span>|<span data-ttu-id="b49a4-236">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-236">win:Double</span></span>|<span data-ttu-id="b49a4-237">내부용으로 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-237">Reserved for internal use.</span></span>|  
|<span data-ttu-id="b49a4-238">ThroughputRatio</span><span class="sxs-lookup"><span data-stu-id="b49a4-238">ThroughputRatio</span></span>|<span data-ttu-id="b49a4-239">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-239">win:Double</span></span>|<span data-ttu-id="b49a4-240">이 간격 동안 활성 작업자 스레드 수의 변화로 인해 발생한 처리량의 상대적인 증가량입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-240">The relative improvement in throughput caused by variations in active worker thread count during this interval.</span></span>|  
|<span data-ttu-id="b49a4-241">Confidence</span><span class="sxs-lookup"><span data-stu-id="b49a4-241">Confidence</span></span>|<span data-ttu-id="b49a4-242">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-242">win:Double</span></span>|<span data-ttu-id="b49a4-243">ThroughputRatio 필드의 유효성 측정값입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-243">A measure of the validity of the ThroughputRatio field.</span></span>|  
|<span data-ttu-id="b49a4-244">NewcontrolSetting</span><span class="sxs-lookup"><span data-stu-id="b49a4-244">NewcontrolSetting</span></span>|<span data-ttu-id="b49a4-245">win:Double</span><span class="sxs-lookup"><span data-stu-id="b49a4-245">win:Double</span></span>|<span data-ttu-id="b49a4-246">활성 스레드 개수에서 미래의 변동에 대한 기준으로 사용될 활성 작업자 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-246">The number of active worker threads that will serve as the baseline for future variations in active thread count.</span></span>|  
|<span data-ttu-id="b49a4-247">NewThreadWaveMagnitude</span><span class="sxs-lookup"><span data-stu-id="b49a4-247">NewThreadWaveMagnitude</span></span>|<span data-ttu-id="b49a4-248">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b49a4-248">Win:UInt16</span></span>|<span data-ttu-id="b49a4-249">활성 스레드 개수에서 미래 변동의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-249">The magnitude of future variations in active thread count.</span></span>|  
|<span data-ttu-id="b49a4-250">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b49a4-250">ClrInstanceID</span></span>|<span data-ttu-id="b49a4-251">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b49a4-251">Win:UInt16</span></span>|<span data-ttu-id="b49a4-252">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-252">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b49a4-253">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="b49a4-253">Back to top</span></span>](#top)  
  
<a name="io"></a>   
## <a name="io-thread-events"></a><span data-ttu-id="b49a4-254">I/O 스레드 이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-254">I/O Thread Events</span></span>  
 <span data-ttu-id="b49a4-255">이러한 스레드 풀 이벤트는 비동기적인 I/O 스레드 풀(완료 포트)에서 스레드에 대해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-255">These thread pool events occur for threads in the I/O thread pool (completion ports), which is asynchronous.</span></span>  
  
### <a name="iothreadcreatev1"></a><span data-ttu-id="b49a4-256">IOThreadCreate_V1</span><span class="sxs-lookup"><span data-stu-id="b49a4-256">IOThreadCreate_V1</span></span>  
 <span data-ttu-id="b49a4-257">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-257">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b49a4-258">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b49a4-258">Keyword for raising the event</span></span>|<span data-ttu-id="b49a4-259">수준</span><span class="sxs-lookup"><span data-stu-id="b49a4-259">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b49a4-260">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b49a4-260">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b49a4-261">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b49a4-261">Informational (4)</span></span>|  
  
 <span data-ttu-id="b49a4-262">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-262">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b49a4-263">이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-263">Event</span></span>|<span data-ttu-id="b49a4-264">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b49a4-264">Event ID</span></span>|<span data-ttu-id="b49a4-265">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b49a4-265">Raised when</span></span>|  
|-|-|-|  
|`IOThreadCreate_V1`|<span data-ttu-id="b49a4-266">44</span><span class="sxs-lookup"><span data-stu-id="b49a4-266">44</span></span>|<span data-ttu-id="b49a4-267">스레드 풀에서 I/O 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-267">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="b49a4-268">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-268">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b49a4-269">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b49a4-269">Field name</span></span>|<span data-ttu-id="b49a4-270">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b49a4-270">Data type</span></span>|<span data-ttu-id="b49a4-271">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-271">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b49a4-272">개수</span><span class="sxs-lookup"><span data-stu-id="b49a4-272">Count</span></span>|<span data-ttu-id="b49a4-273">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b49a4-273">win:UInt64</span></span>|<span data-ttu-id="b49a4-274">새로 생성된 스레드를 포함한 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-274">Number of I/O threads, including the newly created thread.</span></span>|  
|<span data-ttu-id="b49a4-275">NumRetired</span><span class="sxs-lookup"><span data-stu-id="b49a4-275">NumRetired</span></span>|<span data-ttu-id="b49a4-276">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b49a4-276">win:UInt64</span></span>|<span data-ttu-id="b49a4-277">만료된 작업자 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-277">Number of retired worker threads.</span></span>|  
|<span data-ttu-id="b49a4-278">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b49a4-278">ClrInstanceID</span></span>|<span data-ttu-id="b49a4-279">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b49a4-279">Win:UInt16</span></span>|<span data-ttu-id="b49a4-280">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-280">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadretirev1"></a><span data-ttu-id="b49a4-281">IOThreadRetire_V1</span><span class="sxs-lookup"><span data-stu-id="b49a4-281">IOThreadRetire_V1</span></span>  
 <span data-ttu-id="b49a4-282">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-282">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b49a4-283">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b49a4-283">Keyword for raising the event</span></span>|<span data-ttu-id="b49a4-284">수준</span><span class="sxs-lookup"><span data-stu-id="b49a4-284">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b49a4-285">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b49a4-285">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b49a4-286">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b49a4-286">Informational (4)</span></span>|  
  
 <span data-ttu-id="b49a4-287">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-287">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b49a4-288">이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-288">Event</span></span>|<span data-ttu-id="b49a4-289">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b49a4-289">Event ID</span></span>|<span data-ttu-id="b49a4-290">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b49a4-290">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadRetire_V1`|<span data-ttu-id="b49a4-291">46</span><span class="sxs-lookup"><span data-stu-id="b49a4-291">46</span></span>|<span data-ttu-id="b49a4-292">I/O 스레드가 만료 후보가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-292">An I/O thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="b49a4-293">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-293">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b49a4-294">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b49a4-294">Field name</span></span>|<span data-ttu-id="b49a4-295">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b49a4-295">Data type</span></span>|<span data-ttu-id="b49a4-296">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-296">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b49a4-297">개수</span><span class="sxs-lookup"><span data-stu-id="b49a4-297">Count</span></span>|<span data-ttu-id="b49a4-298">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b49a4-298">win:UInt64</span></span>|<span data-ttu-id="b49a4-299">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-299">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="b49a4-300">NumRetired</span><span class="sxs-lookup"><span data-stu-id="b49a4-300">NumRetired</span></span>|<span data-ttu-id="b49a4-301">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b49a4-301">win:UInt64</span></span>|<span data-ttu-id="b49a4-302">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-302">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="b49a4-303">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b49a4-303">ClrInstanceID</span></span>|<span data-ttu-id="b49a4-304">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b49a4-304">Win:UInt16</span></span>|<span data-ttu-id="b49a4-305">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-305">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadunretirev1"></a><span data-ttu-id="b49a4-306">IOThreadUnretire_V1</span><span class="sxs-lookup"><span data-stu-id="b49a4-306">IOThreadUnretire_V1</span></span>  
 <span data-ttu-id="b49a4-307">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-307">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b49a4-308">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b49a4-308">Keyword for raising the event</span></span>|<span data-ttu-id="b49a4-309">수준</span><span class="sxs-lookup"><span data-stu-id="b49a4-309">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b49a4-310">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b49a4-310">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b49a4-311">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b49a4-311">Informational (4)</span></span>|  
  
 <span data-ttu-id="b49a4-312">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-312">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b49a4-313">이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-313">Event</span></span>|<span data-ttu-id="b49a4-314">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b49a4-314">Event ID</span></span>|<span data-ttu-id="b49a4-315">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b49a4-315">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadUnretire_V1`|<span data-ttu-id="b49a4-316">47</span><span class="sxs-lookup"><span data-stu-id="b49a4-316">47</span></span>|<span data-ttu-id="b49a4-317">스레드가 만료 후보가 된 후 대기 기간 내에 도착하는 I/O 때문에 I/O 스레드가 만료 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-317">An I/O thread is unretired because of I/O that arrives within a waiting period after the thread becomes a retirement candidate.</span></span>|  
  
 <span data-ttu-id="b49a4-318">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-318">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b49a4-319">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b49a4-319">Field name</span></span>|<span data-ttu-id="b49a4-320">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b49a4-320">Data type</span></span>|<span data-ttu-id="b49a4-321">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-321">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b49a4-322">개수</span><span class="sxs-lookup"><span data-stu-id="b49a4-322">Count</span></span>|<span data-ttu-id="b49a4-323">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b49a4-323">win:UInt64</span></span>|<span data-ttu-id="b49a4-324">이 스레드를 포함하여 스레드 풀에 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-324">Number of I/O threads in the thread pool, including this one.</span></span>|  
|<span data-ttu-id="b49a4-325">NumRetired</span><span class="sxs-lookup"><span data-stu-id="b49a4-325">NumRetired</span></span>|<span data-ttu-id="b49a4-326">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b49a4-326">win:UInt64</span></span>|<span data-ttu-id="b49a4-327">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-327">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="b49a4-328">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b49a4-328">ClrInstanceID</span></span>|<span data-ttu-id="b49a4-329">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b49a4-329">Win:UInt16</span></span>|<span data-ttu-id="b49a4-330">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-330">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
### <a name="iothreadterminate"></a><span data-ttu-id="b49a4-331">IOThreadTerminate</span><span class="sxs-lookup"><span data-stu-id="b49a4-331">IOThreadTerminate</span></span>  
 <span data-ttu-id="b49a4-332">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-332">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b49a4-333">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="b49a4-333">Keyword for raising the event</span></span>|<span data-ttu-id="b49a4-334">수준</span><span class="sxs-lookup"><span data-stu-id="b49a4-334">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b49a4-335">`ThreadingKeyword` (0x10000)</span><span class="sxs-lookup"><span data-stu-id="b49a4-335">`ThreadingKeyword` (0x10000)</span></span>|<span data-ttu-id="b49a4-336">정보(4)</span><span class="sxs-lookup"><span data-stu-id="b49a4-336">Informational (4)</span></span>|  
  
 <span data-ttu-id="b49a4-337">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-337">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b49a4-338">이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-338">Event</span></span>|<span data-ttu-id="b49a4-339">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="b49a4-339">Event ID</span></span>|<span data-ttu-id="b49a4-340">발생 시기</span><span class="sxs-lookup"><span data-stu-id="b49a4-340">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`IOThreadTerminate`|<span data-ttu-id="b49a4-341">45</span><span class="sxs-lookup"><span data-stu-id="b49a4-341">45</span></span>|<span data-ttu-id="b49a4-342">스레드 풀에서 I/O 스레드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-342">An I/O thread is created in the thread pool.</span></span>|  
  
 <span data-ttu-id="b49a4-343">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-343">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b49a4-344">필드 이름</span><span class="sxs-lookup"><span data-stu-id="b49a4-344">Field name</span></span>|<span data-ttu-id="b49a4-345">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b49a4-345">Data type</span></span>|<span data-ttu-id="b49a4-346">설명</span><span class="sxs-lookup"><span data-stu-id="b49a4-346">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b49a4-347">개수</span><span class="sxs-lookup"><span data-stu-id="b49a4-347">Count</span></span>|<span data-ttu-id="b49a4-348">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b49a4-348">win:UInt64</span></span>|<span data-ttu-id="b49a4-349">스레드 풀에 남아 있는 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-349">Number of I/O threads remaining in the thread pool.</span></span>|  
|<span data-ttu-id="b49a4-350">NumRetired</span><span class="sxs-lookup"><span data-stu-id="b49a4-350">NumRetired</span></span>|<span data-ttu-id="b49a4-351">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="b49a4-351">win:UInt64</span></span>|<span data-ttu-id="b49a4-352">만료된 I/O 스레드의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-352">Number of retired I/O threads.</span></span>|  
|<span data-ttu-id="b49a4-353">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b49a4-353">ClrInstanceID</span></span>|<span data-ttu-id="b49a4-354">Win:UInt16</span><span class="sxs-lookup"><span data-stu-id="b49a4-354">Win:UInt16</span></span>|<span data-ttu-id="b49a4-355">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b49a4-355">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b49a4-356">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b49a4-356">See Also</span></span>  
 [<span data-ttu-id="b49a4-357">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="b49a4-357">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
