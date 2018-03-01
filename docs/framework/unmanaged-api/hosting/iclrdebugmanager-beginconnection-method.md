---
title: "ICLRDebugManager::BeginConnection 메서드"
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
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a637ba71dc966cf311526f468393ef4207e10460
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagerbeginconnection-method"></a><span data-ttu-id="4aba2-102">ICLRDebugManager::BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="4aba2-102">ICLRDebugManager::BeginConnection Method</span></span>
<span data-ttu-id="4aba2-103">호스트와 디버거 식별자 및 이름을 사용 하 여 작업 목록을 연결 하려면 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-103">Establishes a new connection between the host and the debugger to associate a list of tasks with an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4aba2-104">구문</span><span class="sxs-lookup"><span data-stu-id="4aba2-104">Syntax</span></span>  
  
```  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4aba2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4aba2-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="4aba2-106">[in] 공용 언어 런타임 (CLR) 작업의 목록으로 연결 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-106">[in] An identifier to associate with the list of common language runtime (CLR) tasks.</span></span>  
  
 `szConnectionName`  
 <span data-ttu-id="4aba2-107">[in] CLR 작업 목록에 연결할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-107">[in] A friendly name to associate with the list of CLR tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4aba2-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="4aba2-108">Return Value</span></span>  
  
|<span data-ttu-id="4aba2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4aba2-109">HRESULT</span></span>|<span data-ttu-id="4aba2-110">설명</span><span class="sxs-lookup"><span data-stu-id="4aba2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4aba2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4aba2-111">S_OK</span></span>|<span data-ttu-id="4aba2-112">`BeginConnection`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-112">`BeginConnection` returned successfully.</span></span>|  
|<span data-ttu-id="4aba2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4aba2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4aba2-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4aba2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4aba2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4aba2-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-116">The call timed out.</span></span>|  
|<span data-ttu-id="4aba2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4aba2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4aba2-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4aba2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4aba2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4aba2-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4aba2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4aba2-121">E_FAIL</span></span>|<span data-ttu-id="4aba2-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4aba2-123">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4aba2-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4aba2-125">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4aba2-125">E_INVALIDARG</span></span>|<span data-ttu-id="4aba2-126">`dwConnectionId`가 0 또는 `BeginConnection` 이 사용 하 여 이미 호출 `dwConnectionId` 값 또는 `szConnectionName` null입니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-126">`dwConnectionId` was zero, or `BeginConnection` was already called using this `dwConnectionId` value, or `szConnectionName` was null.</span></span>|  
|<span data-ttu-id="4aba2-127">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4aba2-127">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4aba2-128">이 연결과 관련 된 작업의 목록을 유지 하는 메모리가 부족를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-128">Not enough memory could be allocated to hold the list of tasks associated with this connection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4aba2-129">설명</span><span class="sxs-lookup"><span data-stu-id="4aba2-129">Remarks</span></span>  
 <span data-ttu-id="4aba2-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 세 가지 방법을 제공 `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), 및 [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), 식별자 및 이름을 사용 하 여 작업 목록 연결에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-130">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4aba2-131">이러한 세 가지 메서드는 각 작업 집합에는 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-131">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="4aba2-132">`BeginConnection`먼저 호출 되어 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-132">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="4aba2-133">`SetConnectionTasks`다음 호출 되 해당 연결에 연관 될 작업의 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-133">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="4aba2-134">`EndConnection`작업 목록 및 식별자, 이름 간의 연결을 제거 하려면 마지막이 하 라고 합니다. 그러나 서로 다른 연결에 대 한 호출을 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-134">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4aba2-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4aba2-135">Requirements</span></span>  
 <span data-ttu-id="4aba2-136">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4aba2-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4aba2-137">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4aba2-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4aba2-138">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4aba2-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4aba2-139">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4aba2-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aba2-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4aba2-140">See Also</span></span>  
 [<span data-ttu-id="4aba2-141">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4aba2-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="4aba2-142">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4aba2-142">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="4aba2-143">EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="4aba2-143">EndConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)  
 [<span data-ttu-id="4aba2-144">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="4aba2-144">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="4aba2-145">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4aba2-145">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
