---
title: "ICLRTaskManager::SetUILocale 메서드"
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
- ICLRTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::SetUILocale
helpviewer_keywords:
- ICLRTaskManager::SetUILocale method [.NET Framework hosting]
- SetUILocale method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 03adaa9a-2beb-49b3-b2c4-6b4fc3f10715
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fab9da8f7e63ad000595378f5bc36f3aadc2ac3d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtaskmanagersetuilocale-method"></a><span data-ttu-id="cd465-102">ICLRTaskManager::SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="cd465-102">ICLRTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="cd465-103">현재 실행 중인 작업에서 공용 언어 런타임을 (CLR) 사용자 인터페이스 (UI) 로캘 또는 culture 호스트가 수정 했음을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-103">Notifies the common language runtime (CLR) that the host has modified the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd465-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd465-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd465-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd465-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="cd465-106">[in] 새로 할당 된 지역 culture와 사용자 인터페이스에 대 한 언어에 매핑되는 로캘 식별자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language for the user interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd465-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="cd465-107">Return Value</span></span>  
  
|<span data-ttu-id="cd465-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cd465-108">HRESULT</span></span>|<span data-ttu-id="cd465-109">설명</span><span class="sxs-lookup"><span data-stu-id="cd465-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cd465-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cd465-110">S_OK</span></span>|<span data-ttu-id="cd465-111">`SetUILocale`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="cd465-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cd465-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cd465-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cd465-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cd465-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cd465-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-115">The call timed out.</span></span>|  
|<span data-ttu-id="cd465-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cd465-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cd465-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cd465-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cd465-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cd465-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cd465-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cd465-120">E_FAIL</span></span>|<span data-ttu-id="cd465-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cd465-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cd465-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd465-124">설명</span><span class="sxs-lookup"><span data-stu-id="cd465-124">Remarks</span></span>  
 <span data-ttu-id="cd465-125">`SetUILocale`로캘 동기화에 대 한이 포함 되어 메커니즘을 실행할 호스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-125">`SetUILocale` provides an opportunity for the host to execute any mechanisms it might have for the synchronization of locales.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd465-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd465-126">Requirements</span></span>  
 <span data-ttu-id="cd465-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd465-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd465-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cd465-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd465-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cd465-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd465-130">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd465-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd465-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd465-131">See Also</span></span>  
 [<span data-ttu-id="cd465-132">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd465-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="cd465-133">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd465-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="cd465-134">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd465-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="cd465-135">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd465-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
