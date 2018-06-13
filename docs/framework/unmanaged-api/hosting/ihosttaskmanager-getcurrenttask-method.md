---
title: IHostTaskManager::GetCurrentTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2420ddb5cf9be2cfb08f89d27d9aa277305e7ffb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442694"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="99c32-102">IHostTaskManager::GetCurrentTask 메서드</span><span class="sxs-lookup"><span data-stu-id="99c32-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="99c32-103">이 호출이 수행 된 운영 체제 스레드에 대해 현재 실행 중인 작업에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99c32-104">구문</span><span class="sxs-lookup"><span data-stu-id="99c32-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99c32-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99c32-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="99c32-106">[out] 주소에 대 한 포인터는 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 작업이 현재 실행 중인 경우 현재 실행 중인 작업 또는 null을 나타내는 인스턴스는 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99c32-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="99c32-107">Return Value</span></span>  
  
|<span data-ttu-id="99c32-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="99c32-108">HRESULT</span></span>|<span data-ttu-id="99c32-109">설명</span><span class="sxs-lookup"><span data-stu-id="99c32-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="99c32-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="99c32-110">S_OK</span></span>|<span data-ttu-id="99c32-111">`GetCurrentTask` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="99c32-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="99c32-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="99c32-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="99c32-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="99c32-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="99c32-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-115">The call timed out.</span></span>|  
|<span data-ttu-id="99c32-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="99c32-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="99c32-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="99c32-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="99c32-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="99c32-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="99c32-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="99c32-120">E_FAIL</span></span>|<span data-ttu-id="99c32-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="99c32-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="99c32-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="99c32-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="99c32-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="99c32-125">`GetCurrentTask` 운영 체제 스레드는 호스트의 컨트롤 외부에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99c32-126">설명</span><span class="sxs-lookup"><span data-stu-id="99c32-126">Remarks</span></span>  
 <span data-ttu-id="99c32-127">호스트를 설정할 수도 `pTask` 매개 변수를 null 작업을 시작 하지 않은 CLR을 실행 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99c32-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99c32-128">Requirements</span></span>  
 <span data-ttu-id="99c32-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="99c32-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99c32-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="99c32-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99c32-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="99c32-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99c32-132">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99c32-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99c32-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99c32-133">See Also</span></span>  
 [<span data-ttu-id="99c32-134">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99c32-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="99c32-135">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99c32-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="99c32-136">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99c32-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="99c32-137">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99c32-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
