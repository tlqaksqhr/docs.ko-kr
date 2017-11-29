---
title: "ICLRIoCompletionManager::OnComplete 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRIoCompletionManager.OnComplete
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRIoCompletionManager::OnComplete
helpviewer_keywords:
- OnComplete method [.NET Framework hosting]
- ICLRIoCompletionManager::OnComplete method [.NET Framework hosting]
ms.assetid: 003f6974-9727-4322-bed5-e330d1224d0b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9bd38679d1b8d099e5eb6330e03e2333b03780dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclriocompletionmanageroncomplete-method"></a><span data-ttu-id="b281d-102">ICLRIoCompletionManager::OnComplete 메서드</span><span class="sxs-lookup"><span data-stu-id="b281d-102">ICLRIoCompletionManager::OnComplete Method</span></span>
<span data-ttu-id="b281d-103">공용 언어 런타임 (CLR)에 대 한 호출을 사용 하 여 작성 된 I/O 요청의 상태의 알립니다는 [ihostiocompletionmanager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b281d-103">Notifies the common language runtime (CLR) of the status of an I/O request that was made by using a call to the [IHostIoCompletionManager::Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b281d-104">구문</span><span class="sxs-lookup"><span data-stu-id="b281d-104">Syntax</span></span>  
  
```  
HRESULT OnComplete (  
    [in] DWORD dwErrorCode,  
    [in] DWORD NumberOfBytesTransferred,  
    [in] void* pvOverlapped  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b281d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b281d-105">Parameters</span></span>  
 `dwErrorCode`  
 <span data-ttu-id="b281d-106">[in] 바인딩 작업의 상태를 나타내는 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-106">[in] An HRESULT value that indicates the status of the bind operation.</span></span>  
  
-   <span data-ttu-id="b281d-107">S_ok이 고 작업이 성공적으로 완료 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-107">S_OK indicates that the operation completed successfully.</span></span>  
  
-   <span data-ttu-id="b281d-108">HOST_E_INTERRUPTED는 호출이 완료 되기 전에 종료를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-108">HOST_E_INTERRUPTED indicates that the call terminated before completion.</span></span>  
  
-   <span data-ttu-id="b281d-109">E_FAIL 알 수 없는, 복구할 수 없는, 치명적인 오류가 발생 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-109">E_FAIL indicates that an unknown, unrecoverable, catastrophic failure occurred.</span></span>  
  
 `NumberOfBytesTransferred`  
 <span data-ttu-id="b281d-110">[in] I/O 요청을 처리 하는 동안 전송 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-110">[in] The number of bytes transferred during the processing of the I/O request.</span></span>  
  
 `pvOverlapped`  
 <span data-ttu-id="b281d-111">[in] 에 대 한 포인터는 `OVERLAPPED` 에 대 한 호출에 전달 된 구조는 `IHostIoCompletionManager::Bind` 메서드.</span><span class="sxs-lookup"><span data-stu-id="b281d-111">[in] A pointer to the `OVERLAPPED` structure that was passed to the call to the `IHostIoCompletionManager::Bind` method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b281d-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="b281d-112">Return Value</span></span>  
  
|<span data-ttu-id="b281d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b281d-113">HRESULT</span></span>|<span data-ttu-id="b281d-114">설명</span><span class="sxs-lookup"><span data-stu-id="b281d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b281d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="b281d-115">S_OK</span></span>|<span data-ttu-id="b281d-116">`OnComplete`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-116">`OnComplete` returned successfully.</span></span>|  
|<span data-ttu-id="b281d-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b281d-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b281d-118">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b281d-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b281d-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b281d-120">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-120">The call timed out.</span></span>|  
|<span data-ttu-id="b281d-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b281d-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b281d-122">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b281d-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b281d-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b281d-124">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b281d-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b281d-125">E_FAIL</span></span>|<span data-ttu-id="b281d-126">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b281d-127">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-127">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b281d-128">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b281d-129">설명</span><span class="sxs-lookup"><span data-stu-id="b281d-129">Remarks</span></span>  
 <span data-ttu-id="b281d-130">CLR 메서드를 사용 하 여 호스트를 통해 I/O 요청은 호스트에서 I/O 완료 추상화를 구현 하는 경우 [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-130">If the host implements an I/O completion abstraction, the CLR makes I/O requests through the host by using methods of [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md).</span></span> <span data-ttu-id="b281d-131">호스트는 다음 호출 하 여 `OnComplete` 메서드를 이러한 요청의 결과 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-131">The host then calls the `OnComplete` method to notify the runtime of the outcome of such requests.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b281d-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b281d-132">Requirements</span></span>  
 <span data-ttu-id="b281d-133">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b281d-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b281d-134">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b281d-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b281d-135">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b281d-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b281d-136">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b281d-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b281d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b281d-137">See Also</span></span>  
 [<span data-ttu-id="b281d-138">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b281d-138">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="b281d-139">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b281d-139">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)  
 [<span data-ttu-id="b281d-140">IHostThreadPoolManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b281d-140">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
