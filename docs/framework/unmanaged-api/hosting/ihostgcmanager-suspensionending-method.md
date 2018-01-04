---
title: "IHostGCManager::SuspensionEnding 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostGCManager.SuspensionEnding
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostGCManager::SuspensionEnding
helpviewer_keywords:
- SuspensionEnding method, IHostGCManager interface [.NET Framework hosting]
- IHostGCManager::SuspensionEnding method [.NET Framework hosting]
ms.assetid: 8849a1db-17f0-44b7-880a-bd36d431eb91
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b9660a0aa755e297721679bcf6db798384f12abd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanagersuspensionending-method"></a><span data-ttu-id="127d0-102">IHostGCManager::SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="127d0-102">IHostGCManager::SuspensionEnding Method</span></span>
<span data-ttu-id="127d0-103">공용 언어 런타임 (CLR) 가비지 수집을 위해 중단 된 스레드의 작업을 다시 시작 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-103">Notifies the host that the common language runtime (CLR) is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="127d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="127d0-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="127d0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="127d0-105">Parameters</span></span>  
 `generation`  
 <span data-ttu-id="127d0-106">[in] 이제 가비지 컬렉션 세대를 스레드가 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-106">[in] The garbage collection generation that is just finishing, from which the thread is resuming.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="127d0-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="127d0-107">Return Value</span></span>  
  
|<span data-ttu-id="127d0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="127d0-108">HRESULT</span></span>|<span data-ttu-id="127d0-109">설명</span><span class="sxs-lookup"><span data-stu-id="127d0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="127d0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="127d0-110">S_OK</span></span>|<span data-ttu-id="127d0-111">`SuspensionEnding`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-111">`SuspensionEnding` returned successfully.</span></span>|  
|<span data-ttu-id="127d0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="127d0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="127d0-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="127d0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="127d0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="127d0-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-115">The call timed out.</span></span>|  
|<span data-ttu-id="127d0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="127d0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="127d0-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="127d0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="127d0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="127d0-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="127d0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="127d0-120">E_FAIL</span></span>|<span data-ttu-id="127d0-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="127d0-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="127d0-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="127d0-124">설명</span><span class="sxs-lookup"><span data-stu-id="127d0-124">Remarks</span></span>  
 <span data-ttu-id="127d0-125">CLR에서는 `SuspensionEnding` 스레드가 다시 시작 하는 호스트에 알리기 위해 가비지 수집을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-125">The CLR calls `SuspensionEnding` after it performs a garbage collection, to inform the host that the thread is resuming execution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="127d0-126">만들어진 메서드 호출 스레드 일정을 재조정 마십시오.</span><span class="sxs-lookup"><span data-stu-id="127d0-126">Do not reschedule the thread the method call was made from.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="127d0-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="127d0-127">Requirements</span></span>  
 <span data-ttu-id="127d0-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="127d0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="127d0-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="127d0-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="127d0-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="127d0-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="127d0-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="127d0-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="127d0-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="127d0-132">See Also</span></span>  
 [<span data-ttu-id="127d0-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="127d0-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="127d0-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="127d0-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="127d0-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="127d0-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="127d0-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="127d0-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="127d0-137">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="127d0-137">IHostGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)
