---
title: "IHostTask::SetPriority 메서드"
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
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2f9a57442b1671ef0286536215d10768636e3aa8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttasksetpriority-method"></a><span data-ttu-id="b3335-102">IHostTask::SetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="b3335-102">IHostTask::SetPriority Method</span></span>
<span data-ttu-id="b3335-103">현재 작업에 대 한 호스트 조정 하도록 요청 합니다 스레드 우선 순위 수준 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b3335-103">Requests that the host adjust the thread priority level for the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3335-104">구문</span><span class="sxs-lookup"><span data-stu-id="b3335-104">Syntax</span></span>  
  
```  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3335-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3335-105">Parameters</span></span>  
 `newPriority`  
 <span data-ttu-id="b3335-106">[in] 현재 작업에 대 한 요청 된 스레드 우선 순위 값을 나타내는 integer `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b3335-106">[in] An integer that represents the requested thread priority value for the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3335-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="b3335-107">Return Value</span></span>  
  
|<span data-ttu-id="b3335-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3335-108">HRESULT</span></span>|<span data-ttu-id="b3335-109">설명</span><span class="sxs-lookup"><span data-stu-id="b3335-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3335-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3335-110">S_OK</span></span>|<span data-ttu-id="b3335-111">`SetPriority`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-111">`SetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="b3335-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3335-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3335-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b3335-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b3335-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b3335-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-115">The call timed out.</span></span>|  
|<span data-ttu-id="b3335-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b3335-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b3335-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b3335-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b3335-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b3335-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b3335-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3335-120">E_FAIL</span></span>|<span data-ttu-id="b3335-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b3335-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b3335-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3335-124">설명</span><span class="sxs-lookup"><span data-stu-id="b3335-124">Remarks</span></span>  
 <span data-ttu-id="b3335-125">스레드는 스레드의 우선 순위 수준을에 부분적으로 기초 하는 라운드 로빈 시스템을 사용 하 여 시간을 처리 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-125">Threads are granted processing time using a round-robin system that is partly based on a thread's priority level.</span></span> <span data-ttu-id="b3335-126">`SetPriority`CLR을 현재 작업에 대 한 스레드 우선 순위 수준을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-126">`SetPriority` allows the CLR to set that thread priority level for the current task.</span></span> <span data-ttu-id="b3335-127">다음 `newPriority` 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-127">The following `newPriority` values are supported.</span></span>  
  
-   <span data-ttu-id="b3335-128">THREAD_PRIORITY_ABOVE_NORMAL</span><span class="sxs-lookup"><span data-stu-id="b3335-128">THREAD_PRIORITY_ABOVE_NORMAL</span></span>  
  
-   <span data-ttu-id="b3335-129">THREAD_PRIORITY_BELOW_NORMAL</span><span class="sxs-lookup"><span data-stu-id="b3335-129">THREAD_PRIORITY_BELOW_NORMAL</span></span>  
  
-   <span data-ttu-id="b3335-130">THREAD_PRIORITY_HIGHEST</span><span class="sxs-lookup"><span data-stu-id="b3335-130">THREAD_PRIORITY_HIGHEST</span></span>  
  
-   <span data-ttu-id="b3335-131">THREAD_PRIORITY_IDLE</span><span class="sxs-lookup"><span data-stu-id="b3335-131">THREAD_PRIORITY_IDLE</span></span>  
  
-   <span data-ttu-id="b3335-132">THREAD_PRIORITY_LOWEST</span><span class="sxs-lookup"><span data-stu-id="b3335-132">THREAD_PRIORITY_LOWEST</span></span>  
  
-   <span data-ttu-id="b3335-133">THREAD_PRIORITY_NORMAL</span><span class="sxs-lookup"><span data-stu-id="b3335-133">THREAD_PRIORITY_NORMAL</span></span>  
  
-   <span data-ttu-id="b3335-134">THREAD_PRIORITY_TIME_CRITICAL</span><span class="sxs-lookup"><span data-stu-id="b3335-134">THREAD_PRIORITY_TIME_CRITICAL</span></span>  
  
 <span data-ttu-id="b3335-135">CLR에서는 `SetPriority` 때의 값은 <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> 사용자 코드에 의해 수정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-135">The CLR calls `SetPriority` when the value of the <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> is modified by user code.</span></span> <span data-ttu-id="b3335-136">호스트는 스레드를 할당, 우선 순위에 대 한 자체 알고리즘을 정의할 수 있으며이 요청을 무시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-136">A host can define its own algorithms for thread priority assignment, and is free to ignore this request.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b3335-137">`SetPriority`스레드 우선 순위 수준을 변경 되었는지 여부를 보고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-137">`SetPriority` does not report whether the thread priority level was changed.</span></span> <span data-ttu-id="b3335-138">호출 [ihosttask:: Getpriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) 작업의 스레드가 우선 순위 수준 값을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-138">Call [IHostTask::GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) to determine the value of the task's thread priority level.</span></span>  
  
 <span data-ttu-id="b3335-139">Win32 스레드 우선 순위 수준 값이 정의 된 `SetThreadPriority` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-139">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span> <span data-ttu-id="b3335-140">스레드 우선 순위에 대 한 자세한 내용은 Windows 플랫폼 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-140">For more information about thread priority, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3335-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3335-141">Requirements</span></span>  
 <span data-ttu-id="b3335-142">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b3335-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3335-143">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3335-143">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3335-144">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b3335-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3335-145">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3335-145">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3335-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3335-146">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="b3335-147">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3335-147">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="b3335-148">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3335-148">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="b3335-149">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3335-149">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="b3335-150">GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="b3335-150">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)  
 [<span data-ttu-id="b3335-151">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3335-151">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
