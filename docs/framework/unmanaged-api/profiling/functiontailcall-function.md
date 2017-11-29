---
title: "FunctionTailcall 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionTailcall
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionTailcall
helpviewer_keywords: FunctionTailcall function [.NET Framework profiling]
ms.assetid: 66347e03-9a97-41e8-8f9d-89b80803f7b5
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8bc0d72ad9c11cb36803cc606b460181b44033f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="functiontailcall-function"></a><span data-ttu-id="7fb36-102">FunctionTailcall 함수</span><span class="sxs-lookup"><span data-stu-id="7fb36-102">FunctionTailcall Function</span></span>
<span data-ttu-id="7fb36-103">다른 함수에 대 한 마무리 호출이 수행 하려고 합니다. 현재 실행 중인 함수는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-103">Notifies the profiler that the currently executing function is about to perform a tail call to another function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7fb36-104">`FunctionTailcall` 함수는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-104">The `FunctionTailcall` function is deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="7fb36-105">작동 하도록 하는 계속 되지만 성능 저하가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="7fb36-106">사용 하 여 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) 함수를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-106">Use the [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fb36-107">구문</span><span class="sxs-lookup"><span data-stu-id="7fb36-107">Syntax</span></span>  
  
```  
void __stdcall FunctionTailcall (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7fb36-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7fb36-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="7fb36-109">[in] 마무리 호출을 수행 하려고 하는 현재 실행 중인 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-109">[in] The identifier of the currently executing function that is about to make a tail call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7fb36-110">설명</span><span class="sxs-lookup"><span data-stu-id="7fb36-110">Remarks</span></span>  
 <span data-ttu-id="7fb36-111">마무리 호출의 대상 함수 ´ ֲ 현재 스택 프레임을 마무리 호출을 수행한 함수의 호출자에 게 직접 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-111">The target function of the tail call will use the current stack frame, and will return directly to the caller of the function that made the tail call.</span></span> <span data-ttu-id="7fb36-112">즉, 한 [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) 콜백 마무리 호출의 대상이 되는 함수에 대 한 실행 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-112">This means that a [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback will not be issued for a function that is the target of a tail call.</span></span>  
  
 <span data-ttu-id="7fb36-113">`FunctionTailcall` 는 콜백 함수입니다; 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-113">The `FunctionTailcall` function is a callback; you must implement it.</span></span> <span data-ttu-id="7fb36-114">구현을 사용 해야 합니다는 `__declspec`(`naked`) 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-114">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="7fb36-115">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="7fb36-116">항목에는 부동 소수점 FPU (단위) 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="7fb36-117">끝낼 때 호출자에 의해 밀어넣은 모든 매개 변수 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="7fb36-118">구현 `FunctionTailcall` 가비지 수집이 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-118">The implementation of `FunctionTailcall` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="7fb36-119">스택 가비지 컬렉션에 적합 한 상태의 수 없을 수도 구현 가비지 수집을 시도 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-119">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="7fb36-120">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionTailcall` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-120">If a garbage collection is attempted, the runtime will block until `FunctionTailcall` returns.</span></span>  
  
 <span data-ttu-id="7fb36-121">또한는 `FunctionTailcall` 함수를 호출 해서는 안에서 또는 관리 코드에 관리 되는 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-121">Also, the `FunctionTailcall` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fb36-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fb36-122">Requirements</span></span>  
 <span data-ttu-id="7fb36-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb36-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fb36-124">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="7fb36-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="7fb36-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fb36-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fb36-126">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="7fb36-126">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb36-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fb36-127">See Also</span></span>  
 [<span data-ttu-id="7fb36-128">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="7fb36-128">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="7fb36-129">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="7fb36-129">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="7fb36-130">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="7fb36-130">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="7fb36-131">프로 파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="7fb36-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
