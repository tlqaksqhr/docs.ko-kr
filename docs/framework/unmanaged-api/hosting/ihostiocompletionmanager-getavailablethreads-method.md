---
title: "IHostIoCompletionManager::GetAvailableThreads 메서드"
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
- IHostIoCompletionManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: bab363d1-b859-47a4-9884-5661c611cce7
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 66f2471e07ae5827d2edb553b4226784b42278c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagergetavailablethreads-method"></a><span data-ttu-id="9c44b-102">IHostIoCompletionManager::GetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="9c44b-102">IHostIoCompletionManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="9c44b-103">현재 요청을 처리 하지는 호스트에 의해 관리 되는 스레드 총 I/O 완료 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-103">Gets the number of I/O completion threads, of the total number of threads managed by the host, that are not currently servicing requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c44b-104">구문</span><span class="sxs-lookup"><span data-stu-id="9c44b-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9c44b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9c44b-105">Parameters</span></span>  
 `pdwAvailableIoCompletionThreads`  
 <span data-ttu-id="9c44b-106">[out] I/O 완료 스레드는 호스트에 의해 관리 되는 요청을 현재 사용할 수 있는 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-106">[out] A pointer to the number of I/O completion threads managed by the host that are currently available to service requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9c44b-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9c44b-107">Return Value</span></span>  
  
|<span data-ttu-id="9c44b-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9c44b-108">HRESULT</span></span>|<span data-ttu-id="9c44b-109">설명</span><span class="sxs-lookup"><span data-stu-id="9c44b-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9c44b-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9c44b-110">S_OK</span></span>|<span data-ttu-id="9c44b-111">`GetAvailableThreads`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="9c44b-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9c44b-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9c44b-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9c44b-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9c44b-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9c44b-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-115">The call timed out.</span></span>|  
|<span data-ttu-id="9c44b-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9c44b-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9c44b-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9c44b-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9c44b-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9c44b-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9c44b-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9c44b-120">E_FAIL</span></span>|<span data-ttu-id="9c44b-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9c44b-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9c44b-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9c44b-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="9c44b-124">E_NOTIMPL</span></span>|<span data-ttu-id="9c44b-125">호스트의 구현을 제공 하지 않는 `GetAvailableThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c44b-126">설명</span><span class="sxs-lookup"><span data-stu-id="9c44b-126">Remarks</span></span>  
 <span data-ttu-id="9c44b-127">호스트 구현, 성능, 확장성 등의 이유로 I/O 완료 스레드 풀의 크기에 대 한 독점적인 제어권을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-127">A host might want exclusive control over the size of the I/O completion thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="9c44b-128">따라서 호스트는 구현할 필요가 없습니다 `GetAvailableThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-128">Therefore, the host is not required to implement `GetAvailableThreads`.</span></span> <span data-ttu-id="9c44b-129">이 경우 호스트는이 메서드의 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c44b-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9c44b-130">Requirements</span></span>  
 <span data-ttu-id="9c44b-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9c44b-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c44b-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9c44b-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9c44b-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9c44b-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9c44b-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c44b-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c44b-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c44b-135">See Also</span></span>  
 [<span data-ttu-id="9c44b-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c44b-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="9c44b-137">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9c44b-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
