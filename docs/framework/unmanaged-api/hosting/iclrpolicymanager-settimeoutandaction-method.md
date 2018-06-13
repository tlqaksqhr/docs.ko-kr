---
title: ICLRPolicyManager::SetTimeoutAndAction 메서드
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c375fdffacccb27c20878c4e6adef9dd947148e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435526"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a><span data-ttu-id="b9a1c-102">ICLRPolicyManager::SetTimeoutAndAction 메서드</span><span class="sxs-lookup"><span data-stu-id="b9a1c-102">ICLRPolicyManager::SetTimeoutAndAction Method</span></span>
<span data-ttu-id="b9a1c-103">지정된 된 작업에 대 한 제한 시간 값을 설정 하 고 공용 언어 런타임 (CLR)는 작업이 수행 될 때 수행 해야 하는 정책 동작을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-103">Sets a timeout value for the specified operation, and specifies the policy action the common language runtime (CLR) should take when the operation occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9a1c-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9a1c-104">Syntax</span></span>  
  
```  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9a1c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9a1c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="b9a1c-106">[in] 중 하나는 [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) 를 설정할 시간 제한 및 정책에 대 한 작업을 나타내는 값을 `action`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to set the timeout and policy `action`.</span></span> <span data-ttu-id="b9a1c-107">다음 값이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="b9a1c-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="b9a1c-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="b9a1c-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="b9a1c-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="b9a1c-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b9a1c-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="b9a1c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="b9a1c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="b9a1c-112">[in] 새 시간 제한 값, 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="b9a1c-113">값이 무한 원인 `operation` 시간 초과를 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-113">A value of INFINITE causes `operation` never to time out.</span></span>  
  
 `action`  
 <span data-ttu-id="b9a1c-114">[in] 중 하나는 [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) CLR 때 수행 해야 정책 작업을 나타내는 값을 `operation` 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-114">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action that the CLR should take when `operation` occurs.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9a1c-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="b9a1c-115">Return Value</span></span>  
  
|<span data-ttu-id="b9a1c-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9a1c-116">HRESULT</span></span>|<span data-ttu-id="b9a1c-117">설명</span><span class="sxs-lookup"><span data-stu-id="b9a1c-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b9a1c-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="b9a1c-118">S_OK</span></span>|<span data-ttu-id="b9a1c-119">`SetTimeoutAndAction` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-119">`SetTimeoutAndAction` returned successfully.</span></span>|  
|<span data-ttu-id="b9a1c-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b9a1c-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b9a1c-121">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b9a1c-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b9a1c-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b9a1c-123">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-123">The call timed out.</span></span>|  
|<span data-ttu-id="b9a1c-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b9a1c-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b9a1c-125">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b9a1c-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b9a1c-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b9a1c-127">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b9a1c-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b9a1c-128">E_FAIL</span></span>|<span data-ttu-id="b9a1c-129">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b9a1c-130">E_FAIL을 반환 하는 메서드 후 CLR을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-130">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b9a1c-131">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b9a1c-132">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b9a1c-132">E_INVALIDARG</span></span>|<span data-ttu-id="b9a1c-133">시간 초과 설정할 수 없습니다 지정 된 `operation`, 또는 잘못 된 값에 대 한 제공 된 `action`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-133">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `action`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9a1c-134">설명</span><span class="sxs-lookup"><span data-stu-id="b9a1c-134">Remarks</span></span>  
 <span data-ttu-id="b9a1c-135">`SetTimeoutAndAction` 기능을 캡슐화는 [iclrpolicymanager:: Settimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) 및 [iclrpolicymanager:: Setactionontimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) 메서드를 다음 두 가지 방법에 대 한 순차적 호출 대신 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-135">`SetTimeoutAndAction` encapsulates the capabilities of the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) and [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) methods, and can be called in place of sequential calls to these two methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b9a1c-136">CLR 작업에 대 한 제한 시간 동작으로 정책 작업 값 중 일부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-136">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="b9a1c-137">유효한 값에 대 한 이러한 두 가지 방법에 대 한 항목의 설명 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-137">See the Remarks sections of the topics for these two methods for valid values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9a1c-138">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9a1c-138">Requirements</span></span>  
 <span data-ttu-id="b9a1c-139">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9a1c-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9a1c-140">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b9a1c-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b9a1c-141">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="b9a1c-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9a1c-142">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9a1c-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a1c-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9a1c-143">See Also</span></span>  
 [<span data-ttu-id="b9a1c-144">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="b9a1c-144">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="b9a1c-145">EPolicyAction 열거형</span><span class="sxs-lookup"><span data-stu-id="b9a1c-145">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="b9a1c-146">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9a1c-146">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="b9a1c-147">SetActionOnTimeout 메서드</span><span class="sxs-lookup"><span data-stu-id="b9a1c-147">SetActionOnTimeout Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md)  
 [<span data-ttu-id="b9a1c-148">Iclrpolicymanager:: Settimeoutandaction</span><span class="sxs-lookup"><span data-stu-id="b9a1c-148">ICLRPolicyManager::SetTimeoutAndAction</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeoutandaction-method.md)
