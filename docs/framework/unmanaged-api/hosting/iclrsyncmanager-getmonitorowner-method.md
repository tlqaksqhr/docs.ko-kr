---
title: "ICLRSyncManager::GetMonitorOwner 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRSyncManager.GetMonitorOwner
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90fbba9a5aead27d79c5355d69bc12481e826b65
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="0ac12-102">ICLRSyncManager::GetMonitorOwner 메서드</span><span class="sxs-lookup"><span data-stu-id="0ac12-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="0ac12-103">가져옵니다는 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 지정한 쿠키로 식별 되는 모니터를 담당 하는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="0ac12-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ac12-104">구문</span><span class="sxs-lookup"><span data-stu-id="0ac12-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ac12-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0ac12-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="0ac12-106">[in] 모니터와 관련 된 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="0ac12-107">[out] 에 대 한 포인터는 `IHostTask` 현재 소유 하는 모니터 또는 null는 작업이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="0ac12-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ac12-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="0ac12-108">Return Value</span></span>  
  
|<span data-ttu-id="0ac12-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ac12-109">HRESULT</span></span>|<span data-ttu-id="0ac12-110">설명</span><span class="sxs-lookup"><span data-stu-id="0ac12-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ac12-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ac12-111">S_OK</span></span>|<span data-ttu-id="0ac12-112">`GetMonitorOwner`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="0ac12-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ac12-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ac12-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0ac12-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0ac12-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0ac12-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-116">The call timed out.</span></span>|  
|<span data-ttu-id="0ac12-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0ac12-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0ac12-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0ac12-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0ac12-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0ac12-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0ac12-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0ac12-121">E_FAIL</span></span>|<span data-ttu-id="0ac12-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0ac12-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0ac12-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ac12-125">설명</span><span class="sxs-lookup"><span data-stu-id="0ac12-125">Remarks</span></span>  
 <span data-ttu-id="0ac12-126">호스트는 일반적으로 호출 `GetMonitorOwner` 교착 상태 감지 메커니즘의 일부분으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="0ac12-127">쿠키는 모니터와 연결에 대 한 호출을 사용 하 여 만들어질 때 [ihostsyncmanager:: Createmonitorevent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ac12-128">모니터 기반의 이벤트를 해제에 대 한 호출을 차단할 수-교착 상태가 되지 않고-이 메서드에 대 한 호출에서 실행 되는 모니터와 관련 된 쿠키에 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="0ac12-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="0ac12-129">이 모니터를 가져오려는 경우에 다른 작업 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="0ac12-130">`GetMonitorOwner`항상 즉시 반환 하 고에 대 한 호출 후 언제 든 지 호출할 수 `CreateMonitorEvent`합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="0ac12-131">호스트는 태스크가 대기 하는 이벤트를 처리 될 때까지 기다릴 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ac12-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0ac12-132">Requirements</span></span>  
 <span data-ttu-id="0ac12-133">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac12-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ac12-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0ac12-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0ac12-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0ac12-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ac12-136">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ac12-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ac12-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ac12-137">See Also</span></span>  
 [<span data-ttu-id="0ac12-138">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ac12-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="0ac12-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0ac12-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
