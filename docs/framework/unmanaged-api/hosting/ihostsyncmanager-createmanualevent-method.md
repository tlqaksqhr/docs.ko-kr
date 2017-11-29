---
title: "IHostSyncManager::CreateManualEvent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7b43a6b26c3788708419d3598e95bba1273dcb9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="558e2-102">IHostSyncManager::CreateManualEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="558e2-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="558e2-103">수동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="558e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="558e2-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="558e2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="558e2-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="558e2-106">[in] `true`, 개체가 고, 그렇지 않으면 신호를 받은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="558e2-107">[out] 주소에 대 한 포인터는 [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) 인스턴스에 지정 하거나 이벤트를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="558e2-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="558e2-108">Return Value</span></span>  
  
|<span data-ttu-id="558e2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="558e2-109">HRESULT</span></span>|<span data-ttu-id="558e2-110">설명</span><span class="sxs-lookup"><span data-stu-id="558e2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="558e2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="558e2-111">S_OK</span></span>|<span data-ttu-id="558e2-112">`CreateManualEvent`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="558e2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="558e2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="558e2-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="558e2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="558e2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="558e2-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-116">The call timed out.</span></span>|  
|<span data-ttu-id="558e2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="558e2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="558e2-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="558e2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="558e2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="558e2-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="558e2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="558e2-121">E_FAIL</span></span>|<span data-ttu-id="558e2-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="558e2-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="558e2-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="558e2-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="558e2-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="558e2-126">요청 된 이벤트 개체를 만들 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="558e2-127">설명</span><span class="sxs-lookup"><span data-stu-id="558e2-127">Remarks</span></span>  
 <span data-ttu-id="558e2-128">`CreateManualEvent`만듭니다는 `IHostManualEvent`를 호출 해야 하는 수동 다시 설정 이벤트 개체는 [ihostmanualevent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) 신호 되지 않은 상태로 설정 하는 방법은 합니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="558e2-129">`CreateManualEvent`Win32 미러링 `CreateEvent` 의 값으로 함수 `true` 에 대해 지정 된는 `bManualReset` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="558e2-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="558e2-130">Requirements</span></span>  
 <span data-ttu-id="558e2-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="558e2-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="558e2-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="558e2-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="558e2-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="558e2-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="558e2-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="558e2-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="558e2-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="558e2-135">See Also</span></span>  
 [<span data-ttu-id="558e2-136">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="558e2-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="558e2-137">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="558e2-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="558e2-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="558e2-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
