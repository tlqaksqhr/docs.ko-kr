---
title: "ICLRTask2::EndPreventAsyncAbort 메서드"
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
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b18f6b8f6768c0a2980489cf8b84e16a9dd31350
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="85bc0-102">ICLRTask2::EndPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="85bc0-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="85bc0-103">새 또는 스레드의 스레드 중단 요청을 보류 중인 현재 스레드를 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85bc0-104">구문</span><span class="sxs-lookup"><span data-stu-id="85bc0-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="85bc0-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="85bc0-105">Return Value</span></span>  
 <span data-ttu-id="85bc0-106">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="85bc0-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="85bc0-107">HRESULT</span></span>|<span data-ttu-id="85bc0-108">설명</span><span class="sxs-lookup"><span data-stu-id="85bc0-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="85bc0-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="85bc0-109">S_OK</span></span>|<span data-ttu-id="85bc0-110">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="85bc0-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="85bc0-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="85bc0-112">메서드는 현재 스레드의 되지 않는 스레드에서 호출 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85bc0-113">설명</span><span class="sxs-lookup"><span data-stu-id="85bc0-113">Remarks</span></span>  
 <span data-ttu-id="85bc0-114">현재 스레드에 대 한 하나에서이 메서드는 지연 스레드 중단 감소 카운터를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="85bc0-115">에 대 한 호출이 [iclrtask2:: Beginpreventasyncabort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) 및 `EndPreventAsyncAbort` 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="85bc0-116">카운터는 0 보다 큰,으로 현재 스레드에 대 한 스레드 중단이 지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="85bc0-117">이 기능을 통해 노출 되는 기능은 가상 컴퓨터 (VM)에서 내부적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="85bc0-118">이러한 메서드를 잘못 사용 하면 VM 지정 되지 않은 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="85bc0-119">예를 들어 호출 `EndPreventAsyncAbort` 먼저 호출 하지 않고 `BeginPreventAsyncAbort` VM가 증가 이전에 때 카운터가 0으로 설정 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="85bc0-120">마찬가지로, 내부 카운터 오버플로를 검사 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="85bc0-121">호스트와 VM으로 증가 하기 때문에 필수 한도 초과 하는 경우 결과 동작 지정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85bc0-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85bc0-122">Requirements</span></span>  
 <span data-ttu-id="85bc0-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="85bc0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85bc0-124">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="85bc0-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85bc0-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="85bc0-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85bc0-126">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85bc0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85bc0-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85bc0-127">See Also</span></span>  
 [<span data-ttu-id="85bc0-128">BeginPreventAsyncAbort 메서드</span><span class="sxs-lookup"><span data-stu-id="85bc0-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [<span data-ttu-id="85bc0-129">ICLRTask2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85bc0-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [<span data-ttu-id="85bc0-130">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85bc0-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="85bc0-131">IHostTask 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85bc0-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="85bc0-132">IHostTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85bc0-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [<span data-ttu-id="85bc0-133">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85bc0-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
