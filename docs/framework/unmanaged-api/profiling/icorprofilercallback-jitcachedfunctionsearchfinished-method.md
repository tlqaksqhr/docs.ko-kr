---
title: ICorProfilerCallback::JITCachedFunctionSearchFinished 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchFinished
helpviewer_keywords:
- JITCachedFunctionSearchFinished method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchFinished method [.NET Framework profiling]
ms.assetid: 3c325c82-cddd-4b00-b3da-e450c36abf62
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89c7b0fe0f3ade3f57aa50b100bc9b4ecc904a17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451999"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchfinished-method"></a><span data-ttu-id="ee15f-102">ICorProfilerCallback::JITCachedFunctionSearchFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="ee15f-102">ICorProfilerCallback::JITCachedFunctionSearchFinished Method</span></span>
<span data-ttu-id="ee15f-103">네이티브 이미지 생성기 (NGen.exe)를 사용 하 여 이전에 컴파일된 함수에 대 한 검색을 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ee15f-103">Notifies the profiler that a search has finished for a function that was compiled previously using the Native Image Generator (NGen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee15f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ee15f-104">Syntax</span></span>  
  
```  
HRESULT JITCachedFunctionSearchFinished(  
    [in] FunctionID        functionId,  
    [in] COR_PRF_JIT_CACHE result);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ee15f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ee15f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ee15f-106">[in] 검색이 수행 되었을 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ee15f-106">[in] The ID of the function for which the search was performed.</span></span>  
  
 `result`  
 <span data-ttu-id="ee15f-107">[in] 값은 [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) 검색 결과 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ee15f-107">[in] A value of the [COR_PRF_JIT_CACHE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-jit-cache-enumeration.md) enumeration that indicates the result of the search.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee15f-108">설명</span><span class="sxs-lookup"><span data-stu-id="ee15f-108">Remarks</span></span>  
 <span data-ttu-id="ee15f-109">.NET Framework 버전 2.0에에서는 [icorprofilercallback:: Jitcachedfunctionsearchstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) 및 `JITCachedFunctionSearchFinished` 보통 NGen 이미지의 모든 함수에 대 한 콜백이 수행 될 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee15f-109">In the .NET Framework version 2.0, the [ICorProfilerCallback::JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md) and `JITCachedFunctionSearchFinished` callbacks will not be made for all functions in regular NGen images.</span></span> <span data-ttu-id="ee15f-110">만 NGen 이미지의 프로파일러에 대 한 액세스에 최적화 된 이미지의 모든 기능에 대 한 콜백을 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee15f-110">Only NGen images optimized for a profiler will generate callbacks for all functions in the image.</span></span> <span data-ttu-id="ee15f-111">그러나 추가 오버 헤드로 인해 프로파일러를 요청 해야 NGen 이미지 프로파일러 액세스에 최적화 된 이러한 콜백 함수를 컴파일된-just-in-time JIT ()를 사용 하려는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee15f-111">However, due to the additional overhead, a profiler should request profiler-optimized NGen images only if it intends to use these callbacks to force a function to be compiled just-in-time (JIT).</span></span> <span data-ttu-id="ee15f-112">그렇지 않으면 프로파일러 함수 정보를 수집 하기 위한 지연 전략을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee15f-112">Otherwise, the profiler should use a lazy strategy for gathering function information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee15f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ee15f-113">Requirements</span></span>  
 <span data-ttu-id="ee15f-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee15f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee15f-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ee15f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ee15f-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee15f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee15f-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee15f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee15f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee15f-118">See Also</span></span>  
 [<span data-ttu-id="ee15f-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ee15f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
