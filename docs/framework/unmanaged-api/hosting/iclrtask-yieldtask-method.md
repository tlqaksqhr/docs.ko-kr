---
title: "ICLRTask::YieldTask 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask.YieldTask
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask::YieldTask
helpviewer_keywords:
- ICLRTask::YieldTask method [.NET Framework hosting]
- YieldTask method [.NET Framework hosting]
ms.assetid: b8eb4095-3a8f-4be3-9446-63e9893dce7d
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6a02a69329958593aec546ca9c60e3d201ce2a92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskyieldtask-method"></a><span data-ttu-id="c2e74-102">ICLRTask::YieldTask 메서드</span><span class="sxs-lookup"><span data-stu-id="c2e74-102">ICLRTask::YieldTask Method</span></span>
<span data-ttu-id="c2e74-103">요청 합니다 공용 언어 런타임 (CLR)에서 작업 하는 현재 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스가 나타내는 및 프로세서 시간을 다른 작업을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-103">Requests that the common language runtime (CLR) put aside the task that the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance represents, and make the processor time available to other tasks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e74-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2e74-104">Syntax</span></span>  
  
```  
HRESULT YieldTask ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="c2e74-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="c2e74-105">Return Value</span></span>  
  
|<span data-ttu-id="c2e74-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2e74-106">HRESULT</span></span>|<span data-ttu-id="c2e74-107">설명</span><span class="sxs-lookup"><span data-stu-id="c2e74-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2e74-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2e74-108">S_OK</span></span>|<span data-ttu-id="c2e74-109">`YieldTask`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-109">`YieldTask` returned successfully.</span></span>|  
|<span data-ttu-id="c2e74-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c2e74-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c2e74-111">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c2e74-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c2e74-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c2e74-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-113">The call timed out.</span></span>|  
|<span data-ttu-id="c2e74-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c2e74-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c2e74-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c2e74-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c2e74-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c2e74-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c2e74-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c2e74-118">E_FAIL</span></span>|<span data-ttu-id="c2e74-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c2e74-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c2e74-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2e74-122">설명</span><span class="sxs-lookup"><span data-stu-id="c2e74-122">Remarks</span></span>  
 <span data-ttu-id="c2e74-123">호출 하는 호스트 `YieldTask` 에 다른 작업이 나 프로세스에 대 한 프로세서 리소스를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-123">A host calls `YieldTask` to request processor resources for other tasks or processes.</span></span> <span data-ttu-id="c2e74-124">이 메서드는 주로 장기 실행 코드의 CPU 시간을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-124">This method is primarily intended to allow long-running code to give up CPU time.</span></span> <span data-ttu-id="c2e74-125">런타임에서 작업 하려고 하는 현재 `ICLRTask` 처리 시간을 얻을 수 있지만 성공 되지 않을 수도 있는 상태의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-125">The runtime attempts to put the task that the current `ICLRTask` instance represents in a state where it can yield processing time, but makes no guarantee of success.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2e74-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2e74-126">Requirements</span></span>  
 <span data-ttu-id="c2e74-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c2e74-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2e74-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c2e74-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c2e74-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c2e74-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2e74-130">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2e74-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e74-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2e74-131">See Also</span></span>  
 [<span data-ttu-id="c2e74-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2e74-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="c2e74-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2e74-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="c2e74-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2e74-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="c2e74-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2e74-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
