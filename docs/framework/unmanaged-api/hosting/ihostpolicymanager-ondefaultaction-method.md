---
title: "IHostPolicyManager::OnDefaultAction 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager.OnDefaultAction
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d1fded3d986e6505d0a321c47b03b5cdf9d881a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="2fe17-102">IHostPolicyManager::OnDefaultAction 메서드</span><span class="sxs-lookup"><span data-stu-id="2fe17-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="2fe17-103">공용 언어 런타임 (CLR)에 대 한 호출에 의해 설정 된 기본 작업을 수행 하려고 하는 호스트에 알립니다는 [iclrpolicymanager:: Setdefaultaction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) 메서드에 대 한 응답으로 스레드 중단 또는 <xref:System.AppDomain> 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fe17-104">구문</span><span class="sxs-lookup"><span data-stu-id="2fe17-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2fe17-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2fe17-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="2fe17-106">[in] 중 하나는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) CLR 응답 이벤트의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="2fe17-107">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) CLR 이벤트에 대 한 응답으로 수행 되는 작업을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fe17-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="2fe17-108">Return Value</span></span>  
  
|<span data-ttu-id="2fe17-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fe17-109">HRESULT</span></span>|<span data-ttu-id="2fe17-110">설명</span><span class="sxs-lookup"><span data-stu-id="2fe17-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fe17-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fe17-111">S_OK</span></span>|<span data-ttu-id="2fe17-112">`OnDefaultAction`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="2fe17-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2fe17-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2fe17-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="2fe17-115">성공적으로</span><span class="sxs-lookup"><span data-stu-id="2fe17-115">successfully</span></span>|  
|<span data-ttu-id="2fe17-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2fe17-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2fe17-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-117">The call timed out.</span></span>|  
|<span data-ttu-id="2fe17-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2fe17-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2fe17-119">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2fe17-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2fe17-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2fe17-121">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2fe17-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2fe17-122">E_FAIL</span></span>|<span data-ttu-id="2fe17-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2fe17-124">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2fe17-125">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2fe17-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2fe17-126">Requirements</span></span>  
 <span data-ttu-id="2fe17-127">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe17-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fe17-128">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fe17-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fe17-129">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2fe17-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fe17-130">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fe17-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe17-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fe17-131">See Also</span></span>  
 [<span data-ttu-id="2fe17-132">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="2fe17-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="2fe17-133">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="2fe17-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="2fe17-134">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fe17-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="2fe17-135">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2fe17-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
