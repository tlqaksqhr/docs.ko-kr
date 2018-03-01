---
title: "IHostIoCompletionManager::SetCLRIoCompletionManager 메서드"
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
- IHostIoCompletionManager.SetCLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager::SetCLRIoCompletionManager method [.NET Framework hosting]
- SetCLRIoCompletionManager method [.NET Framework hosting]
ms.assetid: 4254bb01-3a14-4f34-a3be-60ff1f5072b5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fde1045fd0f15e7255a163c1f1b041800e85921
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagersetclriocompletionmanager-method"></a><span data-ttu-id="6be2e-102">IHostIoCompletionManager::SetCLRIoCompletionManager 메서드</span><span class="sxs-lookup"><span data-stu-id="6be2e-102">IHostIoCompletionManager::SetCLRIoCompletionManager Method</span></span>
<span data-ttu-id="6be2e-103">호스트에 대 한 인터페이스 포인터에 제공 된 [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) 공용 언어 런타임 (CLR)에 의해 구현 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="6be2e-103">Provides the host with an interface pointer to the [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) instance implemented by the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be2e-104">구문</span><span class="sxs-lookup"><span data-stu-id="6be2e-104">Syntax</span></span>  
  
```  
HRESULT SetCLRIoCompletionManager (  
    [in] ICLRIoCompletionManager *pManager  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6be2e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6be2e-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="6be2e-106">[in] 에 대 한 인터페이스 포인터는 `ICLRIoCompletionManager` 인스턴스 CLR에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-106">[in] An interface pointer to an `ICLRIoCompletionManager` instance provided by the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6be2e-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6be2e-107">Return Value</span></span>  
  
|<span data-ttu-id="6be2e-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6be2e-108">HRESULT</span></span>|<span data-ttu-id="6be2e-109">설명</span><span class="sxs-lookup"><span data-stu-id="6be2e-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6be2e-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6be2e-110">S_OK</span></span>|<span data-ttu-id="6be2e-111">`SetCLRIoCompletionManager`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-111">`SetCLRIoCompletionManager` returned successfully.</span></span>|  
|<span data-ttu-id="6be2e-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6be2e-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6be2e-113">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6be2e-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6be2e-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6be2e-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-115">The call timed out.</span></span>|  
|<span data-ttu-id="6be2e-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6be2e-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6be2e-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6be2e-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6be2e-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6be2e-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6be2e-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6be2e-120">E_FAIL</span></span>|<span data-ttu-id="6be2e-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6be2e-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6be2e-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6be2e-124">설명</span><span class="sxs-lookup"><span data-stu-id="6be2e-124">Remarks</span></span>  
 <span data-ttu-id="6be2e-125">CLR가 호출 후 `SetCLRIoCompletionManager`, 호스트에서는 호출 [iclriocompletionmanager:: Oncomplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) I/O 요청이 완료 될 때 CLR에 알리기 위해 합니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-125">After the CLR has called `SetCLRIoCompletionManager`, the host must call [ICLRIoCompletionManager::OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md) to notify the CLR when an I/O request has been completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6be2e-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6be2e-126">Requirements</span></span>  
 <span data-ttu-id="6be2e-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6be2e-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6be2e-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6be2e-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6be2e-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6be2e-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6be2e-130">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6be2e-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be2e-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6be2e-131">See Also</span></span>  
 [<span data-ttu-id="6be2e-132">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6be2e-132">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="6be2e-133">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6be2e-133">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
