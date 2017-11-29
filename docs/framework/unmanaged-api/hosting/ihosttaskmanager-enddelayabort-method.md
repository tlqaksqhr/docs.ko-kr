---
title: "IHostTaskManager::EndDelayAbort 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.EndDelayAbort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::EndDelayAbort
helpviewer_keywords:
- EndDelayAbort method [.NET Framework hosting]
- IHostTaskManager::EndDelayAbort method [.NET Framework hosting]
ms.assetid: 6e02facb-2504-4356-9af5-0cee1f8436a7
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45148c506e2f6073dc175abe4397fad2172b355e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttaskmanagerenddelayabort-method"></a><span data-ttu-id="9397c-102">IHostTaskManager::EndDelayAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="9397c-102">IHostTaskManager::EndDelayAbort Method</span></span>
<span data-ttu-id="9397c-103">관리 코드는 호스트를 종료 하 고 없는 현재 작업을 중단 하지 말아야, 기간을 호출한 후에 알립니다. [ihosttaskmanager:: Begindelayabort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-103">Notifies the host that managed code is exiting the period in which the current task must not be aborted, following an earlier call to [IHostTaskManager::BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9397c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9397c-104">Syntax</span></span>  
  
```  
HRESULT EndDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="9397c-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="9397c-105">Return Value</span></span>  
  
|<span data-ttu-id="9397c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9397c-106">HRESULT</span></span>|<span data-ttu-id="9397c-107">설명</span><span class="sxs-lookup"><span data-stu-id="9397c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9397c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="9397c-108">S_OK</span></span>|<span data-ttu-id="9397c-109">`EndDelayAbort`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-109">`EndDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="9397c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9397c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9397c-111">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9397c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9397c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9397c-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-113">The call timed out.</span></span>|  
|<span data-ttu-id="9397c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9397c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9397c-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9397c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9397c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9397c-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9397c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9397c-118">E_FAIL</span></span>|<span data-ttu-id="9397c-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9397c-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9397c-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9397c-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="9397c-122">E_UNEXPECTED</span></span>|<span data-ttu-id="9397c-123">`EndDelayAbort`해당 호출 하지 않고 호출 된 `BeginDelayAbort`합니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-123">`EndDelayAbort` was called without a corresponding call to `BeginDelayAbort`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9397c-124">설명</span><span class="sxs-lookup"><span data-stu-id="9397c-124">Remarks</span></span>  
 <span data-ttu-id="9397c-125">CLR은 해당 호출 `BeginDelayAbort` 호출 하기 전에 현재 작업에서 `EndDelayAbort`합니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-125">The CLR makes a corresponding call to `BeginDelayAbort` on the current task before calling `EndDelayAbort`.</span></span> <span data-ttu-id="9397c-126">이러한 해당 호출 없는 경우에서 호스트의 구현을 [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) 에서 E_UNEXPECTED를 반환 해야 `EndDelayAbort`, 아무 작업도 수행 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-126">In the absence of such a corresponding call, the host's implementation of [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md) should return E_UNEXPECTED from `EndDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9397c-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9397c-127">Requirements</span></span>  
 <span data-ttu-id="9397c-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9397c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9397c-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9397c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9397c-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9397c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9397c-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9397c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9397c-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9397c-132">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="9397c-133">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9397c-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="9397c-134">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9397c-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="9397c-135">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9397c-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="9397c-136">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9397c-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
