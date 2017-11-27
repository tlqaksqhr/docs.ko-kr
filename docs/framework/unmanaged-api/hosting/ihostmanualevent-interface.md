---
title: "IHostManualEvent 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostManualEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostManualEvent
helpviewer_keywords: IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c19125d96d5f4a9e91fc083d53f36ebebd2c569
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmanualevent-interface"></a><span data-ttu-id="fb6cc-102">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb6cc-102">IHostManualEvent Interface</span></span>
<span data-ttu-id="fb6cc-103">수동 다시 설정 이벤트의 표현 호스트의 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fb6cc-103">Provides the host's implementation of a representation of a manual reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fb6cc-104">메서드</span><span class="sxs-lookup"><span data-stu-id="fb6cc-104">Methods</span></span>  
  
|<span data-ttu-id="fb6cc-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fb6cc-105">Method</span></span>|<span data-ttu-id="fb6cc-106">설명</span><span class="sxs-lookup"><span data-stu-id="fb6cc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fb6cc-107">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="fb6cc-107">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|<span data-ttu-id="fb6cc-108">현재 다시 설정 `IHostManualEvent` 인스턴스 신호 되지 않은 상태로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb6cc-108">Resets the current `IHostManualEvent` instance to a non-signaled state.</span></span>|  
|[<span data-ttu-id="fb6cc-109">Set 메서드</span><span class="sxs-lookup"><span data-stu-id="fb6cc-109">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|<span data-ttu-id="fb6cc-110">에서는 현재 `IHostManualEvent` 인스턴스 신호를 받은 상태로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb6cc-110">Sets the current `IHostManualEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="fb6cc-111">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="fb6cc-111">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|<span data-ttu-id="fb6cc-112">현재 `IHostManualEvent` 가 소유 될 때까지 대기 하는 인스턴스 또는 지정된 된 시간 간격이 경과 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="fb6cc-112">Causes the current `IHostManualEvent` instance to wait until it is owned, or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb6cc-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb6cc-113">Requirements</span></span>  
 <span data-ttu-id="fb6cc-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb6cc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb6cc-115">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fb6cc-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb6cc-116">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fb6cc-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb6cc-117">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb6cc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb6cc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb6cc-118">See Also</span></span>  
 [<span data-ttu-id="fb6cc-119">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb6cc-119">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="fb6cc-120">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb6cc-120">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="fb6cc-121">IHostSemaphore 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb6cc-121">IHostSemaphore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)  
 [<span data-ttu-id="fb6cc-122">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb6cc-122">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="fb6cc-123">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb6cc-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
