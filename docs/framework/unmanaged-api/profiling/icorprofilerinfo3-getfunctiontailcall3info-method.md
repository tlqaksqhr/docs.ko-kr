---
title: "ICorProfilerInfo3::GetFunctionTailcall3Info 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aae55a9e183c9e013603218ba217be79b2425e46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="8aee0-102">ICorProfilerInfo3::GetFunctionTailcall3Info 메서드</span><span class="sxs-lookup"><span data-stu-id="8aee0-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="8aee0-103">프로파일러에 보고 하는 함수의 스택 프레임을 제공 된 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8aee0-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="8aee0-104">이 함수는 `FunctionTailcall3WithInfo` 콜백 중에만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aee0-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aee0-105">구문</span><span class="sxs-lookup"><span data-stu-id="8aee0-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8aee0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8aee0-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8aee0-107">[in] `FunctionID` 의 함수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aee0-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="8aee0-108">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8aee0-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="8aee0-109">프로파일러는 동일한 제공 해야 `eltInfo` 프로파일러에 제공 된는 `FunctionTailcall3WithInfo` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8aee0-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="8aee0-110">[out] 지정된 스택 프레임에 대한 일반 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="8aee0-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="8aee0-111">이 핸들은 프로파일러가 `GetFunctionTailcall3Info` 메서드를 호출한 `FunctionTailcall3WithInfo` 콜백 중에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="8aee0-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8aee0-112">설명</span><span class="sxs-lookup"><span data-stu-id="8aee0-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aee0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8aee0-113">Requirements</span></span>  
 <span data-ttu-id="8aee0-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8aee0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aee0-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8aee0-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8aee0-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8aee0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8aee0-117">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aee0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aee0-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8aee0-118">See Also</span></span>  
 [<span data-ttu-id="8aee0-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8aee0-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="8aee0-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8aee0-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="8aee0-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="8aee0-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="8aee0-122">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aee0-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="8aee0-123">프로 파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8aee0-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="8aee0-124">프로파일링</span><span class="sxs-lookup"><span data-stu-id="8aee0-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
