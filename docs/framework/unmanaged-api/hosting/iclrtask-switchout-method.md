---
title: "ICLRTask::SwitchOut 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.SwitchOut
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::SwitchOut
helpviewer_keywords:
- ICLRTask::SwitchOut method [.NET Framework hosting]
- SwitchOut method [.NET Framework hosting]
ms.assetid: b6fb168c-b24b-4ecf-a390-2b5ba3317ae6
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8fc8fcc5550981b2b8f4a51877d9e6571954f48b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskswitchout-method"></a><span data-ttu-id="0485d-102">ICLRTask::SwitchOut 메서드</span><span class="sxs-lookup"><span data-stu-id="0485d-102">ICLRTask::SwitchOut Method</span></span>
<span data-ttu-id="0485d-103">현재 나타내는 작업이 공용 언어 런타임 (CLR)에 게 알리는 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스는 더 이상 가능한 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-103">Notifies the common language runtime (CLR) that the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance is no longer in an operable state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0485d-104">구문</span><span class="sxs-lookup"><span data-stu-id="0485d-104">Syntax</span></span>  
  
```  
HRESULT SwitchOut ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0485d-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="0485d-105">Return Value</span></span>  
  
|<span data-ttu-id="0485d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0485d-106">HRESULT</span></span>|<span data-ttu-id="0485d-107">설명</span><span class="sxs-lookup"><span data-stu-id="0485d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0485d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0485d-108">S_OK</span></span>|<span data-ttu-id="0485d-109">`SwitchOut`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-109">`SwitchOut` returned successfully.</span></span>|  
|<span data-ttu-id="0485d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0485d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0485d-111">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0485d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0485d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0485d-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-113">The call timed out.</span></span>|  
|<span data-ttu-id="0485d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0485d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0485d-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0485d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0485d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0485d-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0485d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0485d-118">E_FAIL</span></span>|<span data-ttu-id="0485d-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0485d-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0485d-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0485d-122">설명</span><span class="sxs-lookup"><span data-stu-id="0485d-122">Remarks</span></span>  
 <span data-ttu-id="0485d-123">호출 하는 호스트 `SwitchOut` 를 일시적으로 중지 된 작업을 실행 CLR에 알릴 수는 현재 `ICLRTask` 인스턴스가 나타내는 않으며 작업 일정이 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-123">A host calls `SwitchOut` to inform the CLR that it has temporarily stopped executing the task that the current `ICLRTask` instance represents, and will reschedule the task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0485d-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0485d-124">Requirements</span></span>  
 <span data-ttu-id="0485d-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0485d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0485d-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0485d-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0485d-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0485d-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0485d-128">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0485d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0485d-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0485d-129">See Also</span></span>  
 [<span data-ttu-id="0485d-130">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0485d-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="0485d-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0485d-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="0485d-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0485d-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="0485d-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0485d-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
