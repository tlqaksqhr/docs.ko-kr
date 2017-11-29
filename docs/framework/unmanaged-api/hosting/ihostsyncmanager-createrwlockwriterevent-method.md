---
title: "IHostSyncManager::CreateRWLockWriterEvent 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateRWLockWriterEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c89dec681102f96f96f1d7f3e802ded0a2df7b4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="1c971-102">IHostSyncManager::CreateRWLockWriterEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="1c971-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="1c971-103">작성기 잠금 구현에 대 한 자동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c971-104">구문</span><span class="sxs-lookup"><span data-stu-id="1c971-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c971-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c971-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="1c971-106">[in] 자동 재설정 이벤트와 연결 하는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="1c971-107">[out] 주소에 대 한 포인터는 [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) 인스턴스에 지정 하거나 이벤트 개체를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c971-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="1c971-108">Return Value</span></span>  
  
|<span data-ttu-id="1c971-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1c971-109">HRESULT</span></span>|<span data-ttu-id="1c971-110">설명</span><span class="sxs-lookup"><span data-stu-id="1c971-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1c971-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1c971-111">S_OK</span></span>|<span data-ttu-id="1c971-112">`CreateRWLockWriterEvent`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="1c971-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1c971-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1c971-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1c971-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1c971-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1c971-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-116">The call timed out.</span></span>|  
|<span data-ttu-id="1c971-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1c971-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1c971-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1c971-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1c971-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1c971-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1c971-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1c971-121">E_FAIL</span></span>|<span data-ttu-id="1c971-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1c971-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1c971-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1c971-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1c971-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1c971-126">요청 된 이벤트 개체를 만들 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1c971-127">설명</span><span class="sxs-lookup"><span data-stu-id="1c971-127">Remarks</span></span>  
 <span data-ttu-id="1c971-128">CLR에서는 `CreateRWLockWriterEvent` 에 대 한 참조를 가져올 메서드를 프로그램 `IHostAutoEvent` 작성기 잠금 구현에 사용할 인스턴스를 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="1c971-129">호스트의 반복 메서드를 호출 하 여 잠금을 기다리는 작업을 확인 하려면 지정된 된 쿠키를 사용할 수는 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c971-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c971-130">Requirements</span></span>  
 <span data-ttu-id="1c971-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1c971-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c971-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1c971-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c971-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1c971-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c971-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c971-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c971-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c971-135">See Also</span></span>  
 [<span data-ttu-id="1c971-136">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c971-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="1c971-137">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c971-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="1c971-138">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c971-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="1c971-139">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c971-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
