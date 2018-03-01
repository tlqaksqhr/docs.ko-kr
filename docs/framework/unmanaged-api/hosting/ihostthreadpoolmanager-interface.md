---
title: "IHostThreadPoolManager 인터페이스"
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
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1cd58c53deec0a895ae6f67cccf26d2c8c2530be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanager-interface"></a><span data-ttu-id="65da1-102">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65da1-102">IHostThreadPoolManager Interface</span></span>
<span data-ttu-id="65da1-103">공용 언어 런타임 (CLR) 스레드 풀을 구성 하 고 스레드 풀에 작업 항목 큐에 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="65da1-103">Provides methods that enable the common language runtime (CLR) to configure the thread pool and to queue work items to the thread pool.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65da1-104">메서드</span><span class="sxs-lookup"><span data-stu-id="65da1-104">Methods</span></span>  
  
|<span data-ttu-id="65da1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="65da1-105">Method</span></span>|<span data-ttu-id="65da1-106">설명</span><span class="sxs-lookup"><span data-stu-id="65da1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="65da1-107">GetAvailableThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="65da1-107">GetAvailableThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|<span data-ttu-id="65da1-108">작업 항목을 현재 처리 되지 않습니다. 스레드 풀의 스레드 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65da1-108">Gets the number of threads in the thread pool that are not currently processing work items.</span></span>|  
|[<span data-ttu-id="65da1-109">GetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="65da1-109">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|<span data-ttu-id="65da1-110">스레드 풀에 동시에 호스트를 유지 하는 스레드의 최대 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65da1-110">Gets the maximum number of threads that the host maintains concurrently in the thread pool.</span></span>|  
|[<span data-ttu-id="65da1-111">GetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="65da1-111">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|<span data-ttu-id="65da1-112">요청에 대비 하 여에서 호스트를 유지 관리 하는 유휴 상태 스레드의 최소 개수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65da1-112">Gets the minimum number of idle threads that the host maintains in anticipation of requests.</span></span>|  
|[<span data-ttu-id="65da1-113">QueueUserWorkItem 메서드</span><span class="sxs-lookup"><span data-stu-id="65da1-113">QueueUserWorkItem Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|<span data-ttu-id="65da1-114">실행을 위한 함수 큐 대기 하 고 함수에서 사용할 데이터를 포함 하는 개체를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="65da1-114">Queues a function for execution, and provides an object containing data to be used by the function.</span></span>|  
|[<span data-ttu-id="65da1-115">SetMaxThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="65da1-115">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|<span data-ttu-id="65da1-116">최대 스레드 풀에서 호스트를 유지할 수 있는 스레드 수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65da1-116">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>|  
|[<span data-ttu-id="65da1-117">SetMinThreads 메서드</span><span class="sxs-lookup"><span data-stu-id="65da1-117">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|<span data-ttu-id="65da1-118">요청에 대비 하 여에서 호스트를 유지 해야 하는 유휴 상태 스레드의 최소 개수를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65da1-118">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65da1-119">설명</span><span class="sxs-lookup"><span data-stu-id="65da1-119">Remarks</span></span>  
 <span data-ttu-id="65da1-120">호스트에 대 한 호출에 지정 된 값을 사용 하 여 스레드 풀을 구성 하지 않아도 됩니다는 `SetMaxThreads` 및 `SetMinThreads` 메서드.</span><span class="sxs-lookup"><span data-stu-id="65da1-120">The host is not required to configure the thread pool by using the values specified in calls to the `SetMaxThreads` and `SetMinThreads` methods.</span></span> <span data-ttu-id="65da1-121">이 경우 호스트는 이러한 방법 중에서 E_NOTIMPL HRESULT 값을 반환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65da1-121">In this case, the host should return an HRESULT value of E_NOTIMPL from these methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65da1-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65da1-122">Requirements</span></span>  
 <span data-ttu-id="65da1-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65da1-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65da1-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="65da1-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65da1-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="65da1-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65da1-126">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65da1-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65da1-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65da1-127">See Also</span></span>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="65da1-128">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65da1-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
