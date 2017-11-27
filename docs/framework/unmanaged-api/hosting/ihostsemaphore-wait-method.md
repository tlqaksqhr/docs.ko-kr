---
title: "IHostSemaphore::Wait 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSemaphore.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSemaphore::Wait
helpviewer_keywords:
- IHostSemaphore::Wait method [.NET Framework hosting]
- Wait method, IHostSemaphore interface [.NET Framework hosting]
ms.assetid: 0da962a3-ce55-44dd-ab7a-14ad7105af4a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d30a946cadc312e683d256ce6f08528cffa95481
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsemaphorewait-method"></a><span data-ttu-id="9babd-102">IHostSemaphore::Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="9babd-102">IHostSemaphore::Wait Method</span></span>
<span data-ttu-id="9babd-103">현재 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 소유 될 때까지 대기 하는 인스턴스 또는 지정된 된 양의 시간 간격이 경과 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-103">Causes the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance to wait until it is owned or the specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9babd-104">구문</span><span class="sxs-lookup"><span data-stu-id="9babd-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9babd-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9babd-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="9babd-106">[in] 경우, 반환 하기 전에 대기할 밀리초 수 현재 `IHostSemaphore` 인스턴스를 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-106">[in] The number of milliseconds to wait before returning, if the current `IHostSemaphore` instance is not owned.</span></span>  
  
 `option`  
 <span data-ttu-id="9babd-107">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 이 호스트가 수행할 동작을 지정 하는 값을 작업이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying what action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9babd-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="9babd-108">Return Value</span></span>  
  
|<span data-ttu-id="9babd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9babd-109">HRESULT</span></span>|<span data-ttu-id="9babd-110">설명</span><span class="sxs-lookup"><span data-stu-id="9babd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9babd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9babd-111">S_OK</span></span>|<span data-ttu-id="9babd-112">`Wait`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="9babd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9babd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9babd-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9babd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9babd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9babd-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-116">The call timed out.</span></span>|  
|<span data-ttu-id="9babd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9babd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9babd-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9babd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9babd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9babd-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9babd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9babd-121">E_FAIL</span></span>|<span data-ttu-id="9babd-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9babd-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9babd-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9babd-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="9babd-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="9babd-126">호스트 대기 간격 중 교착 상태를 감지 하 여 현재 `IHostSemaphore` 인스턴스 교착 상태가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-126">The host detected a deadlock during the wait interval, and chose the current `IHostSemaphore` instance as a deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9babd-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9babd-127">Requirements</span></span>  
 <span data-ttu-id="9babd-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9babd-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9babd-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9babd-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9babd-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9babd-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9babd-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9babd-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9babd-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9babd-132">See Also</span></span>  
 [<span data-ttu-id="9babd-133">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9babd-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="9babd-134">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9babd-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="9babd-135">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9babd-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="9babd-136">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9babd-136">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="9babd-137">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9babd-137">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
