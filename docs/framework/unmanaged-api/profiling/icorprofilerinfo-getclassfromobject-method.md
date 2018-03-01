---
title: "ICorProfilerInfo::GetClassFromObject 메서드"
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
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ffc2e72746074776caee6fa9b87563df41fcc6b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="54fa5-102">ICorProfilerInfo::GetClassFromObject 메서드</span><span class="sxs-lookup"><span data-stu-id="54fa5-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="54fa5-103">가져옵니다는 `ClassID` 지정 된 개체의 해당 `ObjectID`합니다.</span><span class="sxs-lookup"><span data-stu-id="54fa5-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54fa5-104">구문</span><span class="sxs-lookup"><span data-stu-id="54fa5-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54fa5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="54fa5-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="54fa5-106">[in] 가져올 개체의 ID는 `ClassID`합니다.</span><span class="sxs-lookup"><span data-stu-id="54fa5-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="54fa5-107">[out] 반환 된에 대 한 포인터 `ClassID`합니다.</span><span class="sxs-lookup"><span data-stu-id="54fa5-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54fa5-108">설명</span><span class="sxs-lookup"><span data-stu-id="54fa5-108">Remarks</span></span>  
 <span data-ttu-id="54fa5-109">Null `pClassId` 나타냅니다 `objectId` 언로드되고 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54fa5-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54fa5-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54fa5-110">Requirements</span></span>  
 <span data-ttu-id="54fa5-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="54fa5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54fa5-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="54fa5-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="54fa5-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54fa5-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54fa5-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54fa5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54fa5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54fa5-115">See Also</span></span>  
 [<span data-ttu-id="54fa5-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54fa5-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
