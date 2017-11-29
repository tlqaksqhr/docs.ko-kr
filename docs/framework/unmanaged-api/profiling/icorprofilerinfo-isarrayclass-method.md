---
title: "ICorProfilerInfo::IsArrayClass 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.IsArrayClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd07541095158d17b80333b83015d6b1f33a5dcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="6d013-102">ICorProfilerInfo::IsArrayClass 메서드</span><span class="sxs-lookup"><span data-stu-id="6d013-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="6d013-103">지정된 된 클래스 배열 클래스 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d013-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d013-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d013-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d013-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d013-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="6d013-106">[in] 검사 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6d013-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="6d013-107">[out] 배열 요소의 형식을 나타내는 CorElementType 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6d013-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="6d013-108">[out] 사용 가능한 경우 배열 요소의 클래스 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6d013-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="6d013-109">[out] 배열 차수 (즉, 차원의 수)를 나타내는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6d013-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d013-110">설명</span><span class="sxs-lookup"><span data-stu-id="6d013-110">Remarks</span></span>  
 <span data-ttu-id="6d013-111">클래스가 있는 경우 지정 된 배열 클래스는 `IsArrayClass` 메서드는 s_ok이 고 HRESULT와 모든 null이 아닌 출력 매개 변수 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d013-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="6d013-112">이렇게 하지 않으면 S_FALSE를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6d013-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d013-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d013-113">Requirements</span></span>  
 <span data-ttu-id="6d013-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6d013-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d013-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d013-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d013-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d013-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d013-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d013-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d013-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d013-118">See Also</span></span>  
 [<span data-ttu-id="6d013-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d013-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
