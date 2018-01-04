---
title: "IHostTask::Join 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.Join
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 85ee44fe9185364a6870b996ca98cfe6cc297bf7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskjoin-method"></a><span data-ttu-id="3f456-102">IHostTask::Join 메서드</span><span class="sxs-lookup"><span data-stu-id="3f456-102">IHostTask::Join Method</span></span>
<span data-ttu-id="3f456-103">현재 작업까지 호출 작업을 차단 [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) 인스턴스 완료 되 면 지정 된 시간 간격이 지나면 또는 [ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-103">Blocks the calling task until the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f456-104">구문</span><span class="sxs-lookup"><span data-stu-id="3f456-104">Syntax</span></span>  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3f456-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3f456-105">Parameters</span></span>  
 `milliseconds`  
 <span data-ttu-id="3f456-106">[in] 작업이 종료 될 때까지 기다릴 밀리초의 시간 간격입니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-106">[in] The time interval, in milliseconds, to wait for the task to terminate.</span></span> <span data-ttu-id="3f456-107">이 간격이 경과할 때까지 작업을 종료 하는 경우에 호출 작업이 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-107">If this interval elapses before the task terminates, the calling task unblocks.</span></span>  
  
 `option`  
 <span data-ttu-id="3f456-108">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-108">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values.</span></span> <span data-ttu-id="3f456-109">Wait_alertable 값 호스트 하는 경우 작업에 지시 `Alert` 하기 전에 호출 `milliseconds` 경과 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-109">A value of WAIT_ALERTABLE instructs the host to wake the task if `Alert` is called before `milliseconds` elapses.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f456-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="3f456-110">Return Value</span></span>  
  
|<span data-ttu-id="3f456-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3f456-111">HRESULT</span></span>|<span data-ttu-id="3f456-112">설명</span><span class="sxs-lookup"><span data-stu-id="3f456-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3f456-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3f456-113">S_OK</span></span>|<span data-ttu-id="3f456-114">`Join`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-114">`Join` returned successfully.</span></span>|  
|<span data-ttu-id="3f456-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3f456-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3f456-116">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3f456-117">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3f456-117">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3f456-118">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-118">The call timed out.</span></span>|  
|<span data-ttu-id="3f456-119">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3f456-119">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3f456-120">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-120">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3f456-121">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3f456-121">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3f456-122">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던, 또는 현재 `IHostTask` 인스턴스 작업에 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-122">An event was canceled while a blocked thread or fiber was waiting on it, or the current `IHostTask` instance is not associated with a task.</span></span>|  
|<span data-ttu-id="3f456-123">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3f456-123">E_FAIL</span></span>|<span data-ttu-id="3f456-124">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-124">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3f456-125">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-125">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3f456-126">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-126">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3f456-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3f456-127">Requirements</span></span>  
 <span data-ttu-id="3f456-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f456-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f456-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3f456-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3f456-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3f456-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f456-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f456-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f456-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f456-132">See Also</span></span>  
 [<span data-ttu-id="3f456-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f456-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3f456-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f456-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3f456-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f456-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="3f456-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3f456-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="3f456-137">WAIT_OPTION 열거형</span><span class="sxs-lookup"><span data-stu-id="3f456-137">WAIT_OPTION Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
