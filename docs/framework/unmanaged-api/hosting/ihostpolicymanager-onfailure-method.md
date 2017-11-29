---
title: "IHostPolicyManager::OnFailure 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager.OnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dd8c5e071eca6b287b570006f33d7a1a43c1def9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="c759b-102">IHostPolicyManager::OnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="c759b-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="c759b-103">공용 언어 런타임 (CLR)를 호출 하 여 지정 된 작업을 수행 하려고 하는 호스트에 알립니다는 [iclrpolicymanager:: Setactiononfailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) 메서드에 대 한 응답으로 리소스 할당 또는 확보 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c759b-104">구문</span><span class="sxs-lookup"><span data-stu-id="c759b-104">Syntax</span></span>  
  
```  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c759b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c759b-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="c759b-106">[in] 중 하나는 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) CLR 응답 실패의 종류를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="c759b-107">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 값을 대 한 응답으로 수행 되는 CLR 작업을 나타내는 `failure`합니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c759b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c759b-108">Return Value</span></span>  
  
|<span data-ttu-id="c759b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c759b-109">HRESULT</span></span>|<span data-ttu-id="c759b-110">설명</span><span class="sxs-lookup"><span data-stu-id="c759b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c759b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c759b-111">S_OK</span></span>|<span data-ttu-id="c759b-112">`OnFailure`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="c759b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c759b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c759b-114">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c759b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c759b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c759b-116">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-116">The call timed out.</span></span>|  
|<span data-ttu-id="c759b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c759b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c759b-118">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c759b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c759b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c759b-120">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c759b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c759b-121">E_FAIL</span></span>|<span data-ttu-id="c759b-122">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c759b-123">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c759b-124">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c759b-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c759b-125">Requirements</span></span>  
 <span data-ttu-id="c759b-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c759b-127">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c759b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c759b-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c759b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c759b-129">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c759b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c759b-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c759b-130">See Also</span></span>  
 [<span data-ttu-id="c759b-131">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="c759b-131">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="c759b-132">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="c759b-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="c759b-133">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c759b-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="c759b-134">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c759b-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
