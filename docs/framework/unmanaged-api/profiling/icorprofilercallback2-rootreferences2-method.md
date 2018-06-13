---
title: ICorProfilerCallback2::RootReferences2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.RootReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: abf92749e1139a85ea2f49fb5d5caff69ce39c24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458463"
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="ff68c-102">ICorProfilerCallback2::RootReferences2 메서드</span><span class="sxs-lookup"><span data-stu-id="ff68c-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="ff68c-103">가비지 컬렉션이 발생 한 후 루트 참조에 대 한 프로파일러를 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="ff68c-104">이 메서드는의 확장은 [icorprofilercallback:: Rootreferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ff68c-104">This method is an extension of the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff68c-105">구문</span><span class="sxs-lookup"><span data-stu-id="ff68c-105">Syntax</span></span>  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff68c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff68c-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="ff68c-107">[in] 에 있는 요소의 수는 `rootRefIds`, `rootKinds`, `rootFlags`, 및 `rootIds` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="ff68c-108">[in] 개체 Id, 스택에 개체 또는 정적 개체는 각각 참조의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="ff68c-109">요소는 `rootKinds` 의 해당 요소를 분류 하는 정보를 제공 하는 배열은 `rootRefIds` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="ff68c-110">[in] 배열을 [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) 가비지 수집 루트 형식을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-110">[in] An array of [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="ff68c-111">[in] 배열을 [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) 가비지 수집 루트의 속성을 설명 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="ff68c-112">[in] UINT_PTR 값의 배열 값에 따라 가비지 수집 루트에 대 한 추가 정보를 포함 하는 정수를 해당 지점에서 `rootKinds` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="ff68c-113">루트의 유형이 스택을 인 루트 ID 변수를 포함 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="ff68c-114">루트 ID가 0 이면 함수는는 명명 되지 않은 함수는 CLR에 내부입니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="ff68c-115">루트의 유형이 핸들 인 경우 가비지 컬렉션 핸들에 대 한 루트 ID가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="ff68c-116">다른 루트 형식에 대 한 ID는 불투명 값 이므로 무시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff68c-117">설명</span><span class="sxs-lookup"><span data-stu-id="ff68c-117">Remarks</span></span>  
 <span data-ttu-id="ff68c-118">`rootRefIds`, `rootKinds`, `rootFlags`, 및 `rootIds` 배열은 병렬 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="ff68c-119">즉, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, 및 `rootIds[i]` 모두 동일한 루트를 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="ff68c-120">둘 다 `RootReferences` 및 `RootReferences2` 프로파일러에 알리기 위해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="ff68c-121">프로파일러 됩니다 일반적으로 한 가지 방법은 또는 다른 두만 때문에 구현에 전달 된 정보 `RootReferences2` 전달의 상위 집합 `RootReferences`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="ff68c-122">항목은 `rootRefIds` 0 되 해당 루트 참조는 null을 의미 하는 관리 되는 힙에 있는 개체를 참조 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="ff68c-123">반환 된 개체 Id `RootReferences2` 가비지 수집 이전 주소에서 새 주소 개체를 이동 하는 중일 수 있으므로 콜백 하는 동안 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="ff68c-124">그러므로 프로파일러는 `RootReferences2` 호출 중에 개체 검사를 시도하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="ff68c-125">때 [icorprofilercallback2:: Garbagecollectionfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) 은 호출 개체를 모두 새 위치로 이동 되었고 안전 하 게 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-125">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff68c-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff68c-126">Requirements</span></span>  
 <span data-ttu-id="ff68c-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff68c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff68c-128">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff68c-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff68c-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff68c-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff68c-130">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff68c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff68c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff68c-131">See Also</span></span>  
 [<span data-ttu-id="ff68c-132">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff68c-132">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ff68c-133">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff68c-133">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
