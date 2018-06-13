---
title: ICorProfilerInfo2::GetClassIDInfo2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetClassIDInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetClassIDInfo2
helpviewer_keywords:
- GetClassIDInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassIDInfo2 method [.NET Framework profiling]
ms.assetid: 0141d582-d066-4d49-8d1f-ae82129a1960
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2af0eacbff8220be7f2286f7f345f14126972261
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458525"
---
# <a name="icorprofilerinfo2getclassidinfo2-method"></a><span data-ttu-id="c1c32-102">ICorProfilerInfo2::GetClassIDInfo2 메서드</span><span class="sxs-lookup"><span data-stu-id="c1c32-102">ICorProfilerInfo2::GetClassIDInfo2 Method</span></span>
<span data-ttu-id="c1c32-103">부모 모듈 및 메타 데이터 지정된 된 클래스의 제네릭 정의 열기에 대 한 토큰 가져옵니다는 `ClassID` , 부모 클래스의 및 `ClassID` 있는 클래스의 경우 각 형식 인수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-103">Gets the parent module and metadata token for the open generic definition of the specified class, the `ClassID` of its parent class, and the `ClassID` for each type argument, if present, of the class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c32-104">구문</span><span class="sxs-lookup"><span data-stu-id="c1c32-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo2(  
    [in]  ClassID classId,  
    [out] ModuleID *pModuleId,  
    [out] mdTypeDef *pTypeDefToken,  
    [out] ClassID *pParentClassId,  
    [in]  ULONG32 cNumTypeArgs,  
    [out] ULONG32 *pcNumTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1c32-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1c32-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="c1c32-106">[in] 정보가 검색되는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-106">[in] The ID of the class for which information will be retrieved.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="c1c32-107">[out] 지정된 된 클래스의 제네릭 정의 열기에 대 한 부모 모듈의 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-107">[out] Pointer to the ID of the parent module for the open generic definition of the specified class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="c1c32-108">[out] 지정된 된 클래스의 제네릭 정의 열기에 대 한 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-108">[out] Pointer to the metadata token for the open generic definition of the specified class.</span></span>  
  
 `pParentClassId`  
 <span data-ttu-id="c1c32-109">[out] 부모 클래스의 ID에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-109">[out] Pointer to the ID of the parent class.</span></span>  
  
 `cNumTypeArgs`  
 <span data-ttu-id="c1c32-110">[in] `typeArgs` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-110">[in] The size of the `typeArgs` array.</span></span>  
  
 `pcNumTypeArgs`  
 <span data-ttu-id="c1c32-111">[out] 사용 가능한 요소의 총수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-111">[out] Pointer to the total number of available elements.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="c1c32-112">[out] 각각 클래스의 형식 인수 ID를 나타내는 `ClassID` 값의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-112">[out] An array of `ClassID` values, each of which represents the ID of a type argument of the class.</span></span> <span data-ttu-id="c1c32-113">메서드가 반환되면 `typeArgs`에 사용 가능한 `ClassID` 값이 일부 또는 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-113">When the method returns, `typeArgs` will contain some or all the available `ClassID` values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1c32-114">설명</span><span class="sxs-lookup"><span data-stu-id="c1c32-114">Remarks</span></span>  
 <span data-ttu-id="c1c32-115">`GetClassIDInfo2` 메서드는 비슷합니다는 [icorprofilerinfo:: Getclassidinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) 메서드, 하지만 `GetClassIDInfo2` 제네릭 형식에 대 한 추가 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-115">The `GetClassIDInfo2` method is similar to the [ICorProfilerInfo::GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md) method, but `GetClassIDInfo2` obtains additional information about a generic type.</span></span>  
  
 <span data-ttu-id="c1c32-116">프로파일러 코드를 호출할 수 [icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) 얻으려고는 [메타 데이터](../../../../docs/framework/unmanaged-api/metadata/index.md) 지정 된 모듈에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-116">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a [metadata](../../../../docs/framework/unmanaged-api/metadata/index.md) interface for a given module.</span></span> <span data-ttu-id="c1c32-117">그런 다음 `pTypeDefToken`에서 참조된 위치로 반환되는 메타데이터 토큰을 사용하여 클래스에 대한 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-117">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="c1c32-118">`GetClassIDInfo2`가 반환된 후 `typeArgs` 버퍼가 `ClassID` 값을 모두 포함할 수 있을 만큼 충분히 큰지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-118">After `GetClassIDInfo2` returns, you must verify that the `typeArgs` buffer was large enough to contain all the `ClassID` values.</span></span> <span data-ttu-id="c1c32-119">이렇게 하려면 `pcNumTypeArgs`가 가리키는 값을 `cNumTypeArgs` 매개 변수의 값과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-119">To do this, compare the value that `pcNumTypeArgs` points to with the value of the `cNumTypeArgs` parameter.</span></span> <span data-ttu-id="c1c32-120">`pcNumTypeArgs`이 `cNumTypeArgs`보다 큰 값을 가리키는 경우 더 큰 `typeArgs` 버퍼를 할당하고 `cNumTypeArgs`을 더 큰 새 크기로 업데이트한 후 `GetClassIDInfo2`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-120">If `pcNumTypeArgs` points to a value that is larger than `cNumTypeArgs`, allocate a larger `typeArgs` buffer, update `cNumTypeArgs` with the new, larger size, and call `GetClassIDInfo2` again.</span></span>  
  
 <span data-ttu-id="c1c32-121">또는 길이가 0인 `typeArgs` 버퍼로 `GetClassIDInfo2`를 먼저 호출하여 올바른 버퍼 크기를 구합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-121">Alternatively, you can first call `GetClassIDInfo2` with a zero-length `typeArgs` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="c1c32-122">그런 다음 `typeArgs` 버퍼 크기를 `pcNumTypeArgs`에 반환된 값으로 설정하고 `GetClassIDInfo2`를 다시 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-122">You can then set the `typeArgs` buffer size to the value returned in `pcNumTypeArgs` and call `GetClassIDInfo2` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c32-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1c32-123">Requirements</span></span>  
 <span data-ttu-id="c1c32-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c1c32-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1c32-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1c32-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1c32-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1c32-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1c32-127">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c32-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c32-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1c32-128">See Also</span></span>  
 [<span data-ttu-id="c1c32-129">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1c32-129">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="c1c32-130">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1c32-130">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [<span data-ttu-id="c1c32-131">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1c32-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c1c32-132">프로파일링</span><span class="sxs-lookup"><span data-stu-id="c1c32-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
