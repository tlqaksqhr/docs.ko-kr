---
title: "IHostSyncManager::CreateCrstWithSpinCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateCrstWithSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31830f97cff1c302ee573b8248eb1d83e696ac48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a><span data-ttu-id="18f3e-102">IHostSyncManager::CreateCrstWithSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="18f3e-102">IHostSyncManager::CreateCrstWithSpinCount Method</span></span>
<span data-ttu-id="18f3e-103">동기화에 대 한 스핀 카운트 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-103">Creates a critical section object with spin count for synchronization.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f3e-104">구문</span><span class="sxs-lookup"><span data-stu-id="18f3e-104">Syntax</span></span>  
  
```  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18f3e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18f3e-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="18f3e-106">[in] 임계 영역 개체의 스핀 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-106">[in] Specifies the spin count for the critical section object.</span></span>  
  
 `ppCrst`  
 <span data-ttu-id="18f3e-107">[out] 주소에 대 한 포인터는 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스에 지정 하거나 임계 영역을 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-107">[out] A pointer to the address of an [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance, or null if the critical section could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="18f3e-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="18f3e-108">Return Value</span></span>  
  
|<span data-ttu-id="18f3e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="18f3e-109">HRESULT</span></span>|<span data-ttu-id="18f3e-110">설명</span><span class="sxs-lookup"><span data-stu-id="18f3e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18f3e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="18f3e-111">S_OK</span></span>|<span data-ttu-id="18f3e-112">`CreateCrstWithSpinCount`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-112">`CreateCrstWithSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="18f3e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="18f3e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="18f3e-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="18f3e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="18f3e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="18f3e-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-116">The call timed out.</span></span>|  
|<span data-ttu-id="18f3e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="18f3e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="18f3e-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="18f3e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="18f3e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="18f3e-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="18f3e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="18f3e-121">E_FAIL</span></span>|<span data-ttu-id="18f3e-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="18f3e-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="18f3e-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="18f3e-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="18f3e-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="18f3e-126">요청 된 중요 한 섹션을 만들 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-126">Not enough memory was available to create the requested critical section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18f3e-127">설명</span><span class="sxs-lookup"><span data-stu-id="18f3e-127">Remarks</span></span>  
 <span data-ttu-id="18f3e-128">스핀 수는 다중 프로세서 시스템 에서만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-128">A spin count is used only on a multi-processor system.</span></span> <span data-ttu-id="18f3e-129">스핀 수 호출 스레드를 사용할 수 없는 임계 연관 된 도달한 세마포에 대해 대기 작업을 수행 하기 전에 회전 해야 하는 횟수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-129">The spin count specifies the number of times a calling thread must spin before it performs a wait operation on a semaphore that is associated with an unavailable critical section.</span></span> <span data-ttu-id="18f3e-130">임계 영역 회전 작업 중에 무료 되 면 호출 스레드가 대기 작업을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-130">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span> <span data-ttu-id="18f3e-131">`CreateCrstWithSpinCount`Win32 미러링 `InitializeCriticalSectionAndSpinCount` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-131">`CreateCrstWithSpinCount` mirrors the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18f3e-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18f3e-132">Requirements</span></span>  
 <span data-ttu-id="18f3e-133">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="18f3e-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f3e-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="18f3e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="18f3e-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="18f3e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18f3e-136">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f3e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f3e-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18f3e-137">See Also</span></span>  
 [<span data-ttu-id="18f3e-138">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18f3e-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="18f3e-139">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18f3e-139">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="18f3e-140">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18f3e-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
