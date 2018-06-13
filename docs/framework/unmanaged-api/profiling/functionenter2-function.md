---
title: FunctionEnter2 함수
ms.date: 03/30/2017
api_name:
- FunctionEnter2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionEnter2
helpviewer_keywords:
- FunctionEnter2 function [.NET Framework profiling]
ms.assetid: ce7a21f9-0ca3-4b92-bc4b-bb803cae3f51
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d79249a2540adbd7f1b7e9bf36c899ba94d71e2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452392"
---
# <a name="functionenter2-function"></a><span data-ttu-id="41f56-102">FunctionEnter2 함수</span><span class="sxs-lookup"><span data-stu-id="41f56-102">FunctionEnter2 Function</span></span>
<span data-ttu-id="41f56-103">제어는 함수에 전달 되는 및 프레임 및 함수 인수는 스택에 대 한 정보를 제공 합니다. 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-103">Notifies the profiler that control is being passed to a function and provides information about the stack frame and function arguments.</span></span> <span data-ttu-id="41f56-104">이 함수를 대체는 [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-104">This function supersedes the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41f56-105">구문</span><span class="sxs-lookup"><span data-stu-id="41f56-105">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter2 (  
    [in]  FunctionID                       funcId,   
    [in]  UINT_PTR                         clientData,   
    [in]  COR_PRF_FRAME_INFO               func,   
    [in]  COR_PRF_FUNCTION_ARGUMENT_INFO  *argumentInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41f56-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="41f56-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="41f56-107">[in] 컨트롤이 전달 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-107">[in] The identifier of the function to which control is passed.</span></span>  
  
 `clientData`  
 <span data-ttu-id="41f56-108">[in] 프로파일러를 사용 하 여 이전에 지정 하는 다시 매핑된 함수 식별자는 [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-108">[in] The remapped function identifier, which the profiler previously specified by using the [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) function.</span></span>  
  
 `func`  
 <span data-ttu-id="41f56-109">[in] A `COR_PRF_FRAME_INFO` 스택 프레임에 대 한 정보를 가리키는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-109">[in] A `COR_PRF_FRAME_INFO` value that points to information about the stack frame.</span></span>  
  
 <span data-ttu-id="41f56-110">프로파일러에 실행 엔진으로 다시 전달 될 수 있는 불투명 핸들로이 처리 해야는 [icorprofilerinfo2:: Getfunctioninfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="41f56-110">The profiler should treat this as an opaque handle that can be passed back to the execution engine in the [ICorProfilerInfo2::GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method.</span></span>  
  
 `argumentInfo`  
 <span data-ttu-id="41f56-111">[in] 에 대 한 포인터는 [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) 함수의 인수의 메모리에 위치를 지정 하는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-111">[in] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md) structure that specifies the locations in memory of the function's arguments.</span></span>  
  
 <span data-ttu-id="41f56-112">인수 정보에 액세스 하려면는 `COR_PRF_ENABLE_FUNCTION_ARGS` 플래그를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-112">In order to access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag must be set.</span></span> <span data-ttu-id="41f56-113">프로파일러를 사용할 수는 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 이벤트 플래그를 설정 하는 방법은 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-113">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41f56-114">설명</span><span class="sxs-lookup"><span data-stu-id="41f56-114">Remarks</span></span>  
 <span data-ttu-id="41f56-115">값은 `func` 및 `argumentInfo` 매개 후 유효 하지 않습니다는 `FunctionEnter2` 함수 반환 값이 변경 될 수 있습니다 또는 소멸 될 예정 이므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-115">The values of the `func` and `argumentInfo` parameters are not valid after the `FunctionEnter2` function returns because the values may change or be destroyed.</span></span>  
  
 <span data-ttu-id="41f56-116">`FunctionEnter2` 는 콜백 함수입니다; 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-116">The `FunctionEnter2` function is a callback; you must implement it.</span></span> <span data-ttu-id="41f56-117">구현을 사용 해야 합니다는 `__declspec`(`naked`) 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-117">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="41f56-118">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-118">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="41f56-119">항목에는 부동 소수점 FPU (단위) 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-119">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="41f56-120">끝낼 때 호출자에 의해 밀어넣은 모든 매개 변수 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-120">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="41f56-121">구현 `FunctionEnter2` 가비지 수집이 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-121">The implementation of `FunctionEnter2` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="41f56-122">스택 가비지 컬렉션에 적합 한 상태의 수 없을 수도 구현 가비지 수집을 시도 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-122">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="41f56-123">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionEnter2` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-123">If a garbage collection is attempted, the runtime will block until `FunctionEnter2` returns.</span></span>  
  
 <span data-ttu-id="41f56-124">또한는 `FunctionEnter2` 함수를 호출 해서는 안에서 또는 관리 코드에 관리 되는 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-124">Also, the `FunctionEnter2` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41f56-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="41f56-125">Requirements</span></span>  
 <span data-ttu-id="41f56-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="41f56-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41f56-127">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="41f56-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="41f56-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41f56-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41f56-129">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41f56-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41f56-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41f56-130">See Also</span></span>  
 [<span data-ttu-id="41f56-131">FunctionLeave2 함수</span><span class="sxs-lookup"><span data-stu-id="41f56-131">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="41f56-132">FunctionTailcall2 함수</span><span class="sxs-lookup"><span data-stu-id="41f56-132">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="41f56-133">SetEnterLeaveFunctionHooks2 메서드</span><span class="sxs-lookup"><span data-stu-id="41f56-133">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="41f56-134">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="41f56-134">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
