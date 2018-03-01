---
title: "ICorProfilerInfo2::DoStackSnapshot 메서드"
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
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5548254eb160547643a874fd2e31a085ec6f3ecb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a><span data-ttu-id="2694a-102">ICorProfilerInfo2::DoStackSnapshot 메서드</span><span class="sxs-lookup"><span data-stu-id="2694a-102">ICorProfilerInfo2::DoStackSnapshot Method</span></span>
<span data-ttu-id="2694a-103">에서는 지정 된 스레드에 대 한 스택 관리 되는 프레임에 설명 하 고 프로파일러는 콜백을 통해 정보를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-103">Walks the managed frames on the stack for the specified thread, and sends information to the profiler through a callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2694a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2694a-104">Syntax</span></span>  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2694a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2694a-105">Parameters</span></span>  
 `thread`  
 <span data-ttu-id="2694a-106">[in] 대상 스레드가의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-106">[in] The ID of the target thread.</span></span>  
  
 <span data-ttu-id="2694a-107">에 null을 전달 `thread` 현재 스레드에 대 한 스냅숏을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-107">Passing null in `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="2694a-108">경우는 `ThreadID` 의 다른 스레드에 전달 됩니다, 공용 언어 런타임 (CLR) 해당 스레드를 일시 중단, 스냅숏, 수행 및 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-108">If a `ThreadID` of a different thread is passed, the common language runtime (CLR) suspends that thread, performs the snapshot, and resumes.</span></span>  
  
 `callback`  
 <span data-ttu-id="2694a-109">[in] 구현에 대 한 포인터는 [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) 메서드를 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보와 함께 프로파일러를 제공 하는 CLR에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-109">[in] A pointer to the implementation of the [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) method, which is called by the CLR to provide the profiler with information on each managed frame and each run of unmanaged frames.</span></span>  
  
 <span data-ttu-id="2694a-110">`StackSnapshotCallback` 메서드는 프로파일러 기록기에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-110">The `StackSnapshotCallback` method is implemented by the profiler writer.</span></span>  
  
 `infoFlags`  
 <span data-ttu-id="2694a-111">[in] 값은 [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) 하 여 각 프레임에 대 한 다시 전달할 데이터의 양을 지정 하는 열거형 `StackSnapshotCallback`합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-111">[in] A value of the [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) enumeration, which specifies the amount of data to be passed back for each frame by `StackSnapshotCallback`.</span></span>  
  
 `clientData`  
 <span data-ttu-id="2694a-112">[in] 에 직접 전달 되는 클라이언트 데이터에 대 한 포인터는 `StackSnapshotCallback` 콜백 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-112">[in] A pointer to the client data, which is passed straight through to the `StackSnapshotCallback` callback function.</span></span>  
  
 `context`  
 <span data-ttu-id="2694a-113">[in] Win32에 대 한 포인터 `CONTEXT` 스택 워크를 초기값으로 사용 되는 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-113">[in] A pointer to a Win32 `CONTEXT` structure, which is used to seed the stack walk.</span></span> <span data-ttu-id="2694a-114">Win32 `CONTEXT` 구조 CPU 레지스터의 값을 포함 하 고 특정 시점에서 CPU의 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-114">The Win32 `CONTEXT` structure contains values of the CPU registers and represents the state of the CPU at a particular moment in time.</span></span>  
  
 <span data-ttu-id="2694a-115">시드 스택 워크가 스택의 맨이 관리 되지 않는 도우미 코드; 시작 위치를 결정 하는 CLR을 사용 하면 그렇지 않으면 초기값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-115">The seed helps the CLR determine where to begin the stack walk, if the top of the stack is unmanaged helper code; otherwise, the seed is ignored.</span></span> <span data-ttu-id="2694a-116">비동기 워크에 대 한 초기값을 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-116">A seed must be supplied for an asynchronous walk.</span></span> <span data-ttu-id="2694a-117">동기 워크를 수행 하는 없는 시드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-117">If you are doing a synchronous walk, no seed is necessary.</span></span>  
  
 <span data-ttu-id="2694a-118">`context` 매개 변수는 COR_PRF_SNAPSHOT_CONTEXT 플래그에 전달 된 경우에 유효는 `infoFlags` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-118">The `context` parameter is valid only if the COR_PRF_SNAPSHOT_CONTEXT flag was passed in the `infoFlags` parameter.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="2694a-119">[in] 크기는 `CONTEXT` 에서 참조 하는 구조는 `context` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-119">[in] The size of the `CONTEXT` structure, which is referenced by the `context` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2694a-120">설명</span><span class="sxs-lookup"><span data-stu-id="2694a-120">Remarks</span></span>  
 <span data-ttu-id="2694a-121">에 대 한 null을 전달 `thread` 현재 스레드에 대 한 스냅숏을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-121">Passing null for `thread` yields a snapshot of the current thread.</span></span> <span data-ttu-id="2694a-122">대상 스레드가 일시 중단 된 경우에 스냅숏은 다른 스레드의 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-122">Snapshots can be taken of other threads only if the target thread is suspended at the time.</span></span>  
  
 <span data-ttu-id="2694a-123">프로파일러가 스택을 탐색 하는 경우 호출 `DoStackSnapshot`합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-123">When the profiler wants to walk the stack, it calls `DoStackSnapshot`.</span></span> <span data-ttu-id="2694a-124">CLR에서 해당 호출에서 반환 되기 전에 호출 하면 `StackSnapshotCallback` 여러 번 한 번 각각에 대해 관리 되는 프레임 (또는 관리 되지 않는 프레임의 실행) 스택에 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-124">Before the CLR returns from that call, it calls your `StackSnapshotCallback` several times, once for each managed frame (or run of unmanaged frames) on the stack.</span></span> <span data-ttu-id="2694a-125">관리 되지 않는 프레임이 발생 한 경우를 검색 해야 해당 사용자가 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-125">When unmanaged frames are encountered, you must walk them yourself.</span></span>  
  
 <span data-ttu-id="2694a-126">스택 워크는 순서는 반대 프레임으로 스택에 밀어넣은 어떻게입니다: (마지막 푸시할) 첫 번째, 기본 (첫 번째 푸시) 프레임별 마지막 리프입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-126">The order in which the stack is walked is the reverse of how the frames were pushed onto the stack: leaf (last-pushed) frame first, main (first-pushed) frame last.</span></span>  
  
 <span data-ttu-id="2694a-127">프로파일러는 관리 되는 스택 워크를 프로그래밍 하는 방법에 대 한 자세한 내용은 참조 [.NET Framework 2.0의 프로파일러 스택 워크: 기본 사항 및 기능 이외에](http://go.microsoft.com/fwlink/?LinkId=73638)합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-127">For more information about how to program the profiler to walk managed stacks, see [Profiler Stack Walking in the .NET Framework 2.0: Basics and Beyond](http://go.microsoft.com/fwlink/?LinkId=73638).</span></span>  
  
 <span data-ttu-id="2694a-128">다음 섹션에 설명 된 대로 스택 워크는 동기적 이거나 비동기적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-128">A stack walk can be synchronous or asynchronous, as explained in the following sections.</span></span>  
  
## <a name="synchronous-stack-walk"></a><span data-ttu-id="2694a-129">동기 스택 워크</span><span class="sxs-lookup"><span data-stu-id="2694a-129">Synchronous Stack Walk</span></span>  
 <span data-ttu-id="2694a-130">동기 스택 워크는 콜백에 대 한 응답의 현재 스레드 스택을 탐색 하는 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-130">A synchronous stack walk involves walking the stack of the current thread in response to a callback.</span></span> <span data-ttu-id="2694a-131">시드 나 일시 중단에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-131">It does not require seeding or suspending.</span></span>  
  
 <span data-ttu-id="2694a-132">동기 수행한 프로파일러 중 하나를 호출 하는 CLR에 대 한 응답으로 호출 하는 시기를 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (또는 [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) 메서드를 호출 하면 `DoStackSnapshot` 의 스택을 탐색 하 고 현재 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-132">You make a synchronous call when, in response to the CLR calling one of your profiler's [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (or [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) methods, you call `DoStackSnapshot` to walk the stack of the current thread.</span></span> <span data-ttu-id="2694a-133">스택 모양을 알림을에서 같은 보려는 경우 유용 [icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-133">This is useful when you want to see what the stack looks like at a notification such as [ICorProfilerCallback::ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md).</span></span> <span data-ttu-id="2694a-134">호출 하면 `DoStackSnapshot` 내에서 프로그램 `ICorProfilerCallback` 에 null을 전달 메서드는 `context` 및 `thread` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-134">You just call `DoStackSnapshot` from within your `ICorProfilerCallback` method, passing null in the `context` and `thread` parameters.</span></span>  
  
## <a name="asynchronous-stack-walk"></a><span data-ttu-id="2694a-135">비동기 스택 워크</span><span class="sxs-lookup"><span data-stu-id="2694a-135">Asynchronous Stack Walk</span></span>  
 <span data-ttu-id="2694a-136">비동기 스택 워크는 다른 스레드의 스택 또는 현재 스레드의 현재 스레드에 대 한 스택 워크가 하지만 콜백에 대 한 응답에 없는 과정이 수반 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-136">An asynchronous stack walk entails walking the stack of a different thread, or walking the stack of the current thread, not in response to a callback, but by hijacking the current thread's instruction pointer.</span></span> <span data-ttu-id="2694a-137">비동기 워크 필요 스택 맨 관리 되지 않는 하지 않은 코드를 플랫폼의 일부 이면 시드 호출 (PInvoke) 또는 COM 호출 되었지만 CLR 자체의 도우미 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-137">An asynchronous walk requires a seed if the top of the stack is unmanaged code that is not part of a platform invoke (PInvoke) or COM call, but helper code in the CLR itself.</span></span> <span data-ttu-id="2694a-138">예를 들어 코드 적시에 (JIT) 컴파일 또는 가비지 수집을 수행 하는 도우미 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-138">For example, code that does just-in-time (JIT) compiling or garbage collection is helper code.</span></span>  
  
 <span data-ttu-id="2694a-139">직접 대상 스레드가 일시 중단 하 여 초기값을 가져와야 하 고 스택 워크 맨 위의 찾을 때까지 직접 관리 되는 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-139">You obtain a seed by directly suspending the target thread and walking its stack yourself, until you find the topmost managed frame.</span></span> <span data-ttu-id="2694a-140">대상 스레드를 일시 중단 된 후에 대상 스레드의 현재 레지스터 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-140">After the target thread is suspended, get the target thread's current register context.</span></span> <span data-ttu-id="2694a-141">다음으로 호출 하 여 비관리 코드에 레지스터 컨텍스트로 가리키는지 여부를 결정 [icorprofilerinfo:: Getfunctionfromip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) -반환 하는 경우는 `FunctionID` 0과 같은 프레임은 관리 되지 않는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-141">Next, determine whether the register context points to unmanaged code by calling [ICorProfilerInfo::GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) — if it returns a `FunctionID` equal to zero, the frame is unmanaged code.</span></span> <span data-ttu-id="2694a-142">첫 번째 관리 되는 프레임에 도달 하 고 해당 프레임에 대 한 레지스터 컨텍스트에 따라 시드 컨텍스트 계산 될 때까지 스택을 이제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-142">Now, walk the stack until you reach the first managed frame, and then calculate the seed context based on the register context for that frame.</span></span>  
  
 <span data-ttu-id="2694a-143">호출 `DoStackSnapshot` 비동기 스택 워크를 시작 하 여 시드 컨텍스트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-143">Call `DoStackSnapshot` with your seed context to begin the asynchronous stack walk.</span></span> <span data-ttu-id="2694a-144">초기값을 지정 하지 않으면 경우 `DoStackSnapshot` 스택의 맨 위에 있는 관리 되는 프레임을 건너뛸 수 있습니다 및 결과적 하면 스택 워크가 불완전 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-144">If you do not supply a seed, `DoStackSnapshot` might skip managed frames at the top of the stack and, consequently, will give you an incomplete stack walk.</span></span> <span data-ttu-id="2694a-145">JIT 컴파일 또는 네이티브 이미지 생성기 (Ngen.exe)를 가리켜야 초기값을 제공한 경우-생성 된 코드입니다. 그렇지 않으면 `DoStackSnapshot` CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-145">If you do supply a seed, it must point to JIT-compiled or Native Image Generator (Ngen.exe)-generated code; otherwise, `DoStackSnapshot` returns the failure code, CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX.</span></span>  
  
 <span data-ttu-id="2694a-146">비동기 스택 워크 수 쉽게 교착 상태가 발생할 또는 액세스 위반, 다음이 지침을 따르지 않는 경우:</span><span class="sxs-lookup"><span data-stu-id="2694a-146">Asynchronous stack walks can easily cause deadlocks or access violations, unless you follow these guidelines:</span></span>  
  
-   <span data-ttu-id="2694a-147">직접 스레드를 중지 하면에서 관리 되는 코드를 실행 하지 않은 스레드만 다른 스레드를 일시 중단 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-147">When you directly suspend threads, remember that only a thread that has never run managed code can suspend another thread.</span></span>  
  
-   <span data-ttu-id="2694a-148">블록 항상 프로그램 [icorprofilercallback:: Threaddestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) 해당 스레드의 스택 워크 완료 될 때까지 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-148">Always block in your [ICorProfilerCallback::ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) callback until that thread's stack walk is complete.</span></span>  
  
-   <span data-ttu-id="2694a-149">프로파일러 가비지 수집을 트리거할 수 있는 CLR 함수를 호출 하는 동안 잠금을 보유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-149">Do not hold a lock while your profiler calls into a CLR function that can trigger a garbage collection.</span></span> <span data-ttu-id="2694a-150">즉, 소유 하는 스레드에서 가비지 수집을 트리거하는 호출을 수행할 수 있는 경우는 잠금을 유지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-150">That is, do not hold a lock if the owning thread might make a call that triggers a garbage collection.</span></span>  
  
 <span data-ttu-id="2694a-151">이기도 교착 상태의 위험이 호출 하는 경우 `DoStackSnapshot` 별도 대상 스레드 스택을 탐색할 수 있도록 프로파일러 만든 스레드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-151">There is also a risk of deadlock if you call `DoStackSnapshot` from a thread that your profiler has created so that you can walk the stack of a separate target thread.</span></span> <span data-ttu-id="2694a-152">특정 처음으로 만든 스레드에서 시작 `ICorProfilerInfo*` 메서드 (포함 하 여 `DoStackSnapshot`), CLR 스레드별 해당 스레드에서 CLR 관련 초기화를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-152">The first time the thread you created enters certain `ICorProfilerInfo*` methods (including `DoStackSnapshot`), the CLR will perform per-thread, CLR-specific initialization on that thread.</span></span> <span data-ttu-id="2694a-153">프로파일러는를 안내 하려는 해당 스택 대상 스레드가 일시 중단 및 해당 대상 스레드가이 스레드 초기화를 수행 하는 데 필요한 잠금을 소유한에 발생 하는 경우 교착 상태가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-153">If your profiler has suspended the target thread whose stack you are trying to walk, and if that target thread happened to own a lock necessary for performing this per-thread initialization, a deadlock will occur.</span></span> <span data-ttu-id="2694a-154">이러한 교착 상태를 방지 하려면 초기에 호출을 확인 `DoStackSnapshot` 안내 하는 경우 프로파일러 만든 스레드에서는 별도 스레드를 대상으로 하지만 대상 스레드를 먼저 일시지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-154">To avoid this deadlock, make an initial call into `DoStackSnapshot` from your profiler-created thread to walk a separate target thread, but do not suspend the target thread first.</span></span> <span data-ttu-id="2694a-155">이 초기 호출 스레드를 초기화 하는 교착 상태 없이 완료할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-155">This initial call ensures that the per-thread initialization can complete without deadlock.</span></span> <span data-ttu-id="2694a-156">경우 `DoStackSnapshot` 성공 하 고 하나 이상의 프레임을 보고 해당 시점 이후에 것이 해당 프로파일러 만든 스레드를 모든 대상 스레드 및 호출을 일시 중단에 대 한 안전 `DoStackSnapshot` 대상 스레드 스택을 탐색 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-156">If `DoStackSnapshot` succeeds and reports at least one frame, after that point, it will be safe for that profiler-created thread to suspend any target thread and call `DoStackSnapshot` to walk the stack of that target thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2694a-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2694a-157">Requirements</span></span>  
 <span data-ttu-id="2694a-158">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2694a-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2694a-159">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2694a-159">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2694a-160">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2694a-160">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2694a-161">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2694a-161">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2694a-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2694a-162">See Also</span></span>  
 [<span data-ttu-id="2694a-163">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2694a-163">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="2694a-164">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2694a-164">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
