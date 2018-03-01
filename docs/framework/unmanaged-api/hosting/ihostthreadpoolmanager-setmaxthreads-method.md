---
title: "IHostThreadPoolManager::SetMaxThreads 메서드"
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
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e3f637b1a50e3be3c544a107c603bc84ba2d5450
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="8e5eb-102">IHostThreadPoolManager::SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="8e5eb-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="8e5eb-103">최대 스레드 풀에서 호스트를 유지할 수 있는 스레드 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e5eb-104">구문</span><span class="sxs-lookup"><span data-stu-id="8e5eb-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e5eb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e5eb-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="8e5eb-106">스레드 풀에 있는 최대 작업자 스레드 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8e5eb-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="8e5eb-107">Return Value</span></span>  
  
|<span data-ttu-id="8e5eb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8e5eb-108">HRESULT</span></span>|<span data-ttu-id="8e5eb-109">설명</span><span class="sxs-lookup"><span data-stu-id="8e5eb-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8e5eb-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="8e5eb-110">S_OK</span></span>|<span data-ttu-id="8e5eb-111">`SetMaxThreads`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="8e5eb-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8e5eb-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8e5eb-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8e5eb-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8e5eb-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8e5eb-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-115">The call timed out.</span></span>|  
|<span data-ttu-id="8e5eb-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8e5eb-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8e5eb-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8e5eb-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8e5eb-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8e5eb-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8e5eb-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8e5eb-120">E_FAIL</span></span>|<span data-ttu-id="8e5eb-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="8e5eb-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8e5eb-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8e5eb-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="8e5eb-124">E_NOTIMPL</span></span>|<span data-ttu-id="8e5eb-125">호스트의 구현을 제공 하지 않는 `SetMaxThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e5eb-126">설명</span><span class="sxs-lookup"><span data-stu-id="8e5eb-126">Remarks</span></span>  
 <span data-ttu-id="8e5eb-127">호스트는 CLR 스레드 풀의 크기를 구성할 수 있도록 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="8e5eb-128">일부 호스트 구현, 성능, 확장성 등의 이유로 스레드 풀에 대 한 독점적인 제어권을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="8e5eb-129">이 경우 호스트 E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e5eb-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e5eb-130">Requirements</span></span>  
 <span data-ttu-id="8e5eb-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e5eb-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e5eb-132">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8e5eb-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8e5eb-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8e5eb-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e5eb-134">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e5eb-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5eb-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8e5eb-135">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="8e5eb-136">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="8e5eb-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="8e5eb-137">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="8e5eb-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="8e5eb-138">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e5eb-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
