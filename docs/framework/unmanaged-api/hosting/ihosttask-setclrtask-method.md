---
title: IHostTask::SetCLRTask 메서드
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2149293989136e0b006f044c925353efbfd94031
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442802"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="7e9c6-102">IHostTask::SetCLRTask 메서드</span><span class="sxs-lookup"><span data-stu-id="7e9c6-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="7e9c6-103">연결 된 `ICLRTask` 인스턴스를 현재 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e9c6-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e9c6-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e9c6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e9c6-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="7e9c6-106">[in] 에 대 한 인터페이스 포인터의 `ICLRTask` 현재와 연결할 인스턴스 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e9c6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="7e9c6-107">Return Value</span></span>  
  
|<span data-ttu-id="7e9c6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e9c6-108">HRESULT</span></span>|<span data-ttu-id="7e9c6-109">설명</span><span class="sxs-lookup"><span data-stu-id="7e9c6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e9c6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e9c6-110">S_OK</span></span>|<span data-ttu-id="7e9c6-111">`SetCLRTask` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="7e9c6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e9c6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e9c6-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e9c6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e9c6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e9c6-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-115">The call timed out.</span></span>|  
|<span data-ttu-id="7e9c6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e9c6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e9c6-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e9c6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e9c6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e9c6-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e9c6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e9c6-120">E_FAIL</span></span>|<span data-ttu-id="7e9c6-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e9c6-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e9c6-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e9c6-124">설명</span><span class="sxs-lookup"><span data-stu-id="7e9c6-124">Remarks</span></span>  
 <span data-ttu-id="7e9c6-125">CLR에서는 `SetCLRTask` 연결 하는 `ICLRTask` 인스턴스를 현재 `IHostTask` 를 호출 하 여 생성 된 인스턴스 [ihosttaskmanager:: Createtask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e9c6-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e9c6-126">Requirements</span></span>  
 <span data-ttu-id="7e9c6-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9c6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e9c6-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e9c6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e9c6-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7e9c6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e9c6-130">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e9c6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9c6-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e9c6-131">See Also</span></span>  
 [<span data-ttu-id="7e9c6-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e9c6-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="7e9c6-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e9c6-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="7e9c6-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e9c6-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="7e9c6-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e9c6-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
