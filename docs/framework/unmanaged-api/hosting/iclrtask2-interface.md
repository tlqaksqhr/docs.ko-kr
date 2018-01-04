---
title: "ICLRTask2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTask2
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTask2
helpviewer_keywords: ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8701cff3400e46660fac90486cf5648d29aa9972
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="1943e-102">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1943e-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="1943e-103">모든 기능을 제공 된 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인터페이스; 또한 스레드 중단 현재 스레드에서 지연 될 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1943e-104">메서드</span><span class="sxs-lookup"><span data-stu-id="1943e-104">Methods</span></span>  
  
|<span data-ttu-id="1943e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="1943e-105">Method</span></span>|<span data-ttu-id="1943e-106">설명</span><span class="sxs-lookup"><span data-stu-id="1943e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1943e-107">BeginPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="1943e-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="1943e-108">지연 새 스레드 현재 스레드에 대 한 요청을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="1943e-109">EndPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="1943e-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="1943e-110">새 또는 스레드의 스레드 중단 요청을 보류 중인 현재 스레드를 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1943e-111">설명</span><span class="sxs-lookup"><span data-stu-id="1943e-111">Remarks</span></span>  
 <span data-ttu-id="1943e-112">`ICLRTask2` 상속는 `ICLRTask` 인터페이스 및 호스트에서 실패 하면 안 되는 코드 영역을 보호 하기 위해 스레드 중단을 지연 시킬 수 있는 메서드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="1943e-113">호출 `BeginPreventAsyncAbort` 카운터가 증가 하 고 지연 스레드 중단은 현재 스레드 및 호출에 대 한 `EndPreventAsyncAbort` 감소 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="1943e-114">에 대 한 호출이 `BeginPreventAsyncAbort` 및 `EndPreventAsyncAbort` 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="1943e-115">카운터는 0 보다 큰,으로 현재 스레드에 대 한 스레드 중단이 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="1943e-116">경우에 대 한 호출이 `BeginPreventAsyncAbort` 및 `EndPreventAsyncAbort` 됩니다 하지 않을 스레드 중단 현재 스레드를 전달할 수 없는 상태가 될 때까지 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="1943e-117">자체적으로 중단 하는 스레드에 지연이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="1943e-118">이 기능을 통해 노출 되는 기능은 가상 컴퓨터 (VM)에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="1943e-119">이러한 메서드를 잘못 사용 하면 VM 지정 되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="1943e-120">예를 들어 호출 `EndPreventAsyncAbort` 먼저 호출 하지 않고 `BeginPreventAsyncAbort` VM가 증가 이전에 때 카운터가 0으로 설정 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="1943e-121">마찬가지로, 내부 카운터 오버플로를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="1943e-122">호스트와 VM으로 증가 하기 때문에 필수 한도 초과 하는 경우 결과 동작 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="1943e-123">상속 된 멤버에 대 한 정보에 대 한 `ICLRTask` 와 다른이 인터페이스의 사용에 대 한 참조는 [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1943e-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1943e-124">Requirements</span></span>  
 <span data-ttu-id="1943e-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1943e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1943e-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1943e-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1943e-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1943e-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1943e-128">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1943e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1943e-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1943e-129">See Also</span></span>  
 [<span data-ttu-id="1943e-130">ICLRTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1943e-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="1943e-131">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1943e-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="1943e-132">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1943e-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="1943e-133">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1943e-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="1943e-134">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1943e-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
