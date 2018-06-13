---
title: IHostSemaphore 인터페이스
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103deb5ec46ba8c1d385c5339bc52a0c220c4c93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33439770"
---
# <a name="ihostsemaphore-interface"></a><span data-ttu-id="6a746-102">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a746-102">IHostSemaphore Interface</span></span>
<span data-ttu-id="6a746-103">스레딩에 대 한 세마포 호스트의 구현을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6a746-103">Represents the host's implementation of a semaphore for threading.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6a746-104">메서드</span><span class="sxs-lookup"><span data-stu-id="6a746-104">Methods</span></span>  
  
|<span data-ttu-id="6a746-105">메서드</span><span class="sxs-lookup"><span data-stu-id="6a746-105">Method</span></span>|<span data-ttu-id="6a746-106">설명</span><span class="sxs-lookup"><span data-stu-id="6a746-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6a746-107">ReleaseSemaphore 메서드</span><span class="sxs-lookup"><span data-stu-id="6a746-107">ReleaseSemaphore Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|<span data-ttu-id="6a746-108">현재 수를 늘립니다 `IHostSemaphore` 인스턴스를 지정 된 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6a746-108">Increases the count of the current `IHostSemaphore` instance by the specified amount.</span></span>|  
|[<span data-ttu-id="6a746-109">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="6a746-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|<span data-ttu-id="6a746-110">현재 `IHostSemaphore` 소유 될 때까지 대기 하는 인스턴스 또는 지정된 된 양의 시간 간격이 경과 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a746-110">Causes the current `IHostSemaphore` instance to wait until it is owned or the specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a746-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a746-111">Requirements</span></span>  
 <span data-ttu-id="6a746-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6a746-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a746-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a746-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a746-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6a746-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a746-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a746-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a746-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a746-116">See Also</span></span>  
 [<span data-ttu-id="6a746-117">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a746-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="6a746-118">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a746-118">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="6a746-119">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a746-119">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="6a746-120">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a746-120">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="6a746-121">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a746-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
