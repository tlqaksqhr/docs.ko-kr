---
title: "IHostSecurityContext::Capture 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityContext.Capture
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityContext::Capture
helpviewer_keywords:
- Capture method [.NET Framework hosting]
- IHostSecurityContext::Capture method [.NET Framework hosting]
ms.assetid: ae0836d0-1170-4494-bac5-d0e809df51a2
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: def431dd40c6dd7aa6688a638971d3676bbd1ffb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsecuritycontextcapture-method"></a><span data-ttu-id="d9e6a-102">IHostSecurityContext::Capture 메서드</span><span class="sxs-lookup"><span data-stu-id="d9e6a-102">IHostSecurityContext::Capture Method</span></span>
<span data-ttu-id="d9e6a-103">복제본을 가져옵니다는 [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) 에 대 한 호출에서 반환 된 인스턴스 [ihostsecuritymanager:: Getsecuritycontext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-103">Gets a clone of the [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9e6a-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9e6a-104">Syntax</span></span>  
  
```  
HRESULT Capture (  
    [out] IHostSecurityContext** ppClonedContext  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9e6a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9e6a-105">Parameters</span></span>  
 `ppClonedContext`  
 <span data-ttu-id="d9e6a-106">[out] 복제본의 주소에 대 한 포인터는 `IHostSecurityContext` 캡처할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-106">[out] A pointer to the address of a clone of the `IHostSecurityContext` object to be captured.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9e6a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="d9e6a-107">Return Value</span></span>  
  
|<span data-ttu-id="d9e6a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9e6a-108">HRESULT</span></span>|<span data-ttu-id="d9e6a-109">설명</span><span class="sxs-lookup"><span data-stu-id="d9e6a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9e6a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9e6a-110">S_OK</span></span>|<span data-ttu-id="d9e6a-111">`Capture`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-111">`Capture` returned successfully.</span></span>|  
|<span data-ttu-id="d9e6a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9e6a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9e6a-113">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9e6a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9e6a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9e6a-115">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-115">The call timed out.</span></span>|  
|<span data-ttu-id="d9e6a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9e6a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9e6a-117">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9e6a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9e6a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9e6a-119">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9e6a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9e6a-120">E_FAIL</span></span>|<span data-ttu-id="d9e6a-121">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9e6a-122">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9e6a-123">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9e6a-124">설명</span><span class="sxs-lookup"><span data-stu-id="d9e6a-124">Remarks</span></span>  
 <span data-ttu-id="d9e6a-125">반환 된 인터페이스 포인터 `Capture` 복제본 캡처된 컨텍스트의입니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-125">The interface pointer returned from `Capture` is a clone of the captured context.</span></span> <span data-ttu-id="d9e6a-126">이 정보를 비동기 코드 포인트 간에 이동에서 호출이 발생 된 포인터의 수명 분리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-126">When this information is moved across an asynchronous code point, its lifetime is separated from that of the pointer against which the call was made.</span></span> <span data-ttu-id="d9e6a-127">따라서 원래 포인터를 릴리스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-127">The original pointer can therefore be released.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9e6a-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d9e6a-128">Requirements</span></span>  
 <span data-ttu-id="d9e6a-129">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d9e6a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9e6a-130">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d9e6a-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9e6a-131">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d9e6a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9e6a-132">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9e6a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9e6a-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9e6a-133">See Also</span></span>  
 [<span data-ttu-id="d9e6a-134">IHostSecurityContext 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9e6a-134">IHostSecurityContext Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [<span data-ttu-id="d9e6a-135">IHostSecurityManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d9e6a-135">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
