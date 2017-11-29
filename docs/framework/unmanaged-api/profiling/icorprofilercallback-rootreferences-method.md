---
title: "ICorProfilerCallback::RootReferences 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RootReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a12dec1ed0fecad235090592def9689f60e50193
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="3224d-102">ICorProfilerCallback::RootReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="3224d-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="3224d-103">가비지 수집 후 루트 참조에 대 한 정보를 프로파일러를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3224d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3224d-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3224d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3224d-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="3224d-106">[in] 에 대 한 참조 횟수는 `rootRefIds` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="3224d-107">[in] 스택에 개체 또는 정적 개체가 참조 하는 개체 Id의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3224d-108">설명</span><span class="sxs-lookup"><span data-stu-id="3224d-108">Remarks</span></span>  
 <span data-ttu-id="3224d-109">둘 다 `RootReferences` 및 [icorprofilercallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) 프로파일러에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="3224d-110">하나 또는 다른 프로파일러 일반적으로 구현 둘 정보에 전달 되므로 `RootReferences2` 전달의 상위 집합 `RootReferences`합니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="3224d-111">에 대 한 수의 `rootRefIds` null 개체가 포함 될 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="3224d-112">예를 들어 스택에 선언 된 모든 개체 참조는 가비지 수집기에서 루트로 처리 되 고 항상 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="3224d-113">반환 된 개체 Id `RootReferences` 가비지 수집 이전 주소에서 새 주소 개체를 이동 하는 중일 수 있으므로 콜백 하는 동안 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="3224d-114">따라서 프로파일러 마십시오 중에 개체 검사는 `RootReferences` 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="3224d-115">때 [icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 은 호출 개체를 모두 새 위치로 이동 되었고 안전 하 게 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3224d-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3224d-116">Requirements</span></span>  
 <span data-ttu-id="3224d-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3224d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3224d-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3224d-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3224d-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3224d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3224d-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3224d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3224d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3224d-121">See Also</span></span>  
 [<span data-ttu-id="3224d-122">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3224d-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
