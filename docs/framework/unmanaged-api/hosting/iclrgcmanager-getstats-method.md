---
title: "ICLRGCManager::GetStats 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager.GetStats
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c6ba88eebb963749247b318f14ef52bb116e3f0c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrgcmanagergetstats-method"></a><span data-ttu-id="371f4-102">ICLRGCManager::GetStats 메서드</span><span class="sxs-lookup"><span data-stu-id="371f4-102">ICLRGCManager::GetStats Method</span></span>
<span data-ttu-id="371f4-103">공용 언어 런타임의 가비지 수집 시스템에 대 한 현재 통계의 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-103">Gets a set of current statistics about the common language runtime's garbage collection system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="371f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="371f4-104">Syntax</span></span>  
  
```  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="371f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="371f4-105">Parameters</span></span>  
 `pStats`  
 <span data-ttu-id="371f4-106">[out에서] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 요청 된 통계가 포함 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="371f4-106">[in, out] A [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) instance that contains the requested statistics.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="371f4-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="371f4-107">Return Value</span></span>  
  
|<span data-ttu-id="371f4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="371f4-108">HRESULT</span></span>|<span data-ttu-id="371f4-109">설명</span><span class="sxs-lookup"><span data-stu-id="371f4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="371f4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="371f4-110">S_OK</span></span>|<span data-ttu-id="371f4-111">`GetStats`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-111">`GetStats` returned successfully.</span></span>|  
|<span data-ttu-id="371f4-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="371f4-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="371f4-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="371f4-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="371f4-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="371f4-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-115">The call timed out.</span></span>|  
|<span data-ttu-id="371f4-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="371f4-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="371f4-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="371f4-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="371f4-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="371f4-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="371f4-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="371f4-120">E_FAIL</span></span>|<span data-ttu-id="371f4-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="371f4-122">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="371f4-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="371f4-124">설명</span><span class="sxs-lookup"><span data-stu-id="371f4-124">Remarks</span></span>  
 <span data-ttu-id="371f4-125">계산 하 고 지정 된 통계만 반환 하는 CLR의 `Flags` 필드 `pStats`합니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-125">The CLR calculates and returns only those statistics that are specified by the `Flags` field of `pStats`.</span></span>  
  
 <span data-ttu-id="371f4-126">설정의 `Flags` 필드의 하나 이상의 값에는 [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) 에서 통계를 지정 하는 열거형은 [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) 구조 설정지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-126">Set the `Flags` field to one or more values of the [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeration to specify which statistics in the [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) structure are to be set.</span></span>  
  
 <span data-ttu-id="371f4-127">사용의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-127">An example of the usage is as follows:</span></span>  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a><span data-ttu-id="371f4-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="371f4-128">Requirements</span></span>  
 <span data-ttu-id="371f4-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="371f4-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="371f4-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="371f4-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="371f4-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="371f4-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="371f4-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="371f4-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="371f4-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="371f4-133">See Also</span></span>  
 [<span data-ttu-id="371f4-134">자동 메모리 관리</span><span class="sxs-lookup"><span data-stu-id="371f4-134">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="371f4-135">COR_GC_STATS 구조체</span><span class="sxs-lookup"><span data-stu-id="371f4-135">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [<span data-ttu-id="371f4-136">COR_GC_STAT_TYPES 열거형</span><span class="sxs-lookup"><span data-stu-id="371f4-136">COR_GC_STAT_TYPES Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)  
 [<span data-ttu-id="371f4-137">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="371f4-137">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="371f4-138">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="371f4-138">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="371f4-139">ICLRGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="371f4-139">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="371f4-140">CLR 호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="371f4-140">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="371f4-141">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="371f4-141">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="371f4-142">호스팅</span><span class="sxs-lookup"><span data-stu-id="371f4-142">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
