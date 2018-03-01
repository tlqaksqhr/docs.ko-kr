---
title: "ICLRDebugManager::SetConnectionTasks 메서드"
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
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 09f7e47acfcfbde8d5d9724c3a37303f1a584adb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a><span data-ttu-id="a50aa-102">ICLRDebugManager::SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="a50aa-102">ICLRDebugManager::SetConnectionTasks Method</span></span>
<span data-ttu-id="a50aa-103">연결 목록이 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 라는 이름과 식별자를 사용 하 여 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a50aa-103">Associates a list of [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instances with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a50aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="a50aa-104">Syntax</span></span>  
  
```  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a50aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a50aa-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="a50aa-106">[in] 연결 하는 연결에 대 한 호스트에 고유한 식별자는 `ppCLRTask` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-106">[in] The host-specific identifier for the connection with which to associate the `ppCLRTask` array.</span></span>  
  
 `dwCount`  
 <span data-ttu-id="a50aa-107">[in] 멤버 수가 `ppCLRTask`합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-107">[in] The number of members of `ppCLRTask`.</span></span> <span data-ttu-id="a50aa-108">이 번호는 0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-108">This number must be greater than zero.</span></span>  
  
 `ppCLRTask`  
 <span data-ttu-id="a50aa-109">[in] 배열을 `ICLRTask` 을로 식별 되는 연결에 연결에 대 한 포인터 `id`합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-109">[in] An array of `ICLRTask` pointers to associate with the connection identified by `id`.</span></span> <span data-ttu-id="a50aa-110">이 배열에 구성원을 하나 이상 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-110">This array must contain at least one member.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a50aa-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="a50aa-111">Return Value</span></span>  
  
|<span data-ttu-id="a50aa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a50aa-112">HRESULT</span></span>|<span data-ttu-id="a50aa-113">설명</span><span class="sxs-lookup"><span data-stu-id="a50aa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a50aa-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a50aa-114">S_OK</span></span>|<span data-ttu-id="a50aa-115">`SetConnectionTasks`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-115">`SetConnectionTasks` returned successfully.</span></span>|  
|<span data-ttu-id="a50aa-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a50aa-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a50aa-117">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a50aa-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a50aa-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a50aa-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-119">The call timed out.</span></span>|  
|<span data-ttu-id="a50aa-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a50aa-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a50aa-121">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a50aa-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a50aa-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a50aa-123">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a50aa-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a50aa-124">E_FAIL</span></span>|<span data-ttu-id="a50aa-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a50aa-126">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a50aa-127">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a50aa-128">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a50aa-128">E_INVALIDARG</span></span>|<span data-ttu-id="a50aa-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) 이 값을 사용 하 여 호출 되지 않은 `id`, 또는 `dwCount` 또는 `id` 0 또는의 요소 중 하나는 `ppCLRTask` null입니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-129">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) has not been called using this value of `id`, or `dwCount` or `id` is zero, or one of the elements of `ppCLRTask` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a50aa-130">설명</span><span class="sxs-lookup"><span data-stu-id="a50aa-130">Remarks</span></span>  
 <span data-ttu-id="a50aa-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 세 가지 방법을 제공 `BeginConnection`, `SetConnectionTasks`, 및 [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), 식별자 및 이름을 사용 하 여 작업 목록 연결에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-131">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, `SetConnectionTasks`, and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a50aa-132">이러한 세 가지 메서드는 각 작업 집합에는 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-132">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="a50aa-133">`BeginConnection`먼저 호출 되어 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-133">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="a50aa-134">`SetConnectionTasks`다음 호출 되 해당 연결에 연관 될 작업의 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-134">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="a50aa-135">`EndConnection`작업 목록 및 식별자, 이름 간의 연결을 제거 하려면 마지막이 하 라고 합니다. 그러나 서로 다른 연결에 대 한 호출을 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-135">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a50aa-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a50aa-136">Requirements</span></span>  
 <span data-ttu-id="a50aa-137">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a50aa-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a50aa-138">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a50aa-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a50aa-139">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a50aa-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a50aa-140">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a50aa-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50aa-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a50aa-141">See Also</span></span>  
 [<span data-ttu-id="a50aa-142">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50aa-142">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="a50aa-143">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50aa-143">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="a50aa-144">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="a50aa-144">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="a50aa-145">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="a50aa-145">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="a50aa-146">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a50aa-146">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
