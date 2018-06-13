---
title: IHostThreadPoolManager::GetAvailableThreads 메서드
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetAvailableThreads
helpviewer_keywords:
- GetAvailableThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::GetAvailableThreads method [.NET Framework hosting]
ms.assetid: 61d26dfd-7f24-4e7d-a63e-b30a463f08e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8350140bb0871acc560163848ac50eafef42f01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441217"
---
# <a name="ihostthreadpoolmanagergetavailablethreads-method"></a><span data-ttu-id="ff589-102">IHostThreadPoolManager::GetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="ff589-102">IHostThreadPoolManager::GetAvailableThreads Method</span></span>
<span data-ttu-id="ff589-103">작업 항목을 현재 처리 되지 않습니다. 스레드 풀의 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-103">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff589-104">구문</span><span class="sxs-lookup"><span data-stu-id="ff589-104">Syntax</span></span>  
  
```  
HRESULT GetAvailableThreads (  
    [out] DWORD *pdwAvailableWorkerThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ff589-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff589-105">Parameters</span></span>  
 `pdwAvailableWorkerThreads`  
 <span data-ttu-id="ff589-106">[out] 작업 항목을 현재 처리 되지 않습니다. 스레드 풀의 스레드 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-106">[out] Pointer to the number of threads in the thread pool that are not currently processing work items.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ff589-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ff589-107">Return Value</span></span>  
  
|<span data-ttu-id="ff589-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ff589-108">HRESULT</span></span>|<span data-ttu-id="ff589-109">설명</span><span class="sxs-lookup"><span data-stu-id="ff589-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ff589-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ff589-110">S_OK</span></span>|<span data-ttu-id="ff589-111">`GetAvailableThreads` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-111">`GetAvailableThreads` returned successfully.</span></span>|  
|<span data-ttu-id="ff589-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ff589-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ff589-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ff589-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ff589-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ff589-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-115">The call timed out.</span></span>|  
|<span data-ttu-id="ff589-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ff589-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ff589-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ff589-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ff589-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ff589-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ff589-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ff589-120">E_FAIL</span></span>|<span data-ttu-id="ff589-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ff589-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ff589-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ff589-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="ff589-124">E_NOTIMPL</span></span>|<span data-ttu-id="ff589-125">호스트의 구현을 제공 하지 않는 `GetAvailableThreads`합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-125">The host does not provide an implementation of `GetAvailableThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff589-126">설명</span><span class="sxs-lookup"><span data-stu-id="ff589-126">Remarks</span></span>  
 <span data-ttu-id="ff589-127">호스트의 구현을 제공 하지 않는 경우 `GetAvailableThreads`, E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-127">If the host does not provide an implementation of `GetAvailableThreads`, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff589-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff589-128">Requirements</span></span>  
 <span data-ttu-id="ff589-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff589-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ff589-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff589-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ff589-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff589-132">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff589-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff589-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff589-133">See Also</span></span>  
 <xref:System.Threading.ThreadPool.GetAvailableThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="ff589-134">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff589-134">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
