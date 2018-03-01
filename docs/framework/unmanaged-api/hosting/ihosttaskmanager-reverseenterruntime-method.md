---
title: "IHostTaskManager::ReverseEnterRuntime 메서드"
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
- IHostTaskManager.ReverseEnterRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::ReverseEnterRuntime
helpviewer_keywords:
- IHostTaskManager::ReverseEnterRuntime method [.NET Framework hosting]
- ReverseEnterRuntime method [.NET Framework hosting]
ms.assetid: b1e26bff-d3ea-436e-9867-29720df999f4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69743f6b7229f89d19d4134a11bb5f37fe5ca928
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerreverseenterruntime-method"></a><span data-ttu-id="f23bb-102">IHostTaskManager::ReverseEnterRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="f23bb-102">IHostTaskManager::ReverseEnterRuntime Method</span></span>
<span data-ttu-id="f23bb-103">비관리 코드에서 공용 언어 런타임 (CLR)로 호출이 수행 되는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-103">Notifies the host that a call is being made into the common language runtime (CLR) from unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f23bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="f23bb-104">Syntax</span></span>  
  
```  
HRESULT ReverseEnterRuntime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="f23bb-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="f23bb-105">Return Value</span></span>  
  
|<span data-ttu-id="f23bb-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f23bb-106">HRESULT</span></span>|<span data-ttu-id="f23bb-107">설명</span><span class="sxs-lookup"><span data-stu-id="f23bb-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f23bb-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="f23bb-108">S_OK</span></span>|<span data-ttu-id="f23bb-109">`ReverseEnterRuntime`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-109">`ReverseEnterRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="f23bb-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f23bb-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f23bb-111">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f23bb-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f23bb-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f23bb-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-113">The call timed out.</span></span>|  
|<span data-ttu-id="f23bb-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f23bb-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f23bb-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f23bb-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f23bb-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f23bb-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f23bb-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f23bb-118">E_FAIL</span></span>|<span data-ttu-id="f23bb-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f23bb-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f23bb-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f23bb-122">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f23bb-122">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f23bb-123">메모리가 부족 하 여 요청 된 리소스 할당을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-123">Not enough memory is available to complete the requested resource allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f23bb-124">설명</span><span class="sxs-lookup"><span data-stu-id="f23bb-124">Remarks</span></span>  
 <span data-ttu-id="f23bb-125">호출할 때마다 발생 하는 시퀀스에서 관리 코드에서 CLR로 호출을 수행 하는 경우 `ReverseEnterRuntime` 에 대 한 호출에 해당 [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-125">If the call into the CLR is made from a sequence that originated in managed code, each call to `ReverseEnterRuntime` corresponds to a call to [ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f23bb-126">호출 비관리 코드에서 중첩 되지 않은 상태로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-126">Calls can originate from unmanaged code without being nested.</span></span> <span data-ttu-id="f23bb-127">이 경우에 대 한 호출이 있습니다. [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), 또는 `ReverseLeaveRuntime`, 호출 수 및 `ReverseEnterRuntime` 호출 수와 같지 않습니다 `ReverseLeaveRuntime`합니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-127">In this case, there is no call to [EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md), [LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md), or `ReverseLeaveRuntime`, and the number of calls to `ReverseEnterRuntime` does not equal the number of calls to `ReverseLeaveRuntime`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f23bb-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f23bb-128">Requirements</span></span>  
 <span data-ttu-id="f23bb-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f23bb-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f23bb-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f23bb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f23bb-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f23bb-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f23bb-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f23bb-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f23bb-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f23bb-133">See Also</span></span>  
 [<span data-ttu-id="f23bb-134">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f23bb-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="f23bb-135">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f23bb-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="f23bb-136">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f23bb-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="f23bb-137">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f23bb-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
