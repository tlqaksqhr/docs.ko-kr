---
title: "IHostIoCompletionManager::GetMaxThreads 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.GetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::GetMaxThreads
helpviewer_keywords:
- IHostIoCompletionManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: e7a6cadc-2433-4472-a701-58891abcde45
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4e7df4acd435c767a1d0c3ae4484a236359cfb38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagergetmaxthreads-method"></a><span data-ttu-id="1ba97-102">IHostIoCompletionManager::GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="1ba97-102">IHostIoCompletionManager::GetMaxThreads Method</span></span>
<span data-ttu-id="1ba97-103">I/O 요청을 처리 하는 호스트를 할당할 수 있는 스레드 최대 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-103">Gets the maximum number of threads that the host can allot to service I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba97-104">구문</span><span class="sxs-lookup"><span data-stu-id="1ba97-104">Syntax</span></span>  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxIoCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ba97-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1ba97-105">Parameters</span></span>  
 `pdwMaxIoCompletionThreads`  
 <span data-ttu-id="1ba97-106">[out] 호스트 서비스 I/O 요청에 할당할 수 있는 스레드 풀의 스레드 최대 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-106">[out] A pointer to the maximum number of threads in the thread pool that the host can allot to service I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ba97-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1ba97-107">Return Value</span></span>  
  
|<span data-ttu-id="1ba97-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ba97-108">HRESULT</span></span>|<span data-ttu-id="1ba97-109">설명</span><span class="sxs-lookup"><span data-stu-id="1ba97-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ba97-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ba97-110">S_OK</span></span>|<span data-ttu-id="1ba97-111">`GetMaxThreads`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-111">`GetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="1ba97-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1ba97-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1ba97-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1ba97-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1ba97-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1ba97-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-115">The call timed out.</span></span>|  
|<span data-ttu-id="1ba97-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1ba97-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1ba97-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1ba97-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1ba97-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1ba97-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1ba97-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1ba97-120">E_FAIL</span></span>|<span data-ttu-id="1ba97-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1ba97-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1ba97-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1ba97-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="1ba97-124">E_NOTIMPL</span></span>|<span data-ttu-id="1ba97-125">호스트의 구현을 제공 하지 않는 `GetMaxThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-125">The host does not provide an implementation of `GetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ba97-126">설명</span><span class="sxs-lookup"><span data-stu-id="1ba97-126">Remarks</span></span>  
 <span data-ttu-id="1ba97-127">호스트 구현, 성능, 확장성 등의 이유로 I/O 요청의 처리에 할당할 수 있는 스레드 수에 대 한 독점적인 제어권을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-127">A host might want exclusive control over the number of threads that can be allotted to process I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="1ba97-128">이러한 이유로 호스트는 구현할 필요가 없습니다 `GetMaxThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-128">For this reason, the host is not required to implement `GetMaxThreads`.</span></span> <span data-ttu-id="1ba97-129">이 경우 호스트는이 메서드의 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ba97-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1ba97-130">Requirements</span></span>  
 <span data-ttu-id="1ba97-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1ba97-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ba97-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ba97-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ba97-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1ba97-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ba97-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ba97-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba97-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ba97-135">See Also</span></span>  
 [<span data-ttu-id="1ba97-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ba97-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="1ba97-137">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ba97-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
