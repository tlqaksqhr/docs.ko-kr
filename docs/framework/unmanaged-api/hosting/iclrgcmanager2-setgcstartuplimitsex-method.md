---
title: "ICLRGCManager2::SetGCStartupLimitsEx 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager2.SetGCStartupLimitsEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager2::SetCLRGCStartupLimitsEx
helpviewer_keywords:
- ICLRGCManager2::SetGCStartupLimitsEx method [.NET Framework hosting]
- SetGCStartupLimitsEx method, ICLRGCManager2 interface [.NET Framework hosting]
ms.assetid: 6c3a08a9-5d65-48d4-8bbf-2a86ed7d356a
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73f5678008354b312964f0cb32d768d36a641fd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager2setgcstartuplimitsex-method"></a><span data-ttu-id="ccd88-102">ICLRGCManager2::SetGCStartupLimitsEx 메서드</span><span class="sxs-lookup"><span data-stu-id="ccd88-102">ICLRGCManager2::SetGCStartupLimitsEx Method</span></span>
<span data-ttu-id="ccd88-103">가비지 수집 세그먼트의 크기와 0 세대 가비지 수집 시스템의 최대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-103">Sets the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccd88-104">구문</span><span class="sxs-lookup"><span data-stu-id="ccd88-104">Syntax</span></span>  
  
```  
HRESULT SetGCStartupLimitsEx (  
    [in] SIZE_T SegmentSize,   
    [in] SIZE_T MaxGen0Size  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccd88-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ccd88-105">Parameters</span></span>  
 `SegmentSize`  
 <span data-ttu-id="ccd88-106">[in] 가비지 수집 세그먼트의 지정 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-106">[in] The specified size of a garbage collection segment.</span></span>  
  
 <span data-ttu-id="ccd88-107">최소 세그먼트 크기는 4MB입니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-107">The minimum segment size is 4 MB.</span></span> <span data-ttu-id="ccd88-108">1mb 단위로 증가 또는 더 큰 세그먼트 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-108">Segments can be increased in increments of 1 MB or larger.</span></span>  
  
 `MaxGen0Size`  
 <span data-ttu-id="ccd88-109">[in] 0 세대에 대 한 지정 된 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-109">[in] The specified maximum size for generation 0.</span></span>  
  
 <span data-ttu-id="ccd88-110">0 세대의 최소 크기는 64KB입니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-110">The minimum generation 0 size is 64 KB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccd88-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="ccd88-111">Return Value</span></span>  
  
|<span data-ttu-id="ccd88-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ccd88-112">HRESULT</span></span>|<span data-ttu-id="ccd88-113">설명</span><span class="sxs-lookup"><span data-stu-id="ccd88-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ccd88-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ccd88-114">S_OK</span></span>|<span data-ttu-id="ccd88-115">`SetGCStartupLimitsEx`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-115">`SetGCStartupLimitsEx` returned successfully.</span></span>|  
|<span data-ttu-id="ccd88-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ccd88-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ccd88-117">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ccd88-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ccd88-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ccd88-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-119">The call timed out.</span></span>|  
|<span data-ttu-id="ccd88-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ccd88-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ccd88-121">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ccd88-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ccd88-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ccd88-123">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ccd88-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ccd88-124">E_FAIL</span></span>|<span data-ttu-id="ccd88-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ccd88-126">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-126">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ccd88-127">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccd88-128">설명</span><span class="sxs-lookup"><span data-stu-id="ccd88-128">Remarks</span></span>  
 <span data-ttu-id="ccd88-129">값은 `SetGCStartupLimitsEx` 호스트를 시작 하기 전에 집합을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-129">The values that `SetGCStartupLimitsEx` sets can be specified only before the host is started.</span></span> <span data-ttu-id="ccd88-130">나중에 대 한 호출이 `SetGCStartupLimitsEx` 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-130">Later calls to `SetGCStartupLimitsEx` are ignored.</span></span>  
  
 <span data-ttu-id="ccd88-131">매개 변수 중 하나가 다른 영향을 주지 않고을 설정 하려면 0 (영)을 변경 하려면 매개 변수에 대해 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-131">To set either parameter without affecting the other, specify 0 (zero) for the parameter you don't want to change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccd88-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccd88-132">Requirements</span></span>  
 <span data-ttu-id="ccd88-133">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ccd88-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccd88-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ccd88-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccd88-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ccd88-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccd88-136">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccd88-136">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd88-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccd88-137">See Also</span></span>  
 [<span data-ttu-id="ccd88-138">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="ccd88-138">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="ccd88-139">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="ccd88-139">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="ccd88-140">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccd88-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="ccd88-141">ICLRGCManager2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccd88-141">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)
