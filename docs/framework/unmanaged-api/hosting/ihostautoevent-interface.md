---
title: "IHostAutoEvent 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAutoEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAutoEvent
helpviewer_keywords: IHostAutoEvent interface [.NET Framework hosting]
ms.assetid: 6c1d15c1-a80a-4ee9-b1e4-6e859db6575a
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91e790cf7c97c0045535870c2d41d628f943a22d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostautoevent-interface"></a><span data-ttu-id="98bb0-102">IHostAutoEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98bb0-102">IHostAutoEvent Interface</span></span>
<span data-ttu-id="98bb0-103">호스트에서 구현 하는 자동 재설정 이벤트의 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98bb0-103">Provides a representation of the host's implementation of an auto-reset event.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98bb0-104">메서드</span><span class="sxs-lookup"><span data-stu-id="98bb0-104">Methods</span></span>  
  
|<span data-ttu-id="98bb0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="98bb0-105">Method</span></span>|<span data-ttu-id="98bb0-106">설명</span><span class="sxs-lookup"><span data-stu-id="98bb0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98bb0-107">Set 메서드</span><span class="sxs-lookup"><span data-stu-id="98bb0-107">Set Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-set-method.md)|<span data-ttu-id="98bb0-108">에서는 현재 `IHostAutoEvent` 인스턴스 신호를 받은 상태로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98bb0-108">Sets the current `IHostAutoEvent` instance to a signaled state.</span></span>|  
|[<span data-ttu-id="98bb0-109">Wait 메서드</span><span class="sxs-lookup"><span data-stu-id="98bb0-109">Wait Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-wait-method.md)|<span data-ttu-id="98bb0-110">현재 `IHostAutoEvent` 이벤트가 소유 될 때까지 대기 하는 인스턴스 또는 지정된 된 시간 간격이 경과 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="98bb0-110">Causes the current `IHostAutoEvent` instance to wait until the event is owned or a specified amount of time elapses.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98bb0-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="98bb0-111">Requirements</span></span>  
 <span data-ttu-id="98bb0-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="98bb0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98bb0-113">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="98bb0-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98bb0-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="98bb0-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98bb0-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98bb0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98bb0-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98bb0-116">See Also</span></span>  
 [<span data-ttu-id="98bb0-117">ICLRSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98bb0-117">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="98bb0-118">IHostManualEvent 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98bb0-118">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="98bb0-119">IHostSyncManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98bb0-119">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [<span data-ttu-id="98bb0-120">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="98bb0-120">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
