---
title: "IHostSyncManager::CreateSemaphore 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateSemaphore
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7c7e33e4f178a4fd51ae27912959d0e4edf30ecb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a><span data-ttu-id="f6ef0-102">IHostSyncManager::CreateSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="f6ef0-102">IHostSyncManager::CreateSemaphore Method</span></span>
<span data-ttu-id="f6ef0-103">만듭니다는 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 대기 이벤트에 대 한 세마포도 사용할 공용 언어 런타임 (CLR)에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-103">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the common language runtime (CLR) to use as a semaphore for wait events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6ef0-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6ef0-104">Syntax</span></span>  
  
```  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6ef0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f6ef0-105">Parameters</span></span>  
 `dwInitial`  
 <span data-ttu-id="f6ef0-106">[in] 초기 카운트 `ppSemaphore`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-106">[in] The initial count for `ppSemaphore`.</span></span>  
  
 `dwMax`  
 <span data-ttu-id="f6ef0-107">[in] 에 대 한 최대 카운트 `ppSemaphore`합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-107">[in] The maximum count for `ppSemaphore`.</span></span>  
  
 `ppSemaphore`  
 <span data-ttu-id="f6ef0-108">[out] 주소에 대 한 포인터는 `IHostSemaphore` 인스턴스에 지정 하거나 세마포를 만들 수 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-108">[out] A pointer to the address of an `IHostSemaphore` instance, or null if the semaphore could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6ef0-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="f6ef0-109">Return Value</span></span>  
  
|<span data-ttu-id="f6ef0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6ef0-110">HRESULT</span></span>|<span data-ttu-id="f6ef0-111">설명</span><span class="sxs-lookup"><span data-stu-id="f6ef0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f6ef0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f6ef0-112">S_OK</span></span>|<span data-ttu-id="f6ef0-113">`CreateSemaphore`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-113">`CreateSemaphore` returned successfully.</span></span>|  
|<span data-ttu-id="f6ef0-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f6ef0-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f6ef0-115">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f6ef0-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f6ef0-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f6ef0-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-117">The call timed out.</span></span>|  
|<span data-ttu-id="f6ef0-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f6ef0-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f6ef0-119">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f6ef0-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f6ef0-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f6ef0-121">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f6ef0-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f6ef0-122">E_FAIL</span></span>|<span data-ttu-id="f6ef0-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f6ef0-124">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f6ef0-125">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="f6ef0-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f6ef0-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="f6ef0-127">요청 된 이벤트 개체를 만들 메모리가 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f6ef0-128">설명</span><span class="sxs-lookup"><span data-stu-id="f6ef0-128">Remarks</span></span>  
 <span data-ttu-id="f6ef0-129">`CreateSemaphore`이름이 같은 Win32 함수를 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-129">`CreateSemaphore` mirrors the Win32 function that has the same name.</span></span> <span data-ttu-id="f6ef0-130">`dwInitial` 및 `dwMax` 매개 변수는 win32 세마포 개수에 대 한 동일한 의미 체계를 사용 `lInitialCount` 및 `lMaximumCount` 매개 변수를 각각.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-130">The `dwInitial` and `dwMax` parameters use the same semantics for the semaphore count as the Win32 `lInitialCount` and `lMaximumCount` parameters, respectively.</span></span> <span data-ttu-id="f6ef0-131">`dwInitial`0이 하 여야 하 고 `dwMax`(포함).</span><span class="sxs-lookup"><span data-stu-id="f6ef0-131">`dwInitial` must be between zero and `dwMax`, inclusive.</span></span> <span data-ttu-id="f6ef0-132">`dwMax`0 보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-132">`dwMax` must be greater than zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6ef0-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6ef0-133">Requirements</span></span>  
 <span data-ttu-id="f6ef0-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6ef0-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6ef0-135">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f6ef0-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f6ef0-136">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f6ef0-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f6ef0-137">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6ef0-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6ef0-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6ef0-138">See Also</span></span>  
 [<span data-ttu-id="f6ef0-139">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6ef0-139">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="f6ef0-140">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6ef0-140">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="f6ef0-141">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f6ef0-141">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
