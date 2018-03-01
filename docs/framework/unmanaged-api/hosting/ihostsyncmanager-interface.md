---
title: "IHostSyncManager 인터페이스"
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
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b51e1dd9219c30eb4918bf1e331c96585f7c03ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanager-interface"></a><span data-ttu-id="854d8-102">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="854d8-102">IHostSyncManager Interface</span></span>
<span data-ttu-id="854d8-103">공용 언어 런타임 (CLR) Win32 동기화 기능을 사용 하지 않고 호스트를 호출 하 여 동기화 기본 형식을 만드는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-103">Provides methods that allow the common language runtime (CLR) to create synchronization primitives by calling the host instead of using the Win32 synchronization functions.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="854d8-104">메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-104">Methods</span></span>  
  
|<span data-ttu-id="854d8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-105">Method</span></span>|<span data-ttu-id="854d8-106">설명</span><span class="sxs-lookup"><span data-stu-id="854d8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="854d8-107">CreateAutoEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-107">CreateAutoEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|<span data-ttu-id="854d8-108">자동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-108">Creates an auto-reset event object.</span></span>|  
|[<span data-ttu-id="854d8-109">CreateCrst 메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-109">CreateCrst Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|<span data-ttu-id="854d8-110">동기화에 대 한 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-110">Creates a critical section object for synchronization.</span></span>|  
|[<span data-ttu-id="854d8-111">CreateCrstWithSpinCount 메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-111">CreateCrstWithSpinCount Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|<span data-ttu-id="854d8-112">동기화에 대 한 스핀 카운트 임계 영역 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-112">Creates a critical section object with spin count for synchronization.</span></span>|  
|[<span data-ttu-id="854d8-113">CreateManualEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-113">CreateManualEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|<span data-ttu-id="854d8-114">수동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-114">Creates a manual-reset event object.</span></span>|  
|[<span data-ttu-id="854d8-115">CreateMonitorEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-115">CreateMonitorEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|<span data-ttu-id="854d8-116">모니터링 되는 자동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-116">Creates a monitored auto-reset event object.</span></span>|  
|[<span data-ttu-id="854d8-117">CreateRWLockReaderEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-117">CreateRWLockReaderEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|<span data-ttu-id="854d8-118">판독기 잠금 구현에 대 한 수동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-118">Creates a manual-reset event object for the implementation of a reader lock.</span></span>|  
|[<span data-ttu-id="854d8-119">CreateRWLockWriterEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-119">CreateRWLockWriterEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|<span data-ttu-id="854d8-120">작성기 잠금 구현에 대 한 자동 재설정 이벤트 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-120">Creates an auto-reset event object for the implementation of a writer lock.</span></span>|  
|[<span data-ttu-id="854d8-121">CreateSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-121">CreateSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|<span data-ttu-id="854d8-122">만듭니다는 [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) 대기 이벤트에 대 한 세마포도 사용할 CLR에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-122">Creates an [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) object for the CLR to use as a semaphore for wait events.</span></span>|  
|[<span data-ttu-id="854d8-123">SetCLRSyncManager 메서드</span><span class="sxs-lookup"><span data-stu-id="854d8-123">SetCLRSyncManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|<span data-ttu-id="854d8-124">설정의 [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) 현재와 연결할 인스턴스 `IHostSyncManager` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="854d8-124">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current `IHostSyncManager` instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="854d8-125">설명</span><span class="sxs-lookup"><span data-stu-id="854d8-125">Remarks</span></span>  
 <span data-ttu-id="854d8-126">CLR은 호스트의 구현을 검색 `IHostSyncManager` 호출 하 여는 [ihostcontrol:: Gethostmanager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) 메서드는 `IID` IID_IHostSyncManager의 합니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-126">The CLR discovers the host's implementation of `IHostSyncManager` by calling the [IHostControl::GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) method with an `IID` of IID_IHostSyncManager.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="854d8-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="854d8-127">Requirements</span></span>  
 <span data-ttu-id="854d8-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="854d8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="854d8-129">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="854d8-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="854d8-130">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="854d8-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="854d8-131">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="854d8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="854d8-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="854d8-132">See Also</span></span>  
 [<span data-ttu-id="854d8-133">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="854d8-133">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="854d8-134">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="854d8-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
