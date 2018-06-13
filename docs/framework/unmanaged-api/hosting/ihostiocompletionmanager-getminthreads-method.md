---
title: IHostIoCompletionManager::GetMinThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetMinThreads
helpviewer_keywords:
- GetMinThreads method, IHostIoCompletionManager interface [.NET Framework hosting]
- IHostIoCompletionManager::GetMinThreads method [.NET Framework hosting]
ms.assetid: d7a7f733-677d-481c-b3d5-444fcc502b8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353d98feed2ab54cf13af92883348598e822c1d5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439093"
---
# <a name="ihostiocompletionmanagergetminthreads-method"></a><span data-ttu-id="4293d-102">IHostIoCompletionManager::GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="4293d-102">IHostIoCompletionManager::GetMinThreads Method</span></span>
<span data-ttu-id="4293d-103">최소 I/O 요청 처리를 위한 호스트에서 제공 하는 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-103">Gets the minimum number of threads that the host provides for processing I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4293d-104">구문</span><span class="sxs-lookup"><span data-stu-id="4293d-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *pdwMinIOCompletionThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4293d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4293d-105">Parameters</span></span>  
 `pdwMinIOCompletionThreads`  
 <span data-ttu-id="4293d-106">[out] 호스트 프로세스 I/O 요청에 제공 하는 스레드의 최소 개수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-106">[out] A pointer to the minimum number of threads that the host provides to process I/O requests.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4293d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="4293d-107">Return Value</span></span>  
  
|<span data-ttu-id="4293d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4293d-108">HRESULT</span></span>|<span data-ttu-id="4293d-109">설명</span><span class="sxs-lookup"><span data-stu-id="4293d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4293d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4293d-110">S_OK</span></span>|<span data-ttu-id="4293d-111">`GetMinThreads` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="4293d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4293d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4293d-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4293d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4293d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4293d-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-115">The call timed out.</span></span>|  
|<span data-ttu-id="4293d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4293d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4293d-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4293d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4293d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4293d-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4293d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4293d-120">E_FAIL</span></span>|<span data-ttu-id="4293d-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4293d-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4293d-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4293d-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="4293d-124">E_NOTIMPL</span></span>|<span data-ttu-id="4293d-125">호스트의 구현을 제공 하지 않는 `GetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4293d-126">설명</span><span class="sxs-lookup"><span data-stu-id="4293d-126">Remarks</span></span>  
 <span data-ttu-id="4293d-127">호스트 구현, 성능, 확장성 등의 이유로 서비스 I/O 요청에 할당 된 스레드 수에 대 한 독점적인 제어권을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-127">A host might want exclusive control over the number of threads allotted to service I/O requests, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="4293d-128">이러한 이유로 호스트는 구현할 필요가 없습니다 `GetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-128">For this reason, the host is not required to implement `GetMinThreads`.</span></span> <span data-ttu-id="4293d-129">이 경우 호스트는이 메서드의 E_NOTIMPL을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-129">In this case, the host should return E_NOTIMPL from this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4293d-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4293d-130">Requirements</span></span>  
 <span data-ttu-id="4293d-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4293d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4293d-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4293d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4293d-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4293d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4293d-134">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4293d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4293d-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4293d-135">See Also</span></span>  
 [<span data-ttu-id="4293d-136">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4293d-136">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="4293d-137">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4293d-137">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
