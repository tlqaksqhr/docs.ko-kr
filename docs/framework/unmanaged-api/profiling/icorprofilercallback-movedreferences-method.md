---
title: "ICorProfilerCallback::MovedReferences 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.MovedReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type: apiref
caps.latest.revision: "26"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 424694770bac05611288279b2b42992a17afaa6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackmovedreferences-method"></a><span data-ttu-id="6e701-102">ICorProfilerCallback::MovedReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="6e701-102">ICorProfilerCallback::MovedReferences Method</span></span>
<span data-ttu-id="6e701-103">압축 가비지 컬렉션의 결과로 힙에 있는 개체의 새 레이아웃을 보고하려고 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-103">Called to report the new layout of objects in the heap as a result of a compacting garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e701-104">구문</span><span class="sxs-lookup"><span data-stu-id="6e701-104">Syntax</span></span>  
  
```  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e701-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e701-105">Parameters</span></span>  
 `cMovedObjectIDRanges`  
 <span data-ttu-id="6e701-106">[in] 압축 가비지 컬렉션 후에 이동된 연속 개체 블록 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-106">[in] The number of blocks of contiguous objects that moved as the result of the compacting garbage collection.</span></span> <span data-ttu-id="6e701-107">즉, `cMovedObjectIDRanges` 값은 `oldObjectIDRangeStart`, `newObjectIDRangeStart` 및 `cObjectIDRangeLength` 배열의 총 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-107">That is, the value of `cMovedObjectIDRanges` is the total size of the `oldObjectIDRangeStart`, `newObjectIDRangeStart`, and `cObjectIDRangeLength` arrays.</span></span>  
  
 <span data-ttu-id="6e701-108">`MovedReferences`의 다음 세 인수는 병렬 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-108">The next three arguments of `MovedReferences` are parallel arrays.</span></span> <span data-ttu-id="6e701-109">즉, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` 및 `cObjectIDRangeLength[i]`는 모두 단일 연속 개체 블록과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-109">In other words, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]`, and `cObjectIDRangeLength[i]` all concern a single block of contiguous objects.</span></span>  
  
 `oldObjectIDRangeStart`  
 <span data-ttu-id="6e701-110">[in] 메모리에서 연속 라이브 개체 블록의 이전(가비지 수집 전) 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-110">[in] An array of `ObjectID` values, each of which is the old (pre-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `newObjectIDRangeStart`  
 <span data-ttu-id="6e701-111">[in] 메모리에서 연속 라이브 개체 블록의 새(가비지 수집 후) 시작 주소를 각각 나타내는 `ObjectID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-111">[in] An array of `ObjectID` values, each of which is the new (post-garbage collection) starting address of a block of contiguous, live objects in memory.</span></span>  
  
 `cObjectIDRangeLength`  
 <span data-ttu-id="6e701-112">[in] 메모리의 연속 개체 블록의 크기를 각각 나타내는 정수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-112">[in] An array of integers, each of which is the size of a block of contiguous objects in memory.</span></span>  
  
 <span data-ttu-id="6e701-113">크기는 `oldObjectIDRangeStart` 및 `newObjectIDRangeStart` 배열에서 참조된 각 블록에 대해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-113">A size is specified for each block that is referenced in the `oldObjectIDRangeStart` and `newObjectIDRangeStart` arrays.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6e701-114">설명</span><span class="sxs-lookup"><span data-stu-id="6e701-114">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6e701-115">이 메서드는 64비트 플랫폼에서 4GB보다 큰 개체의 크기를 `MAX_ULONG`으로 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-115">This method reports sizes as `MAX_ULONG` for objects that are greater than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="6e701-116">4GB 보다 큰 경우에 개체의 크기를 가져오려면는 [icorprofilercallback4:: Movedreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-116">To get the size of objects that are larger than 4 GB, use the [ICorProfilerCallback4::MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="6e701-117">압축 가비지 수집기는 데드 개체가 사용한 메모리를 회수하고 확보된 공간을 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-117">A compacting garbage collector reclaims the memory occupied by dead objects and compacts that freed space.</span></span> <span data-ttu-id="6e701-118">따라서 라이브 개체가 힙 내에서 이동될 수 있고 이전 알림으로 분산된 `ObjectID` 값이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-118">As a result, live objects might be moved within the heap, and `ObjectID` values distributed by previous notifications might change.</span></span>  
  
 <span data-ttu-id="6e701-119">기존 `ObjectID` 값(`oldObjectID`)이 다음 범위 내에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-119">Assume that an existing `ObjectID` value (`oldObjectID`) lies within the following range:</span></span>  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 <span data-ttu-id="6e701-120">이 경우 범위 시작부터 개체 시작까지 오프셋은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-120">In this case, the offset from the start of the range to the start of the object is as follows:</span></span>  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 <span data-ttu-id="6e701-121">다음 범위에 있는 `i` 값에 대해</span><span class="sxs-lookup"><span data-stu-id="6e701-121">For any value of `i` that is in the following range:</span></span>  
  
 <span data-ttu-id="6e701-122">0 <= `i` < `cMovedObjectIDRanges`</span><span class="sxs-lookup"><span data-stu-id="6e701-122">0 <= `i` < `cMovedObjectIDRanges`</span></span>  
  
 <span data-ttu-id="6e701-123">새 `ObjectID`를 다음과 같이 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-123">you can calculate the new `ObjectID` as follows:</span></span>  
  
 <span data-ttu-id="6e701-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span><span class="sxs-lookup"><span data-stu-id="6e701-124">`newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)</span></span>  
  
 <span data-ttu-id="6e701-125">콜백 자체가 진행되는 동안 `MovedReferences`를 통해 전달된 `ObjectID` 값은 유효하지 않습니다. 가비지 수집이 이전 위치에서 새 위치로 개체를 이동하는 중일 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-125">None of the `ObjectID` values passed by `MovedReferences` are valid during the callback itself, because the garbage collection might be in the middle of moving objects from old locations to new locations.</span></span> <span data-ttu-id="6e701-126">그러므로 프로파일러는 `MovedReferences` 호출 중에 개체 검사를 시도하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-126">Therefore, profilers should not attempt to inspect objects during a `MovedReferences` call.</span></span> <span data-ttu-id="6e701-127">A [icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 콜백은 모든 개체가 새 위치로 이동 되었고 검사가 수행 될 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-127">A [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indicates that all objects have been moved to their new locations and inspection can be performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e701-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e701-128">Requirements</span></span>  
 <span data-ttu-id="6e701-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6e701-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e701-130">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6e701-130">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6e701-131">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6e701-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6e701-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e701-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e701-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e701-133">See Also</span></span>  
 [<span data-ttu-id="6e701-134">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e701-134">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="6e701-135">MovedReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="6e701-135">MovedReferences2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)  
 [<span data-ttu-id="6e701-136">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e701-136">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="6e701-137">프로파일링</span><span class="sxs-lookup"><span data-stu-id="6e701-137">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
