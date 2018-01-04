---
title: "ICorProfilerCallback4::ReJITCompilationStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback4.ReJITCompilationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 903db06089f7c68843b503c94483087ff9fce636
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a><span data-ttu-id="ed2a6-102">ICorProfilerCallback4::ReJITCompilationStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="ed2a6-102">ICorProfilerCallback4::ReJITCompilationStarted Method</span></span>
<span data-ttu-id="ed2a6-103">적시에 (JIT) 컴파일러는 함수를 다시 시작 했습니다 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-103">Notifies the profiler that the just-in-time (JIT) compiler has started to recompile a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed2a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed2a6-104">Syntax</span></span>  
  
```  
HRESULT ReJITCompilationStarted(    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed2a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed2a6-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="ed2a6-106">[in] JIT 컴파일러를 다시 컴파일하려면 시작 되는 함수의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-106">[in] The ID of the function that the JIT compiler has started to recompile.</span></span>  
  
 `rejitId`  
 <span data-ttu-id="ed2a6-107">[in] 다시 컴파일이 ID 새 버전의 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-107">[in] The recompilation ID of the new version of the function.</span></span>  
  
 `fIsSafeToBlock`  
 <span data-ttu-id="ed2a6-108">[in] `true` 차단;이 콜백에서 반환 하는 호출 스레드를 기다리는 런타임 시 있는지 나타내려면 `false` 차단는 영향을 주지 않는지 런타임에 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-108">[in] `true` to indicate that blocking may cause the runtime to wait for the calling thread to return from this callback; `false` to indicate that blocking will not affect the operation of the runtime.</span></span> <span data-ttu-id="ed2a6-109">값이 `true` 런타임에 대해, 영향을 주지 않으며 하지만 프로 파일링 결과 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-109">A value of `true` does not harm the runtime, but can affect the profiling results.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed2a6-110">설명</span><span class="sxs-lookup"><span data-stu-id="ed2a6-110">Remarks</span></span>  
 <span data-ttu-id="ed2a6-111">둘 이상의 쌍을 받을 수는 `ReJITCompilationStarted` 및 [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) 메서드 호출 각 함수에 대 한 방식으로 인해 런타임 핸들 클래스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-111">It is possible to receive more than one pair of `ReJITCompilationStarted` and [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) method calls for each function because of the way the runtime handles class constructors.</span></span> <span data-ttu-id="ed2a6-112">예를 들어 런타임에 메서드 A를 다시 컴파일하려면 시작 되기는 하지만 클래스 B에 대 한 클래스 생성자를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-112">For example, the runtime starts to recompile method A, but the class constructor for class B needs to be run.</span></span> <span data-ttu-id="ed2a6-113">따라서 런타임 클래스 B에 대 한 생성자를 다시 컴파일 및 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-113">Therefore, the runtime recompiles the constructor for class B and runs it.</span></span> <span data-ttu-id="ed2a6-114">생성자가 실행 되는 동안 A 메서드 A 다시 컴파일해야 하는 메서드를 호출을 하면 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-114">While the constructor is running, it makes a call to method A, which causes method A to be recompiled again.</span></span> <span data-ttu-id="ed2a6-115">이 시나리오에서 메서드 A의 첫 번째 다시 컴파일이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-115">In this scenario, the first recompilation of method A is halted.</span></span> <span data-ttu-id="ed2a6-116">그러나 둘 다 JIT 다시 컴파일 이벤트와 함께 A가 보고 하는 메서드를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-116">However, both attempts to recompile method A are reported with JIT recompilation events.</span></span>  
  
 <span data-ttu-id="ed2a6-117">프로파일러는 두 스레드 콜백 하 동시에 경우에 JIT 다시 컴파일 콜백의 시퀀스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-117">Profilers must support the sequence of JIT recompilation callbacks in cases where two threads are simultaneously making callbacks.</span></span> <span data-ttu-id="ed2a6-118">예를 들어, 호출 스레드가 A `ReJITCompilationStarted`; 있으 나 먼저 스레드 A 호출 [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), 스레드 B 호출 [icorprofilercallback:: Exceptionsearchfunctionenter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) 함수 ID로 `ReJITCompilationStarted` A. 스레드에 대 한 콜백 함수 ID 해야 아직 유효 하지 않은 표시 될 수 있습니다 때문에에 대 한 호출 [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) 프로파일러에서 아직 받지 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-118">For example, thread A calls `ReJITCompilationStarted`; however, before thread A calls [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), thread B calls [ICorProfilerCallback::ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) with the function ID from the `ReJITCompilationStarted` callback for thread A. It might appear that the function ID should not yet be valid because a call to [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) had not yet been received by the profiler.</span></span> <span data-ttu-id="ed2a6-119">그러나이 경우 함수 ID는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-119">However, in this case, the function ID is valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed2a6-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed2a6-120">Requirements</span></span>  
 <span data-ttu-id="ed2a6-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed2a6-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed2a6-122">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ed2a6-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ed2a6-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed2a6-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed2a6-124">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed2a6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed2a6-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed2a6-125">See Also</span></span>  
 [<span data-ttu-id="ed2a6-126">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed2a6-126">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ed2a6-127">ICorProfilerCallback4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed2a6-127">ICorProfilerCallback4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [<span data-ttu-id="ed2a6-128">JITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="ed2a6-128">JITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [<span data-ttu-id="ed2a6-129">ReJITCompilationFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="ed2a6-129">ReJITCompilationFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
