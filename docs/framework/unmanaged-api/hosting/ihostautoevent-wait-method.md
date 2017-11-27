---
title: "IHostAutoEvent::Wait 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAutoEvent.Wait
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAutoEvent::Wait
helpviewer_keywords:
- Wait method, IHostAutoEvent interface [.NET Framework hosting]
- IHostAutoEvent::Wait method [.NET Framework hosting]
ms.assetid: 535d51c5-9112-401b-8c36-85f35d7ee609
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a4900d1edc69ad00c98455d388714c2fd1a5156
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostautoeventwait-method"></a><span data-ttu-id="3fecb-102">IHostAutoEvent::Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="3fecb-102">IHostAutoEvent::Wait Method</span></span>
<span data-ttu-id="3fecb-103">현재 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 소유 될 때까지 대기 하는 인스턴스 또는 지정된 된 시간 간격이 경과 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-103">Causes the current [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance to wait until it is owned or a specified amount of time elapses.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fecb-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fecb-104">Syntax</span></span>  
  
```  
HRESULT Wait (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fecb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3fecb-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="3fecb-106">[in] 기간 (밀리초) 현재 `IHostAutoEvent` 경우 스레드가 인스턴스가 반환 되기 전에 대기 해야 또는 파이버 소유권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-106">[in] The number of milliseconds the current `IHostAutoEvent` instance should wait before returning, if no thread or fiber takes ownership.</span></span>  
  
 `option`  
 <span data-ttu-id="3fecb-107">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 경우이 호스트가 수행할 동작을 지정 하는 값을 작업이 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, specifying the action the host should take if this operation blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fecb-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="3fecb-108">Return Value</span></span>  
  
|<span data-ttu-id="3fecb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fecb-109">HRESULT</span></span>|<span data-ttu-id="3fecb-110">설명</span><span class="sxs-lookup"><span data-stu-id="3fecb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fecb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fecb-111">S_OK</span></span>|<span data-ttu-id="3fecb-112">`Wait`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-112">`Wait` returned successfully.</span></span>|  
|<span data-ttu-id="3fecb-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3fecb-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3fecb-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3fecb-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3fecb-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3fecb-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-116">The call timed out.</span></span>|  
|<span data-ttu-id="3fecb-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3fecb-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3fecb-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3fecb-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3fecb-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3fecb-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3fecb-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3fecb-121">E_FAIL</span></span>|<span data-ttu-id="3fecb-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3fecb-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3fecb-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3fecb-125">HOST_E_DEADLOCK</span><span class="sxs-lookup"><span data-stu-id="3fecb-125">HOST_E_DEADLOCK</span></span>|<span data-ttu-id="3fecb-126">호스트 대기 간격 중 교착 상태를 감지 하 고 현재 나타내는 이벤트 `IHostAutoEvent` 인스턴스 교착 상태가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-126">The host detected a deadlock during the wait interval, and chose the event represented by the current `IHostAutoEvent` instance as the deadlock victim.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3fecb-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fecb-127">Requirements</span></span>  
 <span data-ttu-id="3fecb-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3fecb-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fecb-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fecb-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fecb-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3fecb-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fecb-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fecb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fecb-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fecb-132">See Also</span></span>  
 [<span data-ttu-id="3fecb-133">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fecb-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="3fecb-134">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fecb-134">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="3fecb-135">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fecb-135">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="3fecb-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fecb-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
