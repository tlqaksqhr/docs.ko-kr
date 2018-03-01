---
title: "ICorProfilerCallback4::SurvivingReferences2 메서드"
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
- ICorProfilerCallback4.SurvivingReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::SurvivingReferences2
helpviewer_keywords:
- ICorProfilerCallback4::SurvivingReferences2 method [.NET Framework profiling]
- SurvivingReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 02b51888-5d89-4e50-a915-45b7e329aad9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db40e908421c45e9d4192c436995d8137f81ec0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4survivingreferences2-method"></a><span data-ttu-id="3991b-102">ICorProfilerCallback4::SurvivingReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="3991b-102">ICorProfilerCallback4::SurvivingReferences2 Method</span></span>
<span data-ttu-id="3991b-103">비압축 가비지 컬렉션의 결과로 힙에 있는 개체의 레이아웃을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-103">Reports the layout of objects in the heap as a result of a non-compacting garbage collection.</span></span> <span data-ttu-id="3991b-104">이 메서드는 프로파일러가 구현한 경우에 [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-104">This method is called if the profiler has implemented the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interface.</span></span> <span data-ttu-id="3991b-105">이 콜백은 대체는 [icorprofilercallback2:: Survivingreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) 메서드를 큰 길이가 ULONG으로 표현 될 수 있는 길이 초과 하는 개체 범위를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-105">This callback replaces the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, because it can report larger ranges of objects whose lengths exceed what can be expressed in a ULONG.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3991b-106">구문</span><span class="sxs-lookup"><span data-stu-id="3991b-106">Syntax</span></span>  
  
```  
HRESULT SurvivingReferences2(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] SIZE_T  
                cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3991b-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3991b-107">Parameters</span></span>  
 `cSurvivingObjectIDRanges`  
 <span data-ttu-id="3991b-108">[in] 비압축 가비지 컬렉션 후에 유지된 연속 개체 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-108">[in] The number of blocks of contiguous objects that survived as the result of the non-compacting garbage collection.</span></span> <span data-ttu-id="3991b-109">즉, `cSurvivingObjectIDRanges` 값은 각 개체 블록의 `ObjectID` 및 길이를 각각 저장하는 `objectIDRangeStart` 및 `cObjectIDRangeLength` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-109">That is, the value of `cSurvivingObjectIDRanges` is the size of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays, which store an `ObjectID` and a length, respectively, for each block of objects.</span></span>  
  
 <span data-ttu-id="3991b-110">`SurvivingReferences2`의 다음 두 인수는 병렬 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-110">The next two arguments of `SurvivingReferences2` are parallel arrays.</span></span> <span data-ttu-id="3991b-111">즉, `objectIDRangeStart` 및 `cObjectIDRangeLength`는 동일한 연속 개체 블록과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-111">In other words, `objectIDRangeStart` and `cObjectIDRangeLength` concern the same block of contiguous objects.</span></span>  
  
 `objectIDRangeStart`  
 <span data-ttu-id="3991b-112">[in] 메모리에서 연속 라이브 개체 블록의 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-112">[in] An array of `ObjectID` values, each of which is the starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="3991b-113">[in] 메모리에 유지되는 연속 개체 블록의 크기를 각각 나타내는 정수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-113">[in] An array of integers, each of which is the size of a surviving block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="3991b-114">크기는 `objectIDRangeStart` 배열에서 참조된 각 블록에 대해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-114">A size is specified for each block that is referenced in the `objectIDRangeStart` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3991b-115">설명</span><span class="sxs-lookup"><span data-stu-id="3991b-115">Remarks</span></span>  
 <span data-ttu-id="3991b-116">개체가 가비지 수집 후에 유지되었는지 여부를 확인하려면 `objectIDRangeStart` 및 `cObjectIDRangeLength` 배열의 요소를 다음과 같이 해석해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-116">The elements of the `objectIDRangeStart` and `cObjectIDRangeLength` arrays should be interpreted as follows to determine whether an object survived the garbage collection.</span></span> <span data-ttu-id="3991b-117">`ObjectID` 값(`ObjectID`)이 다음 범위 내에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-117">Assume that an `ObjectID` value (`ObjectID`) lies within the following range:</span></span>  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="3991b-118">`i` 값이 다음 범위에 있는 경우 개체가 가비지 수집 후에 유지되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-118">For any value of `i` that is in the following range, the object has survived the garbage collection:</span></span>  
  
 <span data-ttu-id="3991b-119">0 <= `i` < `cSurvivingObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="3991b-119">0 <= `i` < `cSurvivingObjectIDRanges`</span></span>  
  
 <span data-ttu-id="3991b-120">비압축 가비지 컬렉션은 "데드" 개체가 사용한 메모리를 회수하지만 확보된 공간을 압축하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-120">A non-compacting garbage collection reclaims the memory occupied by "dead" objects, but does not compact that freed space.</span></span> <span data-ttu-id="3991b-121">따라서 메모리가 힙에 반환되지만 "라이브" 개체는 이동되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-121">As a result, memory is returned to the heap, but no "live" objects are moved.</span></span>  
  
 <span data-ttu-id="3991b-122">CLR(공용 언어 런타임)은 비압축 가비지 수집을 위해 `SurvivingReferences2`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-122">The common language runtime (CLR) calls `SurvivingReferences2` for non-compacting garbage collections.</span></span> <span data-ttu-id="3991b-123">압축 가비지 컬렉션에 대 한 [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) 대신 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-123">For compacting garbage collections, [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) is called instead.</span></span> <span data-ttu-id="3991b-124">한 세대는 단일 가비지 컬렉션을 압축하고 다른 세대는 압축하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-124">A single garbage collection can be compacting for one generation and non-compacting for another.</span></span> <span data-ttu-id="3991b-125">특정 세대의 가비지 수집에 대 한 프로파일러 중 하나를 받거나는 `SurvivingReferences2` 콜백 또는 [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) 콜백을 다르다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-125">For a garbage collection on any particular generation, the profiler will receive either a `SurvivingReferences2` callback or a [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) callback, but not both.</span></span>  
  
 <span data-ttu-id="3991b-126">제한된 내부 버퍼링, 서버 가비지 수집 중 여러 콜백 발생 및 기타 이유로 인해 특정 가비지 수집 중 `SurvivingReferences2` 콜백을 여러 개 받을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-126">Multiple `SurvivingReferences2` callbacks might be received during a particular garbage collection, because of limited internal buffering, multiple callbacks during server garbage collection, and other reasons.</span></span> <span data-ttu-id="3991b-127">가비지 수집 중 여러 콜백이 발생하는 경우 정보가 누적됩니다. `SurvivingReferences2` 콜백에 보고된 모든 참조가 가비지 수집 후에 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-127">In the case of multiple callbacks during a garbage collection, the information is cumulative; all references that are reported in any `SurvivingReferences2` callback survive the garbage collection.</span></span>  
  
 <span data-ttu-id="3991b-128">프로파일러 둘 다를 구현 하는 경우는 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 및 [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) 인터페이스는 `SurvivingReferences2` 전에 메서드가 호출 되는 [ICorProfilerCallback2:: SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) 메서드이지만 경우에만 `SurvivingReferences2` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-128">If the profiler implements both the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and the [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaces, the `SurvivingReferences2` method is called before the [ICorProfilerCallback2::SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md) method, but only if `SurvivingReferences2` returns successfully.</span></span> <span data-ttu-id="3991b-129">프로파일러는 두 번째 메서드 호출을 방지하기 위해 `SurvivingReferences2` 메서드에서 실패를 나타내는 HRESULT를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-129">Profilers can return an HRESULT that indicates failure from the `SurvivingReferences2` method to avoid calling the second method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3991b-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3991b-130">Requirements</span></span>  
 <span data-ttu-id="3991b-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3991b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3991b-132">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3991b-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3991b-133">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3991b-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3991b-134">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3991b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3991b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3991b-135">See Also</span></span>  
 [<span data-ttu-id="3991b-136">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3991b-136">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="3991b-137">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3991b-137">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [<span data-ttu-id="3991b-138">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3991b-138">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
