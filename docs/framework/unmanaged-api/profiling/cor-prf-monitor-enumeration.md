---
title: "COR_PRF_MONITOR 열거형"
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
- COR_PRF_MONITOR
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_MONITOR
helpviewer_keywords:
- COR_PRF_MONITOR enumeration [.NET Framework profiling]
ms.assetid: 9294d702-b4e5-441c-a930-e63d27b86bfd
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e6dc135681d11a496dbc27553d46a5d101b6d7b9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corprfmonitor-enumeration"></a><span data-ttu-id="c553e-102">COR_PRF_MONITOR 열거형</span><span class="sxs-lookup"><span data-stu-id="c553e-102">COR_PRF_MONITOR Enumeration</span></span>
<span data-ttu-id="c553e-103">프로파일러가 구독하려는 동작, 기능 또는 이벤트를 지정하는 데 사용되는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-103">Contains values that are used to specify behavior, capabilities, or events to which the profiler wishes to subscribe.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c553e-104">구문</span><span class="sxs-lookup"><span data-stu-id="c553e-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_MONITOR_NONE                = 0x00000000,  
    COR_PRF_MONITOR_FUNCTION_UNLOADS    = 0x00000001,  
    COR_PRF_MONITOR_CLASS_LOADS         = 0x00000002,  
    COR_PRF_MONITOR_MODULE_LOADS        = 0x00000004,  
    COR_PRF_MONITOR_ASSEMBLY_LOADS      = 0x00000008,  
    COR_PRF_MONITOR_APPDOMAIN_LOADS     = 0x00000010,  
    COR_PRF_MONITOR_JIT_COMPILATION     = 0x00000020,  
    COR_PRF_MONITOR_EXCEPTIONS          = 0x00000040,  
    COR_PRF_MONITOR_GC                  = 0x00000080,  
    COR_PRF_MONITOR_OBJECT_ALLOCATED    = 0x00000100,  
    COR_PRF_MONITOR_THREADS             = 0x00000200,  
    COR_PRF_MONITOR_REMOTING            = 0x00000400,  
    COR_PRF_MONITOR_CODE_TRANSITIONS    = 0x00000800,  
    COR_PRF_MONITOR_ENTERLEAVE          = 0x00001000,  
    COR_PRF_MONITOR_CCW                 = 0x00002000,  
    COR_PRF_MONITOR_REMOTING_COOKIE     = 0x00004000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_REMOTING_ASYNC      = 0x00008000 |   
                                          COR_PRF_MONITOR_REMOTING,  
    COR_PRF_MONITOR_SUSPENDS            = 0x00010000,  
    COR_PRF_MONITOR_CACHE_SEARCHES      = 0x00020000,  
    COR_PRF_ENABLE_REJIT                = 0x00040000,  
    COR_PRF_ENABLE_INPROC_DEBUGGING     = 0x00080000,  
    COR_PRF_ENABLE_JIT_MAPS             = 0x00100000,  
    COR_PRF_DISABLE_INLINING            = 0x00200000,  
    COR_PRF_DISABLE_OPTIMIZATIONS       = 0x00400000,  
    COR_PRF_ENABLE_OBJECT_ALLOCATED     = 0x00800000,  
    COR_PRF_MONITOR_CLR_EXCEPTIONS      = 0x01000000,  
    COR_PRF_MONITOR_ALL                 = 0x0107FFFF,  
    COR_PRF_ENABLE_FUNCTION_ARGS        = 0X02000000,  
    COR_PRF_ENABLE_FUNCTION_RETVAL      = 0X04000000,  
    COR_PRF_ENABLE_FRAME_INFO           = 0X08000000,  
    COR_PRF_ENABLE_STACK_SNAPSHOT       = 0X10000000,  
    COR_PRF_USE_PROFILE_IMAGES          = 0x20000000,  
    COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST  
                                        = 0x40000000,  
    COR_PRF_DISABLE_ALL_NGEN_IMAGES     = 0x80000000,  
    COR_PRF_ALL                         = 0x8FFFFFFF,  
    COR_PRF_REQUIRE_PROFILE_IMAGE       = COR_PRF_USE_PROFILE_IMAGES |   
                                          COR_PRF_MONITOR_CODE_TRANSITIONS |   
                                          COR_PRF_MONITOR_ENTERLEAVE,  
    COR_PRF_ALLOWABLE_AFTER_ATTACH      = COR_PRF_MONITOR_THREADS |  
                                          COR_PRF_MONITOR_MODULE_LOADS |  
                                          COR_PRF_MONITOR_ASSEMBLY_LOADS |  
                                          COR_PRF_MONITOR_APPDOMAIN_LOADS |  
                                          COR_PRF_ENABLE_STACK_SNAPSHOT |  
                                          COR_PRF_MONITOR_GC |  
                                          COR_PRF_MONITOR_SUSPENDS |  
                                          COR_PRF_MONITOR_CLASS_LOADS |  
                                          COR_PRF_MONITOR_JIT_COMPILATION,  
    COR_PRF_MONITOR_IMMUTABLE           = COR_PRF_MONITOR_CODE_TRANSITIONS |  
                                          COR_PRF_MONITOR_REMOTING |  
                                          COR_PRF_MONITOR_REMOTING_COOKIE |  
                                          COR_PRF_MONITOR_REMOTING_ASYNC |  
                                          COR_PRF_ENABLE_REJIT |  
                                          COR_PRF_ENABLE_INPROC_DEBUGGING |  
                                          COR_PRF_ENABLE_JIT_MAPS |  
                                          COR_PRF_DISABLE_OPTIMIZATIONS |  
                                          COR_PRF_DISABLE_INLINING |  
                                          COR_PRF_ENABLE_OBJECT_ALLOCATED |  
                                          COR_PRF_ENABLE_FUNCTION_ARGS |  
                                          COR_PRF_ENABLE_FUNCTION_RETVAL |  
                                          COR_PRF_ENABLE_FRAME_INFO |  
                                          COR_PRF_USE_PROFILE_IMAGES |  
                     COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST |  
                                          COR_PRF_DISABLE_ALL_NGEN_IMAGES  
} COR_PRF_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="c553e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="c553e-105">Members</span></span>  
 <span data-ttu-id="c553e-106">다음 섹션은 `COR_PRF_MONITOR` 열거형 멤버 범주별으로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-106">The following sections list `COR_PRF_MONITOR` enumeration members by category.</span></span> <span data-ttu-id="c553e-107">범주는:</span><span class="sxs-lookup"><span data-stu-id="c553e-107">The categories are:</span></span>  
  
-   [<span data-ttu-id="c553e-108">설정 된 플래그 없음</span><span class="sxs-lookup"><span data-stu-id="c553e-108">No flags set</span></span>](#None)  
  
-   [<span data-ttu-id="c553e-109">콜백 플래그</span><span class="sxs-lookup"><span data-stu-id="c553e-109">Callback flags</span></span>](#Callback)  
  
-   [<span data-ttu-id="c553e-110">기능 사용 플래그</span><span class="sxs-lookup"><span data-stu-id="c553e-110">Feature-enabling flags</span></span>](#Feature)  
  
-   [<span data-ttu-id="c553e-111">구성 플래그</span><span class="sxs-lookup"><span data-stu-id="c553e-111">Configuration flags</span></span>](#Config)  
  
-   [<span data-ttu-id="c553e-112">복합 플래그</span><span class="sxs-lookup"><span data-stu-id="c553e-112">Composite flags</span></span>](#Composite)  
  
<a name="None"></a>   
### <a name="no-flags-set"></a><span data-ttu-id="c553e-113">설정 된 플래그 없음</span><span class="sxs-lookup"><span data-stu-id="c553e-113">No flags set</span></span>  
  
|<span data-ttu-id="c553e-114">멤버</span><span class="sxs-lookup"><span data-stu-id="c553e-114">Member</span></span>|<span data-ttu-id="c553e-115">설명</span><span class="sxs-lookup"><span data-stu-id="c553e-115">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_NONE`|<span data-ttu-id="c553e-116">플래그가 설정되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-116">No flags are set.</span></span>|  
  
<a name="Callback"></a>   
### <a name="callback-flags"></a><span data-ttu-id="c553e-117">콜백 플래그</span><span class="sxs-lookup"><span data-stu-id="c553e-117">Callback flags</span></span>  
  
|<span data-ttu-id="c553e-118">멤버</span><span class="sxs-lookup"><span data-stu-id="c553e-118">Member</span></span>|<span data-ttu-id="c553e-119">설명</span><span class="sxs-lookup"><span data-stu-id="c553e-119">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="c553e-120">모든 콜백 이벤트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-120">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_APPDOMAIN_LOADS`|<span data-ttu-id="c553e-121">컨트롤의 `AppDomainCreation*` 및 `AppDomainShutdown*` 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-121">Controls the `AppDomainCreation*` and `AppDomainShutdown*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_ASSEMBLY_LOADS`|<span data-ttu-id="c553e-122">컨트롤의 `AssemblyLoad*` 및 `AssemblyUnload*` 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-122">Controls the `AssemblyLoad*` and `AssemblyUnload*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CACHE_SEARCHES`|<span data-ttu-id="c553e-123">컨트롤의 `JITCachedFunctionSearch*` 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-123">Controls the `JITCachedFunctionSearch*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span><br /><br /> <span data-ttu-id="c553e-124">이 플래그의 동작은 .NET Framework 버전 2.0에서 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-124">The behavior of this flag is changed in the .NET Framework version 2.0.</span></span>|  
|`COR_PRF_MONITOR_CCW`|<span data-ttu-id="c553e-125">컨트롤의 `COMClassicVTable*` 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-125">Controls the `COMClassicVTable*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLASS_LOADS`|<span data-ttu-id="c553e-126">컨트롤의 `ClassLoad*` 및 `ClassUnload*` 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-126">Controls the `ClassLoad*` and `ClassUnload*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CLR_EXCEPTIONS`|<span data-ttu-id="c553e-127">컨트롤의 `ExceptionCLRCatcher*` 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-127">Controls the `ExceptionCLRCatcher*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_CODE_TRANSITIONS`|<span data-ttu-id="c553e-128">컨트롤의 [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) 및 [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c553e-128">Controls the [UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md) and [ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface</span></span>|  
|`COR_PRF_MONITOR_ENTERLEAVE`|<span data-ttu-id="c553e-129">컨트롤의 `FunctionEnter*`, `FunctionLeave*`, 및 `FunctionTailCall*` [프로 파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-129">Controls the `FunctionEnter*`,  `FunctionLeave*`, and `FunctionTailCall*`[profiling global static functions](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md).</span></span>|  
|`COR_PRF_MONITOR_EXCEPTIONS`|<span data-ttu-id="c553e-130">컨트롤의 [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md) 콜백 및 `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, 및 `ExceptionCatcher*` 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-130">Controls the [ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md) callback and the `ExceptionSearch*`, `ExceptionOSHandler*`, `ExceptionUnwind*`, and `ExceptionCatcher*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_FUNCTION_UNLOADS`|<span data-ttu-id="c553e-131">컨트롤의 [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md) 에서 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-131">Controls the [FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md) callback in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_GC`|<span data-ttu-id="c553e-132">컨트롤의 [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md), [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md), [ SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md), [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md), [ RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md), [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md), [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md), 및 [FinalizeableObjectQueued ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) 콜백을 `ICorProfilerCallback*` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-132">Controls the [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md),   [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md),  [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md), [MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md),    [SurvivingReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md),  [SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md), [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md),   [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md),  [RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md), [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md), [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md),  [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md), and [FinalizeableObjectQueued](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md) callbacks in the `ICorProfilerCallback*` interfaces.</span></span>|  
|`COR_PRF_MONITOR_JIT_COMPILATION`|<span data-ttu-id="c553e-133">컨트롤의 `JITCompilation*`, [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md), 및 [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-133">Controls the `JITCompilation*`, [JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md), and [JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_MODULE_LOADS`|<span data-ttu-id="c553e-134">컨트롤의 `ModuleLoad*`, `ModuleUnload*`, 및 [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-134">Controls the `ModuleLoad*`,  `ModuleUnload*`, and [ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_OBJECT_ALLOCATED`|<span data-ttu-id="c553e-135">컨트롤의 [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) 에서 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-135">Controls the [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) callback in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING`|<span data-ttu-id="c553e-136">컨트롤의 `Remoting*` 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-136">Controls the `Remoting*` callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_ASYNC`|<span data-ttu-id="c553e-137">`Remoting*` 콜백이 비동기 이벤트를 모니터링하는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-137">Controls whether the `Remoting*` callbacks will monitor asynchronous events.</span></span>|  
|`COR_PRF_MONITOR_REMOTING_COOKIE`|<span data-ttu-id="c553e-138">`Remoting*` 콜백으로 쿠키가 전달되는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-138">Controls whether a cookie is passed to the `Remoting*` callbacks.</span></span>|  
|`COR_PRF_MONITOR_SUSPENDS`|<span data-ttu-id="c553e-139">컨트롤의 `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md), 및 [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md) 콜백을 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-139">Controls the `RuntimeSuspend*`, `RuntimeResume*`, [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md), and [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interface.</span></span>|  
|`COR_PRF_MONITOR_THREADS`|<span data-ttu-id="c553e-140">컨트롤의 [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md), [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md), [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md), 및 [ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md) 콜백을에 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) 및 [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-140">Controls the [ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md),  [ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md),  [ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md), and [ThreadNameChanged](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md) callbacks in the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfaces.</span></span>|  
  
<a name="Feature"></a>   
### <a name="feature-enabling-flags"></a><span data-ttu-id="c553e-141">기능 사용 플래그</span><span class="sxs-lookup"><span data-stu-id="c553e-141">Feature-enabling flags</span></span>  
  
|<span data-ttu-id="c553e-142">멤버</span><span class="sxs-lookup"><span data-stu-id="c553e-142">Member</span></span>|<span data-ttu-id="c553e-143">설명</span><span class="sxs-lookup"><span data-stu-id="c553e-143">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ENABLE_FRAME_INFO`|<span data-ttu-id="c553e-144">정확한를 검색할 수 있도록 `ClassID` 호출 하 여 제네릭 함수에 대 한는 [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) 메서드는 `COR_PRF_FRAME_INFO` 에서 반환 된 값의 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-144">Enables the retrieval of an exact `ClassID` for a generic function by calling the [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md) method with a `COR_PRF_FRAME_INFO` value returned by the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_ARGS`|<span data-ttu-id="c553e-145">사용 하 여 활성화 인수 추적할은 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) 콜백 또는 [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) 콜백 및 [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c553e-145">Enables argument tracing using the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md) callback or the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) callback and the [GetFunctionEnter3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_FUNCTION_RETVAL`|<span data-ttu-id="c553e-146">사용 하 여 반환 값은 추적 하도록 설정 된 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) 콜백 또는 [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) 콜백 및 [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c553e-146">Enables tracing of return values by using the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) callback or the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) callback and [GetFunctionLeave3Info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) method.</span></span>|  
|`COR_PRF_ENABLE_INPROC_DEBUGGING`|<span data-ttu-id="c553e-147">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-147">Deprecated.</span></span><br /><br /> <span data-ttu-id="c553e-148">프로세스 내 디버깅은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-148">In process debugging is not supported.</span></span> <span data-ttu-id="c553e-149">이 플래그는 아무런 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-149">This flag has no effect.</span></span>|  
|`COR_PRF_ENABLE_JIT_MAPS`|<span data-ttu-id="c553e-150">더 이상 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-150">Deprecated.</span></span><br /><br /> <span data-ttu-id="c553e-151">사용 하 여 IL-네이티브 맵을 가져올 프로파일러가 [GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-151">Allows the profiler to obtain IL-to-native maps by using [GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md).</span></span> <span data-ttu-id="c553e-152">.NET Framework 2.0부터는 런타임이 항상 IL-네이티브 맵을 추적하므로 이 플래그는 항상 설정되어 있는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-152">Starting with the .NET Framework 2.0, the runtime always tracks IL-to-native maps; therefore, this flag is always considered to be set.</span></span>|  
|`COR_PRF_ENABLE_OBJECT_ALLOCATED`|<span data-ttu-id="c553e-153">프로파일러가 개체 할당 알림을 받고자 할 수 있음을 런타임에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-153">Informs the runtime that the profiler may want object allocation notifications.</span></span> <span data-ttu-id="c553e-154">이 플래그는 초기화 중에 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-154">This flag must be set during initialization.</span></span> <span data-ttu-id="c553e-155">사용 하 여 나중에 프로파일러를 사용 하면는 `COR_PRF_MONITOR_OBJECT_ALLOCATED` 플래그를 받는 [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-155">It allows the profiler to subsequently use the `COR_PRF_MONITOR_OBJECT_ALLOCATED` flag to receive [ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md) callbacks.</span></span>|  
|`COR_PRF_ENABLE_REJIT`|<span data-ttu-id="c553e-156">에 대 한 호출을 사용 하도록 설정 된 [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) 및 [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c553e-156">Enables calls to the [RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) and [RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) methods.</span></span> <span data-ttu-id="c553e-157">프로파일러는 시작 시 이 플래그를 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-157">The profiler must set this flag on startup.</span></span>  <span data-ttu-id="c553e-158">프로파일러가 이 플래그를 지정하는 경우에는 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-158">If the profiler specifies this flag, it must also specify `COR_PRF_DISABLE_ALL_NGEN_IMAGES`.</span></span>|  
|`COR_PRF_ENABLE_STACK_SNAPSHOT`|<span data-ttu-id="c553e-159">에 대 한 호출을 사용 하도록 설정 된 [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c553e-159">Enables calls to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>|  
  
<a name="Config"></a>   
### <a name="configuration-flags"></a><span data-ttu-id="c553e-160">구성 플래그</span><span class="sxs-lookup"><span data-stu-id="c553e-160">Configuration flags</span></span>  
  
|<span data-ttu-id="c553e-161">멤버</span><span class="sxs-lookup"><span data-stu-id="c553e-161">Member</span></span>|<span data-ttu-id="c553e-162">설명</span><span class="sxs-lookup"><span data-stu-id="c553e-162">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_DISABLE_ALL_NGEN_IMAGES`|<span data-ttu-id="c553e-163">프로파일러 향상 이미지를 비롯한 모든 네이티브 이미지의 로드를 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-163">Prevents all native images (including profiler-enhanced images) from loading.</span></span>  <span data-ttu-id="c553e-164">이 플래그와 `COR_PRF_USE_PROFILE_IMAGES` 플래그가 모두 지정되어 있으면 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-164">If this flag and the `COR_PRF_USE_PROFILE_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
|`COR_PRF_DISABLE_INLINING`|<span data-ttu-id="c553e-165">모든 인라인 처리를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-165">Disables all inlining.</span></span>|  
|`COR_PRF_DISABLE_OPTIMIZATIONS`|<span data-ttu-id="c553e-166">모든 코드 최적화를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-166">Disables all code optimizations.</span></span>|  
|`COR_PRF_DISABLE_TRANSPARENCY_CHECKS_UNDER_FULL_TRUST`|<span data-ttu-id="c553e-167">일반적으로는 완전 신뢰 어셈블리에 대해 JIT(Just-In-Time) 컴파일 및 클래스 로드 중에 수행되는 보안 투명도 확인을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-167">Disables security transparency checks that are normally done during just-in-time (JIT) compilation and class loading for full-trust assemblies.</span></span> <span data-ttu-id="c553e-168">이 경우 일부 계측을 보다 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-168">This can make some instrumentation easier to perform.</span></span>|  
|`COR_PRF_USE_PROFILE_IMAGES`|<span data-ttu-id="c553e-169">네이티브 이미지 검색에서 프로파일러 향상 이미지를 찾도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-169">Causes the native image search to look for profiler-enhanced images.</span></span> <span data-ttu-id="c553e-170">지정한 어셈블리의 프로파일러 향상 이미지가 없으면 공용 언어 런타임이 해당 어셈블리에 대해 JIT로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-170">If no profiler-enhanced image is found for a given assembly, the common language runtime falls back to JIT for that assembly.</span></span> <span data-ttu-id="c553e-171">이 플래그와 `COR_PRF_DISABLE_ALL_NGEN_IMAGES` 플래그가 모두 지정되어 있으면 `COR_PRF_DISABLE_ALL_NGEN_IMAGES`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-171">If this flag and the `COR_PRF_DISABLE_ALL_NGEN_IMAGES` flag are both specified, `COR_PRF_DISABLE_ALL_NGEN_IMAGES` is used.</span></span>|  
  
<a name="Composite"></a>   
### <a name="composite-flags"></a><span data-ttu-id="c553e-172">복합 플래그</span><span class="sxs-lookup"><span data-stu-id="c553e-172">Composite flags</span></span>  
  
|<span data-ttu-id="c553e-173">멤버</span><span class="sxs-lookup"><span data-stu-id="c553e-173">Member</span></span>|<span data-ttu-id="c553e-174">설명</span><span class="sxs-lookup"><span data-stu-id="c553e-174">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_ALL`|<span data-ttu-id="c553e-175">모든 `COR_PRF_MONITOR` 플래그 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-175">Represents all `COR_PRF_MONITOR` flag values.</span></span>|  
|`COR_PRF_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="c553e-176">실행 중인 앱에 프로파일러를 연결한 후에 설정할 수 있는 모든 `COR_PRF_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-176">Represents all `COR_PRF_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span> <span data-ttu-id="c553e-177">구문 섹션에는 이 비트 마스크에 있는 개별 플래그가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-177">The syntax section indicates the individual flags that are present in this bitmask.</span></span>|  
|`COR_PRF_MONITOR_ALL`|<span data-ttu-id="c553e-178">모든 콜백 이벤트를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-178">Enables all callback events.</span></span>|  
|`COR_PRF_MONITOR_IMMUTABLE`|<span data-ttu-id="c553e-179">초기화 중에만 설정할 수 있는 모든 `COR_PRF_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-179">Represents all `COR_PRF_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="c553e-180">초기화 후에 이러한 플래그를 변경하려고 하면 오류를 나타내는 `HRESULT` 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-180">Trying to change any of these flags after initialization returns an `HRESULT` value that indicates failure.</span></span>|  
|`COR_PRF_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="c553e-181">프로필 향상 이미지가 필요한 모든 `COR_PRF_MONITOR` 플래그를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-181">Represents all `COR_PRF_MONITOR` flags that require profile-enhanced images.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c553e-182">설명</span><span class="sxs-lookup"><span data-stu-id="c553e-182">Remarks</span></span>  
 <span data-ttu-id="c553e-183">A `COR_PRF_MONITOR` 값 함께 사용 되는 [icorprofilerinfo:: Geteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) 및 [icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) 공용 언어 런타임에 수행 하는 이벤트 알림을 정의 하는 메서드 프로파일러 합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-183">A `COR_PRF_MONITOR` value is used with the [ICorProfilerInfo::GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) and [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) methods to define the event notifications that the common language runtime makes to the profiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c553e-184">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c553e-184">Requirements</span></span>  
 <span data-ttu-id="c553e-185">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c553e-185">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c553e-186">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c553e-186">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c553e-187">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c553e-187">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c553e-188">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c553e-188">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c553e-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c553e-189">See Also</span></span>  
 [<span data-ttu-id="c553e-190">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="c553e-190">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 [<span data-ttu-id="c553e-191">GetEventMask 메서드</span><span class="sxs-lookup"><span data-stu-id="c553e-191">GetEventMask Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
 [<span data-ttu-id="c553e-192">SetEventMask 메서드</span><span class="sxs-lookup"><span data-stu-id="c553e-192">SetEventMask Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)
