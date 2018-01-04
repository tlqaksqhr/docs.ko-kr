---
title: "IHostCrst::SetSpinCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostCrst.SetSpinCount
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76a3091102a43d17f543010be0c505157d593d2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrstsetspincount-method"></a><span data-ttu-id="5bb00-102">IHostCrst::SetSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="5bb00-102">IHostCrst::SetSpinCount Method</span></span>
<span data-ttu-id="5bb00-103">현재 스핀 수를 설정 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="5bb00-103">Sets the spin count for the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bb00-104">구문</span><span class="sxs-lookup"><span data-stu-id="5bb00-104">Syntax</span></span>  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5bb00-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bb00-105">Parameters</span></span>  
 `dwSpinCount`  
 <span data-ttu-id="5bb00-106">[in] 현재 새 스핀 수 `IHostCrst` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="5bb00-106">[in] The new spin count for the current `IHostCrst` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5bb00-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="5bb00-107">Return Value</span></span>  
  
|<span data-ttu-id="5bb00-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5bb00-108">HRESULT</span></span>|<span data-ttu-id="5bb00-109">설명</span><span class="sxs-lookup"><span data-stu-id="5bb00-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5bb00-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5bb00-110">S_OK</span></span>|<span data-ttu-id="5bb00-111">`SetSpinCount`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-111">`SetSpinCount` returned successfully.</span></span>|  
|<span data-ttu-id="5bb00-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5bb00-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5bb00-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5bb00-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5bb00-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5bb00-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-115">The call timed out.</span></span>|  
|<span data-ttu-id="5bb00-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5bb00-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5bb00-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5bb00-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5bb00-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5bb00-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5bb00-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5bb00-120">E_FAIL</span></span>|<span data-ttu-id="5bb00-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5bb00-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5bb00-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5bb00-124">설명</span><span class="sxs-lookup"><span data-stu-id="5bb00-124">Remarks</span></span>  
 <span data-ttu-id="5bb00-125">다중 프로세서 시스템에서는 현재도 표시 되는 임계 영역 `IHostCrst` 인스턴스를 사용할 수는 호출 스레드를 회전 `dwSpinCount` 호출 하기 전에 번 [ihostsemaphore:: Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) 연결 세마포에서 중요 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-125">On multi-processor systems, if the critical section represented by the current `IHostCrst` instance is unavailable, a calling thread spins `dwSpinCount` times before calling [IHostSemaphore::Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) on a semaphore associated with the critical section.</span></span> <span data-ttu-id="5bb00-126">임계 영역 회전 작업 중에 무료 되 면 호출 스레드가 대기 작업을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-126">If the critical section becomes free during the spin operation, the calling thread avoids the wait operation.</span></span>  
  
 <span data-ttu-id="5bb00-127">사용 현황 `dwSpinCount` Win32에 같은 이름의 매개 변수를 사용 하는에 동일한 `InitializeCriticalSectionAndSpinCount` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-127">The usage of `dwSpinCount` is identical to the usage of the parameter of the same name in the Win32 `InitializeCriticalSectionAndSpinCount` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bb00-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bb00-128">Requirements</span></span>  
 <span data-ttu-id="5bb00-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5bb00-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bb00-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5bb00-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5bb00-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5bb00-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5bb00-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bb00-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb00-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bb00-133">See Also</span></span>  
 [<span data-ttu-id="5bb00-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bb00-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="5bb00-135">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bb00-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="5bb00-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bb00-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
