---
title: "IHostGCManager 인터페이스"
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
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7452f49df6970bf2ca49781f6a38874186bec64f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostgcmanager-interface"></a><span data-ttu-id="5ddf3-102">IHostGCManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ddf3-102">IHostGCManager Interface</span></span>
<span data-ttu-id="5ddf3-103">공용 언어 런타임 (CLR)에 의해 구현 가비지 수집 메커니즘에서 이벤트의 호스트를 알리는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-103">Provides methods that notify the host of events in the garbage collection mechanism implemented by the common language runtime (CLR).</span></span>  
  
## <a name="members"></a><span data-ttu-id="5ddf3-104">멤버</span><span class="sxs-lookup"><span data-stu-id="5ddf3-104">Members</span></span>  
  
|<span data-ttu-id="5ddf3-105">멤버</span><span class="sxs-lookup"><span data-stu-id="5ddf3-105">Member</span></span>|<span data-ttu-id="5ddf3-106">설명</span><span class="sxs-lookup"><span data-stu-id="5ddf3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5ddf3-107">SuspensionEnding 메서드</span><span class="sxs-lookup"><span data-stu-id="5ddf3-107">SuspensionEnding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionending-method.md)|<span data-ttu-id="5ddf3-108">CLR 가비지 수집을 위해 중단 된 스레드의 작업을 다시 시작 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-108">Notifies the host that the CLR is resuming execution of tasks on threads that had been suspended for a garbage collection.</span></span>|  
|[<span data-ttu-id="5ddf3-109">SuspensionStarting 메서드</span><span class="sxs-lookup"><span data-stu-id="5ddf3-109">SuspensionStarting Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-suspensionstarting-method.md)|<span data-ttu-id="5ddf3-110">CLR 가비지 수집을 수행 하기 위해 작업 실행을 중단 하는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-110">Notifies the host that the CLR is suspending execution of tasks, to perform a garbage collection.</span></span>|  
|[<span data-ttu-id="5ddf3-111">ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="5ddf3-111">ThreadIsBlockingForSuspension Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostgcmanager-threadisblockingforsuspension-method.md)|<span data-ttu-id="5ddf3-112">메서드 호출이 만들어진 스레드는 호스트에 알려 줍니다 가비지 수집에 대 한 차단 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-112">Notifies the host that the thread from which the method call was made is about to block for a garbage collection.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ddf3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ddf3-113">Requirements</span></span>  
 <span data-ttu-id="5ddf3-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ddf3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ddf3-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5ddf3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5ddf3-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5ddf3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ddf3-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ddf3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ddf3-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ddf3-118">See Also</span></span>  
 [<span data-ttu-id="5ddf3-119">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ddf3-119">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="5ddf3-120">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ddf3-120">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="5ddf3-121">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ddf3-121">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="5ddf3-122">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ddf3-122">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="5ddf3-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ddf3-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
