---
title: IHostTaskManager::SetUILocale 메서드
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f929dceafc72af89cfd85b1617de7bbd0bc0dfff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442752"
---
# <a name="ihosttaskmanagersetuilocale-method"></a><span data-ttu-id="ccb8f-102">IHostTaskManager::SetUILocale 메서드</span><span class="sxs-lookup"><span data-stu-id="ccb8f-102">IHostTaskManager::SetUILocale Method</span></span>
<span data-ttu-id="ccb8f-103">사용자 인터페이스 (UI) 로캘 또는 culture 현재 실행 중인 작업에서 공용 언어 런타임 (CLR) 변경 된 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-103">Notifies the host that the common language runtime (CLR) has changed the user interface (UI) locale, or culture, on the currently executing task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb8f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ccb8f-104">Syntax</span></span>  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccb8f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ccb8f-105">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="ccb8f-106">[in] 새로 할당 된 지역 culture 및 언어에 매핑하는 로캘 식별자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-106">[in] The locale identifier value that maps to the newly assigned geographical culture and language.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ccb8f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ccb8f-107">Return Value</span></span>  
  
|<span data-ttu-id="ccb8f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ccb8f-108">HRESULT</span></span>|<span data-ttu-id="ccb8f-109">설명</span><span class="sxs-lookup"><span data-stu-id="ccb8f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ccb8f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ccb8f-110">S_OK</span></span>|<span data-ttu-id="ccb8f-111">`SetUILocale` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-111">`SetUILocale` returned successfully.</span></span>|  
|<span data-ttu-id="ccb8f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ccb8f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ccb8f-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ccb8f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ccb8f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ccb8f-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-115">The call timed out.</span></span>|  
|<span data-ttu-id="ccb8f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ccb8f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ccb8f-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ccb8f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ccb8f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ccb8f-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ccb8f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ccb8f-120">E_FAIL</span></span>|<span data-ttu-id="ccb8f-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ccb8f-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ccb8f-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ccb8f-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ccb8f-124">E_NOTIMPL</span></span>|<span data-ttu-id="ccb8f-125">호스트는 UI 문화권을 변경 하는 관리 되는 사용자 코드를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-125">The host does not allow managed user code to change the UI culture.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccb8f-126">설명</span><span class="sxs-lookup"><span data-stu-id="ccb8f-126">Remarks</span></span>  
 <span data-ttu-id="ccb8f-127">런타임 호출 `SetUILocale` 때의 값은 <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> 속성이 관리 코드에 의해 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-127">The runtime calls `SetUILocale` when the value of the <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> property is changed by managed code.</span></span> <span data-ttu-id="ccb8f-128">이 메서드는 로캘 동기화에 대 한이 포함 되어 메커니즘을 실행할 호스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-128">This method provides an opportunity for the host to execute any mechanisms it might have for synchronization of locales.</span></span> <span data-ttu-id="ccb8f-129">호스트의 UI 로캘 관리 코드에서 변경할 수 없도록 로캘 동기화 하는 메커니즘을 구현 하지 않는 경우 E_NOTIMPL이 메서드로부터 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-129">If a host does not allow the UI locale to be changed from managed code, or does not implement a mechanism to synchronize locales, it should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccb8f-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccb8f-130">Requirements</span></span>  
 <span data-ttu-id="ccb8f-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ccb8f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccb8f-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ccb8f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ccb8f-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ccb8f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ccb8f-134">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccb8f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb8f-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ccb8f-135">See Also</span></span>  
 [<span data-ttu-id="ccb8f-136">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccb8f-136">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ccb8f-137">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccb8f-137">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ccb8f-138">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccb8f-138">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ccb8f-139">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccb8f-139">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="ccb8f-140">SetLocale 메서드</span><span class="sxs-lookup"><span data-stu-id="ccb8f-140">SetLocale Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
