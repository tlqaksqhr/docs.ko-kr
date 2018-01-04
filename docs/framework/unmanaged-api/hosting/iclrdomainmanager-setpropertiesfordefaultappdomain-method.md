---
title: "ICLRDomainManager::SetPropertiesForDefaultAppDomain 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de72568f5908dc89c9a4105c927cfba6c7366b80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="ab408-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="ab408-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="ab408-103">기본 응용 프로그램 도메인 초기화를 사용할 수 있는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab408-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab408-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab408-104">Syntax</span></span>  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab408-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab408-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="ab408-106">[in] 항목 수가 `pwszPropertyNames` 및 `pwszPropertyValues`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab408-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="ab408-107">[in] 배열 속성 이름 또는 속성이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ab408-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="ab408-108">현재이 메서드가에서 인식 되는 유일한 속성 이름을 "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="ab408-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="ab408-109">[in] 배열 속성 값 또는 속성이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ab408-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ab408-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="ab408-110">Return Value</span></span>  
 <span data-ttu-id="ab408-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ab408-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ab408-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ab408-112">HRESULT</span></span>|<span data-ttu-id="ab408-113">설명</span><span class="sxs-lookup"><span data-stu-id="ab408-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ab408-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ab408-114">S_OK</span></span>|<span data-ttu-id="ab408-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ab408-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="ab408-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="ab408-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="ab408-117">`pwszPropertyNames`이 방법으로 인식 되지 않은 속성 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab408-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ab408-118">설명</span><span class="sxs-lookup"><span data-stu-id="ab408-118">Remarks</span></span>  
 <span data-ttu-id="ab408-119">"PARTIAL_TRUST_VISIBLE_ASSEMBLIES"에 대 한 속성 값은 조건부가 있는 어셈블리 목록 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 사용 하 여 특성 (APTCA)의 <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> 기본 응용 프로그램에서 부분적으로 신뢰할 수 있는 호출자에 게 표시 되어야 하는 플래그 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="ab408-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab408-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab408-120">Requirements</span></span>  
 <span data-ttu-id="ab408-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ab408-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab408-122">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ab408-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ab408-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ab408-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ab408-124">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab408-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab408-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab408-125">See Also</span></span>  
 [<span data-ttu-id="ab408-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="ab408-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="ab408-127">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab408-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
