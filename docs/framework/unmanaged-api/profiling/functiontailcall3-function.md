---
title: "FunctionTailcall3 함수"
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
- FunctionTailcall3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionTailcall3
helpviewer_keywords:
- FunctionTailcall3 function [.NET Framework profiling]
ms.assetid: 1e48243f-5de6-4bd6-a1d0-e1d248bca4b8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2ae13f25a1f99de4cf7dcb46dd33ed86682bf64
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="functiontailcall3-function"></a><span data-ttu-id="9629d-102">FunctionTailcall3 함수</span><span class="sxs-lookup"><span data-stu-id="9629d-102">FunctionTailcall3 Function</span></span>
<span data-ttu-id="9629d-103">다른 함수에 대 한 마무리 호출이 수행 하려고 합니다. 현재 실행 중인 함수는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9629d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9629d-104">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall3 (FunctionOrRemappedID functionOrRemappedID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9629d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9629d-105">Parameters</span></span>  
 `functionOrRemappedID`  
 <span data-ttu-id="9629d-106">[in] 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-106">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9629d-107">설명</span><span class="sxs-lookup"><span data-stu-id="9629d-107">Remarks</span></span>  
 <span data-ttu-id="9629d-108">`FunctionTailcall3` 콜백 함수 처럼 함수가 호출 되 고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-108">The `FunctionTailcall3` callback function notifies the profiler as functions are being called.</span></span> <span data-ttu-id="9629d-109">사용 하 여는 [icorprofilerinfo3:: Setenterleavefunctionhooks3 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) 이 함수를 구현 하 여 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-109">Use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="9629d-110">`FunctionTailcall3` 는 콜백 함수입니다; 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-110">The `FunctionTailcall3` function is a callback; you must implement it.</span></span> <span data-ttu-id="9629d-111">구현을 사용 해야 합니다는 `__declspec(naked)` 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-111">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="9629d-112">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="9629d-113">항목에는 부동 소수점 FPU (단위) 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="9629d-114">끝낼 때 호출자에 의해 밀어넣은 모든 매개 변수 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="9629d-115">구현 `FunctionTailcall3` 가비지 수집이 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-115">The implementation of `FunctionTailcall3` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="9629d-116">스택 가비지 컬렉션에 적합 한 상태의 수 없을 수도 구현 가비지 수집을 시도 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-116">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="9629d-117">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionTailcall3` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-117">If a garbage collection is attempted, the runtime will block until `FunctionTailcall3` returns.</span></span>  
  
 <span data-ttu-id="9629d-118">`FunctionTailcall3` 함수 관리 코드를 호출 하거나 어떤 방식으로든에서 관리 되는 메모리를 할당 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-118">The `FunctionTailcall3` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9629d-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9629d-119">Requirements</span></span>  
 <span data-ttu-id="9629d-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9629d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9629d-121">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="9629d-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="9629d-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9629d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9629d-123">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9629d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9629d-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9629d-124">See Also</span></span>  
 [<span data-ttu-id="9629d-125">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="9629d-125">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="9629d-126">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="9629d-126">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="9629d-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9629d-127">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="9629d-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9629d-128">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="9629d-129">FunctionTailcall3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="9629d-129">FunctionTailcall3WithInfo Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="9629d-130">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="9629d-130">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="9629d-131">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9629d-131">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="9629d-132">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="9629d-132">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="9629d-133">SetFunctionIDMapper2</span><span class="sxs-lookup"><span data-stu-id="9629d-133">SetFunctionIDMapper2</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)  
 [<span data-ttu-id="9629d-134">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="9629d-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
