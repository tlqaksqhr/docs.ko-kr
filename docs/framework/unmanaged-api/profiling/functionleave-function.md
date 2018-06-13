---
title: FunctionLeave 함수
ms.date: 03/30/2017
api_name:
- FunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionLeave
helpviewer_keywords:
- FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2614ad988496a22f0e6234c2f3300e22ef548308
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452444"
---
# <a name="functionleave-function"></a><span data-ttu-id="a2d8f-102">FunctionLeave 함수</span><span class="sxs-lookup"><span data-stu-id="a2d8f-102">FunctionLeave Function</span></span>
<span data-ttu-id="a2d8f-103">호출자에 게 반환 하는 함수 인지 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2d8f-104">`FunctionLeave` 함수는.NET Framework 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="a2d8f-105">작동 하도록 하는 계속 되지만 성능 저하가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="a2d8f-106">사용 하 여 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) 함수를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2d8f-107">구문</span><span class="sxs-lookup"><span data-stu-id="a2d8f-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2d8f-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a2d8f-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="a2d8f-109">[in] 식별자가 반환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2d8f-110">설명</span><span class="sxs-lookup"><span data-stu-id="a2d8f-110">Remarks</span></span>  
 <span data-ttu-id="a2d8f-111">`FunctionLeave` 는 콜백 함수입니다; 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="a2d8f-112">구현을 사용 해야 합니다는 `__declspec`(`naked`) 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="a2d8f-113">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="a2d8f-114">항목에는 부동 소수점 FPU (단위) 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="a2d8f-115">끝낼 때 호출자에 의해 밀어넣은 모든 매개 변수 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="a2d8f-116">구현 `FunctionLeave` 가비지 수집이 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="a2d8f-117">스택 가비지 컬렉션에 적합 한 상태의 수 없을 수도 구현 가비지 수집을 시도 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="a2d8f-118">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionLeave` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="a2d8f-119">또한는 `FunctionLeave` 함수를 호출 해서는 안에서 또는 관리 코드에 관리 되는 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2d8f-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a2d8f-120">Requirements</span></span>  
 <span data-ttu-id="a2d8f-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a2d8f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2d8f-122">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="a2d8f-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a2d8f-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2d8f-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2d8f-124">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a2d8f-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2d8f-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a2d8f-125">See Also</span></span>  
 [<span data-ttu-id="a2d8f-126">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="a2d8f-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="a2d8f-127">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="a2d8f-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="a2d8f-128">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="a2d8f-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="a2d8f-129">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="a2d8f-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="a2d8f-130">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="a2d8f-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
