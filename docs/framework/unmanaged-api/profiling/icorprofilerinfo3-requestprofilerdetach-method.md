---
title: "ICorProfilerInfo3::RequestProfilerDetach 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.RequestProfilerDetach Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::RequestProfilerDetach
helpviewer_keywords:
- RequestProfilerDetach method [.NET Framework profiling]
- ICorProfilerInfo3::RequestProfilerDetach method [.NET Framework profiling]
ms.assetid: ea102e62-0454-4477-bcf3-126773acd184
topic_type: apiref
caps.latest.revision: "20"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33a5c45bbb64029177a0a680243dd39a825683e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a><span data-ttu-id="c16bf-102">ICorProfilerInfo3::RequestProfilerDetach 메서드</span><span class="sxs-lookup"><span data-stu-id="c16bf-102">ICorProfilerInfo3::RequestProfilerDetach Method</span></span>
<span data-ttu-id="c16bf-103">런타임에 프로파일러를 분리하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-103">Instructs the runtime to detach the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c16bf-104">구문</span><span class="sxs-lookup"><span data-stu-id="c16bf-104">Syntax</span></span>  
  
```  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c16bf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c16bf-105">Parameters</span></span>  
 `dwExpectedCompletionMilliseconds`  
 <span data-ttu-id="c16bf-106">[in] 프로파일러를 언로드하기에 안전한지를 확인하기 전에 CLR(공용 언어 런타임)이 대기해야 하는 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-106">[in] The length of time, in milliseconds, the common language runtime (CLR) should wait before checking to see whether it is safe to unload the profiler.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c16bf-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c16bf-107">Return Value</span></span>  
 <span data-ttu-id="c16bf-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c16bf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c16bf-109">HRESULT</span></span>|<span data-ttu-id="c16bf-110">설명</span><span class="sxs-lookup"><span data-stu-id="c16bf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c16bf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c16bf-111">S_OK</span></span>|<span data-ttu-id="c16bf-112">분리 요청이 유효하고 분리 절차는 다른 스레드에서 계속 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-112">The detach request is valid, and the detach procedure is now continuing on another thread.</span></span> <span data-ttu-id="c16bf-113">분리가 완료되면 `ProfilerDetachSucceeded` 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-113">When the detach is fully complete, a `ProfilerDetachSucceeded` event is issued.</span></span>|  
|<span data-ttu-id="c16bf-114">E_ CORPROF_E_CALLBACK3_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="c16bf-114">E_ CORPROF_E_CALLBACK3_REQUIRED</span></span>|<span data-ttu-id="c16bf-115">프로파일러가 실패 했습니다는 [iunknown:: Queryinterface](http://go.microsoft.com/fwlink/?LinkID=144867) 시도 하는 [ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md) 인터페이스를 분리 작업을 지원 하기 위해 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-115">The profiler failed an [IUnknown::QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) attempt for the [ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md) interface, which it must implement to support the detach operation.</span></span> <span data-ttu-id="c16bf-116">분리가 시도되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-116">Detach was not attempted.</span></span>|  
|<span data-ttu-id="c16bf-117">CORPROF_E_IMMUTABLE_FLAGS_SET</span><span class="sxs-lookup"><span data-stu-id="c16bf-117">CORPROF_E_IMMUTABLE_FLAGS_SET</span></span>|<span data-ttu-id="c16bf-118">프로파일러가 시작 시 변경할 수 없는 플래그를 설정하므로 분리가 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-118">Detachment is impossible because the profiler set immutable flags at startup.</span></span> <span data-ttu-id="c16bf-119">분리가 시도되지 않았고 프로파일러가 완전히 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-119">Detachment was not attempted; the profiler is still fully attached.</span></span>|  
|<span data-ttu-id="c16bf-120">CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT</span><span class="sxs-lookup"><span data-stu-id="c16bf-120">CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT</span></span>|<span data-ttu-id="c16bf-121">분리가 사용 되는 프로파일러 Microsoft MSIL (intermediate language) 코드를 계측 하기 때문에 불가능 또는 삽입 된 `enter` / `leave` 후크입니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-121">Detachment is impossible because the profiler used instrumented Microsoft intermediate language (MSIL) code, or inserted `enter`/`leave` hooks.</span></span> <span data-ttu-id="c16bf-122">분리가 시도되지 않았고 프로파일러가 완전히 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-122">Detachment was not attempted; the profiler is still fully attached.</span></span><br /><br /> <span data-ttu-id="c16bf-123">**참고** 계측 된 MSIL은 코드는 코드를 사용 하 여 프로파일러에서 제공 하는 [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c16bf-123">**Note** Instrumented MSIL is code is code that is provided by the profiler using the [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>|  
|<span data-ttu-id="c16bf-124">CORPROF_E_RUNTIME_UNINITIALIZED</span><span class="sxs-lookup"><span data-stu-id="c16bf-124">CORPROF_E_RUNTIME_UNINITIALIZED</span></span>|<span data-ttu-id="c16bf-125">관리되는 응용 프로그램에서 런타임이 아직 초기화되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-125">The runtime has not been initialized yet in the managed application.</span></span> <span data-ttu-id="c16bf-126">즉, 런타임이 완전히 로드되지 않았습니다. 프로파일러 콜백의 내에서 분리가 요청 하는 경우이 오류 코드가 반환 될 수 있습니다 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c16bf-126">(That is, the runtime has not been fully loaded.) This error code may be returned when detachment is requested inside the profiler callback's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) method.</span></span>|  
|<span data-ttu-id="c16bf-127">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE</span><span class="sxs-lookup"><span data-stu-id="c16bf-127">CORPROF_E_UNSUPPORTED_CALL_SEQUENCE</span></span>|<span data-ttu-id="c16bf-128">지원되지 않는 시간에 `RequestProfilerDetach`가 호출되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-128">`RequestProfilerDetach` was called at an unsupported time.</span></span> <span data-ttu-id="c16bf-129">이 메서드 내에서 아니라 관리 되는 스레드에서 호출 되 면 발생는 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 메서드 내에서 또는 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 가비지 수집을 허용할 수 없는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-129">This occurs if the method is called on a managed thread but not from within an [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) method or from within an [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) method that cannot tolerate a garbage collection.</span></span> <span data-ttu-id="c16bf-130">자세한 내용은 참조 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-130">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c16bf-131">설명</span><span class="sxs-lookup"><span data-stu-id="c16bf-131">Remarks</span></span>  
 <span data-ttu-id="c16bf-132">분리 절차 중에 분리 스레드(프로파일러 분리를 위해 특별히 만들어진 스레드)는 가끔 모든 스레드가 프로파일러 코드를 종료했는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-132">During the detach procedure, the detach thread (the thread created specifically for detaching the profiler) occasionally checks whether all threads have exited the profiler’s code.</span></span> <span data-ttu-id="c16bf-133">프로파일러는 `dwExpectedCompletionMilliseconds` 매개 변수를 통해 소요 시간 예상 값을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-133">The profiler should provide an estimate of how long this should take through the `dwExpectedCompletionMilliseconds` parameter.</span></span> <span data-ttu-id="c16bf-134">프로파일러가 특정 `ICorProfilerCallback*` 메서드 내에서 사용하는 일반적인 시간을 값으로 사용하는 것이 좋습니다. 이 값은 프로파일러의 최대 소요 예상 시간의 절반 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-134">A good value to use is the typical amount of time the profiler spends inside any given `ICorProfilerCallback*` method; this value should not be less than half of the maximum amount of time the profiler expects to spend.</span></span>  
  
 <span data-ttu-id="c16bf-135">분리 스레드에서는 `dwExpectedCompletionMilliseconds`를 사용하여 프로파일러 콜백 코드가 스택에서 모두 제거되었는지를 확인하기 전의 대기 기간을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-135">The detach thread uses `dwExpectedCompletionMilliseconds` to decide how long to sleep before checking whether profiler callback code has been popped off all stacks.</span></span> <span data-ttu-id="c16bf-136">다음 알고리즘의 세부 정보는 CLR의 미래 릴리스에 변경될 수 있지만 프로파일러를 안전하게 언로드할 수 있는 시점을 결정할 때 `dwExpectedCompletionMilliseconds`를 사용할 수 있는 한 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-136">Although the details of the following algorithm may change in future releases of the CLR, it illustrates one way `dwExpectedCompletionMilliseconds` can be used when determining when it is safe to unload the profiler.</span></span> <span data-ttu-id="c16bf-137">분리 스레드는 먼저 `dwExpectedCompletionMilliseconds`밀리초 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-137">The detach thread first sleeps for `dwExpectedCompletionMilliseconds` milliseconds.</span></span> <span data-ttu-id="c16bf-138">찾은 후에 절전 모드에서 활성화 된, CLR 프로파일러 콜백 코드가 아직 있다는, 분리 스레드 대기 다시,이 이번에는 두 번 `dwExpectedCompletionMilliseconds` 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-138">If, after awakening from the sleep, the CLR finds that profiler callback code is still present, the detach thread sleeps again, this time for two times `dwExpectedCompletionMilliseconds` milliseconds.</span></span> <span data-ttu-id="c16bf-139">이 두 번째 대기에서 활성화된 후 분리 스레드는 프로파일러 콜백 코드가 아직 있다는 것을 확인하면 다시 확인하기 전에 10분 동안 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-139">If, after awakening from this second sleep, the detach thread finds that profiler callback code is still present, it sleeps for 10 minutes before checking again.</span></span> <span data-ttu-id="c16bf-140">분리 스레드는 10분마다 계속 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-140">The detach thread continues to recheck every 10 minutes.</span></span>  
  
 <span data-ttu-id="c16bf-141">프로파일러가 `dwExpectedCompletionMilliseconds`를 0(영)으로 지정하면 CLR은 5초 후, 다시 10초 후, 이후 10분마다 확인을 수행할 것임을 의미하는 기본값 5000을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-141">If the profiler specifies `dwExpectedCompletionMilliseconds` as 0 (zero), the CLR uses a default value of 5000, which means that it will perform a check after 5 seconds, again after 10 seconds, and then every 10 minutes thereafter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c16bf-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c16bf-142">Requirements</span></span>  
 <span data-ttu-id="c16bf-143">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c16bf-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c16bf-144">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c16bf-144">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c16bf-145">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c16bf-145">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c16bf-146">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c16bf-146">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c16bf-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c16bf-147">See Also</span></span>  
 [<span data-ttu-id="c16bf-148">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c16bf-148">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="c16bf-149">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c16bf-149">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="c16bf-150">프로파일링</span><span class="sxs-lookup"><span data-stu-id="c16bf-150">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
