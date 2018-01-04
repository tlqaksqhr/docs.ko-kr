---
title: "IHostTask 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask
helpviewer_keywords: IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bbffe2a171c112d4e9650b2c1b2a9ce1f010f382
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttask-interface"></a><span data-ttu-id="3fe91-102">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fe91-102">IHostTask Interface</span></span>
<span data-ttu-id="3fe91-103">공용 언어 런타임 (CLR) 작업을 관리 하기 위해 호스트와 통신할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe91-103">Provides methods that allow the common language runtime (CLR) to communicate with the host to manage tasks.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3fe91-104">메서드</span><span class="sxs-lookup"><span data-stu-id="3fe91-104">Methods</span></span>  
  
|<span data-ttu-id="3fe91-105">메서드</span><span class="sxs-lookup"><span data-stu-id="3fe91-105">Method</span></span>|<span data-ttu-id="3fe91-106">설명</span><span class="sxs-lookup"><span data-stu-id="3fe91-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3fe91-107">Alert 메서드</span><span class="sxs-lookup"><span data-stu-id="3fe91-107">Alert Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|<span data-ttu-id="3fe91-108">현재 작업의 시작을 호스트 하는 요청 `IHostTask` 인스턴스 작업을 중단할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe91-108">Requests that the host wake the task represented by the current `IHostTask` instance, so the task can be aborted.</span></span>|  
|[<span data-ttu-id="3fe91-109">GetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="3fe91-109">GetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|<span data-ttu-id="3fe91-110">현재 작업의 스레드 우선 순위 수준을 가져옵니다 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3fe91-110">Gets the thread priority level of the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="3fe91-111">Join 메서드</span><span class="sxs-lookup"><span data-stu-id="3fe91-111">Join Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|<span data-ttu-id="3fe91-112">현재 작업까지 호출 작업을 차단 `IHostTask` 인스턴스 완료 되 면 지정 된 시간 간격이 지나면 또는 [ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fe91-112">Blocks the calling task until the task represented by the current `IHostTask` instance completes, the specified time interval elapses, or [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) is called.</span></span>|  
|[<span data-ttu-id="3fe91-113">SetCLRTask 메서드</span><span class="sxs-lookup"><span data-stu-id="3fe91-113">SetCLRTask Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|<span data-ttu-id="3fe91-114">연결 된 [ICLRTask 인터페이스](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스를 현재 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3fe91-114">Associates an [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance with the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="3fe91-115">SetPriority 메서드</span><span class="sxs-lookup"><span data-stu-id="3fe91-115">SetPriority Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|<span data-ttu-id="3fe91-116">현재 작업에 대 한 호스트 조정 하도록 요청 합니다 스레드 우선 순위 수준 `IHostTask` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3fe91-116">Requests that the host adjust the thread priority level for the task represented by the current `IHostTask` instance.</span></span>|  
|[<span data-ttu-id="3fe91-117">Start 메서드</span><span class="sxs-lookup"><span data-stu-id="3fe91-117">Start Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|<span data-ttu-id="3fe91-118">호스트 작업 요청 현재 `IHostTask` 코드를 실행할 수 있는 라이브 상태로 일시 중단 된에서 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="3fe91-118">Requests that the host move the task represented by the current `IHostTask` instance from a suspended state to a live state, in which code can be executed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fe91-119">설명</span><span class="sxs-lookup"><span data-stu-id="3fe91-119">Remarks</span></span>  
 <span data-ttu-id="3fe91-120">정의한 메서드를 호출 하는 CLR `IHostTask` 수준 등 작업을 시작 하려면의 스레드 우선 순위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe91-120">The CLR calls methods defined by `IHostTask` to start a task, set its thread priority level, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fe91-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fe91-121">Requirements</span></span>  
 <span data-ttu-id="3fe91-122">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3fe91-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fe91-123">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fe91-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fe91-124">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3fe91-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fe91-125">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fe91-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe91-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fe91-126">See Also</span></span>  
 [<span data-ttu-id="3fe91-127">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fe91-127">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="3fe91-128">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fe91-128">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="3fe91-129">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fe91-129">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="3fe91-130">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fe91-130">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
