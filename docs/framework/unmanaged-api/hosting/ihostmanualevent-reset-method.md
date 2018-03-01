---
title: "IHostManualEvent::Reset 메서드"
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
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d1bbd10437662fc8b7fbb52d65d196d7a519538b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="5772d-102">IHostManualEvent::Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="5772d-102">IHostManualEvent::Reset Method</span></span>
<span data-ttu-id="5772d-103">현재 다시 설정 [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) 인스턴스 신호 되지 않은 상태로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-103">Resets the current [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5772d-104">구문</span><span class="sxs-lookup"><span data-stu-id="5772d-104">Syntax</span></span>  
  
```  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5772d-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="5772d-105">Return Value</span></span>  
  
|<span data-ttu-id="5772d-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5772d-106">HRESULT</span></span>|<span data-ttu-id="5772d-107">설명</span><span class="sxs-lookup"><span data-stu-id="5772d-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5772d-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="5772d-108">S_OK</span></span>|<span data-ttu-id="5772d-109">`Reset`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-109">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="5772d-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5772d-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5772d-111">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5772d-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5772d-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5772d-113">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-113">The call timed out.</span></span>|  
|<span data-ttu-id="5772d-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5772d-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5772d-115">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5772d-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5772d-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5772d-117">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5772d-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5772d-118">E_FAIL</span></span>|<span data-ttu-id="5772d-119">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5772d-120">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5772d-121">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5772d-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5772d-122">Requirements</span></span>  
 <span data-ttu-id="5772d-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5772d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5772d-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5772d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5772d-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5772d-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5772d-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5772d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5772d-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5772d-127">See Also</span></span>  
 [<span data-ttu-id="5772d-128">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5772d-128">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="5772d-129">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5772d-129">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="5772d-130">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5772d-130">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="5772d-131">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5772d-131">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="5772d-132">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5772d-132">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
