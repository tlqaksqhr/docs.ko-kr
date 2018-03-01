---
title: "IHostSyncManager::SetCLRSyncManager 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fca59f0d2617c6fb244b2b1ed7b5cf46a7d5869f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="e0145-102">IHostSyncManager::SetCLRSyncManager 메서드</span><span class="sxs-lookup"><span data-stu-id="e0145-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="e0145-103">설정의 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 현재와 연결할 인스턴스 [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e0145-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0145-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0145-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0145-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0145-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="e0145-106">[in] 에 대 한 포인터는 `ICLRSyncManager` 공용 언어 런타임 (CLR)에서 제공 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e0145-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0145-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e0145-107">Return Value</span></span>  
  
|<span data-ttu-id="e0145-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0145-108">HRESULT</span></span>|<span data-ttu-id="e0145-109">설명</span><span class="sxs-lookup"><span data-stu-id="e0145-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0145-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0145-110">S_OK</span></span>|<span data-ttu-id="e0145-111">`SetCLRSyncManager`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="e0145-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0145-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0145-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0145-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0145-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0145-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-115">The call timed out.</span></span>|  
|<span data-ttu-id="e0145-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0145-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0145-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0145-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0145-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0145-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0145-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0145-120">E_FAIL</span></span>|<span data-ttu-id="e0145-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0145-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0145-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0145-124">설명</span><span class="sxs-lookup"><span data-stu-id="e0145-124">Remarks</span></span>  
 <span data-ttu-id="e0145-125">호스트와 CLR 간의 통신을 위해 일반적으로 호스팅 인터페이스는 쌍으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="e0145-126">쌍의 구성원 중 하나는 호스트에서 구현 되 고 다른 멤버가 CLR에 의해 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="e0145-127">호스트 측 구현으로는 `IHostSyncManager` 인터페이스에 해당 하는 `ICLRSyncManager` CLR에서 구현 된 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="e0145-128">CLR에서는 `SetCLRSyncManager` 제공 하는 `ICLRSyncManager` 현재의 연결 하는 호스트 인스턴스 `IHostSyncManager` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="e0145-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0145-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0145-129">Requirements</span></span>  
 <span data-ttu-id="e0145-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e0145-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0145-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0145-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0145-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e0145-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0145-133">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0145-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0145-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0145-134">See Also</span></span>  
 [<span data-ttu-id="e0145-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0145-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="e0145-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0145-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
