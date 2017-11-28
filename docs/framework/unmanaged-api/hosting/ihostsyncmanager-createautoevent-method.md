---
title: "IHostSyncManager::CreateAutoEvent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateAutoEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e6a792ca9075e48a8092d92e1adf870174dd1af6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="f91d4-102">IHostSyncManager::CreateAutoEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="f91d4-102">IHostSyncManager::CreateAutoEvent Method</span></span>
<span data-ttu-id="f91d4-103">자동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-103">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f91d4-104">구문</span><span class="sxs-lookup"><span data-stu-id="f91d4-104">Syntax</span></span>  
  
```  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f91d4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f91d4-105">Parameters</span></span>  
 `ppEvent`  
 <span data-ttu-id="f91d4-106">[out] 주소에 대 한 포인터는 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 인스턴스는 호스트에 의해 구현 되거나 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-106">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f91d4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f91d4-107">Return Value</span></span>  
  
|<span data-ttu-id="f91d4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f91d4-108">HRESULT</span></span>|<span data-ttu-id="f91d4-109">설명</span><span class="sxs-lookup"><span data-stu-id="f91d4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f91d4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="f91d4-110">S_OK</span></span>|<span data-ttu-id="f91d4-111">`CreateAutoEvent`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-111">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="f91d4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f91d4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f91d4-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f91d4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f91d4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f91d4-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-115">The call timed out.</span></span>|  
|<span data-ttu-id="f91d4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f91d4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f91d4-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f91d4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f91d4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f91d4-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f91d4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f91d4-120">E_FAIL</span></span>|<span data-ttu-id="f91d4-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f91d4-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f91d4-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f91d4-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f91d4-124">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f91d4-125">요청 된 이벤트 개체를 만들 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-125">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f91d4-126">설명</span><span class="sxs-lookup"><span data-stu-id="f91d4-126">Remarks</span></span>  
 <span data-ttu-id="f91d4-127">`CreateAutoEvent`상태가 자동으로 변경 됩니다 신호 대기 스레드가 해제 된 후 자동 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-127">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="f91d4-128">이 메서드는 Win32 미러링 `CreateEvent` 의 값으로 함수 `false` 에 대해 지정 된 된 `bManualReset` 매개 변수</span><span class="sxs-lookup"><span data-stu-id="f91d4-128">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f91d4-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f91d4-129">Requirements</span></span>  
 <span data-ttu-id="f91d4-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f91d4-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f91d4-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f91d4-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f91d4-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f91d4-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f91d4-133">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f91d4-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f91d4-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f91d4-134">See Also</span></span>  
 [<span data-ttu-id="f91d4-135">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f91d4-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="f91d4-136">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f91d4-136">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="f91d4-137">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f91d4-137">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)  
 [<span data-ttu-id="f91d4-138">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f91d4-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
