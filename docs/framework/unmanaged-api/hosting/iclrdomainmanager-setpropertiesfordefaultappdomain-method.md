---
title: ICLRDomainManager::SetPropertiesForDefaultAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetPropertiesForDefaultAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain
helpviewer_keywords:
- ICLRDomainManager::SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
- SetPropertiesForDefaultAppDomain method [.NET Framework hosting]
ms.assetid: 43e61c4b-c435-45ec-9ef6-c68403aa4200
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18db77b42af47b76bf1b3b66748d586c4c41dbd7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433556"
---
# <a name="iclrdomainmanagersetpropertiesfordefaultappdomain-method"></a><span data-ttu-id="7f372-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="7f372-102">ICLRDomainManager::SetPropertiesForDefaultAppDomain Method</span></span>
<span data-ttu-id="7f372-103">기본 응용 프로그램 도메인 초기화를 사용할 수 있는 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f372-103">Sets properties that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f372-104">구문</span><span class="sxs-lookup"><span data-stu-id="7f372-104">Syntax</span></span>  
  
```  
HRESULT SetPropertiesForDefaultAppDomain(  
    [in] DWORD nProperties,  
    [in] LPCWSTR *pwszPropertyNames,  
    [in] LPCWSTR *pwszPropertyValues  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7f372-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7f372-105">Parameters</span></span>  
 `nProperties`  
 <span data-ttu-id="7f372-106">[in] 항목 수가 `pwszPropertyNames` 및 `pwszPropertyValues`합니다.</span><span class="sxs-lookup"><span data-stu-id="7f372-106">[in] The number of entries in `pwszPropertyNames` and `pwszPropertyValues`.</span></span>  
  
 `pwszPropertyNames`  
 <span data-ttu-id="7f372-107">[in] 배열 속성 이름 또는 속성이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="7f372-107">[in] An array of property names, or null if there are no properties.</span></span> <span data-ttu-id="7f372-108">현재이 메서드가에서 인식 되는 유일한 속성 이름을 "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span><span class="sxs-lookup"><span data-stu-id="7f372-108">Currently, the only property name that is recognized by this method is "PARTIAL_TRUST_VISIBLE_ASSEMBLIES".</span></span>  
  
 `pwszPropertyValues`  
 <span data-ttu-id="7f372-109">[in] 배열 속성 값 또는 속성이 없는 경우 null입니다.</span><span class="sxs-lookup"><span data-stu-id="7f372-109">[in] An array of property values, or null if there are no properties.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7f372-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="7f372-110">Return Value</span></span>  
 <span data-ttu-id="7f372-111">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7f372-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7f372-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7f372-112">HRESULT</span></span>|<span data-ttu-id="7f372-113">설명</span><span class="sxs-lookup"><span data-stu-id="7f372-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7f372-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="7f372-114">S_OK</span></span>|<span data-ttu-id="7f372-115">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f372-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="7f372-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span><span class="sxs-lookup"><span data-stu-id="7f372-116">HRESULT_FROM_WIN32(ERROR_UNKNOWN_PROPERTY)</span></span>|<span data-ttu-id="7f372-117">`pwszPropertyNames` 이 방법으로 인식 되지 않은 속성 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f372-117">`pwszPropertyNames` includes a property name that is not recognized by this method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f372-118">설명</span><span class="sxs-lookup"><span data-stu-id="7f372-118">Remarks</span></span>  
 <span data-ttu-id="7f372-119">"PARTIAL_TRUST_VISIBLE_ASSEMBLIES"에 대 한 속성 값은 조건부가 있는 어셈블리 목록 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 사용 하 여 특성 (APTCA)의 <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> 기본 응용 프로그램에서 부분적으로 신뢰할 수 있는 호출자에 게 표시 되어야 하는 플래그 도메인입니다.</span><span class="sxs-lookup"><span data-stu-id="7f372-119">The property value for "PARTIAL_TRUST_VISIBLE_ASSEMBLIES" is a list of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute with the <xref:System.Security.PartialTrustVisibilityLevel.NotVisibleByDefault?displayProperty=nameWithType> flag, which are to be made visible to partially trusted callers in the default application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f372-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7f372-120">Requirements</span></span>  
 <span data-ttu-id="7f372-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7f372-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f372-122">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7f372-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7f372-123">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7f372-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f372-124">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f372-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f372-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f372-125">See Also</span></span>  
 [<span data-ttu-id="7f372-126">호스팅</span><span class="sxs-lookup"><span data-stu-id="7f372-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="7f372-127">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f372-127">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
