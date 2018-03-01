---
title: "ICLRTask::Reset 메서드"
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
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8dc37f47fc01d73ff499ef974a2e11345a95286a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskreset-method"></a><span data-ttu-id="533ce-102">ICLRTask::Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="533ce-102">ICLRTask::Reset Method</span></span>
<span data-ttu-id="533ce-103">호스트가 완료 되는 작업을 CLR의 현재 다시 사용할 수 있도록 공용 언어 런타임 (CLR) 알립니다 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스를 다른 작업을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-103">Informs the common language runtime (CLR) that the host has completed a task, and enables the CLR to reuse the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance to represent another task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="533ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="533ce-104">Syntax</span></span>  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="533ce-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="533ce-105">Parameters</span></span>  
 `fFull`  
 <span data-ttu-id="533ce-106">[in] `true`런타임에서 현재와 관련 된 보안 및 로캘 정보 외에도 모든 스레드 관련 정적 값을 다시 설정 해야 하는 경우, `ICLRTask` 인스턴스이거나, `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-106">[in] `true`, if the runtime should reset all thread-related static values in addition to the security and locale information related to the current `ICLRTask` instance; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="533ce-107">값이 `true`, 런타임에 사용 하 여 저장 된 데이터를 다시 설정 <xref:System.Threading.Thread.AllocateDataSlot%2A> 또는 <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-107">If the value is `true`, the runtime resets data that was stored using <xref:System.Threading.Thread.AllocateDataSlot%2A> or <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="533ce-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="533ce-108">Return Value</span></span>  
  
|<span data-ttu-id="533ce-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="533ce-109">HRESULT</span></span>|<span data-ttu-id="533ce-110">설명</span><span class="sxs-lookup"><span data-stu-id="533ce-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="533ce-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="533ce-111">S_OK</span></span>|<span data-ttu-id="533ce-112">`Reset`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-112">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="533ce-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="533ce-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="533ce-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="533ce-115">성공적으로</span><span class="sxs-lookup"><span data-stu-id="533ce-115">successfully</span></span>|  
|<span data-ttu-id="533ce-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="533ce-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="533ce-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-117">The call timed out.</span></span>|  
|<span data-ttu-id="533ce-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="533ce-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="533ce-119">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="533ce-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="533ce-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="533ce-121">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="533ce-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="533ce-122">E_FAIL</span></span>|<span data-ttu-id="533ce-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="533ce-124">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="533ce-125">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="533ce-126">설명</span><span class="sxs-lookup"><span data-stu-id="533ce-126">Remarks</span></span>  
 <span data-ttu-id="533ce-127">이전에 만든 CLR을 재활용할 수 `ICLRTask` 반복 해 서 새로운 작업이 해야 할 때마다 새 인스턴스를 만들기의 오버 헤드를 방지 하기 위해 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="533ce-127">The CLR can recycle previously created `ICLRTask` instances to avoid the overhead of repeatedly creating new instances every time it needs a fresh task.</span></span> <span data-ttu-id="533ce-128">호스트를 호출 하 여이 기능을 사용 하면 `ICLRTask::Reset` 대신 [iclrtask:: Exittask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) 작업 완료 된 시점입니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-128">The host enables this feature by calling `ICLRTask::Reset` instead of [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) when it has completed a task.</span></span> <span data-ttu-id="533ce-129">다음 목록은 요약의 일반적인 수명 주기는 `ICLRTask` 인스턴스:</span><span class="sxs-lookup"><span data-stu-id="533ce-129">The following list summarizes the normal life cycle of an `ICLRTask` instance:</span></span>  
  
1.  <span data-ttu-id="533ce-130">런타임에서 새 만듭니다 `ICLRTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="533ce-130">The runtime creates a new `ICLRTask` instance.</span></span>  
  
2.  <span data-ttu-id="533ce-131">런타임 호출 [ihosttaskmanager:: Getcurrenttask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) 현재 호스트 작업에 대 한 참조를 얻으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-131">The runtime calls [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) to get a reference to the current host task.</span></span>  
  
3.  <span data-ttu-id="533ce-132">런타임 호출 [ihosttask:: Setclrtask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) 작업과 새 인스턴스를 연결 하는 호스트 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-132">The runtime calls [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) to associate the new instance with the host task.</span></span>  
  
4.  <span data-ttu-id="533ce-133">작업을 실행 하 고 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-133">The task executes and completes.</span></span>  
  
5.  <span data-ttu-id="533ce-134">호스트를 호출 하 여 작업을 소멸 시킵니다. `ICLRTask::ExitTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-134">The host destroys the task by calling `ICLRTask::ExitTask`.</span></span>  
  
 <span data-ttu-id="533ce-135">`Reset`두 가지 방법으로이 시나리오를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-135">`Reset` alters this scenario in two ways.</span></span> <span data-ttu-id="533ce-136">호스트에서는 위의 5 단계에서 `Reset` 클린 상태로 작업을 다시 설정 하려면 다음의 `ICLRTask` 에서 연결 된 인스턴스 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="533ce-136">In step 5 above, the host calls `Reset` to reset the task to a clean state, and then decouples the `ICLRTask` instance from its associated [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span> <span data-ttu-id="533ce-137">원하는 경우 호스트 캐시할 수도 있습니다는 `IHostTask` 인스턴스 다시 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-137">If desired, the host can also cache the `IHostTask` instance for reuse.</span></span> <span data-ttu-id="533ce-138">위의 1 단계에서 공용 언어 런타임은 가져옵니다 재활용 된 `ICLRTask` 새 인스턴스를 만드는 대신 캐시에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-138">In step 1 above, the runtime pulls a recycled `ICLRTask` from the cache instead of creating a new instance.</span></span>  
  
 <span data-ttu-id="533ce-139">이 방법은 호스트에 다시 사용할 수 있는 작업자 태스크의 풀도 있는 경우 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-139">This approach works well when the host also has a pool of reusable worker tasks.</span></span> <span data-ttu-id="533ce-140">호스트 중 하나를 제거 하면 해당 `IHostTask` 인스턴스를 해당 제거 됩니다 `ICLRTask` 호출 하 여 `ExitTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-140">When the host destroys one of its `IHostTask` instances, it destroys the corresponding `ICLRTask` by calling `ExitTask`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="533ce-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="533ce-141">Requirements</span></span>  
 <span data-ttu-id="533ce-142">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="533ce-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="533ce-143">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="533ce-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="533ce-144">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="533ce-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="533ce-145">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="533ce-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="533ce-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="533ce-146">See Also</span></span>  
 [<span data-ttu-id="533ce-147">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="533ce-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="533ce-148">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="533ce-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="533ce-149">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="533ce-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="533ce-150">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="533ce-150">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
