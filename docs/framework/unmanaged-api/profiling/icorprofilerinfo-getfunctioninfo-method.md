---
title: "ICorProfilerInfo::GetFunctionInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetFunctionInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetFunctionInfo
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionInfo method [.NET Framework profiling]
- GetFunctionInfo method [.NET Framework profiling]
ms.assetid: c42b5891-019d-46b3-b551-4606295b75b8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17512077ef7a8ca45fa76c00f93612015948d083
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetfunctioninfo-method"></a><span data-ttu-id="ed643-102">ICorProfilerInfo::GetFunctionInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="ed643-102">ICorProfilerInfo::GetFunctionInfo Method</span></span>
<span data-ttu-id="ed643-103">부모 클래스와 메타 데이터가 지정된 된 함수에 대 한 토큰 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-103">Gets the parent class and metadata token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed643-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed643-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionInfo(  
    [in]  FunctionID functionId,  
    [out] ClassID    *pClassId,  
    [out] ModuleID   *pModuleId,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed643-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed643-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ed643-106">[in] ID를 가져올 부모 클래스와 메타 데이터 토큰에 대 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-106">[in] The ID of the function for which to get the parent class and metadata token.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="ed643-107">[out] 함수의 부모 클래스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-107">[out] A pointer to the parent class of the function.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="ed643-108">[out] 함수의 부모 클래스가 정의된 모듈에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-108">[out] A pointer to the module in which the function's parent class is defined.</span></span>  
  
 `pToken`  
 <span data-ttu-id="ed643-109">[out] 함수의 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-109">[out] A pointer to the metadata token for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed643-110">설명</span><span class="sxs-lookup"><span data-stu-id="ed643-110">Remarks</span></span>  
 <span data-ttu-id="ed643-111">프로파일러 코드를 호출할 수 [icorprofilerinfo:: Getmodulemetadata](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) 지정 된 모듈에 대 한 메타 데이터 인터페이스를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-111">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="ed643-112">`pToken`에서 참조하는 위치로 반환되는 메타데이터 토큰을 사용하여 함수에 대한 메타데이터에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-112">The metadata token that is returned to the location referenced by `pToken` can then be used to access the metadata for the function.</span></span>  
  
 <span data-ttu-id="ed643-113">`ClassID` 제네릭 클래스에 있는 함수의 가져올 수 없습니다 없이 함수를 사용 하는 방법에 대 한 자세한 컨텍스트 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-113">The `ClassID` of a function on a generic class might not be obtainable without more contextual information about the use of the function.</span></span> <span data-ttu-id="ed643-114">이 경우 `pClassId` 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-114">In this case, `pClassId` will be 0.</span></span> <span data-ttu-id="ed643-115">프로파일러 코드를 사용 해야 [icorprofilerinfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) COR_PRF_FRAME_INFO 값이 더 많은 컨텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-115">Profiler code should use [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) with a COR_PRF_FRAME_INFO value to provide more context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed643-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed643-116">Requirements</span></span>  
 <span data-ttu-id="ed643-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed643-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed643-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed643-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed643-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed643-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed643-120">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed643-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed643-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed643-121">See Also</span></span>  
 [<span data-ttu-id="ed643-122">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed643-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
