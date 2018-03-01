---
title: "ICLRDomainManager::SetAppDomainManagerType 메서드"
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
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 37c94da8295a0ebb96d45e3a8f122d96bc2126c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="452da-102">ICLRDomainManager::SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="452da-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="452da-103">파생 된 형식을 지정 된 <xref:System.AppDomainManager?displayProperty=nameWithType> 기본 응용 프로그램 도메인을 초기화 하는 데 사용할 응용 프로그램 도메인 관리자의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="452da-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="452da-104">구문</span><span class="sxs-lookup"><span data-stu-id="452da-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="452da-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="452da-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="452da-106">[in] 응용 프로그램 도메인 관리자 형식을; 포함 하는 어셈블리의 표시 이름 예: "AdMgrExample, Version = 1.0.0.0, Culture = neutral, PublicKeyToken = 6856bccf150f00b3"입니다.</span><span class="sxs-lookup"><span data-stu-id="452da-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="452da-107">[in] 네임 스페이스를 포함 하는 응용 프로그램 도메인 관리자의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="452da-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="452da-108">[in] 조합을 [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) 응용 프로그램 도메인 관리자에 대 한 정보를 제공 하는 열거형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="452da-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="452da-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="452da-109">Return Value</span></span>  
 <span data-ttu-id="452da-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="452da-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="452da-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="452da-111">HRESULT</span></span>|<span data-ttu-id="452da-112">설명</span><span class="sxs-lookup"><span data-stu-id="452da-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="452da-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="452da-113">S_OK</span></span>|<span data-ttu-id="452da-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="452da-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="452da-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="452da-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="452da-116">공용 언어 런타임 (CLR) 프로세스에 로드 되지 않았습니다 또는 CLR 중인 상태를 관리 코드를 실행 하거나 호출을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="452da-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="452da-117">설명</span><span class="sxs-lookup"><span data-stu-id="452da-117">Remarks</span></span>  
 <span data-ttu-id="452da-118">현재 유일한 정의 대 한 값 `dwInitializeDomainFlags` 은 `eInitializeNewDomainFlags_NoSecurityChanges`, 공용 언어 런타임 (CLR)을 설정 하는 응용 프로그램 도메인 관리자 실행 하는 동안 보안 설정을 수정 하지 것입니다이 알려주는 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="452da-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="452da-119">이렇게 하면 조건부가 있는 어셈블리 로드를 최적화 하기 위해 CLR <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성 (APTCA).</span><span class="sxs-lookup"><span data-stu-id="452da-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="452da-120">이 어셈블리 집합의 전이적 closure 크면 시작 시간에 크게 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="452da-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="452da-121">호스트를 지정 하는 경우 `eInitializeNewDomainFlags_NoSecurityChanges` 응용 프로그램 도메인 관리자에 대 한는 <xref:System.InvalidOperationException> 응용 프로그램 도메인의 보안을 수정 하 려 하는 경우에 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="452da-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="452da-122">호출 된 [iclrcontrol:: Setappdomainmanagertype](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)호출 하는 것과 같습니다 `ICLRDomainManager::SetAppDomainManagerType` 와 `eInitializeNewDomainFlags_None`합니다.</span><span class="sxs-lookup"><span data-stu-id="452da-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="452da-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="452da-123">Requirements</span></span>  
 <span data-ttu-id="452da-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="452da-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="452da-125">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="452da-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="452da-126">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="452da-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="452da-127">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="452da-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="452da-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="452da-128">See Also</span></span>  
 [<span data-ttu-id="452da-129">호스팅</span><span class="sxs-lookup"><span data-stu-id="452da-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="452da-130">ICLRDomainManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="452da-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [<span data-ttu-id="452da-131">EInitializeNewDomainFlags 열거형</span><span class="sxs-lookup"><span data-stu-id="452da-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
