---
title: "ICorProfilerCallback2::GarbageCollectionStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b721b990312f9acda5c9e0208f998793735d2cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="55bb5-102">ICorProfilerCallback2::GarbageCollectionStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="55bb5-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="55bb5-103">가비지 수집이 시작 되었음을 코드 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55bb5-104">구문</span><span class="sxs-lookup"><span data-stu-id="55bb5-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55bb5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55bb5-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="55bb5-106">[in] 에 있는 항목의 총 수는 `generationCollected` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="55bb5-107">[in] 되는 부울 값의 배열을 `true` 세대 인덱스에 해당 하 고, 그렇지 않으면이 가비지 수집에 의해 수집 되 고 있으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="55bb5-108">배열의 값을 기준으로 인덱싱되어 있으면는 [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) 생성을 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="55bb5-109">[in] 값은 [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) 가비지 수집 이유를 나타내는 열거형에서 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55bb5-110">설명</span><span class="sxs-lookup"><span data-stu-id="55bb5-110">Remarks</span></span>  
 <span data-ttu-id="55bb5-111">이 가비지 컬렉션에 속하는 모든 콜백이 간에 발생 합니다는 `GarbageCollectionStarted` 콜백 및 해당 [icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="55bb5-112">이러한 콜백은 동일한 스레드에서 발생 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="55bb5-113">이 하는 동안 원래 위치에 개체 검사를 프로파일러에 대 한 안전는 `GarbageCollectionStarted` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="55bb5-114">가비지 수집기에서 반환 된 후 개체 이동을 시작 됩니다 `GarbageCollectionStarted`합니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="55bb5-115">프로파일러 모든 개체 Id를 받을 때까지 유효 하지 않은 것을 고려해 야이 콜백에서 반환 된, 후는 `ICorProfilerCallback2::GarbageCollectionFinished` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55bb5-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55bb5-116">Requirements</span></span>  
 <span data-ttu-id="55bb5-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="55bb5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55bb5-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55bb5-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55bb5-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55bb5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55bb5-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55bb5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55bb5-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55bb5-121">See Also</span></span>  
 [<span data-ttu-id="55bb5-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55bb5-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="55bb5-123">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55bb5-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
