---
title: "IHostTaskManager::SetCLRTaskManager 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.SetCLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::SetCLRTaskManager
helpviewer_keywords:
- IHostTaskManager::SetCLRTaskManager method [.NET Framework hosting]
- SetCLRTaskManager method [.NET Framework hosting]
ms.assetid: ec90ee83-bd4b-408b-9274-62a923ab86a1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ec0d515ad4c0bc21e1036f20f17bf168d7af79d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagersetclrtaskmanager-method"></a><span data-ttu-id="9579c-102">IHostTaskManager::SetCLRTaskManager 메서드</span><span class="sxs-lookup"><span data-stu-id="9579c-102">IHostTaskManager::SetCLRTaskManager Method</span></span>
<span data-ttu-id="9579c-103">호스트에 대 한 인터페이스 포인터에 제공 된 [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) 공용 언어 런타임 (CLR)에 의해 구현 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9579c-103">Provides the host with an interface pointer to an [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9579c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9579c-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTaskManager (  
    [in] ICLRTaskManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9579c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9579c-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="9579c-106">[in] 에 대 한 포인터는 `ICLRTaskManager` 공용 언어 런타임에 의해 구현 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9579c-106">[in] A pointer to an `ICLRTaskManager` instance implemented by the common language runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9579c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9579c-107">Return Value</span></span>  
  
|<span data-ttu-id="9579c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9579c-108">HRESULT</span></span>|<span data-ttu-id="9579c-109">설명</span><span class="sxs-lookup"><span data-stu-id="9579c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9579c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9579c-110">S_OK</span></span>|<span data-ttu-id="9579c-111">`SetCLRTaskManager`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9579c-111">`SetCLRTaskManager` returned successfully.</span></span>|  
|<span data-ttu-id="9579c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9579c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9579c-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9579c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9579c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9579c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9579c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9579c-115">The call timed out.</span></span>|  
|<span data-ttu-id="9579c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9579c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9579c-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9579c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9579c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9579c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9579c-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9579c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9579c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9579c-120">E_FAIL</span></span>|<span data-ttu-id="9579c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9579c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9579c-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9579c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9579c-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9579c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9579c-124">설명</span><span class="sxs-lookup"><span data-stu-id="9579c-124">Remarks</span></span>  
 <span data-ttu-id="9579c-125">런타임 호출 `SetCLRTaskManager` 호스트에 대 한 인터페이스 포인터를 제공 하는 `ICLRTaskManager` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="9579c-125">The runtime calls `SetCLRTaskManager` to provide the host with an interface pointer to an `ICLRTaskManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9579c-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9579c-126">Requirements</span></span>  
 <span data-ttu-id="9579c-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9579c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9579c-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9579c-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9579c-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9579c-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9579c-130">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9579c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9579c-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9579c-131">See Also</span></span>  
 [<span data-ttu-id="9579c-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9579c-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9579c-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9579c-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9579c-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9579c-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9579c-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9579c-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
