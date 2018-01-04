---
title: "ICLRTask::SwitchIn 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SwitchIn
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e99fc43dea70d456bbaab9bba63e5a018e9e9201
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskswitchin-method"></a><span data-ttu-id="d580c-102">ICLRTask::SwitchIn 메서드</span><span class="sxs-lookup"><span data-stu-id="d580c-102">ICLRTask::SwitchIn Method</span></span>
<span data-ttu-id="d580c-103">공용 언어 런타임 (CLR)에 게 알리는 하는 작업 하는 현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 나타내는 작동 가능한 상태가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-103">Notifies the common language runtime (CLR) that the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents is now in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d580c-104">구문</span><span class="sxs-lookup"><span data-stu-id="d580c-104">Syntax</span></span>  
  
```  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d580c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d580c-105">Parameters</span></span>  
 `threadHandle`  
 <span data-ttu-id="d580c-106">[in] 요일을 나타내는 작업이 현재 실제 스레드에 대 한 핸들 `ICLRTask` 인스턴스만 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-106">[in] A handle to the physical thread on which the task represented by the current `ICLRTask` instance is executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d580c-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d580c-107">Return Value</span></span>  
  
|<span data-ttu-id="d580c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d580c-108">HRESULT</span></span>|<span data-ttu-id="d580c-109">설명</span><span class="sxs-lookup"><span data-stu-id="d580c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d580c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d580c-110">S_OK</span></span>|<span data-ttu-id="d580c-111">`SwitchIn`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-111">`SwitchIn` returned successfully.</span></span>|  
|<span data-ttu-id="d580c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d580c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d580c-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d580c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d580c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d580c-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-115">The call timed out.</span></span>|  
|<span data-ttu-id="d580c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d580c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d580c-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d580c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d580c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d580c-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d580c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d580c-120">E_FAIL</span></span>|<span data-ttu-id="d580c-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d580c-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d580c-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="d580c-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="d580c-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="d580c-125">`SwitchIn`에 대 한 이전 호출 없이 호출한 [SwitchOut 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-125">`SwitchIn` was called without an earlier call to [SwitchOut Method](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d580c-126">설명</span><span class="sxs-lookup"><span data-stu-id="d580c-126">Remarks</span></span>  
 <span data-ttu-id="d580c-127">`threadHandle` 매개 변수를 나타내는 작업이 현재 운영 체제 스레드에 핸들을 나타내는 `ICLRTask` 인스턴스가 예약 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-127">The `threadHandle` parameter represents a handle to the operating system thread on which the task represented by the current `ICLRTask` instance has been scheduled.</span></span> <span data-ttu-id="d580c-128">가장이 스레드에서 수행 되 면 호출 해야 [ihostsecuritymanager:: Reverttoself](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) 작업에서 전환 하기 전에.</span><span class="sxs-lookup"><span data-stu-id="d580c-128">If impersonation has occurred on this thread, you must call [IHostSecurityManager::RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) before switching in the task.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d580c-129">에 대 한 호출 `SwitchIn` 한 이전 호출 하지 않고 `SwitchOut` HOST_E_INVALIDOPERATION HRESULT 값와 함께 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-129">A call to `SwitchIn` without an earlier call to `SwitchOut` fails with an HRESULT value of HOST_E_INVALIDOPERATION.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d580c-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d580c-130">Requirements</span></span>  
 <span data-ttu-id="d580c-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d580c-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d580c-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d580c-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d580c-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d580c-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d580c-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d580c-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d580c-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d580c-135">See Also</span></span>  
 [<span data-ttu-id="d580c-136">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d580c-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="d580c-137">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d580c-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="d580c-138">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d580c-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="d580c-139">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d580c-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
