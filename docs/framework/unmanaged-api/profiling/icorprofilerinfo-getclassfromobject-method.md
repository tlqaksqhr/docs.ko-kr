---
title: "ICorProfilerInfo::GetClassFromObject 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetClassFromObject
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 706118a197677ec97672cca36f5bcf6421a1c328
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="b2936-102">ICorProfilerInfo::GetClassFromObject 메서드</span><span class="sxs-lookup"><span data-stu-id="b2936-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="b2936-103">가져옵니다는 `ClassID` 지정 된 개체의 해당 `ObjectID`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2936-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2936-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2936-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2936-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2936-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="b2936-106">[in] 가져올 개체의 ID는 `ClassID`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2936-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="b2936-107">[out] 반환 된에 대 한 포인터 `ClassID`합니다.</span><span class="sxs-lookup"><span data-stu-id="b2936-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2936-108">설명</span><span class="sxs-lookup"><span data-stu-id="b2936-108">Remarks</span></span>  
 <span data-ttu-id="b2936-109">Null `pClassId` 나타냅니다 `objectId` 언로드되고 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2936-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2936-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2936-110">Requirements</span></span>  
 <span data-ttu-id="b2936-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2936-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2936-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b2936-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b2936-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2936-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2936-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2936-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2936-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2936-115">See Also</span></span>  
 [<span data-ttu-id="b2936-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2936-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
