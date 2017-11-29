---
title: "ICLRHostBindingPolicyManager::EvaluatePolicy 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostBindingPolicyManager.EvaluatePolicy
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostBindingPolicyManager::EvaluatePolicy
helpviewer_keywords:
- ICLRHostBindingPolicyManager::EvaluatePolicy method [.NET Framework hosting]
- EvaluatePolicy method [.NET Framework hosting]
ms.assetid: 3a3a9446-7a4e-4836-9b27-5c536c15993d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7471b77deca7b66ba0a30b08ccf934704a7ac61d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iclrhostbindingpolicymanagerevaluatepolicy-method"></a><span data-ttu-id="cda13-102">ICLRHostBindingPolicyManager::EvaluatePolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="cda13-102">ICLRHostBindingPolicyManager::EvaluatePolicy Method</span></span>
<span data-ttu-id="cda13-103">호스트를 대신 하 여 바인딩 정책을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-103">Evaluates binding policy on behalf of the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda13-104">구문</span><span class="sxs-lookup"><span data-stu-id="cda13-104">Syntax</span></span>  
  
```  
HRESULT EvaluatePolicy (  
    [in] LPCWSTR     pwzReferenceIdentity,  
    [in] BYTE       *pbApplicationPolicy,  
    [in] DWORD       cbAppPolicySize,  
    [out, size_is(*pcchPostPolicyReferenceIdentity)] LPWSTR pwzPostPolicyReferenceIdentity,  
    [in, out] DWORD *pcchPostPolicyReferenceIdentity,  
    [out] DWORD     *pdwPoliciesApplied  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cda13-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cda13-105">Parameters</span></span>  
 `pwzReferenceIdentity`  
 <span data-ttu-id="cda13-106">[in] 정책 평가 하기 전에 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-106">[in] A reference to the assembly before the policy evaluation.</span></span>  
  
 `pbApplicationPolicy`  
 <span data-ttu-id="cda13-107">[in] 정책 데이터를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-107">[in] A pointer to a buffer that contains the policy data.</span></span>  
  
 `cbAppPolicySize`  
 <span data-ttu-id="cda13-108">[in] 크기는 `pbApplicationPolicy` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-108">[in] The size of the `pbApplicationPolicy` buffer.</span></span>  
  
 `pwzPostPolicyReferenceIdentity`  
 <span data-ttu-id="cda13-109">[out] 새 정책 데이터 평가 후 어셈블리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-109">[out] A reference to the assembly after the evaluation of the new policy data.</span></span>  
  
 `pcchPostPolicyReferenceIdentity`  
 <span data-ttu-id="cda13-110">[out에서] 새 정책 데이터를 평가한 후 어셈블리 identity 참조 버퍼의 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-110">[in, out] A pointer to the size of the assembly identity reference buffer after the evaluation of the new policy data.</span></span>  
  
 `pdwPoliciesApplied`  
 <span data-ttu-id="cda13-111">[out] 논리 OR 조합에 대 한 포인터 [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) 어떤 정책이 적용 되어 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-111">[out] A pointer to a logical OR combination of [EBindPolicyLevels](../../../../docs/framework/unmanaged-api/hosting/ebindpolicylevels-enumeration.md) values, indicating which policies have been applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cda13-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="cda13-112">Return Value</span></span>  
  
|<span data-ttu-id="cda13-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cda13-113">HRESULT</span></span>|<span data-ttu-id="cda13-114">설명</span><span class="sxs-lookup"><span data-stu-id="cda13-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cda13-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="cda13-115">S_OK</span></span>|<span data-ttu-id="cda13-116">성공적으로 완료 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-116">The evaluation completed successfully.</span></span>|  
|<span data-ttu-id="cda13-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="cda13-117">E_INVALIDARG</span></span>|<span data-ttu-id="cda13-118">중 하나 `pwzReferenceIdentity` 또는 `pbApplicationPolicy` 가 null 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-118">Either `pwzReferenceIdentity` or `pbApplicationPolicy` is a null reference.</span></span>|  
|<span data-ttu-id="cda13-119">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="cda13-119">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="cda13-120">`cbAppPolicySize`너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-120">`cbAppPolicySize` is too small.</span></span>|  
|<span data-ttu-id="cda13-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cda13-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cda13-122">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cda13-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cda13-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cda13-124">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-124">The call timed out.</span></span>|  
|<span data-ttu-id="cda13-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cda13-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cda13-126">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cda13-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cda13-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cda13-128">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cda13-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cda13-129">E_FAIL</span></span>|<span data-ttu-id="cda13-130">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cda13-131">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cda13-132">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cda13-133">설명</span><span class="sxs-lookup"><span data-stu-id="cda13-133">Remarks</span></span>  
 <span data-ttu-id="cda13-134">`EvaluatePolicy` 메서드를 사용 하면 호스트를 호스트 관련 어셈블리를 유지 하기 위해 바인딩 정책을 버전 관리 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-134">The `EvaluatePolicy` method allows the host to influence binding policy to maintain host-specific assembly versioning requirements.</span></span> <span data-ttu-id="cda13-135">정책 엔진 자체는 CLR에 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-135">The policy engine itself remains inside the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cda13-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cda13-136">Requirements</span></span>  
 <span data-ttu-id="cda13-137">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cda13-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cda13-138">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cda13-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cda13-139">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="cda13-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cda13-140">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cda13-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda13-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cda13-141">See Also</span></span>  
 [<span data-ttu-id="cda13-142">ICLRHostBindingPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cda13-142">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)
