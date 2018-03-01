---
title: "FunctionEnter3WithInfo 함수"
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
- FunctionEnter3WithInfo
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- FunctionEnter3WithInfo
helpviewer_keywords:
- FunctionEnter3WithInfo function [.NET Framework profiling]
ms.assetid: 277c3344-d0cb-431e-beae-eb1eeeba8eea
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 848ef06f73aa0cce5d6991a7a59a8ce51ab1745a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="functionenter3withinfo-function"></a><span data-ttu-id="a953b-102">FunctionEnter3WithInfo 함수</span><span class="sxs-lookup"><span data-stu-id="a953b-102">FunctionEnter3WithInfo Function</span></span>
<span data-ttu-id="a953b-103">제어는 함수에 전달 되 고 있음을 프로파일러에 알립니다. 고에 전달 될 수 있는 핸들을 제공 된 [icorprofilerinfo3:: Getfunctionenter3info 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) 스택 프레임 및 함수 인수를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-103">Notifies the profiler that control is being passed to a function, and provides a handle that can be passed to the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to retrieve the stack frame and function arguments.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a953b-104">구문</span><span class="sxs-lookup"><span data-stu-id="a953b-104">Syntax</span></span>  
  
```  
void __stdcall FunctionEnter3WithInfo(  
               [in] FunctionIDOrClientID functionIDOrClientID,  
               [in] COR_PRF_ELT_INFO eltInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a953b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a953b-105">Parameters</span></span>  
 `functionIDOrClientID`  
 <span data-ttu-id="a953b-106">[in] 컨트롤이 전달 함수의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-106">[in] The identifier of the function to which control is passed.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="a953b-107">[in] 지정된 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-107">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="a953b-108">이 핸들은 전달 된 콜백 하는 동안에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-108">This handle is valid only during the callback to which it is passed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a953b-109">설명</span><span class="sxs-lookup"><span data-stu-id="a953b-109">Remarks</span></span>  
 <span data-ttu-id="a953b-110">`FunctionEnter3WithInfo` 콜백 메서드를 통해 프로파일러를 사용 하 여 호출 함수 처럼 프로파일러에 알립니다는 [icorprofilerinfo3:: Getfunctionenter3info 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) 인수 값을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-110">The `FunctionEnter3WithInfo` callback method notifies the profiler as functions are called, and enables the profiler to use the [ICorProfilerInfo3::GetFunctionEnter3Info method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) to inspect argument values.</span></span> <span data-ttu-id="a953b-111">인수 정보에 액세스 하는 `COR_PRF_ENABLE_FUNCTION_ARGS` 플래그는 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-111">To access argument information, the `COR_PRF_ENABLE_FUNCTION_ARGS` flag has to be set.</span></span> <span data-ttu-id="a953b-112">프로파일러 צ ְ ײ는 [icorprofilerinfo:: Seteventmask 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 이벤트 플래그를 설정 하 고 다음 사용 하는 [icorprofilerinfo3:: Setenterleavefunctionhooks3withinfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) 등록 하 여 이 함수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-112">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="a953b-113">`FunctionEnter3WithInfo` 는 콜백 함수입니다; 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-113">The `FunctionEnter3WithInfo` function is a callback; you must implement it.</span></span> <span data-ttu-id="a953b-114">구현을 사용 해야 합니다는 `__declspec(naked)` 저장소 클래스 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-114">The implementation must use the `__declspec(naked)` storage-class attribute.</span></span>  
  
 <span data-ttu-id="a953b-115">실행 엔진은이 함수를 호출 하기 전에 레지스터를 저장 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-115">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="a953b-116">항목에는 부동 소수점 FPU (단위) 포함 하 여 사용 하는 모든 레지스터를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-116">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="a953b-117">끝낼 때 호출자에 의해 밀어넣은 모든 매개 변수 팝 하 여 스택을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-117">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="a953b-118">구현 `FunctionEnter3WithInfo` 가비지 수집이 지연 될 수 있으므로 차단 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-118">The implementation of `FunctionEnter3WithInfo` should not block, because it will delay garbage collection.</span></span> <span data-ttu-id="a953b-119">스택 가비지 컬렉션에 적합 한 상태의 수 없을 수도 구현 가비지 수집을 시도 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-119">The implementation should not attempt a garbage collection, because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="a953b-120">런타임이 될 때까지 차단 됩니다 가비지 수집을 시도 하는 경우 `FunctionEnter3WithInfo` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-120">If a garbage collection is attempted, the runtime will block until `FunctionEnter3WithInfo` returns.</span></span>  
  
 <span data-ttu-id="a953b-121">`FunctionEnter3WithInfo` 함수 관리 코드를 호출 하거나 어떤 방식으로든에서 관리 되는 메모리를 할당 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-121">The `FunctionEnter3WithInfo` function must not call into managed code or cause a managed memory allocation in any way.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a953b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a953b-122">Requirements</span></span>  
 <span data-ttu-id="a953b-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a953b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a953b-124">**헤더:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="a953b-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a953b-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a953b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a953b-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a953b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a953b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a953b-127">See Also</span></span>  
 [<span data-ttu-id="a953b-128">GetFunctionEnter3Info</span><span class="sxs-lookup"><span data-stu-id="a953b-128">GetFunctionEnter3Info</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)  
 [<span data-ttu-id="a953b-129">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="a953b-129">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="a953b-130">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="a953b-130">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="a953b-131">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="a953b-131">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
