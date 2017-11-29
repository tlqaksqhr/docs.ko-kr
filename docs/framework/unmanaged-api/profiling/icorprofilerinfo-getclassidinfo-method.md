---
title: "ICorProfilerInfo::GetClassIDInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetClassIDInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3d8cf1f82ce6df8eed7b0f914003d1b13bf65685
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="e1a70-102">ICorProfilerInfo::GetClassIDInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="e1a70-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="e1a70-103">지정된 된 클래스에 대 한 부모 모듈 및 메타 데이터 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e1a70-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1a70-104">구문</span><span class="sxs-lookup"><span data-stu-id="e1a70-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1a70-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e1a70-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="e1a70-106">[in] ID 정보를 얻기 위한 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a70-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="e1a70-107">[out] 클래스의 부모 모듈의 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a70-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="e1a70-108">[out] 클래스에 대 한 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e1a70-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1a70-109">설명</span><span class="sxs-lookup"><span data-stu-id="e1a70-109">Remarks</span></span>  
 <span data-ttu-id="e1a70-110">프로파일러 코드를 호출할 수 [icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) 지정 된 모듈에 대 한 메타 데이터 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a70-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="e1a70-111">그런 다음 `pTypeDefToken`에서 참조된 위치로 반환되는 메타데이터 토큰을 사용하여 클래스에 대한 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e1a70-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="e1a70-112">제네릭 형식에 대 한 자세한 정보를 가져오려면 [icorprofilerinfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a70-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1a70-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e1a70-113">Requirements</span></span>  
 <span data-ttu-id="e1a70-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e1a70-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1a70-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e1a70-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e1a70-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1a70-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1a70-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1a70-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a70-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1a70-118">See Also</span></span>  
 [<span data-ttu-id="e1a70-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e1a70-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
