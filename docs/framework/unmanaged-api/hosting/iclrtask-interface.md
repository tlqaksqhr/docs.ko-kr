---
title: "ICLRTask 인터페이스"
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
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6fcce85e56abae561b05364a925fdb6b55825669
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask-interface"></a><span data-ttu-id="12944-102">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12944-102">ICLRTask Interface</span></span>
<span data-ttu-id="12944-103">호스트 공용 언어 런타임 (CLR)의 요청을 만들기 위해 하거나 관련된 작업에 대 한 CLR에 알림을 제공 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="12944-103">Provides methods that allow the host to make requests of the common language runtime (CLR), or to provide notification to the CLR about the associated task.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12944-104">메서드</span><span class="sxs-lookup"><span data-stu-id="12944-104">Methods</span></span>  
  
|<span data-ttu-id="12944-105">메서드</span><span class="sxs-lookup"><span data-stu-id="12944-105">Method</span></span>|<span data-ttu-id="12944-106">설명</span><span class="sxs-lookup"><span data-stu-id="12944-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12944-107">Abort 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-107">Abort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|<span data-ttu-id="12944-108">CLR 작업을 중단 하도록 요청 하는 현재 `ICLRTask` 인스턴스가 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="12944-108">Requests that the CLR abort the task that the current `ICLRTask` instance represents.</span></span>|  
|[<span data-ttu-id="12944-109">ExitTask 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-109">ExitTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|<span data-ttu-id="12944-110">작업이 현재 연결 CLR 알립니다 `ICLRTask` 인스턴스가 종료 되 고 작업 종료 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="12944-110">Notifies the CLR that the task associated with the current `ICLRTask` instance is ending, and attempts to shut the task down gracefully.</span></span>|  
|[<span data-ttu-id="12944-111">GetMemStats 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-111">GetMemStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|<span data-ttu-id="12944-112">현재 태스크에 의해 메모리 리소스의 사용에 대 한 통계 정보를 가져옵니다 `ICLRTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="12944-112">Gets statistical information on the use of memory resources by the task represented by the current `ICLRTask` instance.</span></span>|  
|[<span data-ttu-id="12944-113">LocksHeld 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-113">LocksHeld Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|<span data-ttu-id="12944-114">작업에서 현재 보유 중인 잠금 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="12944-114">Gets the number of locks currently held on the task.</span></span>|  
|[<span data-ttu-id="12944-115">NeedsPriorityScheduling 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-115">NeedsPriorityScheduling Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|<span data-ttu-id="12944-116">호스트 현재 작업을 재조정 하기 위해 높은 우선 순위를 할당 해야 하는지 여부를 나타내는 값을 가져옵니다 `ICLRTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="12944-116">Gets a value indicating whether the host should assign a high priority to rescheduling the task represented by the current `ICLRTask` instance.</span></span>|  
|[<span data-ttu-id="12944-117">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-117">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|<span data-ttu-id="12944-118">호스트가 완료 되는 작업을 CLR의 현재 다시 사용할 수 있도록 CLR 알립니다 `ICLRTask` 인스턴스를 다른 작업을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="12944-118">Informs the CLR that the host has completed a task, and enables the CLR to reuse the current `ICLRTask` instance to represent another task.</span></span>|  
|[<span data-ttu-id="12944-119">RudeAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-119">RudeAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|<span data-ttu-id="12944-120">CLR을 현재 작업을 중단 하면 `ICLRTask` 종료 자가 실행 될 보장 하지 않고 즉시 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="12944-120">Causes the CLR to abort the task represented by the current `ICLRTask` instance immediately, without a guarantee that finalizers will be executed.</span></span>|  
|[<span data-ttu-id="12944-121">SetTaskIdentifier 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-121">SetTaskIdentifier Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|<span data-ttu-id="12944-122">현재 작업에 대 한 고유 식별자를 설정 `ICLRTask` 디버깅에서 사용 하기 위해 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="12944-122">Sets a unique identifier for the task represented by the current `ICLRTask` instance, for use in debugging.</span></span>|  
|[<span data-ttu-id="12944-123">SwitchIn 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-123">SwitchIn Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|<span data-ttu-id="12944-124">현재 나타내는 작업이 CLR 알립니다 `ICLRTask` 인스턴스가 가능한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="12944-124">Notifies the CLR that the task represented by the current `ICLRTask` instance is in an operable state.</span></span>|  
|[<span data-ttu-id="12944-125">SwitchOut 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-125">SwitchOut Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|<span data-ttu-id="12944-126">현재 나타내는 작업이 CLR 알립니다 `ICLRTask` 인스턴스는 더 이상 작동 가능한 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12944-126">Notifies the CLR that the task represented by the current `ICLRTask` instance is no longer in an operable state.</span></span>|  
|[<span data-ttu-id="12944-127">YieldTask 메서드</span><span class="sxs-lookup"><span data-stu-id="12944-127">YieldTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|<span data-ttu-id="12944-128">다른 작업에 사용할 수 있는 CLR 확인 프로세서 시간 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="12944-128">Requests that the CLR make processor time available to other tasks.</span></span> <span data-ttu-id="12944-129">CLR은 작업 처리 시간 양보할 수 있는 상태에 놓이게 됩니다 하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12944-129">The CLR makes no guarantee that the task will be put in a state where it can yield processing time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12944-130">설명</span><span class="sxs-lookup"><span data-stu-id="12944-130">Remarks</span></span>  
 <span data-ttu-id="12944-131">`ICLRTask` CLR에 대 한 작업의 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="12944-131">An `ICLRTask` is the representation of a task for the CLR.</span></span> <span data-ttu-id="12944-132">코드 실행 하는 동안 언제 든 지 실행 또는 실행 대기 중인 작업을 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12944-132">At any point during code execution, a task can be described either as running or waiting to run.</span></span> <span data-ttu-id="12944-133">호스트에서는 `ICLRTask::SwitchIn` CLR에 알리기 위해 메서드를 작업 하는 현재 `ICLRTask` 인스턴스가 나타내는 작동 가능한 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12944-133">The host calls the `ICLRTask::SwitchIn` method to notify the CLR that the task that the current `ICLRTask` instance represents is now in an operable state.</span></span> <span data-ttu-id="12944-134">호출한 후 `ICLRTask::SwitchIn`, 호스트 런타임을 호출 하 여 지정 된 대로 스레드 선호도 필요로 하는 경우에 제외 하 고 운영 체제 스레드에서 작업을 예약할 수는 [ihosttaskmanager:: Beginthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) 및 [Ihosttaskmanager:: Endthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="12944-134">After a call to `ICLRTask::SwitchIn`, the host can schedule the task on any operating system thread, except in cases where the runtime requires thread-affinity, as specified by calls to the [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) and [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) methods.</span></span> <span data-ttu-id="12944-135">얼마 후 운영 체제 하 스레드에서 작업을 제거 하 고 실행 중이지 않은 상태로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12944-135">Some time later, the operating system might decide to remove the task from the thread and place it in a non-running state.</span></span> <span data-ttu-id="12944-136">예를 들어이 태스크는 동기화 기본 형식에서 차단 또는 I/O 작업이 완료 될 때까지 대기 될 때마다 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12944-136">For example, this might happen whenever the task blocks on synchronization primitives, or waits for I/O operations to complete.</span></span> <span data-ttu-id="12944-137">호스트에서는 [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) 현재 나타내는 작업이 CLR에 알리는 `ICLRTask` 인스턴스는 더 이상 가능한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="12944-137">The host calls [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) to notify the CLR that the task represented by the current `ICLRTask` instance is no longer in an operable state.</span></span>  
  
 <span data-ttu-id="12944-138">작업은 일반적으로 코드 실행의 끝에 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="12944-138">A task typically terminates at the end of code execution.</span></span> <span data-ttu-id="12944-139">그 당시 호스트 호출 `ICLRTask::ExitTask` 연결 된 제거할 `ICLRTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="12944-139">At that time, the host calls `ICLRTask::ExitTask` to destroy the associated `ICLRTask`.</span></span> <span data-ttu-id="12944-140">하지만 작업을 호출 하 여 재활용할 수도 있습니다 `ICLRTask::Reset`를 허용 하는 `ICLRTask` 인스턴스를 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12944-140">However, tasks can also be recycled by using a call to `ICLRTask::Reset`, which allows the `ICLRTask` instance to be used again.</span></span> <span data-ttu-id="12944-141">이 방법은 반복 해 서 만들고 인스턴스 제거의 오버 헤드를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="12944-141">This approach prevents the overhead of repeatedly creating and destroying instances.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12944-142">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12944-142">Requirements</span></span>  
 <span data-ttu-id="12944-143">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12944-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12944-144">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="12944-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12944-145">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="12944-145">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12944-146">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12944-146">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12944-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12944-147">See Also</span></span>  
 [<span data-ttu-id="12944-148">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12944-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="12944-149">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12944-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="12944-150">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12944-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="12944-151">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12944-151">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="12944-152">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12944-152">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
