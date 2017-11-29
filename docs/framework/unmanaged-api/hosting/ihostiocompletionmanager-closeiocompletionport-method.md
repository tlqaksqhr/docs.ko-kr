---
title: "IHostIoCompletionManager::CloseIoCompletionPort 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostIoCompletionManager.CloseIoCompletionPort
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostIoCompletionManager::CloseIoCompletionPort
helpviewer_keywords:
- IHostIoCompletionManager::CloseIoCompletionPort method [.NET Framework hosting]
- CloseIoCompletionPort method [.NET Framework hosting]
ms.assetid: e86ad7be-3758-498a-a972-5522d69dfbb3
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 066d51c821cf86522ffaca4c15db360ce96ed773
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostiocompletionmanagercloseiocompletionport-method"></a><span data-ttu-id="5580a-102">IHostIoCompletionManager::CloseIoCompletionPort 메서드</span><span class="sxs-lookup"><span data-stu-id="5580a-102">IHostIoCompletionManager::CloseIoCompletionPort Method</span></span>
<span data-ttu-id="5580a-103">호스트에 대 한 이전 호출을 통해 연 포트를 닫도록 요청 [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-103">Requests that the host close a port that was opened through an earlier call to [CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5580a-104">구문</span><span class="sxs-lookup"><span data-stu-id="5580a-104">Syntax</span></span>  
  
```  
HRESULT CloseIoCompletionPort (  
    [in] HANDLE hPort  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5580a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5580a-105">Parameters</span></span>  
 `hPort`  
 <span data-ttu-id="5580a-106">[in] 닫을 포트의 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-106">[in] The handle of the port to close.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5580a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="5580a-107">Return Value</span></span>  
  
|<span data-ttu-id="5580a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5580a-108">HRESULT</span></span>|<span data-ttu-id="5580a-109">설명</span><span class="sxs-lookup"><span data-stu-id="5580a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5580a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5580a-110">S_OK</span></span>|<span data-ttu-id="5580a-111">`CloseIoCompletionPort`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-111">`CloseIoCompletionPort` returned successfully.</span></span>|  
|<span data-ttu-id="5580a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5580a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5580a-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5580a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5580a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5580a-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-115">The call timed out.</span></span>|  
|<span data-ttu-id="5580a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5580a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5580a-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5580a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5580a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5580a-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5580a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5580a-120">E_FAIL</span></span>|<span data-ttu-id="5580a-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5580a-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5580a-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5580a-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5580a-124">E_INVALIDARG</span></span>|<span data-ttu-id="5580a-125">잘못 된 포트 핸들이 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-125">An invalid port handle was passed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5580a-126">설명</span><span class="sxs-lookup"><span data-stu-id="5580a-126">Remarks</span></span>  
 <span data-ttu-id="5580a-127">`hPort`에 대 한 이전 호출에서 만든 포트에 대 한 핸들 이어야 합니다 `CreateIoCompletionPort`합니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-127">`hPort` must be a handle to a port that was created by an earlier call to `CreateIoCompletionPort`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5580a-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5580a-128">Requirements</span></span>  
 <span data-ttu-id="5580a-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5580a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5580a-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5580a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5580a-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5580a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5580a-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5580a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5580a-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5580a-133">See Also</span></span>  
 [<span data-ttu-id="5580a-134">ICLRIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5580a-134">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [<span data-ttu-id="5580a-135">IHostIoCompletionManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5580a-135">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
