---
title: "IHostThreadPoolManager::GetMinThreads 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.GetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8ee8adfb93a3e098bb6df69ad00202118bc1731e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="9bba6-102">IHostThreadPoolManager::GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="9bba6-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="9bba6-103">요청에 대비 하 여에서 스레드 풀에서 호스트를 유지 관리 하는 유휴 상태 스레드의 최소 개수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bba6-104">구문</span><span class="sxs-lookup"><span data-stu-id="9bba6-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9bba6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9bba6-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="9bba6-106">[out] 호스트에서 현재 유지 하는 유휴 작업자 스레드의 최소 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bba6-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9bba6-107">Return Value</span></span>  
  
|<span data-ttu-id="9bba6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9bba6-108">HRESULT</span></span>|<span data-ttu-id="9bba6-109">설명</span><span class="sxs-lookup"><span data-stu-id="9bba6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9bba6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9bba6-110">S_OK</span></span>|<span data-ttu-id="9bba6-111">`GetMinThreads`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="9bba6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9bba6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9bba6-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9bba6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9bba6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9bba6-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-115">The call timed out.</span></span>|  
|<span data-ttu-id="9bba6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9bba6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9bba6-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9bba6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9bba6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9bba6-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9bba6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9bba6-120">E_FAIL</span></span>|<span data-ttu-id="9bba6-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9bba6-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9bba6-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9bba6-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="9bba6-124">E_NOTIMPL</span></span>|<span data-ttu-id="9bba6-125">호스트의 구현을 제공 하지 않는 `GetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bba6-126">설명</span><span class="sxs-lookup"><span data-stu-id="9bba6-126">Remarks</span></span>  
 <span data-ttu-id="9bba6-127">호스트의 구현을 제공 하지 않아도 됩니다 `GetMinThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="9bba6-128">이 경우 E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bba6-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bba6-129">Requirements</span></span>  
 <span data-ttu-id="9bba6-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9bba6-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bba6-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9bba6-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9bba6-132">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="9bba6-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9bba6-133">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bba6-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bba6-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bba6-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="9bba6-135">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="9bba6-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="9bba6-136">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="9bba6-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="9bba6-137">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bba6-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
