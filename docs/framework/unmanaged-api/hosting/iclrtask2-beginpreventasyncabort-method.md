---
title: "ICLRTask2::BeginPreventAsyncAbort 메서드"
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
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7bbbf609963f06e6c0204e8d44db30bb392886e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="88cb7-102">ICLRTask2::BeginPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="88cb7-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="88cb7-103">지연 새 스레드 적용 되는 현재 스레드에서 요청을 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88cb7-104">구문</span><span class="sxs-lookup"><span data-stu-id="88cb7-104">Syntax</span></span>  
  
```  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="88cb7-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="88cb7-105">Return Value</span></span>  
 <span data-ttu-id="88cb7-106">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="88cb7-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="88cb7-107">HRESULT</span></span>|<span data-ttu-id="88cb7-108">설명</span><span class="sxs-lookup"><span data-stu-id="88cb7-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="88cb7-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="88cb7-109">S_OK</span></span>|<span data-ttu-id="88cb7-110">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="88cb7-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="88cb7-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="88cb7-112">메서드는 현재 스레드의 되지 않는 스레드에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88cb7-113">설명</span><span class="sxs-lookup"><span data-stu-id="88cb7-113">Remarks</span></span>  
 <span data-ttu-id="88cb7-114">이 메서드를 호출 하나에서 현재 스레드에 대 한 지연 스레드 중단 카운터를 증가 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="88cb7-115">에 대 한 호출이 `BeginPreventAsyncAbort` 및 [iclrtask2:: Endpreventasyncabort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="88cb7-116">카운터는 0 보다 큰,으로 현재 스레드에 대 한 스레드 중단이 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="88cb7-117">경우이 호출은 호출 하 여 연결 하지는 `EndPreventAsyncAbort` 스레드 중단 현재 스레드를 전달할 수 없는 상태가 될 때까지 수는 메서드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="88cb7-118">자체적으로 중단 하는 스레드에 지연이 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="88cb7-119">이 기능을 통해 노출 되는 기능은 가상 컴퓨터 (VM)에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="88cb7-120">이러한 메서드를 잘못 사용 하면 VM 지정 되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="88cb7-121">예를 들어 호출 `EndPreventAsyncAbort` 먼저 호출 하지 않고 `BeginPreventAsyncAbort` VM가 증가 이전에 때 카운터가 0으로 설정 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="88cb7-122">마찬가지로, 내부 카운터 오버플로를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="88cb7-123">호스트와 VM으로 증가 하기 때문에 필수 한도 초과 하는 경우 결과 동작 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="88cb7-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88cb7-124">Requirements</span></span>  
 <span data-ttu-id="88cb7-125">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="88cb7-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88cb7-126">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="88cb7-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="88cb7-127">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="88cb7-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="88cb7-128">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88cb7-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88cb7-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88cb7-129">See Also</span></span>  
 [<span data-ttu-id="88cb7-130">EndPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="88cb7-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)  
 [<span data-ttu-id="88cb7-131">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88cb7-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="88cb7-132">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88cb7-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="88cb7-133">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88cb7-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="88cb7-134">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88cb7-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="88cb7-135">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88cb7-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
