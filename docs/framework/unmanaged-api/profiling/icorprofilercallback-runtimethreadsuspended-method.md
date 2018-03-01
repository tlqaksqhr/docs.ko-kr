---
title: "ICorProfilerCallback::RuntimeThreadSuspended 메서드"
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
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8f22e9a6ed8c62256bb3e614dbc1278dea24d4e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a><span data-ttu-id="ebe02-102">ICorProfilerCallback::RuntimeThreadSuspended 메서드</span><span class="sxs-lookup"><span data-stu-id="ebe02-102">ICorProfilerCallback::RuntimeThreadSuspended Method</span></span>
<span data-ttu-id="ebe02-103">지정된 된 스레드가 일시 중단 됨 또는 일시 중단 하려고 합니다. 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ebe02-103">Notifies the profiler that the specified thread has been suspended or is about to be suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebe02-104">구문</span><span class="sxs-lookup"><span data-stu-id="ebe02-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ebe02-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ebe02-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="ebe02-106">[in] 일시 중단 된 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ebe02-106">[in] The ID of the thread that has been suspended.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebe02-107">설명</span><span class="sxs-lookup"><span data-stu-id="ebe02-107">Remarks</span></span>  
 <span data-ttu-id="ebe02-108">`RuntimeThreadSuspended` 알림이 사이의 든 지 발생할 수 있습니다는 [icorprofilercallback:: Runtimesuspendstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) 및 연결 된 [icorprofilercallback:: Runtimeresumestarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe02-108">The `RuntimeThreadSuspended` notification can occur any time between the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) and the associated [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span> <span data-ttu-id="ebe02-109">간에 발생 하는 알림 [icorprofilercallback:: Runtimesuspendfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) 및 `RuntimeResumeStarted` 실행 중이 던에서 스레드가 비관리 코드 및 런타임에 진입할 때 일시 중단 된 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebe02-109">Notifications that occur between [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and `RuntimeResumeStarted` are for threads that had been running in unmanaged code and were suspended upon entry to the runtime.</span></span>  
  
 <span data-ttu-id="ebe02-110">일반적으로이 콜백에서 스레드가 일시 중단 된 직후에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe02-110">Generally, this callback occurs just after a thread is suspended.</span></span> <span data-ttu-id="ebe02-111">그러나 현재 실행 중인 스레드 (이 콜백을 호출한 스레드)를 일시 중단 된 경우이 콜백을 스레드가 일시 중단 하기 바로 전에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe02-111">However, if the currently executing thread (the thread that called this callback) is the one that is being suspended, this callback will occur just before the thread is suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebe02-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ebe02-112">Requirements</span></span>  
 <span data-ttu-id="ebe02-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ebe02-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebe02-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ebe02-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ebe02-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebe02-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebe02-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebe02-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebe02-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebe02-117">See Also</span></span>  
 [<span data-ttu-id="ebe02-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ebe02-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ebe02-119">RuntimeThreadResumed 메서드</span><span class="sxs-lookup"><span data-stu-id="ebe02-119">RuntimeThreadResumed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
