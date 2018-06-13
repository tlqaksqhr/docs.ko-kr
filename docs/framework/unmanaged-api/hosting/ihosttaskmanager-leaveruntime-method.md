---
title: IHostTaskManager::LeaveRuntime 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d31c5c1b95d250f90b202b391d908f9c12afb84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444479"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a><span data-ttu-id="723ba-102">IHostTaskManager::LeaveRuntime 메서드</span><span class="sxs-lookup"><span data-stu-id="723ba-102">IHostTaskManager::LeaveRuntime Method</span></span>
<span data-ttu-id="723ba-103">현재 실행 중인 작업이 공용 언어 런타임 (CLR) 종료 하 고 관리 되지 않는 코드를 입력 되려고 함을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-103">Notifies the host that the currently executing task is about to leave the common language runtime (CLR) and enter unmanaged code.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="723ba-104">해당 호출 [ihosttaskmanager:: Enterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) 현재 실행 중인 작업은 관리 코드를 다시 입력 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-104">A corresponding call to [IHostTaskManager::EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md) notifies the host that the currently executing task is reentering managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="723ba-105">구문</span><span class="sxs-lookup"><span data-stu-id="723ba-105">Syntax</span></span>  
  
```  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="723ba-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="723ba-106">Parameters</span></span>  
 `target`  
 <span data-ttu-id="723ba-107">[in] 관리 되지 않는 함수를 호출할 수의 매핑된 이식 가능한 실행 파일 내 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-107">[in] The address within the mapped portable executable file of the unmanaged function to be called.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="723ba-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="723ba-108">Return Value</span></span>  
  
|<span data-ttu-id="723ba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="723ba-109">HRESULT</span></span>|<span data-ttu-id="723ba-110">설명</span><span class="sxs-lookup"><span data-stu-id="723ba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="723ba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="723ba-111">S_OK</span></span>|<span data-ttu-id="723ba-112">`LeaveRuntime` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-112">`LeaveRuntime` returned successfully.</span></span>|  
|<span data-ttu-id="723ba-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="723ba-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="723ba-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="723ba-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="723ba-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="723ba-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-116">The call timed out.</span></span>|  
|<span data-ttu-id="723ba-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="723ba-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="723ba-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="723ba-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="723ba-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="723ba-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="723ba-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="723ba-121">E_FAIL</span></span>|<span data-ttu-id="723ba-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="723ba-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="723ba-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="723ba-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="723ba-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="723ba-126">메모리가 부족 하 여 요청 된 할당을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-126">Not enough memory is available to complete the requested allocation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="723ba-127">설명</span><span class="sxs-lookup"><span data-stu-id="723ba-127">Remarks</span></span>  
 <span data-ttu-id="723ba-128">비관리 코드에서 호출 시퀀스를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-128">Call sequences to and from unmanaged code can be nested.</span></span> <span data-ttu-id="723ba-129">아래 목록에는 가상의 상황을 설명 하는 예를 들어 호출의 시퀀스 `LeaveRuntime`, [ihosttaskmanager:: Reverseenterruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [ihosttaskmanager:: Reverseleaveruntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), 및 `IHostTaskManager::EnterRuntime` 중첩 된 레이어를 식별 하는 호스트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-129">For example, the list below describes a hypothetical situation in which the sequence of calls to `LeaveRuntime`, [IHostTaskManager::ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager::ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md), and `IHostTaskManager::EnterRuntime` allows the host to identify the nested layers.</span></span>  
  
|<span data-ttu-id="723ba-130">작업</span><span class="sxs-lookup"><span data-stu-id="723ba-130">Action</span></span>|<span data-ttu-id="723ba-131">해당 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="723ba-131">Corresponding Method Call</span></span>|  
|------------|-------------------------------|  
|<span data-ttu-id="723ba-132">관리 되는 Visual Basic 실행 호출 플랫폼을 사용 하 여 C에서 작성 하는 관리 되지 않는 함수 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-132">A managed Visual Basic executable calls an unmanaged function written in C by using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="723ba-133">관리 되지 않는 C 함수는 C#으로 작성 된 관리 되는 DLL의 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-133">The unmanaged C function calls a method in a managed DLL written in C#.</span></span>|`IHostTaskManager::ReverseEnterRuntime`|  
|<span data-ttu-id="723ba-134">관리 되는 C# 함수 호출 또한 플랫폼을 사용 하 여 C로 작성 된 다른 관리 되지 않는 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-134">The managed C# function calls another unmanaged function written in C, also using platform invoke.</span></span>|`IHostTaskManager::LeaveRuntime`|  
|<span data-ttu-id="723ba-135">두 번째 관리 되지 않는 함수는 C# 함수를 실행을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-135">The second unmanaged function returns execution to the C# function.</span></span>|`IHostTaskManager::EnterRuntime`|  
|<span data-ttu-id="723ba-136">C# 함수는 첫 번째 관리 되지 않는 함수 실행을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-136">The C# function returns execution to the first unmanaged function.</span></span>|`IHostTaskManager::ReverseLeaveRuntime`|  
|<span data-ttu-id="723ba-137">첫 번째 관리 되지 않는 함수는 Visual Basic 프로그램 실행 제어를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-137">The first unmanaged function returns execution to the Visual Basic program.</span></span>|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a><span data-ttu-id="723ba-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="723ba-138">Requirements</span></span>  
 <span data-ttu-id="723ba-139">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="723ba-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="723ba-140">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="723ba-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="723ba-141">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="723ba-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="723ba-142">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="723ba-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723ba-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="723ba-143">See Also</span></span>  
 [<span data-ttu-id="723ba-144">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="723ba-144">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="723ba-145">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="723ba-145">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="723ba-146">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="723ba-146">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="723ba-147">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="723ba-147">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
