---
title: "IHostControl::GetHostManager 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostControl.GetHostManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostControl::GetHostManager
helpviewer_keywords:
- GetHostManager method [.NET Framework hosting]
- IHostControl::GetHostManager method [.NET Framework hosting]
ms.assetid: 0fa34bca-ed18-4626-9e78-d33684d18edb
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6701350fa9bdb51843b117b0191b677e739807a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcontrolgethostmanager-method"></a><span data-ttu-id="6a192-102">IHostControl::GetHostManager 메서드</span><span class="sxs-lookup"><span data-stu-id="6a192-102">IHostControl::GetHostManager Method</span></span>
<span data-ttu-id="6a192-103">지정 된 호스트의 인터페이스 구현에 대 한 인터페이스 포인터를 가져옵니다 `IID`합니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-103">Gets an interface pointer to the host's implementation of the interface with the specified `IID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a192-104">구문</span><span class="sxs-lookup"><span data-stu-id="6a192-104">Syntax</span></span>  
  
```  
HRESULT GetHostManager (  
    [in] REFIID riid,  
    [out, iid_is(riid)] void** ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6a192-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a192-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="6a192-106">[in] `IID` 공용 언어 런타임 (CLR) 쿼리 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-106">[in] The `IID` of the interface that the common language runtime (CLR) is querying for.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="6a192-107">[out] 호스트 구현 인터페이스 또는 호스트는이 인터페이스를 지원 하지 않는 경우 null에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-107">[out] A pointer to the host-implemented interface, or null if the host does not support this interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a192-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6a192-108">Return Value</span></span>  
  
|<span data-ttu-id="6a192-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a192-109">HRESULT</span></span>|<span data-ttu-id="6a192-110">설명</span><span class="sxs-lookup"><span data-stu-id="6a192-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6a192-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a192-111">S_OK</span></span>|<span data-ttu-id="6a192-112">`GetHostManager`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-112">`GetHostManager` returned successfully.</span></span>|  
|<span data-ttu-id="6a192-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6a192-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6a192-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6a192-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6a192-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6a192-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-116">The call timed out.</span></span>|  
|<span data-ttu-id="6a192-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6a192-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6a192-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6a192-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6a192-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6a192-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6a192-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6a192-121">E_FAIL</span></span>|<span data-ttu-id="6a192-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6a192-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6a192-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6a192-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="6a192-125">E_INVALIDARG</span></span>|<span data-ttu-id="6a192-126">요청 된 `IID` 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-126">The requested `IID` is not valid.</span></span>|  
|<span data-ttu-id="6a192-127">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="6a192-127">E_NOINTERFACE</span></span>|<span data-ttu-id="6a192-128">요청한 인터페이스가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-128">The requested interface is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a192-129">설명</span><span class="sxs-lookup"><span data-stu-id="6a192-129">Remarks</span></span>  
 <span data-ttu-id="6a192-130">CLR 다음 인터페이스 중 하나 이상을 지원 하는지 확인 하려면 호스트를 쿼리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-130">The CLR queries the host to determine whether it supports one or more of the following interfaces:</span></span>  
  
-   [<span data-ttu-id="6a192-131">IHostMemoryManager</span><span class="sxs-lookup"><span data-stu-id="6a192-131">IHostMemoryManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
  
-   [<span data-ttu-id="6a192-132">IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="6a192-132">IHostTaskManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
  
-   [<span data-ttu-id="6a192-133">IHostThreadPoolManager</span><span class="sxs-lookup"><span data-stu-id="6a192-133">IHostThreadPoolManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)  
  
-   [<span data-ttu-id="6a192-134">IHostIoCompletionManager</span><span class="sxs-lookup"><span data-stu-id="6a192-134">IHostIoCompletionManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
  
-   [<span data-ttu-id="6a192-135">IHostSyncManager</span><span class="sxs-lookup"><span data-stu-id="6a192-135">IHostSyncManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
  
-   [<span data-ttu-id="6a192-136">IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="6a192-136">IHostAssemblyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
  
-   [<span data-ttu-id="6a192-137">IHostGCManager</span><span class="sxs-lookup"><span data-stu-id="6a192-137">IHostGCManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-interface.md)  
  
-   [<span data-ttu-id="6a192-138">IHostPolicyManager</span><span class="sxs-lookup"><span data-stu-id="6a192-138">IHostPolicyManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)  
  
-   [<span data-ttu-id="6a192-139">IHostSecurityManager</span><span class="sxs-lookup"><span data-stu-id="6a192-139">IHostSecurityManager</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
  
 <span data-ttu-id="6a192-140">호스트에서 지정된 된 인터페이스를 지 원하는 경우 설정 `ppObject` 를 해당 해당 인터페이스의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-140">If the host supports the specified interface, it sets `ppObject` to its implementation of that interface.</span></span> <span data-ttu-id="6a192-141">그렇지 않으면, 설정 `ppObject` null로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-141">Otherwise, it sets `ppObject` to null.</span></span>  
  
 <span data-ttu-id="6a192-142">CLR에서 호출 하지 않으며 `Release` 관리자 호스트를 종료 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-142">The CLR does not call `Release` on host managers, even when you shut it down.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a192-143">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a192-143">Requirements</span></span>  
 <span data-ttu-id="6a192-144">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6a192-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a192-145">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a192-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a192-146">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6a192-146">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a192-147">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a192-147">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a192-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a192-148">See Also</span></span>  
 [<span data-ttu-id="6a192-149">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a192-149">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
