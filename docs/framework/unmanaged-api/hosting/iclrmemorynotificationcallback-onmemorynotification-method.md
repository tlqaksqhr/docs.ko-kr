---
title: "ICLRMemoryNotificationCallback::OnMemoryNotification 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMemoryNotificationCallback.OnMemoryNotification
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 651dcd6380702a392d2dd06cf899ea567b004ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a><span data-ttu-id="9081e-102">ICLRMemoryNotificationCallback::OnMemoryNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="9081e-102">ICLRMemoryNotificationCallback::OnMemoryNotification Method</span></span>
<span data-ttu-id="9081e-103">공용 언어 런타임을 (CLR)의 컴퓨터에 메모리 사용량에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-103">Notifies the common language runtime (CLR) of the memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9081e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9081e-104">Syntax</span></span>  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9081e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9081e-105">Parameters</span></span>  
 `eMemoryAvailable`  
 <span data-ttu-id="9081e-106">[in] 중 하나는 [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) 값을 컴퓨터의 메모리 부족을 나타내는 현재 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-106">[in] One of the [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) values, indicating the memory pressure the computer is currently experiencing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9081e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9081e-107">Return Value</span></span>  
  
|<span data-ttu-id="9081e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9081e-108">HRESULT</span></span>|<span data-ttu-id="9081e-109">설명</span><span class="sxs-lookup"><span data-stu-id="9081e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9081e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9081e-110">S_OK</span></span>|<span data-ttu-id="9081e-111">`OnMemoryNotification`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-111">`OnMemoryNotification` returned successfully.</span></span>|  
|<span data-ttu-id="9081e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9081e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9081e-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9081e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9081e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9081e-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-115">The call timed out.</span></span>|  
|<span data-ttu-id="9081e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9081e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9081e-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9081e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9081e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9081e-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9081e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9081e-120">E_FAIL</span></span>|<span data-ttu-id="9081e-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9081e-122">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9081e-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9081e-124">설명</span><span class="sxs-lookup"><span data-stu-id="9081e-124">Remarks</span></span>  
 <span data-ttu-id="9081e-125">CLR에 대 한 콜백을 등록 `OnMemoryNotification` 에 대 한 호출을 사용 하 여는 [ihostmemorymanager:: Registermemorynotificationcallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="9081e-125">The CLR registers a callback to `OnMemoryNotification` by using a call to the [IHostMemoryManager::RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) method.</span></span> <span data-ttu-id="9081e-126">런타임에서 콜백에서 반환 되는 정보를 사용 하 여 메모리를 확보 추가 호스트 메모리 리소스가 부족 하다 고 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-126">The runtime uses the information returned in the callback to free additional memory when the host reports that memory resources are running low.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9081e-127">에 대 한 호출이 `OnMemoryNotification` 를 차단 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-127">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="9081e-128">항상 즉시 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-128">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9081e-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9081e-129">Requirements</span></span>  
 <span data-ttu-id="9081e-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9081e-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9081e-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9081e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9081e-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9081e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9081e-133">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9081e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9081e-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9081e-134">See Also</span></span>  
 [<span data-ttu-id="9081e-135">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9081e-135">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [<span data-ttu-id="9081e-136">RegisterMemoryNotificationCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="9081e-136">RegisterMemoryNotificationCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)  
 [<span data-ttu-id="9081e-137">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9081e-137">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
