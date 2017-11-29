---
title: "ICorProfilerInfo2::GetArrayObjectInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetArrayObjectInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1a1e0c986286483f8236de3a1c73f043691820d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="daa32-102">ICorProfilerInfo2::GetArrayObjectInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="daa32-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="daa32-103">배열 개체에 대 한 자세한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="daa32-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daa32-104">구문</span><span class="sxs-lookup"><span data-stu-id="daa32-104">Syntax</span></span>  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="daa32-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="daa32-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="daa32-106">[in] 유효한 배열 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="daa32-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="daa32-107">[in] 배열 차수 (차원 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="daa32-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="daa32-108">[out] 각각 배열의 차원 크기를 나타내는 정수를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="daa32-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="daa32-109">[out] 배열 차원의 바인딩된 각각 더 작은 값을 나타내는 정수를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="daa32-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="daa32-110">[out] C + + 규칙에 따라 배치 되는 배열에 대 한 원시 버퍼의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="daa32-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daa32-111">설명</span><span class="sxs-lookup"><span data-stu-id="daa32-111">Remarks</span></span>  
 <span data-ttu-id="daa32-112">`pDimensionSizes` 및 `pDimensionLowerBounds` 하므로 각 배열에 있는 동일한 인덱스에 있는 요소는 동일한 엔터티의 특성에는 병렬 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="daa32-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daa32-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="daa32-113">Requirements</span></span>  
 <span data-ttu-id="daa32-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="daa32-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daa32-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="daa32-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="daa32-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="daa32-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="daa32-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daa32-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daa32-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="daa32-118">See Also</span></span>  
 [<span data-ttu-id="daa32-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daa32-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="daa32-120">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="daa32-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
