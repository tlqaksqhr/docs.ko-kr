---
title: "ICLRGCManager::SetGCStartupLimits 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.SetGCStartupLimits
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4fd5a1135866b75ea1d11fc5a14289104edfeac4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a><span data-ttu-id="304aa-102">ICLRGCManager::SetGCStartupLimits 메서드</span><span class="sxs-lookup"><span data-stu-id="304aa-102">ICLRGCManager::SetGCStartupLimits Method</span></span>
<span data-ttu-id="304aa-103">가비지 수집 세그먼트의 크기와 0 세대 가비지 수집 시스템의 최대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="304aa-104">부터는 [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)]세그먼트 크기를 설정할 수 있습니다 및 0 세대의 최대 크기를 보다 큰 값, `DWORD` 를 사용 하 여는 [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="304aa-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can set segment size and maximum generation 0 size to values greater than `DWORD` by using the [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="304aa-105">구문</span><span class="sxs-lookup"><span data-stu-id="304aa-105">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="304aa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="304aa-106">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="304aa-107">[in] 가비지 수집 세그먼트의 지정 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-107">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="304aa-108">최소 세그먼트 크기는 4MB입니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-108">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="304aa-109">1mb 단위로 증가 또는 더 큰 세그먼트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-109">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="304aa-110">[in] 0 세대에 대 한 지정 된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-110">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="304aa-111">0 세대의 최소 크기는 64KB입니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-111">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="304aa-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="304aa-112">Return Value</span></span>  
  
|<span data-ttu-id="304aa-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="304aa-113">HRESULT</span></span>|<span data-ttu-id="304aa-114">설명</span><span class="sxs-lookup"><span data-stu-id="304aa-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="304aa-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="304aa-115">S_OK</span></span>|<span data-ttu-id="304aa-116">`SetGCStartupLimits`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-116">`SetGCStartupLimits` returned successfully.</span></span>|  
|<span data-ttu-id="304aa-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="304aa-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="304aa-118">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="304aa-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="304aa-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="304aa-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-120">The call timed out.</span></span>|  
|<span data-ttu-id="304aa-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="304aa-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="304aa-122">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="304aa-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="304aa-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="304aa-124">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="304aa-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="304aa-125">E_FAIL</span></span>|<span data-ttu-id="304aa-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="304aa-127">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="304aa-128">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="304aa-129">설명</span><span class="sxs-lookup"><span data-stu-id="304aa-129">Remarks</span></span>  
 <span data-ttu-id="304aa-130">값은 `SetGCStartupLimits` 집합을 한 번만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-130">The values that `SetGCStartupLimits` sets can be specified only once.</span></span> <span data-ttu-id="304aa-131">나중에 대 한 호출이 `SetGCStartupLimits` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-131">Later calls to `SetGCStartupLimits` are ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="304aa-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="304aa-132">Requirements</span></span>  
 <span data-ttu-id="304aa-133">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="304aa-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="304aa-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="304aa-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="304aa-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="304aa-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="304aa-136">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="304aa-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="304aa-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="304aa-137">See Also</span></span>  
 [<span data-ttu-id="304aa-138">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="304aa-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="304aa-139">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="304aa-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="304aa-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="304aa-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="304aa-141">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="304aa-141">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
