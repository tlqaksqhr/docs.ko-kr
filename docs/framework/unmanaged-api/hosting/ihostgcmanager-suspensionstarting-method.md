---
title: IHostGCManager::SuspensionStarting 메서드
ms.date: 03/30/2017
api_name:
- IHostGCManager.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager::SuspensionStarting
helpviewer_keywords:
- SuspensionStarting method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionStarting method [.NET Framework hosting]
ms.assetid: c381f524-94cf-4fa2-9298-50f847a03431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a84da2a337554873e94b47eb51916088edbb5a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439035"
---
# <a name="ihostgcmanagersuspensionstarting-method"></a><span data-ttu-id="66794-102">IHostGCManager::SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="66794-102">IHostGCManager::SuspensionStarting Method</span></span>
<span data-ttu-id="66794-103">공용 언어 런타임 (CLR) 가비지 수집을 수행 하기 위해 작업 실행을 중단 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="66794-103">Notifies the host that the common language runtime (CLR) is suspending execution of tasks, to perform a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66794-104">구문</span><span class="sxs-lookup"><span data-stu-id="66794-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="66794-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="66794-105">Return Value</span></span>  
  
|<span data-ttu-id="66794-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66794-106">HRESULT</span></span>|<span data-ttu-id="66794-107">설명</span><span class="sxs-lookup"><span data-stu-id="66794-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66794-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="66794-108">S_OK</span></span>|<span data-ttu-id="66794-109">`SuspensionStarting` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="66794-109">`SuspensionStarting` returned successfully.</span></span>|  
|<span data-ttu-id="66794-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="66794-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="66794-111">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66794-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="66794-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="66794-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="66794-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66794-113">The call timed out.</span></span>|  
|<span data-ttu-id="66794-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="66794-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="66794-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="66794-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="66794-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="66794-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="66794-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="66794-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="66794-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="66794-118">E_FAIL</span></span>|<span data-ttu-id="66794-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="66794-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="66794-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="66794-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="66794-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="66794-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66794-122">설명</span><span class="sxs-lookup"><span data-stu-id="66794-122">Remarks</span></span>  
 <span data-ttu-id="66794-123">CLR에서는 `SuspensionStarting` 가비지 수집이 발생 하는 호스트입니다.</span><span class="sxs-lookup"><span data-stu-id="66794-123">The CLR calls `SuspensionStarting` to inform the host that garbage collection is occurring.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="66794-124">이 작업의 일정을 재조정 마십시오.</span><span class="sxs-lookup"><span data-stu-id="66794-124">Do not reschedule this task.</span></span> <span data-ttu-id="66794-125">호스트는 작업을 다시 예약 해야 때 [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66794-125">The host must reschedule a task when [ThreadIsBlockingForSuspension](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md) is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66794-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="66794-126">Requirements</span></span>  
 <span data-ttu-id="66794-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="66794-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66794-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="66794-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="66794-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="66794-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="66794-130">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66794-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66794-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66794-131">See Also</span></span>  
 [<span data-ttu-id="66794-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66794-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="66794-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66794-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="66794-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66794-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="66794-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66794-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="66794-136">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="66794-136">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
