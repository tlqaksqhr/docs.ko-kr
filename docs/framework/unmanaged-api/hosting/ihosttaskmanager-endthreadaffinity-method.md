---
title: "IHostTaskManager::EndThreadAffinity 메서드"
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
- IHostTaskManager.EndThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::EndThreadAffinity
helpviewer_keywords:
- EndThreadAffinity method [.NET Framework hosting]
- IHostTaskManager::EndThreadAffinity method [.NET Framework hosting]
ms.assetid: 7738a904-0cd7-4fde-a3eb-2323a5533157
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b12bdc16d70b9e4ccaecbee1b8bcd4e8f05d59dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagerendthreadaffinity-method"></a><span data-ttu-id="9fe9a-102">IHostTaskManager::EndThreadAffinity 메서드</span><span class="sxs-lookup"><span data-stu-id="9fe9a-102">IHostTaskManager::EndThreadAffinity Method</span></span>
<span data-ttu-id="9fe9a-103">관리 코드는 호스트를 종료 하 고 없는 현재 작업 이동 하지 말아야 다른 운영 체제 스레드에 기간을 호출한 후에 알립니다. [ihosttaskmanager:: Beginthreadaffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-103">Notifies the host that managed code is exiting the period in which the current task must not be moved to another operating system thread, following an earlier call to [IHostTaskManager::BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe9a-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fe9a-104">Syntax</span></span>  
  
```  
HRESULT EndThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9fe9a-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="9fe9a-105">Return Value</span></span>  
  
|<span data-ttu-id="9fe9a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9fe9a-106">HRESULT</span></span>|<span data-ttu-id="9fe9a-107">설명</span><span class="sxs-lookup"><span data-stu-id="9fe9a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9fe9a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9fe9a-108">S_OK</span></span>|<span data-ttu-id="9fe9a-109">`EndThreadAffinity`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-109">`EndThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="9fe9a-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9fe9a-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9fe9a-111">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9fe9a-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9fe9a-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9fe9a-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-113">The call timed out.</span></span>|  
|<span data-ttu-id="9fe9a-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9fe9a-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9fe9a-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9fe9a-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9fe9a-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9fe9a-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9fe9a-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9fe9a-118">E_FAIL</span></span>|<span data-ttu-id="9fe9a-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9fe9a-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9fe9a-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9fe9a-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="9fe9a-122">E_UNEXPECTED</span></span>|<span data-ttu-id="9fe9a-123">`EndThreadAffinity`이전 해당 호출을 하지 않고 호출 된 `BeginThreadAffinity`합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-123">`EndThreadAffinity` was called without an earlier corresponding call to `BeginThreadAffinity`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fe9a-124">설명</span><span class="sxs-lookup"><span data-stu-id="9fe9a-124">Remarks</span></span>  
 <span data-ttu-id="9fe9a-125">CLR은 해당 호출 `BeginThreadAffinity` 호출 하기 전에 현재 작업에서 `EndThreadAffinity`합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-125">The CLR makes a corresponding call to `BeginThreadAffinity` on the current task before calling `EndThreadAffinity`.</span></span> <span data-ttu-id="9fe9a-126">이러한 해당 호출 없는 경우에서 호스트의 구현을 [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) E_UNEXPECTED를 반환 하 고는 아무런 작업도 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED, and take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fe9a-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fe9a-127">Requirements</span></span>  
 <span data-ttu-id="9fe9a-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9fe9a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe9a-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9fe9a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9fe9a-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9fe9a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9fe9a-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe9a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe9a-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fe9a-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="9fe9a-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fe9a-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9fe9a-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fe9a-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9fe9a-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fe9a-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9fe9a-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9fe9a-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
