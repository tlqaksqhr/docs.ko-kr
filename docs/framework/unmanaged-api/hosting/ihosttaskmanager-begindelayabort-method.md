---
title: "IHostTaskManager::BeginDelayAbort 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.BeginDelayAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a6b37c87f26013dab95f7607e03463437b9797a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="ec130-102">IHostTaskManager::BeginDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="ec130-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="ec130-103">호스트 관리 코드에는 현재 작업 중단할 수 없는 기간이 시작 됨을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec130-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec130-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ec130-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="ec130-105">Return Value</span></span>  
  
|<span data-ttu-id="ec130-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ec130-106">HRESULT</span></span>|<span data-ttu-id="ec130-107">설명</span><span class="sxs-lookup"><span data-stu-id="ec130-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ec130-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ec130-108">S_OK</span></span>|<span data-ttu-id="ec130-109">`BeginDelayAbort`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="ec130-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ec130-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ec130-111">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ec130-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ec130-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ec130-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-113">The call timed out.</span></span>|  
|<span data-ttu-id="ec130-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ec130-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ec130-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ec130-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ec130-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ec130-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ec130-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ec130-118">E_FAIL</span></span>|<span data-ttu-id="ec130-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ec130-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ec130-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ec130-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="ec130-122">E_UNEXPECTED</span></span>|<span data-ttu-id="ec130-123">`BeginDelayAbort`가 이미 호출 된 해당 호출 되지만 [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) 아직 수신 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec130-124">설명</span><span class="sxs-lookup"><span data-stu-id="ec130-124">Remarks</span></span>  
 <span data-ttu-id="ec130-125">호스트 될 때까지 현재 작업을 중단 하지 해야 `EndDelayAbort` 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="ec130-126">다시 호출 하는 경우 `BeginDelayAbort` 에 대 한 중간 호출 없이 이루어집니다 `EndDelayAbort`, 호스트에서 E_UNEXPECTED를 반환 해야 `BeginDelayAbort`, 아무 작업도 수행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec130-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec130-127">Requirements</span></span>  
 <span data-ttu-id="ec130-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ec130-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec130-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ec130-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ec130-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ec130-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec130-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec130-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec130-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec130-132">See Also</span></span>  
 [<span data-ttu-id="ec130-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec130-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ec130-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec130-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ec130-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec130-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="ec130-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ec130-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
