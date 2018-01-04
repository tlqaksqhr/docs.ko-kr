---
title: "ICLRPolicyManager::SetActionOnFailure 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRPolicyManager.SetActionOnFailure
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4440b36485ed900b5e64adcead2525dbb7d5206e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a><span data-ttu-id="36369-102">ICLRPolicyManager::SetActionOnFailure 메서드</span><span class="sxs-lookup"><span data-stu-id="36369-102">ICLRPolicyManager::SetActionOnFailure Method</span></span>
<span data-ttu-id="36369-103">공용 언어 런타임 (CLR)의 오류가 발생할 경우 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36369-103">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36369-104">구문</span><span class="sxs-lookup"><span data-stu-id="36369-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36369-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36369-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="36369-106">[in] 중 하나는 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) 의 조치를 사용 하는 오류 유형을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="36369-106">[in] One of the [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values, indicating the type of failure for which to take action.</span></span>  
  
 `action`  
 <span data-ttu-id="36369-107">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 오류가 발생할 경우 수행할 작업을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="36369-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action to be taken when a failure occurs.</span></span> <span data-ttu-id="36369-108">지원 되는 값 목록은 설명 섹션을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="36369-108">For a list of supported values, see the Remarks section.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36369-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="36369-109">Return Value</span></span>  
  
|<span data-ttu-id="36369-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="36369-110">HRESULT</span></span>|<span data-ttu-id="36369-111">설명</span><span class="sxs-lookup"><span data-stu-id="36369-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="36369-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="36369-112">S_OK</span></span>|<span data-ttu-id="36369-113">`SetActionOnFailure`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36369-113">`SetActionOnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="36369-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="36369-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="36369-115">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36369-115">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="36369-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="36369-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="36369-117">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36369-117">The call timed out.</span></span>|  
|<span data-ttu-id="36369-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="36369-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="36369-119">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36369-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="36369-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="36369-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="36369-121">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="36369-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="36369-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="36369-122">E_FAIL</span></span>|<span data-ttu-id="36369-123">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="36369-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="36369-124">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36369-124">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="36369-125">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="36369-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="36369-126">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="36369-126">E_INVALIDARG</span></span>|<span data-ttu-id="36369-127">지정된 된 작업에 대 한 정책 작업을 설정할 수 없습니다 또는 작업에 대 한 정책 작업이 잘못 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="36369-127">A policy action cannot be set for the specified operation, or an invalid policy action was specified for the operation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36369-128">설명</span><span class="sxs-lookup"><span data-stu-id="36369-128">Remarks</span></span>  
 <span data-ttu-id="36369-129">기본적으로 CLR 즉, 메모리 리소스를 할당 하지 못하면 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="36369-129">By default, the CLR throws an exception when it fails to allocate a resource such as memory.</span></span> <span data-ttu-id="36369-130">`SetActionOnFailure`호스트를 정책 작업을 실패를 지정 하 여이 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36369-130">`SetActionOnFailure` allows the host to override this behavior by specifying the policy action to take upon failure.</span></span> <span data-ttu-id="36369-131">다음 표에서 조합을 보여 줍니다. [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) 및 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) 지원 되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="36369-131">The following table shows the combinations of [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) and [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values that are supported.</span></span> <span data-ttu-id="36369-132">(에서 FAIL_ 접두사를 생략 하는 [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) 값입니다.)</span><span class="sxs-lookup"><span data-stu-id="36369-132">(The FAIL_ prefix is omitted from [EClrFailure](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md) values.)</span></span>  
  
||<span data-ttu-id="36369-133">NonCriticalResource</span><span class="sxs-lookup"><span data-stu-id="36369-133">NonCriticalResource</span></span>|<span data-ttu-id="36369-134">CriticalResource</span><span class="sxs-lookup"><span data-stu-id="36369-134">CriticalResource</span></span>|<span data-ttu-id="36369-135">FatalRuntime</span><span class="sxs-lookup"><span data-stu-id="36369-135">FatalRuntime</span></span>|<span data-ttu-id="36369-136">OrphanedLock</span><span class="sxs-lookup"><span data-stu-id="36369-136">OrphanedLock</span></span>|<span data-ttu-id="36369-137">StackOverflow</span><span class="sxs-lookup"><span data-stu-id="36369-137">StackOverflow</span></span>|<span data-ttu-id="36369-138">AccessViolation</span><span class="sxs-lookup"><span data-stu-id="36369-138">AccessViolation</span></span>|<span data-ttu-id="36369-139">CodeContract</span><span class="sxs-lookup"><span data-stu-id="36369-139">CodeContract</span></span>|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|<span data-ttu-id="36369-140">X</span><span class="sxs-lookup"><span data-stu-id="36369-140">X</span></span>|<span data-ttu-id="36369-141">X</span><span class="sxs-lookup"><span data-stu-id="36369-141">X</span></span>||||<span data-ttu-id="36369-142">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-142">N/A</span></span>||  
|<span data-ttu-id="36369-143">eThrowException</span><span class="sxs-lookup"><span data-stu-id="36369-143">eThrowException</span></span>|<span data-ttu-id="36369-144">X</span><span class="sxs-lookup"><span data-stu-id="36369-144">X</span></span>|<span data-ttu-id="36369-145">X</span><span class="sxs-lookup"><span data-stu-id="36369-145">X</span></span>||||<span data-ttu-id="36369-146">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-146">N/A</span></span>||  
|`eAbortThread`|<span data-ttu-id="36369-147">X</span><span class="sxs-lookup"><span data-stu-id="36369-147">X</span></span>|<span data-ttu-id="36369-148">X</span><span class="sxs-lookup"><span data-stu-id="36369-148">X</span></span>||||<span data-ttu-id="36369-149">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-149">N/A</span></span>|<span data-ttu-id="36369-150">X</span><span class="sxs-lookup"><span data-stu-id="36369-150">X</span></span>|  
|`eRudeAbortThread`|<span data-ttu-id="36369-151">X</span><span class="sxs-lookup"><span data-stu-id="36369-151">X</span></span>|<span data-ttu-id="36369-152">X</span><span class="sxs-lookup"><span data-stu-id="36369-152">X</span></span>||||<span data-ttu-id="36369-153">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-153">N/A</span></span>|<span data-ttu-id="36369-154">X</span><span class="sxs-lookup"><span data-stu-id="36369-154">X</span></span>|  
|`eUnloadAppDomain`|<span data-ttu-id="36369-155">X</span><span class="sxs-lookup"><span data-stu-id="36369-155">X</span></span>|<span data-ttu-id="36369-156">X</span><span class="sxs-lookup"><span data-stu-id="36369-156">X</span></span>||<span data-ttu-id="36369-157">X</span><span class="sxs-lookup"><span data-stu-id="36369-157">X</span></span>||<span data-ttu-id="36369-158">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-158">N/A</span></span>|<span data-ttu-id="36369-159">X</span><span class="sxs-lookup"><span data-stu-id="36369-159">X</span></span>|  
|`eRudeUnloadAppDomain`|<span data-ttu-id="36369-160">X</span><span class="sxs-lookup"><span data-stu-id="36369-160">X</span></span>|<span data-ttu-id="36369-161">X</span><span class="sxs-lookup"><span data-stu-id="36369-161">X</span></span>||<span data-ttu-id="36369-162">X</span><span class="sxs-lookup"><span data-stu-id="36369-162">X</span></span>|<span data-ttu-id="36369-163">X</span><span class="sxs-lookup"><span data-stu-id="36369-163">X</span></span>|<span data-ttu-id="36369-164">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-164">N/A</span></span>|<span data-ttu-id="36369-165">X</span><span class="sxs-lookup"><span data-stu-id="36369-165">X</span></span>|  
|`eExitProcess`|<span data-ttu-id="36369-166">X</span><span class="sxs-lookup"><span data-stu-id="36369-166">X</span></span>|<span data-ttu-id="36369-167">X</span><span class="sxs-lookup"><span data-stu-id="36369-167">X</span></span>||<span data-ttu-id="36369-168">X</span><span class="sxs-lookup"><span data-stu-id="36369-168">X</span></span>|<span data-ttu-id="36369-169">X</span><span class="sxs-lookup"><span data-stu-id="36369-169">X</span></span>|<span data-ttu-id="36369-170">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-170">N/A</span></span>|<span data-ttu-id="36369-171">X</span><span class="sxs-lookup"><span data-stu-id="36369-171">X</span></span>|  
|<span data-ttu-id="36369-172">eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="36369-172">eFastExitProcess</span></span>|<span data-ttu-id="36369-173">X</span><span class="sxs-lookup"><span data-stu-id="36369-173">X</span></span>|<span data-ttu-id="36369-174">X</span><span class="sxs-lookup"><span data-stu-id="36369-174">X</span></span>||<span data-ttu-id="36369-175">X</span><span class="sxs-lookup"><span data-stu-id="36369-175">X</span></span>|<span data-ttu-id="36369-176">X</span><span class="sxs-lookup"><span data-stu-id="36369-176">X</span></span>|<span data-ttu-id="36369-177">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-177">N/A</span></span>||  
|`eRudeExitProcess`|<span data-ttu-id="36369-178">X</span><span class="sxs-lookup"><span data-stu-id="36369-178">X</span></span>|<span data-ttu-id="36369-179">X</span><span class="sxs-lookup"><span data-stu-id="36369-179">X</span></span>|<span data-ttu-id="36369-180">X</span><span class="sxs-lookup"><span data-stu-id="36369-180">X</span></span>|<span data-ttu-id="36369-181">X</span><span class="sxs-lookup"><span data-stu-id="36369-181">X</span></span>|<span data-ttu-id="36369-182">X</span><span class="sxs-lookup"><span data-stu-id="36369-182">X</span></span>|<span data-ttu-id="36369-183">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-183">N/A</span></span>||  
|`eDisableRuntime`|<span data-ttu-id="36369-184">X</span><span class="sxs-lookup"><span data-stu-id="36369-184">X</span></span>|<span data-ttu-id="36369-185">X</span><span class="sxs-lookup"><span data-stu-id="36369-185">X</span></span>|<span data-ttu-id="36369-186">X</span><span class="sxs-lookup"><span data-stu-id="36369-186">X</span></span>|<span data-ttu-id="36369-187">X</span><span class="sxs-lookup"><span data-stu-id="36369-187">X</span></span>|<span data-ttu-id="36369-188">X</span><span class="sxs-lookup"><span data-stu-id="36369-188">X</span></span>|<span data-ttu-id="36369-189">N/A</span><span class="sxs-lookup"><span data-stu-id="36369-189">N/A</span></span>||  
  
## <a name="requirements"></a><span data-ttu-id="36369-190">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36369-190">Requirements</span></span>  
 <span data-ttu-id="36369-191">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36369-191">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36369-192">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="36369-192">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="36369-193">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="36369-193">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36369-194">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36369-194">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36369-195">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36369-195">See Also</span></span>  
 [<span data-ttu-id="36369-196">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="36369-196">EClrFailure Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrfailure-enumeration.md)  
 [<span data-ttu-id="36369-197">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="36369-197">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="36369-198">ICLRControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36369-198">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="36369-199">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="36369-199">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
