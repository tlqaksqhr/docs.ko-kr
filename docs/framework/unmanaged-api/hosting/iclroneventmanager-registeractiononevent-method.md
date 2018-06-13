---
title: ICLROnEventManager::RegisterActionOnEvent 메서드
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c12e1fff4910458a17c09e482ba8ede9c1625c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434018"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a><span data-ttu-id="c15eb-102">ICLROnEventManager::RegisterActionOnEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="c15eb-102">ICLROnEventManager::RegisterActionOnEvent Method</span></span>
<span data-ttu-id="c15eb-103">지정된 된 이벤트에 대 한 콜백 포인터를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-103">Registers a callback pointer for the specified event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c15eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="c15eb-104">Syntax</span></span>  
  
```  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c15eb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c15eb-105">Parameters</span></span>  
 `event`  
 <span data-ttu-id="c15eb-106">[in] 중 하나는 [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) 이벤트를 등록할에서 설명 하는 콜백 포인터를 나타내는 값을 `pAction`합니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-106">[in] One of the [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) values, indicating the event for which to register the callback pointer described by `pAction`.</span></span>  
  
 `pAction`  
 <span data-ttu-id="c15eb-107">[in] 에 대 한 포인터는 [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) 등록된 이벤트가 발생할 때 호출 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-107">[in] A pointer to an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) object that is called when the registered event fires.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c15eb-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c15eb-108">Return Value</span></span>  
  
|<span data-ttu-id="c15eb-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c15eb-109">HRESULT</span></span>|<span data-ttu-id="c15eb-110">설명</span><span class="sxs-lookup"><span data-stu-id="c15eb-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c15eb-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c15eb-111">S_OK</span></span>|<span data-ttu-id="c15eb-112">`RegisterActionOnEvent` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-112">`RegisterActionOnEvent` returned successfully.</span></span>|  
|<span data-ttu-id="c15eb-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c15eb-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c15eb-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c15eb-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c15eb-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c15eb-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-116">The call timed out.</span></span>|  
|<span data-ttu-id="c15eb-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c15eb-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c15eb-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c15eb-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c15eb-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c15eb-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c15eb-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c15eb-121">E_FAIL</span></span>|<span data-ttu-id="c15eb-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c15eb-123">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c15eb-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c15eb-125">설명</span><span class="sxs-lookup"><span data-stu-id="c15eb-125">Remarks</span></span>  
 <span data-ttu-id="c15eb-126">호스트에서 설명 하는 두 개의 이벤트 형식 중 하나 또는 모두에 대 한 콜백을 등록할 수 `EClrEvent`합니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-126">The host can register callbacks for either or both of the two event types described by `EClrEvent`.</span></span> <span data-ttu-id="c15eb-127">호스트를 가져옵니다는 `ICLROnEventManager` 호출 하 여 인터페이스는 [iclrcontrol:: Getclrmanager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c15eb-127">The host gets the `ICLROnEventManager` interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c15eb-128">이벤트는 `RegisterActionOnEvent` 레지스터는 서로 다른 스레드의 신호를 보내는 언로드 또는 CLR의 비활성화 하 고 두 번 이상 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-128">The events that `RegisterActionOnEvent` registers can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c15eb-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c15eb-129">Requirements</span></span>  
 <span data-ttu-id="c15eb-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c15eb-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c15eb-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c15eb-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c15eb-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c15eb-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c15eb-133">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c15eb-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c15eb-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c15eb-134">See Also</span></span>  
 [<span data-ttu-id="c15eb-135">EClrEvent 열거형</span><span class="sxs-lookup"><span data-stu-id="c15eb-135">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="c15eb-136">IActionOnCLREvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c15eb-136">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="c15eb-137">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c15eb-137">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="c15eb-138">ICLROnEventManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c15eb-138">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
