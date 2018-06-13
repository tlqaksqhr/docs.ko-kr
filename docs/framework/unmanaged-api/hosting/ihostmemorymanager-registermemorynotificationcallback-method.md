---
title: IHostMemoryManager::RegisterMemoryNotificationCallback 메서드
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d68790cdb671efdd0761ceef59196e8646654d5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439608"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a><span data-ttu-id="38585-102">IHostMemoryManager::RegisterMemoryNotificationCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="38585-102">IHostMemoryManager::RegisterMemoryNotificationCallback Method</span></span>
<span data-ttu-id="38585-103">호스트에 공용 언어 런타임 (CLR)를 알리기 위해 호출 하는 콜백 함수에 대 한 포인터는 컴퓨터의 현재 메모리 로드를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="38585-103">Registers a pointer to a callback function that the host invokes to notify the common language runtime (CLR) of the current memory load on the computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38585-104">구문</span><span class="sxs-lookup"><span data-stu-id="38585-104">Syntax</span></span>  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38585-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38585-105">Parameters</span></span>  
 `pCallback`  
 <span data-ttu-id="38585-106">[in] 에 대 한 인터페이스 포인터는 [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) CLR에서 구현 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="38585-106">[in] An interface pointer to an [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instance that is implemented by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38585-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="38585-107">Return Value</span></span>  
  
|<span data-ttu-id="38585-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38585-108">HRESULT</span></span>|<span data-ttu-id="38585-109">설명</span><span class="sxs-lookup"><span data-stu-id="38585-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38585-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="38585-110">S_OK</span></span>|<span data-ttu-id="38585-111">`RegisterMemoryNotificationCallback` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38585-111">`RegisterMemoryNotificationCallback` returned successfully.</span></span>|  
|<span data-ttu-id="38585-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="38585-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="38585-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38585-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="38585-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="38585-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="38585-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="38585-115">The call timed out.</span></span>|  
|<span data-ttu-id="38585-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="38585-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="38585-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38585-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="38585-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="38585-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="38585-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="38585-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="38585-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="38585-120">E_FAIL</span></span>|<span data-ttu-id="38585-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="38585-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="38585-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38585-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="38585-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38585-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38585-124">설명</span><span class="sxs-lookup"><span data-stu-id="38585-124">Remarks</span></span>  
 <span data-ttu-id="38585-125">때문에 `ICLRMemoryNotificationCallback` 인터페이스 메서드를 하나만 정의 ([iclrmemorynotificationcallback:: Onmemorynotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), 않기 때문에 `pCallback` 에 대 한 포인터는 `ICLRMemoryNotificationCallback` CLR에서 제공 하는 인스턴스는 등록은 콜백 함수 자체에 대 한 효과적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="38585-125">Because the `ICLRMemoryNotificationCallback` interface defines only one method ([ICLRMemoryNotificationCallback::OnMemoryNotification](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)), and because `pCallback` is a pointer to an `ICLRMemoryNotificationCallback` instance provided by the CLR, the registration is effectively for the callback function itself.</span></span> <span data-ttu-id="38585-126">호스트에서 호출 `OnMemoryNotification` 표준 Win32 대신 보고서 메모리가 중 상태가 `CreateMemoryResourceNotification` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="38585-126">The host invokes `OnMemoryNotification` to report memory pressure conditions, rather than using the standard Win32 `CreateMemoryResourceNotification` function.</span></span> <span data-ttu-id="38585-127">자세한 내용은 Windows 플랫폼 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="38585-127">For more information, see the Windows Platform documentation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38585-128">에 대 한 호출이 `OnMemoryNotification` 를 차단 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="38585-128">Calls to `OnMemoryNotification` never block.</span></span> <span data-ttu-id="38585-129">항상 즉시 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38585-129">They always return immediately.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38585-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38585-130">Requirements</span></span>  
 <span data-ttu-id="38585-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38585-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38585-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="38585-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38585-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="38585-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38585-134">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38585-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38585-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38585-135">See Also</span></span>  
 [<span data-ttu-id="38585-136">ICLRMemoryNotificationCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38585-136">ICLRMemoryNotificationCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [<span data-ttu-id="38585-137">IHostMemoryManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38585-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
