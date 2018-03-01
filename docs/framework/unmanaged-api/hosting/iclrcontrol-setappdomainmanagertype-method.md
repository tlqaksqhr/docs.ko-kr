---
title: "ICLRControl::SetAppDomainManagerType 메서드"
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
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bbddefa4211d63f012bce3532d7133b59c4ee1b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="ffeba-102">ICLRControl::SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="ffeba-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="ffeba-103">파생 된 형식을 설정 <xref:System.AppDomainManager> 응용 프로그램 도메인 관리자에 대 한 형식으로.</span><span class="sxs-lookup"><span data-stu-id="ffeba-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffeba-104">구문</span><span class="sxs-lookup"><span data-stu-id="ffeba-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ffeba-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ffeba-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="ffeba-106">[in] 요청된 된 형식에서 파생 된 어셈블리의 이름을 <xref:System.AppDomainManager> 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="ffeba-107">[in] 구현 되는 형식의 이름을 `pwzAppDomainManagerAssembly` 의 기능을 구현 하는 매개 변수 <xref:System.AppDomainManager>합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffeba-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="ffeba-108">Return Value</span></span>  
  
|<span data-ttu-id="ffeba-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffeba-109">HRESULT</span></span>|<span data-ttu-id="ffeba-110">설명</span><span class="sxs-lookup"><span data-stu-id="ffeba-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffeba-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffeba-111">S_OK</span></span>|<span data-ttu-id="ffeba-112">메서드가 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="ffeba-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ffeba-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ffeba-114">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ffeba-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ffeba-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ffeba-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-116">The call timed out.</span></span>|  
|<span data-ttu-id="ffeba-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ffeba-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ffeba-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ffeba-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ffeba-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ffeba-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ffeba-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffeba-121">E_FAIL</span></span>|<span data-ttu-id="ffeba-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffeba-123">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ffeba-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffeba-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ffeba-125">Requirements</span></span>  
 <span data-ttu-id="ffeba-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ffeba-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffeba-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ffeba-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffeba-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ffeba-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffeba-129">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffeba-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffeba-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ffeba-130">See Also</span></span>  
 [<span data-ttu-id="ffeba-131">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffeba-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="ffeba-132">IHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ffeba-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
