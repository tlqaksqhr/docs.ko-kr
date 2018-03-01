---
title: "IHostIoCompletionManager::SetMaxThreads 메서드"
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
- IHostIoCompletionManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::SetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: ebad4f40-d9f1-4dc6-9b27-a89c9eb3926f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3d2d8436d85f7be40c89693628794b007e0c6a88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostiocompletionmanagersetmaxthreads-method"></a><span data-ttu-id="e9169-102">IHostIoCompletionManager::SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="e9169-102">IHostIoCompletionManager::SetMaxThreads Method</span></span>
<span data-ttu-id="e9169-103">I/O 요청을 할당 하는 호스트 하는 스레드의 최대 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-103">Sets the maximum number of threads that the host allots to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9169-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9169-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD dwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9169-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e9169-105">Parameters</span></span>  
 `dwMaxIoCompletionThreads`  
 <span data-ttu-id="e9169-106">[in] I/O 요청에 할당할 스레드의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-106">[in] The maximum number of threads to allot for I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9169-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="e9169-107">Return Value</span></span>  
  
|<span data-ttu-id="e9169-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9169-108">HRESULT</span></span>|<span data-ttu-id="e9169-109">설명</span><span class="sxs-lookup"><span data-stu-id="e9169-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9169-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9169-110">S_OK</span></span>|<span data-ttu-id="e9169-111">`SetMaxThreads`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="e9169-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e9169-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e9169-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e9169-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e9169-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e9169-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-115">The call timed out.</span></span>|  
|<span data-ttu-id="e9169-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e9169-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e9169-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e9169-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e9169-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e9169-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e9169-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e9169-120">E_FAIL</span></span>|<span data-ttu-id="e9169-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e9169-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e9169-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e9169-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e9169-124">E_NOTIMPL</span></span>|<span data-ttu-id="e9169-125">호스트의 구현을 제공 하지 않는 `SetMaxThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9169-126">설명</span><span class="sxs-lookup"><span data-stu-id="e9169-126">Remarks</span></span>  
 <span data-ttu-id="e9169-127">`SetMaxThreads`I/O 포트에서 서비스 요청에 사용할 수 있는 스레드의 최대 수를 설정할 수 있는 CLR을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-127">`SetMaxThreads` provides the CLR with an opportunity to set the maximum number of threads that are available to service requests on I/O ports.</span></span> <span data-ttu-id="e9169-128">호스트 구현, 성능, 확장성 등의 이유로 스레드 풀의 크기에 대 한 독점적인 제어권을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-128">A host might need exclusive control over the size of the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="e9169-129">이러한 이유로 호스트는 구현할 필요가 없습니다 `SetMaxThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-129">For this reason, the host is not required to implement `SetMaxThreads`.</span></span> <span data-ttu-id="e9169-130">이 경우 호스트는이 메서드의 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-130">In this case, a host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9169-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e9169-131">Requirements</span></span>  
 <span data-ttu-id="e9169-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e9169-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9169-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9169-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9169-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e9169-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9169-135">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9169-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9169-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9169-136">See Also</span></span>  
 [<span data-ttu-id="e9169-137">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9169-137">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="e9169-138">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e9169-138">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
