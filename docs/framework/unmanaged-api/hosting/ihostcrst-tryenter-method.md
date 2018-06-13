---
title: IHostCrst::TryEnter 메서드
ms.date: 03/30/2017
api_name:
- IHostCrst.TryEnter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::TryEnter
helpviewer_keywords:
- IHostCrst::TryEnter method [.NET Framework hosting]
- TryEnter method [.NET Framework hosting]
ms.assetid: a922fa98-beab-4f09-a342-cc94fc65687f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3773ad1c6e279d38231e778bb0a81dd765aff82a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438986"
---
# <a name="ihostcrsttryenter-method"></a><span data-ttu-id="4d128-102">IHostCrst::TryEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="4d128-102">IHostCrst::TryEnter Method</span></span>
<span data-ttu-id="4d128-103">현재 임계 영역을 입력 하려고 [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4d128-103">Attempts to enter the critical section represented by the current [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d128-104">구문</span><span class="sxs-lookup"><span data-stu-id="4d128-104">Syntax</span></span>  
  
```  
HRESULT TryEnter (  
    [in]  DWORD  option,  
    [out] BOOL   *pbSucceeded  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d128-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d128-105">Parameters</span></span>  
 `option`  
 <span data-ttu-id="4d128-106">[in] 중 하나는 [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) 값을 호스트 하는 경우 수행할 동작을 나타내는 작업을 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-106">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) values, indicating what action the host should take if the operation blocks.</span></span>  
  
 `pbSucceeded`  
 <span data-ttu-id="4d128-107">[out] `true` 임계 영역이 고, 그러지 않으면 입력 한 될 수 있도록 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-107">[out] `true` if the critical section can be entered; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d128-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="4d128-108">Return Value</span></span>  
  
|<span data-ttu-id="4d128-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d128-109">HRESULT</span></span>|<span data-ttu-id="4d128-110">설명</span><span class="sxs-lookup"><span data-stu-id="4d128-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d128-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d128-111">S_OK</span></span>|<span data-ttu-id="4d128-112">`TryEnter` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-112">`TryEnter` returned successfully.</span></span>|  
|<span data-ttu-id="4d128-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4d128-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4d128-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4d128-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4d128-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4d128-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-116">The call timed out.</span></span>|  
|<span data-ttu-id="4d128-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4d128-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4d128-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4d128-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4d128-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4d128-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4d128-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4d128-121">E_FAIL</span></span>|<span data-ttu-id="4d128-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4d128-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4d128-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d128-125">설명</span><span class="sxs-lookup"><span data-stu-id="4d128-125">Remarks</span></span>  
 <span data-ttu-id="4d128-126">`TryEnter` 즉시 반환 되며 호출 스레드에서 임계 영역 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-126">`TryEnter` returns immediately and indicates whether the calling thread entered the critical section.</span></span> <span data-ttu-id="4d128-127">이 메서드는 Wind32 미러링 `TryEnterCriticalSection` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-127">This method mirrors the Wind32 `TryEnterCriticalSection` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d128-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d128-128">Requirements</span></span>  
 <span data-ttu-id="4d128-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d128-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d128-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4d128-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d128-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4d128-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d128-132">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d128-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d128-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d128-133">See Also</span></span>  
 [<span data-ttu-id="4d128-134">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d128-134">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="4d128-135">IHostCrst 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d128-135">IHostCrst Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)  
 [<span data-ttu-id="4d128-136">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d128-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
