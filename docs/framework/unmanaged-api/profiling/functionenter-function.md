---
title: "FunctionEnter 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionEnter
helpviewer_keywords: FunctionEnter function [.NET Framework profiling]
ms.assetid: bf4ffa50-4506-4dd4-aa13-a0457b47ca74
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0cd98e6db0f400d022fe0af4e96336616cbb7183
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="functionenter-function"></a><span data-ttu-id="95153-102">FunctionEnter 함수</span><span class="sxs-lookup"><span data-stu-id="95153-102">FunctionEnter Function</span></span>
<span data-ttu-id="95153-103">제어는 함수에 전달 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="95153-103">Notifies the profiler that control is being passed to a function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95153-104">`FunctionEnter` .NET Framework 버전 2.0에서에서 함수는 사용 되지 않으며 사용 성능 저하를 유발 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-104">The `FunctionEnter` function is deprecated in the .NET Framework version 2.0, and its use will incur a performance penalty.</span></span> <span data-ttu-id="95153-105">사용 하 여 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) 함수를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-105">Use the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95153-106">구문</span><span class="sxs-lookup"><span data-stu-id="95153-106">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter (  
    [in]  FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95153-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95153-107">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="95153-108">[in] 컨트롤이 전달 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-108">[in] The identifier of the function to which control is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95153-109">설명</span><span class="sxs-lookup"><span data-stu-id="95153-109">Remarks</span></span>  
 <span data-ttu-id="95153-110">`FunctionEnter` 는 콜백 함수입니다; 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-110">The `FunctionEnter` function is a callback; you must implement it.</span></span> <span data-ttu-id="95153-111">구현을 사용 해야 합니다는 `__declspec`(`naked`) 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="95153-111">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="95153-112">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95153-112">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="95153-113">항목에는 부동 소수점 FPU (단위) 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-113">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="95153-114">끝낼 때 호출자에 의해 밀어넣은 모든 매개 변수 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-114">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="95153-115">구현 `FunctionEnter` 가비지 수집이 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-115">The implementation of `FunctionEnter` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="95153-116">스택 가비지 컬렉션에 적합 한 상태의 수 없을 수도 구현 가비지 수집을 시도 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-116">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="95153-117">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionEnter` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-117">If a garbage collection is attempted, the runtime will block until `FunctionEnter` returns.</span></span>  
  
 <span data-ttu-id="95153-118">또한는 `FunctionEnter` 함수를 호출 해서는 안에서 또는 관리 코드에 관리 되는 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-118">Also, the `FunctionEnter` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95153-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95153-119">Requirements</span></span>  
 <span data-ttu-id="95153-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95153-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95153-121">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="95153-121">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="95153-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95153-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95153-123">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="95153-123">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95153-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95153-124">See Also</span></span>  
 [<span data-ttu-id="95153-125">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="95153-125">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="95153-126">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="95153-126">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="95153-127">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="95153-127">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="95153-128">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="95153-128">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="95153-129">프로 파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="95153-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
