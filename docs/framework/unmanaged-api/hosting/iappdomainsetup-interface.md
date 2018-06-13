---
title: IAppDomainSetup 인터페이스
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcbc446eabcfcbc28c830f8860bde726c8eb6e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434770"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="fec47-102">IAppDomainSetup 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fec47-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="fec47-103">구성할 수 있는 속성을 제공는 <xref:System.AppDomain?displayProperty=nameWithType> 유형 호출 하기 전에 [icorruntimehost:: Createdomainex](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="fec47-104">속성</span><span class="sxs-lookup"><span data-stu-id="fec47-104">Properties</span></span>  
  
|<span data-ttu-id="fec47-105">속성</span><span class="sxs-lookup"><span data-stu-id="fec47-105">Property</span></span>|<span data-ttu-id="fec47-106">설명</span><span class="sxs-lookup"><span data-stu-id="fec47-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="fec47-107">응용 프로그램을 포함 하는 디렉터리의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="fec47-108">응용 프로그램의 이름을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="fec47-109">영역 이름을 관련 가져오거나 응용 프로그램에 파일을 섀도 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="fec47-110">응용 프로그램에 대 한 구성 파일의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="fec47-111">동적으로 생성 되는 파일 저장 및 액세스 되는 디렉터리의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="fec47-112">이 도메인과 연결 된 라이선스 파일의 경로 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="fec47-113">와 결합 하는 디렉터리 목록을 가져오거나 설정 합니다.는 <xref:System.AppDomainSetup.ApplicationBase%2A> 디렉터리를 전용 어셈블리를 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="fec47-114">포함 또는 제외 하는 문자열 값을 가져오거나 설정 합니다. <xref:System.AppDomainSetup.ApplicationBase%2A> 응용 프로그램에 대 한 검색 경로에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="fec47-115">어셈블리 섀도 복사를 포함 하는 디렉터리의 이름을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="fec47-116">섀도 복사 설정 되어 있는지 여부 또는 해제 여부를 나타내는 문자열을 가져오거나 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="fec47-117">유효한 값은 "true" 또는 "false"입니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fec47-118">설명</span><span class="sxs-lookup"><span data-stu-id="fec47-118">Remarks</span></span>  
 <span data-ttu-id="fec47-119">`IAppDomainSetup` 인터페이스의 관리 되는 해당 <xref:System.IAppDomainSetup> 인터페이스는 <xref:System.AppDomainSetup> 구현을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="fec47-120">참조 <xref:System.IAppDomainSetup?displayProperty=nameWithType> 에 대 한 해당 속성에 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="fec47-121">`IAppDomainSetup` 에 추가할 수 있는 어셈블리 바인딩 정보를 나타내는 <xref:System.AppDomain> 만들어지기 전에 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="fec47-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="fec47-122">예를 들어 호스트를 설정할 수는 <xref:System.AppDomainSetup.ApplicationBase%2A> 관리 되는 어셈블리 속성을 공용 언어 런타임 (CLR)를 검색 되는 루트 디렉터리를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fec47-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fec47-123">Requirements</span></span>  
 <span data-ttu-id="fec47-124">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fec47-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fec47-125">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fec47-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fec47-126">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="fec47-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fec47-127">**.NET framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fec47-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fec47-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fec47-128">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup>  
 [<span data-ttu-id="fec47-129">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fec47-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
