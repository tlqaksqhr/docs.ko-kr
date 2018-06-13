---
title: ICLRRuntimeHost::ExecuteInAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteInAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 96352ec5eaba67489dbef999925c56475611746c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435970"
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="6df3f-102">ICLRRuntimeHost::ExecuteInAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="6df3f-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="6df3f-103">지정 된 <xref:System.AppDomain> 지정 된 관리 코드를 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6df3f-104">구문</span><span class="sxs-lookup"><span data-stu-id="6df3f-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6df3f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6df3f-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="6df3f-106">[in] 숫자 ID는 <xref:System.AppDomain> 지정 된 메서드를 실행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="6df3f-107">[in] 지정 된 실행 하는 함수에 대 한 포인터 <xref:System.AppDomain>합니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="6df3f-108">[in] 불투명 호출자가 할당 한 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="6df3f-109">이 매개 변수는 공용 언어 런타임 (CLR)으로 도메인 콜백에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="6df3f-110">런타임에서 관리 되는 힙 메모리; 않습니다. 할당 및 수명이이 메모리의 호출자에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6df3f-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="6df3f-111">Return Value</span></span>  
  
|<span data-ttu-id="6df3f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6df3f-112">HRESULT</span></span>|<span data-ttu-id="6df3f-113">설명</span><span class="sxs-lookup"><span data-stu-id="6df3f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6df3f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="6df3f-114">S_OK</span></span>|<span data-ttu-id="6df3f-115">`ExecuteInAppDomain` 성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="6df3f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6df3f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6df3f-117">CLR은 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6df3f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6df3f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6df3f-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-119">The call timed out.</span></span>|  
|<span data-ttu-id="6df3f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6df3f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6df3f-121">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6df3f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6df3f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6df3f-123">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6df3f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6df3f-124">E_FAIL</span></span>|<span data-ttu-id="6df3f-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6df3f-126">메서드가 E_FAIL을 반환 하는 경우 CLR을 하는 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6df3f-127">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6df3f-128">설명</span><span class="sxs-lookup"><span data-stu-id="6df3f-128">Remarks</span></span>  
 <span data-ttu-id="6df3f-129">`ExecuteInAppDomain` 호스트가 제어할 수 있도록 관리 되는 <xref:System.AppDomain> 에 지정된 된 관리 되는 메서드를 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="6df3f-130">값에 해당 하는 응용 프로그램 도메인 식별자의 값을 얻을 수는 <xref:System.AppDomain.Id%2A> 속성을 호출 하 여 [GetCurrentAppDomainId 메서드](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6df3f-131">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6df3f-131">Requirements</span></span>  
 <span data-ttu-id="6df3f-132">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6df3f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6df3f-133">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6df3f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6df3f-134">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6df3f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6df3f-135">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6df3f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6df3f-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6df3f-136">See Also</span></span>  
 [<span data-ttu-id="6df3f-137">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6df3f-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
