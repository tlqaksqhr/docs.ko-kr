---
title: "ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetClassFromTokenAndTypeArgs
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetClassFromTokenAndTypeArgs
helpviewer_keywords:
- GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
- ICorProfilerInfo2::GetClassFromTokenAndTypeArgs method [.NET Framework profiling]
ms.assetid: b25c88f0-71b9-443b-8eea-1c94db0a44b9
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a459f8e9ec6d63dc42d6a0a8f752c129d278524
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getclassfromtokenandtypeargs-method"></a><span data-ttu-id="01f44-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs 메서드</span><span class="sxs-lookup"><span data-stu-id="01f44-102">ICorProfilerInfo2::GetClassFromTokenAndTypeArgs Method</span></span>
<span data-ttu-id="01f44-103">가져옵니다는 `ClassID` 지정한 메타 데이터 토큰을 사용 하 여 형식의 및 `ClassID` 값 형식 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-103">Gets the `ClassID` of a type by using the specified metadata token and the `ClassID` values of any type arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f44-104">구문</span><span class="sxs-lookup"><span data-stu-id="01f44-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromTokenAndTypeArgs(  
    [in] ModuleID moduleID,  
    [in] mdTypeDef typeDef,  
    [in] ULONG32 cTypeArgs,  
    [in, size_is(cTypeArgs)] ClassID typeArgs[],  
    [out] ClassID* pClassID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01f44-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01f44-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="01f44-106">[in] 형식 프로시저가 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-106">[in] The ID of the module in which the type resides.</span></span>  
  
 `typeDef`  
 <span data-ttu-id="01f44-107">[in] `mdTypeDef` 유형을 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-107">[in] An `mdTypeDef` metadata token that references the type.</span></span>  
  
 `cTypeArgs`  
 <span data-ttu-id="01f44-108">[in] 지정된 된 형식에 대 한 형식 매개 변수 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-108">[in] The number of type parameters for the given type.</span></span> <span data-ttu-id="01f44-109">이 값에는 제네릭이 아닌 형식에는 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-109">This value must be zero for non-generic types.</span></span>  
  
 `typeArgs`  
 <span data-ttu-id="01f44-110">[in] 배열 `ClassID` 값을 각각는 인수 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-110">[in] An array of `ClassID` values, each of which is an argument of the type.</span></span> <span data-ttu-id="01f44-111">값 `typeArgs` 경우 NULL이 될 수 `cTypeArgs` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-111">The value of `typeArgs` can be NULL if `cTypeArgs` is set to zero.</span></span>  
  
 `pClassID`  
 <span data-ttu-id="01f44-112">[out] 에 대 한 포인터는 `ClassID` 지정 된 형식의 합니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-112">[out] A pointer to the `ClassID` of the specified type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01f44-113">설명</span><span class="sxs-lookup"><span data-stu-id="01f44-113">Remarks</span></span>  
 <span data-ttu-id="01f44-114">호출의 `GetClassFromTokenAndTypeArgs` 메서드는 `mdTypeRef` 대신는 `mdTypeDef` 메타 데이터 토큰 예기치 않은 결과 가질 수 있습니다; 호출자가 해결 해야는 `mdTypeRef` 에 `mdTypeDef` 전달할 경우.</span><span class="sxs-lookup"><span data-stu-id="01f44-114">Calling the `GetClassFromTokenAndTypeArgs` method with an `mdTypeRef` instead of an `mdTypeDef` metadata token can have unpredictable results; callers should resolve the `mdTypeRef` to an `mdTypeDef` when passing it.</span></span>  
  
 <span data-ttu-id="01f44-115">형식을 아직 로드 되지 않은 경우 호출 `GetClassFromTokenAndTypeArgs` 로드를 여러 컨텍스트에서 위험한 작업을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-115">If the type is not already loaded, calling `GetClassFromTokenAndTypeArgs` will trigger loading, which is a dangerous operation in many contexts.</span></span> <span data-ttu-id="01f44-116">예를 들어, 런타임에서 순환 로드를 시도할 때 모듈이 나 다른 형식을 로드 하는 동안이 메서드를 호출 무한 루프가 발생할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-116">For example, calling this method during loading of modules or other types could lead to an infinite loop as the runtime attempts to circularly load things.</span></span>  
  
 <span data-ttu-id="01f44-117">일반적으로 사용 하 여 `GetClassFromTokenAndTypeArgs` 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-117">In general, use of `GetClassFromTokenAndTypeArgs` is discouraged.</span></span> <span data-ttu-id="01f44-118">저장 해야 프로파일러 특정 형식에 대 한 이벤트에 관심이 `ModuleID` 및 `mdTypeDef` 해당 형식 및 사용 하 여 [icorprofilerinfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) 확인 하려면 여부는 지정 된 `ClassID` 의입니다는 필요한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-118">If profilers are interested in events for a particular type, they should store the `ModuleID` and `mdTypeDef` of that type, and use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) to check whether a given `ClassID` is that of the desired type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01f44-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01f44-119">Requirements</span></span>  
 <span data-ttu-id="01f44-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01f44-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01f44-121">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="01f44-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="01f44-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="01f44-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="01f44-123">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01f44-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f44-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01f44-124">See Also</span></span>  
 [<span data-ttu-id="01f44-125">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01f44-125">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="01f44-126">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01f44-126">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
