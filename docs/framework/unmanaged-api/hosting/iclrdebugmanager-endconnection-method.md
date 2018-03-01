---
title: "ICLRDebugManager::EndConnection 메서드"
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
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 210226b697eb3dffe574bd842ca31e83948891a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugmanagerendconnection-method"></a><span data-ttu-id="f2f26-102">ICLRDebugManager::EndConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="f2f26-102">ICLRDebugManager::EndConnection Method</span></span>
<span data-ttu-id="f2f26-103">작업 목록 및 식별자 및 이름을 사이의 연결을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-103">Removes the association between a list of tasks and an identifier and a friendly name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f26-104">구문</span><span class="sxs-lookup"><span data-stu-id="f2f26-104">Syntax</span></span>  
  
```  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2f26-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f2f26-105">Parameters</span></span>  
 `dwConnectionId`  
 <span data-ttu-id="f2f26-106">[in] 공용 언어 런타임 (CLR) 작업의 연결 된 목록과 연결에 대 한 호스트 관련 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-106">[in] The host-specific identifier for the connection and the associated list of common language runtime (CLR) tasks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2f26-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f2f26-107">Return Value</span></span>  
  
|<span data-ttu-id="f2f26-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f2f26-108">HRESULT</span></span>|<span data-ttu-id="f2f26-109">설명</span><span class="sxs-lookup"><span data-stu-id="f2f26-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f2f26-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2f26-110">S_OK</span></span>|<span data-ttu-id="f2f26-111">`EndConnection`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-111">`EndConnection` returned successfully.</span></span>|  
|<span data-ttu-id="f2f26-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f2f26-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f2f26-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f2f26-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f2f26-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f2f26-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-115">The call timed out.</span></span>|  
|<span data-ttu-id="f2f26-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f2f26-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f2f26-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f2f26-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f2f26-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f2f26-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f2f26-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f2f26-120">E_FAIL</span></span>|<span data-ttu-id="f2f26-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f2f26-122">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f2f26-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f2f26-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f2f26-124">E_INVALIDARG</span></span>|<span data-ttu-id="f2f26-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) 를 사용 하 여 호출 되지가 `dwConnectionId`, 또는 `dwConnectionId` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-125">[BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md) was never called using `dwConnectionId`, or `dwConnectionId` was zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2f26-126">설명</span><span class="sxs-lookup"><span data-stu-id="f2f26-126">Remarks</span></span>  
 <span data-ttu-id="f2f26-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) 세 가지 방법을 제공 `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), 및 `EndConnection`, 식별자 및 이름을 사용 하 여 작업 목록 연결에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-127">[ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) provides three methods, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), and `EndConnection`, for associating task lists with identifiers and friendly names.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f2f26-128">이러한 세 가지 메서드는 각 작업 집합에는 특정 순서로 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-128">These three methods must be called in a specific order for each set of tasks.</span></span> <span data-ttu-id="f2f26-129">`BeginConnection`먼저 호출 되어 새 연결을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-129">`BeginConnection` is called first to establish a new connection.</span></span> <span data-ttu-id="f2f26-130">`SetConnectionTasks`다음 호출 되 해당 연결에 연관 될 작업의 집합을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-130">`SetConnectionTasks` is called next to provide the set of tasks to be associated with that connection.</span></span> <span data-ttu-id="f2f26-131">`EndConnection`작업 목록 및 식별자, 이름 간의 연결을 제거 하려면 마지막이 하 라고 합니다. 그러나 서로 다른 연결에 대 한 호출을 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-131">`EndConnection` is called last to remove the association between the task list and the identifier and friendly name.However, calls for different connections can be nested.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2f26-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f2f26-132">Requirements</span></span>  
 <span data-ttu-id="f2f26-133">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f2f26-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2f26-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2f26-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2f26-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f2f26-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2f26-136">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2f26-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f26-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2f26-137">See Also</span></span>  
 [<span data-ttu-id="f2f26-138">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2f26-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="f2f26-139">ICLRDebugManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2f26-139">ICLRDebugManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)  
 [<span data-ttu-id="f2f26-140">BeginConnection 메서드</span><span class="sxs-lookup"><span data-stu-id="f2f26-140">BeginConnection Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)  
 [<span data-ttu-id="f2f26-141">SetConnectionTasks 메서드</span><span class="sxs-lookup"><span data-stu-id="f2f26-141">SetConnectionTasks Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)  
 [<span data-ttu-id="f2f26-142">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f2f26-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
