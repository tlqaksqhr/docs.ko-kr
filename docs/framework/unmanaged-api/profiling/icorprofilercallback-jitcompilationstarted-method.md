---
title: "ICorProfilerCallback::JITCompilationStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 12a25f452ccb121ef7ebcae05048eb7116b4ac48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a><span data-ttu-id="d47fe-102">ICorProfilerCallback::JITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="d47fe-102">ICorProfilerCallback::JITCompilationStarted Method</span></span>
<span data-ttu-id="d47fe-103">적시에 (JIT) 컴파일러의 함수 컴파일을 시작 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-103">Notifies the profiler that the just-in-time (JIT) compiler has started to compile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d47fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="d47fe-104">Syntax</span></span>  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d47fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d47fe-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="d47fe-106">[in] 컴파일을 시작 하는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-106">[in] The ID of the function for which the compilation is starting.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="d47fe-107">[in] 차단 여부를 나타내는 프로파일러 값 런타임의 작업에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-107">[in] A value indicating to the profiler whether blocking will affect the operation of the runtime.</span></span> <span data-ttu-id="d47fe-108">값은 `true` 차단;이 콜백에서 반환 하는 호출 스레드를 기다리는 런타임 시 경우 이렇게 하지 않으면 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-108">The value is `true` if blocking may cause the runtime to wait for the calling thread to return from this callback; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="d47fe-109">값이 있지만 `true` 런타임 나쁜 영향을 주지, 프로 파일링 결과 왜곡 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-109">Although a value of `true` will not harm the runtime, it can skew the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d47fe-110">설명</span><span class="sxs-lookup"><span data-stu-id="d47fe-110">Remarks</span></span>  
 <span data-ttu-id="d47fe-111">둘 이상의 쌍을 받을 수는 `JITCompilationStarted` 및 [icorprofilercallback:: Jitcompilationfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) 생성자를 호출 각 함수에 대 한 방식으로 인해 런타임 핸들 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-111">It is possible to receive more than one pair of `JITCompilationStarted` and [ICorProfilerCallback::JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="d47fe-112">예를 들어 JIT 컴파일 메서드 A는 런타임 시작 되기는 하지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-112">For example, the runtime starts to JIT-compile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="d47fe-113">따라서 런타임 JIT 컴파일은 클래스 B에 대 한 생성자 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-113">Therefore, the runtime JIT-compiles the constructor for class B and runs it.</span></span> <span data-ttu-id="d47fe-114">생성자가 실행 되는 동안 메서드에 A A를 다시 수 없는 JIT 컴파일된 메서드를 호출을 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-114">While the constructor is running, it makes a call to method A, which causes method A to be JIT-compiled again.</span></span> <span data-ttu-id="d47fe-115">이 시나리오에서 메서드 A의 첫 번째 JIT 컴파일 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-115">In this scenario, the first JIT compilation of method A is halted.</span></span> <span data-ttu-id="d47fe-116">그러나 JIT 컴파일 메서드 A 번의 시도가 모두 JIT 컴파일 이벤트로 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-116">However, both attempts to JIT-compile method A are reported with JIT-compilation events.</span></span> <span data-ttu-id="d47fe-117">프로파일러를 호출 하 여 Microsoft MSIL (intermediate language) 코드는 메서드에 대 한 대체 하려는 경우는 [icorprofilerinfo:: Setilfunctionbody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) 메서드를 둘 다에 대해 해야 `JITCompilationStarted` 이벤트, 하지만 동일한 MSIL 블록을 사용할 수 있습니다 모두 합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-117">If the profiler is going to replace Microsoft intermediate language (MSIL) code for method A by calling the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, it must do so for both `JITCompilationStarted` events, but it may use the same MSIL block for both.</span></span>  
  
 <span data-ttu-id="d47fe-118">프로파일러는 두 스레드 콜백 하 동시에 경우에 JIT 콜백 시퀀스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-118">Profilers must support the sequence of JIT callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="d47fe-119">예를 들어, 호출 스레드가 A `JITCompilationStarted`합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-119">For example, thread A calls `JITCompilationStarted`.</span></span> <span data-ttu-id="d47fe-120">그러나 스레드는 호출 전에 `JITCompilationFinished`, 스레드 B 호출 [icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) A의 스레드에서 함수 ID로 `JITCompilationStarted` 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-120">However, before thread A calls `JITCompilationFinished`, thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from thread A's `JITCompilationStarted` callback.</span></span> <span data-ttu-id="d47fe-121">함수 ID 해야 아직 유효 하지 않은 표시 될 수 있습니다 때문에에 대 한 호출 `JITCompilationFinished` 프로파일러에서 아직 받지 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-121">It might appear that the function ID should not yet be valid because a call to `JITCompilationFinished` had not yet been received by the profiler.</span></span> <span data-ttu-id="d47fe-122">그러나 이와 같은 경우에 함수 ID는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-122">However, in a case like this one, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d47fe-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d47fe-123">Requirements</span></span>  
 <span data-ttu-id="d47fe-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d47fe-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d47fe-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d47fe-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d47fe-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d47fe-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d47fe-127">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d47fe-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d47fe-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d47fe-128">See Also</span></span>  
 [<span data-ttu-id="d47fe-129">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d47fe-129">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="d47fe-130">JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="d47fe-130">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
