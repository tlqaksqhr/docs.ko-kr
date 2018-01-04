---
title: "IHostSyncManager::CreateMonitorEvent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateMonitorEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae12db71f4eae0f7d887fda26e05401f4f23ee5c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="78433-102">IHostSyncManager::CreateMonitorEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="78433-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="78433-103">모니터링 되는 자동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="78433-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78433-104">구문</span><span class="sxs-lookup"><span data-stu-id="78433-104">Syntax</span></span>  
  
```  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="78433-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="78433-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="78433-106">[in] 이벤트 개체와 연결 하는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="78433-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="78433-107">[out] 주소에 대 한 포인터는 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 인스턴스에 지정 하거나 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="78433-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="78433-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="78433-108">Return Value</span></span>  
  
|<span data-ttu-id="78433-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="78433-109">HRESULT</span></span>|<span data-ttu-id="78433-110">설명</span><span class="sxs-lookup"><span data-stu-id="78433-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="78433-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="78433-111">S_OK</span></span>|<span data-ttu-id="78433-112">`CreateMonitorEvent`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="78433-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="78433-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="78433-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="78433-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78433-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="78433-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="78433-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="78433-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="78433-116">The call timed out.</span></span>|  
|<span data-ttu-id="78433-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="78433-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="78433-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78433-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="78433-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="78433-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="78433-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="78433-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="78433-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="78433-121">E_FAIL</span></span>|<span data-ttu-id="78433-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="78433-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="78433-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78433-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="78433-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="78433-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="78433-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="78433-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="78433-126">요청 된 이벤트 개체를 만들 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78433-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="78433-127">설명</span><span class="sxs-lookup"><span data-stu-id="78433-127">Remarks</span></span>  
 <span data-ttu-id="78433-128">`CreateMonitorEvent`반환는 `IHostAutoEvent` CLR은 관리 되는 구현에서 사용 하는 <xref:System.Threading.Monitor?displayProperty=nameWithType> 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="78433-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="78433-129">이 메서드는 Win32을 미러링합니다. `CreateEvent` 의 값으로 함수 `false` 에 대해 지정 된 된 `bManualReset` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="78433-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="78433-130">호스트를 호출 하 여 작업 모니터에서 대기를 확인 하려면 쿠키를 사용할 수는 [iclrsyncmanager:: Getmonitorowner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="78433-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78433-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78433-131">Requirements</span></span>  
 <span data-ttu-id="78433-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="78433-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78433-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="78433-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="78433-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="78433-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78433-135">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78433-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78433-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="78433-136">See Also</span></span>  
 [<span data-ttu-id="78433-137">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78433-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="78433-138">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78433-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="78433-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78433-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="78433-140">모니터</span><span class="sxs-lookup"><span data-stu-id="78433-140">Monitors</span></span>](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)
