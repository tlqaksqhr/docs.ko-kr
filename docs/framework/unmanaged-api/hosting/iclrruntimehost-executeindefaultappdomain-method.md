---
title: "ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteInDefaultAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteInDefaultAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInDefaultAppDomain method [.NET Framework hosting]
- ExecuteInDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 30b5cf9a-a762-4bd4-be12-d6c1442b78b1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec4cf37150cab7b52066a884b6fe117b0e611106
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostexecuteindefaultappdomain-method"></a><span data-ttu-id="c02bb-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="c02bb-102">ICLRRuntimeHost::ExecuteInDefaultAppDomain Method</span></span>
<span data-ttu-id="c02bb-103">지정된 된 관리 되는 어셈블리에 지정 된 형식의 지정된 된 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-103">Calls the specified method of the specified type in the specified managed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c02bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="c02bb-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInDefaultAppDomain (  
    [in] LPCWSTR pwzAssemblyPath,  
    [in] LPCWSTR pwzTypeName,   
    [in] LPCWSTR pwzMethodName,  
    [in] LPCWSTR pwzArgument,  
    [out] DWORD *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c02bb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c02bb-105">Parameters</span></span>  
 `pwzAssemblyPath`  
 <span data-ttu-id="c02bb-106">[in] 에 대 한 경로 <xref:System.Reflection.Assembly> 정의 하는 <xref:System.Type> 호출 방법은 합니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-106">[in] The path to the <xref:System.Reflection.Assembly> that defines the <xref:System.Type> whose method is to be invoked.</span></span>  
  
 `pwzTypeName`  
 <span data-ttu-id="c02bb-107">[in] 이름에서 <xref:System.Type> 호출할 메서드를 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-107">[in] The name of the <xref:System.Type> that defines the method to invoke.</span></span>  
  
 `pwzMethodName`  
 <span data-ttu-id="c02bb-108">[in] 호출할 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-108">[in] The name of the method to invoke.</span></span>  
  
 `pwzArgument`  
 <span data-ttu-id="c02bb-109">[in] 메서드에 전달할 문자열 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-109">[in] The string parameter to pass to the method.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="c02bb-110">[out] 호출 된 메서드에서 반환 된 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-110">[out] The integer value returned by the invoked method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c02bb-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c02bb-111">Return Value</span></span>  
  
|<span data-ttu-id="c02bb-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c02bb-112">HRESULT</span></span>|<span data-ttu-id="c02bb-113">설명</span><span class="sxs-lookup"><span data-stu-id="c02bb-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c02bb-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="c02bb-114">S_OK</span></span>|<span data-ttu-id="c02bb-115">`ExecuteInDefaultAppDomain`성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-115">`ExecuteInDefaultAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="c02bb-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c02bb-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c02bb-117">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c02bb-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c02bb-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c02bb-119">호출 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-119">The call timed out.</span></span>|  
|<span data-ttu-id="c02bb-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c02bb-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c02bb-121">호출자에 게 잠금을 소유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c02bb-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c02bb-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c02bb-123">차단 된 스레드 이벤트 취소 되었습니다 또는 파이버가 기다리던 합니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c02bb-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c02bb-124">E_FAIL</span></span>|<span data-ttu-id="c02bb-125">알 수 없는 치명적인 오류가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c02bb-126">메서드가 E_FAIL을 반환 하는 경우 CRL을 프로세스 내에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-126">If a method returns E_FAIL, the CRL is no longer usable within the process.</span></span> <span data-ttu-id="c02bb-127">호스팅 방법에 대 한 후속 호출 HOST_E_CLRNOTAVAILABLE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c02bb-128">설명</span><span class="sxs-lookup"><span data-stu-id="c02bb-128">Remarks</span></span>  
 <span data-ttu-id="c02bb-129">호출 된 메서드에 다음 서명이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-129">The invoked method must have the following signature:</span></span>  
  
```  
static int pwzMethodName (String pwzArgument)  
```  
  
 <span data-ttu-id="c02bb-130">여기서 `pwzMethodName` 호출 된 메서드의 이름을 나타내는 및 `pwzArgument` 해당 메서드에 매개 변수로 전달 된 문자열 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-130">where `pwzMethodName` represents the name of the invoked method, and `pwzArgument` represents the string value passed as a parameter to that method.</span></span> <span data-ttu-id="c02bb-131">HRESULT 값 s_ok이 고에 설정 된 경우 `pReturnValue` 호출 된 메서드에서 반환 된 정수 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-131">If the HRESULT value is set to S_OK, `pReturnValue` is set to the integer value returned by the invoked method.</span></span> <span data-ttu-id="c02bb-132">그렇지 않으면 `pReturnValue` 설정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-132">Otherwise, `pReturnValue` is not set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c02bb-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c02bb-133">Requirements</span></span>  
 <span data-ttu-id="c02bb-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c02bb-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c02bb-135">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c02bb-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c02bb-136">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c02bb-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c02bb-137">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c02bb-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c02bb-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c02bb-138">See Also</span></span>  
 [<span data-ttu-id="c02bb-139">ICLRRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c02bb-139">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
