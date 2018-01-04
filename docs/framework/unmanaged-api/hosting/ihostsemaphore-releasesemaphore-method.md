---
title: "IHostSemaphore::ReleaseSemaphore 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSemaphore.ReleaseSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSemaphore::ReleaseSemaphore
helpviewer_keywords:
- ReleaseSemaphore method [.NET Framework hosting]
- IHostSemaphore::ReleaseSemaphore method [.NET Framework hosting]
ms.assetid: a343d197-979a-4ac6-ab8c-cb8a05f3120e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6828726fe81cc99adc719659a6eb1b15afda84c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsemaphorereleasesemaphore-method"></a><span data-ttu-id="0574d-102">IHostSemaphore::ReleaseSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="0574d-102">IHostSemaphore::ReleaseSemaphore Method</span></span>
<span data-ttu-id="0574d-103">현재 수를 늘립니다 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 인스턴스를 지정 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-103">Increases the count of the current [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) instance by the specified amount.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0574d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0574d-104">Syntax</span></span>  
  
```  
HRESULT ReleaseSemaphore (  
    [in]  LONG  lReleaseCount,  
    [out] LONG  *lpPreviousCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0574d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0574d-105">Parameters</span></span>  
 `lReleaseCount`  
 <span data-ttu-id="0574d-106">[in] 현재 개수를 늘릴 양 `IHostSemaphore` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="0574d-106">[in] The amount by which to increase the count of the current `IHostSemaphore` instance.</span></span> <span data-ttu-id="0574d-107">이 값은 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-107">This amount must be greater than zero.</span></span>  
  
 `lpPreviousCount`  
 <span data-ttu-id="0574d-108">[out] 이전 개수 또는 호출자에 게 이전 카운트를 필요 하지 않은 경우 null에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-108">[out] A pointer to the previous count, or null if the caller does not require the previous count.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0574d-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="0574d-109">Return Value</span></span>  
  
|<span data-ttu-id="0574d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0574d-110">HRESULT</span></span>|<span data-ttu-id="0574d-111">설명</span><span class="sxs-lookup"><span data-stu-id="0574d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0574d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0574d-112">S_OK</span></span>|<span data-ttu-id="0574d-113">`ReleaseSemaphore`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-113">`ReleaseSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="0574d-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0574d-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0574d-115">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0574d-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0574d-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0574d-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-117">The call timed out.</span></span>|  
|<span data-ttu-id="0574d-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0574d-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0574d-119">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0574d-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0574d-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0574d-121">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0574d-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0574d-122">E_FAIL</span></span>|<span data-ttu-id="0574d-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0574d-124">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0574d-125">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0574d-126">설명</span><span class="sxs-lookup"><span data-stu-id="0574d-126">Remarks</span></span>  
 <span data-ttu-id="0574d-127">CLR은 일반적으로 호출 `ReleaseSemaphore` 값에 대 한 1 전달 하는 리소스를 사용 하 여 완료 했음을 호스트에 알리기 위해는 `lReleaseCount` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-127">The CLR typically calls `ReleaseSemaphore` to notify the host that it has finished using a resource, passing a value of 1 for the `lReleaseCount` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0574d-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0574d-128">Requirements</span></span>  
 <span data-ttu-id="0574d-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0574d-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0574d-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0574d-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0574d-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0574d-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0574d-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0574d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0574d-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0574d-133">See Also</span></span>  
 [<span data-ttu-id="0574d-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0574d-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="0574d-135">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0574d-135">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="0574d-136">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0574d-136">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="0574d-137">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0574d-137">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="0574d-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0574d-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
