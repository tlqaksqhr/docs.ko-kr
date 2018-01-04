---
title: "ICorProfilerCallback::RuntimeSuspendStarted 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dc1b229a21b59a842a5bcc47620302711cecdc42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="1b741-102">ICorProfilerCallback::RuntimeSuspendStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="1b741-102">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>
<span data-ttu-id="1b741-103">런타임에서 모든 런타임 스레드를 일시 중단 하려고 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1b741-103">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b741-104">구문</span><span class="sxs-lookup"><span data-stu-id="1b741-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b741-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1b741-105">Parameters</span></span>  
 `suspendReason`  
 <span data-ttu-id="1b741-106">[in] 값은 [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) 일시 중단 이유를 나타내는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="1b741-106">[in] A value of the [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b741-107">설명</span><span class="sxs-lookup"><span data-stu-id="1b741-107">Remarks</span></span>  
 <span data-ttu-id="1b741-108">비관리 코드에 있는 모든 런타임 스레드 다시 런타임에 입력 하려고 시도할 때까지 실행을 계속 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b741-108">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="1b741-109">해당 시점 것도 일시 중단 됩니다 런타임 재개할 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b741-109">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="1b741-110">런타임에 입력 하는 새 스레드에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b741-110">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="1b741-111">런타임에서 모든 스레드는 인터럽트 가능한 코드에 이미 또는 인터럽트 가능한 코드에 도달할 때 일시 중단 하 라는 메시지가 표시 되는 경우 즉시 하거나 일시 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b741-111">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b741-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b741-112">Requirements</span></span>  
 <span data-ttu-id="1b741-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b741-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b741-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1b741-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1b741-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b741-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b741-116">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b741-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b741-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b741-117">See Also</span></span>  
 [<span data-ttu-id="1b741-118">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b741-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="1b741-119">RuntimeSuspendAborted 메서드</span><span class="sxs-lookup"><span data-stu-id="1b741-119">RuntimeSuspendAborted Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [<span data-ttu-id="1b741-120">RuntimeSuspendFinished 메서드</span><span class="sxs-lookup"><span data-stu-id="1b741-120">RuntimeSuspendFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
