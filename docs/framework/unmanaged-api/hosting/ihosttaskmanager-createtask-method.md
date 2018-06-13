---
title: IHostTaskManager::CreateTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0cb539d5b10c8a027a8c73c68ccc04aa490cb4df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443169"
---
# <a name="ihosttaskmanagercreatetask-method"></a><span data-ttu-id="0d7c1-102">IHostTaskManager::CreateTask 메서드</span><span class="sxs-lookup"><span data-stu-id="0d7c1-102">IHostTaskManager::CreateTask Method</span></span>
<span data-ttu-id="0d7c1-103">호스트에서 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-103">Requests that the host create a new task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d7c1-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d7c1-104">Syntax</span></span>  
  
```  
HRESULT CreateTask (  
    [in]  DWORD stacksize,   
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d7c1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d7c1-105">Parameters</span></span>  
 `stacksize`  
 <span data-ttu-id="0d7c1-106">[in] 요청 된 스택 또는 0 (영) 기본 크기를 바이트 단위로 요청 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-106">[in] The requested size, in bytes, of the requested stack, or 0 (zero) for the default size.</span></span>  
  
 `pStartAddress`  
 <span data-ttu-id="0d7c1-107">[in] 함수에 대 한 포인터는 태스크를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-107">[in] A pointer to the function the task is to execute.</span></span>  
  
 `pParameter`  
 <span data-ttu-id="0d7c1-108">[in] 매개 변수를 사용 하는 함수는 함수 또는 null 인 경우에 전달 될 사용자 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-108">[in] A pointer to the user data to be passed to the function, or null if the function takes no parameters.</span></span>  
  
 `ppTask`  
 <span data-ttu-id="0d7c1-109">[out] 주소에 대 한 포인터는 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스 호스트 또는 null 경우 만든 작업을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-109">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance created by the host, or null if the task cannot be created.</span></span> <span data-ttu-id="0d7c1-110">작업은 명시적으로 호출 하 여 시작 될 때까지 일시 중단된 된 상태에 남아 [ihosttask:: Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-110">The task remains in a suspended state until it is explicitly started by a call to [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d7c1-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="0d7c1-111">Return Value</span></span>  
  
|<span data-ttu-id="0d7c1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d7c1-112">HRESULT</span></span>|<span data-ttu-id="0d7c1-113">설명</span><span class="sxs-lookup"><span data-stu-id="0d7c1-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0d7c1-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="0d7c1-114">S_OK</span></span>|<span data-ttu-id="0d7c1-115">`CreateTask` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-115">`CreateTask` returned successfully.</span></span>|  
|<span data-ttu-id="0d7c1-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0d7c1-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0d7c1-117">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0d7c1-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0d7c1-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0d7c1-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-119">The call timed out.</span></span>|  
|<span data-ttu-id="0d7c1-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0d7c1-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0d7c1-121">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0d7c1-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0d7c1-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0d7c1-123">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0d7c1-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0d7c1-124">E_FAIL</span></span>|<span data-ttu-id="0d7c1-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0d7c1-126">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0d7c1-127">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0d7c1-128">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="0d7c1-128">E_OUTOFMEMORY</span></span>|<span data-ttu-id="0d7c1-129">요청 된 작업을 만드는 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-129">Not enough memory was available to create the requested task.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d7c1-130">설명</span><span class="sxs-lookup"><span data-stu-id="0d7c1-130">Remarks</span></span>  
 <span data-ttu-id="0d7c1-131">CLR에서는 `CreateTask` 를 호스트에서 새 작업을 만들도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-131">The CLR calls `CreateTask` to request that the host create a new task.</span></span> <span data-ttu-id="0d7c1-132">에 인터페이스 포인터를 반환 하는 호스트는 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-132">The host returns an interface pointer to an `IHostTask` instance.</span></span> <span data-ttu-id="0d7c1-133">반환된 된 작업은 명시적으로 호출 하 여 시작 될 때까지 일시 중지 해야 `IHostTask::Start`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-133">The returned task must remain suspended until it is explicitly started by a call to `IHostTask::Start`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d7c1-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d7c1-134">Requirements</span></span>  
 <span data-ttu-id="0d7c1-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7c1-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d7c1-136">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0d7c1-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0d7c1-137">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0d7c1-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d7c1-138">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d7c1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7c1-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d7c1-139">See Also</span></span>  
 [<span data-ttu-id="0d7c1-140">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d7c1-140">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="0d7c1-141">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d7c1-141">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="0d7c1-142">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d7c1-142">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="0d7c1-143">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d7c1-143">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
