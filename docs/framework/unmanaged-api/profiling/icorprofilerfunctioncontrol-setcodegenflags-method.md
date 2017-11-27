---
title: "ICorProfilerFunctionControl::SetCodegenFlags 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerFunctionControl.SetCodegenFlags
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerFunctionControl::SetCodegenFlags
helpviewer_keywords:
- ICorProfilerFunctionControl::SetCodegenFlags method [.NET Framework profiling]
- SetCodegenFlags method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: a2d5daa5-b990-4ae5-bf2a-c0862fe58bd7
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: eb212b0fb777e960d7121dadaf4715b44306db6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerfunctioncontrolsetcodegenflags-method"></a><span data-ttu-id="84fbb-102">ICorProfilerFunctionControl::SetCodegenFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="84fbb-102">ICorProfilerFunctionControl::SetCodegenFlags Method</span></span>
<span data-ttu-id="84fbb-103">하나 이상의 플래그 설정 된 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) 다시 컴파일된 함수는-just-in-time (JIT)에 대 한 코드 생성을 제어 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-103">Sets one or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration to control code generation for a just-in-time (JIT) recompiled function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84fbb-104">구문</span><span class="sxs-lookup"><span data-stu-id="84fbb-104">Syntax</span></span>  
  
```  
HRESULT SetCodegenFlags(  
    [in] DWORD flags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84fbb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84fbb-105">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="84fbb-106">[in] 하나 이상의 플래그는 [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-106">[in] One or more flags from the [COR_PRF_CODEGEN_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-codegen-flags-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84fbb-107">설명</span><span class="sxs-lookup"><span data-stu-id="84fbb-107">Remarks</span></span>  
 <span data-ttu-id="84fbb-108">프로파일러를 통해이 인터페이스의 인스턴스를 가져옵니다는 [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-108">The profiler obtains an instance of this interface through the [ICorProfilerCallback4::GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) callback.</span></span> <span data-ttu-id="84fbb-109">`SetCodegenFlags`프로파일러는 다시 컴파일된 함수에 대 한 코드 생성을 제어를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-109">`SetCodegenFlags` allows the profiler to control the code generation for the recompiled function.</span></span> <span data-ttu-id="84fbb-110">모든 다른 JIT 다시 컴파일 매개 변수를와 마찬가지로 코드 생성 플래그 함수의 모든 인스턴스에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-110">As with all other JIT recompilation parameters, the code generation flags apply to all instances of the function.</span></span>  
  
 <span data-ttu-id="84fbb-111">JIT 컴파일러는 함수를 컴파일할 때 다른 소스에서 지정 된 다른 플래그와 함께 이러한 컴파일 플래그를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-111">The JIT compiler considers these compilation flags, along with other flags specified by other sources, when compiling a function.</span></span>  <span data-ttu-id="84fbb-112">다른 소스는 디버거, 사용 하 여 전역 플래그 설정으로 시작할 때 프로파일러에서 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 메서드 (값을 가진 `COR_PRF_DISABLE_INLINING` 및 `COR_PRF_DISABLE_OPTIMIZATIONS`), 및의 [ Icorprofilercallback:: Jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-112">The other sources include the debugger, global flags set by the profiler on startup by using the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method (with the values `COR_PRF_DISABLE_INLINING` and `COR_PRF_DISABLE_OPTIMIZATIONS`), and the profiler’s [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback.</span></span>  <span data-ttu-id="84fbb-113">JIT 컴파일러 최적화의 최소 크기를 요청 하는 원본에 대 한 우선 순위를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-113">The JIT compiler gives precedence to a source that requests the least amount of optimizing.</span></span>  <span data-ttu-id="84fbb-114">예를 들어, 프로파일러를 지정 하는 경우 `COR_PRF_DISABLE_INLINING` 시작 시 하지만 지정 하지 않습니다 `COR_PRF_CODEGEN_DISABLE_INLINING` 에 [icorprofilerfunctioncontrol:: Setcodegenflags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) 콜백 인라이닝 여전히 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-114">For example, if the profiler specifies `COR_PRF_DISABLE_INLINING` on startup, but does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in the [ICorProfilerFunctionControl::SetCodegenFlags](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setcodegenflags-method.md) callback, inlining is still disabled.</span></span>  <span data-ttu-id="84fbb-115">마찬가지로, 프로파일러를 지정 하지 않는 경우 `COR_PRF_CODEGEN_DISABLE_INLINING` 에 `SetCodegenFlags`, 하지만 다음 비활성화를 사용 하 여 인라인 처리는 [icorprofilercallback:: Jitinlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) 인라인 처리 콜백을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-115">Similarly, if the profiler does not specify `COR_PRF_CODEGEN_DISABLE_INLINING` in `SetCodegenFlags`, but then disables inlining by using the [ICorProfilerCallback::JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callback, inlining is disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84fbb-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84fbb-116">Requirements</span></span>  
 <span data-ttu-id="84fbb-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="84fbb-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84fbb-118">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="84fbb-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="84fbb-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84fbb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84fbb-120">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84fbb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84fbb-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84fbb-121">See Also</span></span>  
 [<span data-ttu-id="84fbb-122">ICorProfilerFunctionControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84fbb-122">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
