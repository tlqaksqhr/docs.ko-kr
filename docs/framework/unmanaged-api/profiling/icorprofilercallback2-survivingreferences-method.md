---
title: "ICorProfilerCallback2::SurvivingReferences 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback2.SurvivingReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::SurvivingReferences
helpviewer_keywords:
- ICorProfilerCallback2::SurvivingReferences method [.NET Framework profiling]
- SurvivingReferences method [.NET Framework profiling]
ms.assetid: f165200e-3a91-47f7-88fc-13ff10c8babc
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69bbc5a907a0c6061da877e93ccf1312ea67c826
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2survivingreferences-method"></a><span data-ttu-id="5a70c-102">ICorProfilerCallback2::SurvivingReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="5a70c-102">ICorProfilerCallback2::SurvivingReferences Method</span></span>
<span data-ttu-id="5a70c-103">비압축 가비지 컬렉션의 결과로 힙에 있는 개체의 레이아웃을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a70c-104">구문</span><span class="sxs-lookup"><span data-stu-id="5a70c-104">Syntax</span></span>  
  
```  
HRESULT SurvivingReferences(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] ULONG  
                cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a70c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a70c-105">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="5a70c-106">[in] 비압축 가비지 컬렉션 후에 유지된 연속 개체 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-106">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="5a70c-107">즉, `cSurvivingObjectIDRanges` 값은 각 개체 블록의 `ObjectID` 및 길이를 각각 저장하는 `objectIDRangeStart` 및 `cObjectIDRangeLength` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-107">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="5a70c-108">`SurvivingReferences`의 다음 두 인수는 병렬 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-108">The next two arguments of `SurvivingReferences` are parallel arrays.</span></span> <span data-ttu-id="5a70c-109">즉, `objectIDRangeStart` 및 `cObjectIDRangeLength`는 동일한 연속 개체 블록과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-109">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="5a70c-110">[in] 메모리에서 연속 라이브 개체 블록의 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-110">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="5a70c-111">[in] 메모리에 유지되는 연속 개체 블록의 크기를 각각 나타내는 정수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-111">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="5a70c-112">크기는 `objectIDRangeStart` 배열에서 참조된 각 블록에 대해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-112">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a70c-113">설명</span><span class="sxs-lookup"><span data-stu-id="5a70c-113">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5a70c-114">이 메서드는 64비트 플랫폼에서 4GB보다 큰 개체의 크기를 `MAX_ULONG`으로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-114">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="5a70c-115">4GB 보다 큰 경우에 개체를 사용 하 여는 [icorprofilercallback4:: Survivingreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-115">For objects that are larger than 4 GB, use the [ICorProfilerCallback4::SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="5a70c-116">개체가 가비지 수집 후에 유지되었는지 여부를 확인하려면 `objectIDRangeStart` 및 `cObjectIDRangeLength` 배열의 요소를 다음과 같이 해석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="5a70c-117">`ObjectID` 값(`ObjectID`)이 다음 범위 내에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="5a70c-118">`i` 값이 다음 범위에 있는 경우 개체가 가비지 수집 후에 유지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="5a70c-119">0 <= `i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="5a70c-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="5a70c-120">비압축 가비지 컬렉션은 "데드" 개체가 사용한 메모리를 회수하지만 확보된 공간을 압축하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="5a70c-121">따라서 메모리가 힙에 반환되지만 "라이브" 개체는 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="5a70c-122">CLR(공용 언어 런타임)은 비압축 가비지 수집을 위해 `SurvivingReferences`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-122">The common language runtime (CLR) calls `SurvivingReferences` for non-compacting garbage collections.</span></span> <span data-ttu-id="5a70c-123">압축 가비지 컬렉션에 대 한 [icorprofilercallback:: Movedreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) 대신 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-123">For compacting garbage collections, [ICorProfilerCallback::MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) is called instead.</span></span> <span data-ttu-id="5a70c-124">한 세대는 단일 가비지 컬렉션을 압축하고 다른 세대는 압축하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="5a70c-125">특정 세대의 가비지 수집에 대해 프로파일러는 `SurvivingReferences` 콜백이나 `MovedReferences` 콜백 중 하나를 받게 되며 둘 다 받을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences` callback or a `MovedReferences` callback, but not both.</span></span>  
  
 <span data-ttu-id="5a70c-126">제한된 내부 버퍼링, 서버 가비지 수집 시 여러 스레드 보고 및 기타 이유로 인해 특정 가비지 수집 중 `SurvivingReferences` 콜백을 여러 개 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-126">Multiple `SurvivingReferences` callbacks might be received during a particular garbage collection, due to limited internal buffering, multiple threads reporting in the case of server garbage collection, and other reasons.</span></span> <span data-ttu-id="5a70c-127">가비지 수집 중 여러 콜백이 발생하는 경우 정보가 누적됩니다. `SurvivingReferences` 콜백에 보고된 모든 참조가 가비지 수집 후에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-127">In the case of multiple callbacks during a garbage collection, the information is cumulative — all references that are reported in any `SurvivingReferences` callback survive the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a70c-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a70c-128">Requirements</span></span>  
 <span data-ttu-id="5a70c-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5a70c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a70c-130">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a70c-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a70c-131">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a70c-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a70c-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a70c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a70c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a70c-133">See Also</span></span>  
 [<span data-ttu-id="5a70c-134">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a70c-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="5a70c-135">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a70c-135">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="5a70c-136">SurvivingReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="5a70c-136">SurvivingReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)
