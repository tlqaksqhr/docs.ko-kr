---
title: '&lt;캐시&gt;'
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2a9766b826eb7a708b4b4e99b6bd984f9fc76812
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltcachesgt"></a><span data-ttu-id="32c22-102">&lt;캐시&gt;</span><span class="sxs-lookup"><span data-stu-id="32c22-102">&lt;caches&gt;</span></span>
<span data-ttu-id="32c22-103">세션 토큰에서 토큰 재생 검색에 사용 되는 캐시에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-103">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="32c22-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="32c22-104">\<system.identityModel></span></span>  
<span data-ttu-id="32c22-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="32c22-105">\<identityConfiguration></span></span>  
<span data-ttu-id="32c22-106">\<캐시 ></span><span class="sxs-lookup"><span data-stu-id="32c22-106">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c22-107">구문</span><span class="sxs-lookup"><span data-stu-id="32c22-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32c22-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="32c22-108">Attributes and Elements</span></span>  
 <span data-ttu-id="32c22-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32c22-110">특성</span><span class="sxs-lookup"><span data-stu-id="32c22-110">Attributes</span></span>  
 <span data-ttu-id="32c22-111">없음</span><span class="sxs-lookup"><span data-stu-id="32c22-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32c22-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="32c22-112">Child Elements</span></span>  
  
|<span data-ttu-id="32c22-113">요소</span><span class="sxs-lookup"><span data-stu-id="32c22-113">Element</span></span>|<span data-ttu-id="32c22-114">설명</span><span class="sxs-lookup"><span data-stu-id="32c22-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32c22-115">\<sessionSecurityTokenCache ></span><span class="sxs-lookup"><span data-stu-id="32c22-115">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="32c22-116">세션 토큰에 대 한 캐시 서비스 또는 보안 토큰 처리기 컬렉션에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-116">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="32c22-117">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="32c22-117">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="32c22-118">토큰 재생 캐시는 서비스 또는 보안 토큰 처리기 컬렉션에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-118">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32c22-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="32c22-119">Parent Elements</span></span>  
  
|<span data-ttu-id="32c22-120">요소</span><span class="sxs-lookup"><span data-stu-id="32c22-120">Element</span></span>|<span data-ttu-id="32c22-121">설명</span><span class="sxs-lookup"><span data-stu-id="32c22-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32c22-122">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="32c22-122">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="32c22-123">서비스 수준 id 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-123">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="32c22-124">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="32c22-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="32c22-125">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32c22-126">설명</span><span class="sxs-lookup"><span data-stu-id="32c22-126">Remarks</span></span>  
 <span data-ttu-id="32c22-127">A `<caches>` 에서 서비스 수준에서 요소를 지정할 수 있습니다는 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준 아래에 `<securityTokenHandlerConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-127">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="32c22-128">서비스에 지정 된 토큰 처리기 컬렉션에 대 한 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-128">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="32c22-129">`<caches>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-129">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="32c22-130">구성 된 캐시도 표시 됩니다는 <xref:System.IdentityModel.Configuration.IdentityModelCaches> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="32c22-130">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32c22-131">예제</span><span class="sxs-lookup"><span data-stu-id="32c22-131">Example</span></span>  
 <span data-ttu-id="32c22-132">다음 XML에 세션 보안 토큰을 보관 하기 위한 사용자 지정 캐시의 구성을 보여 줍니다 (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="32c22-132">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="32c22-133">구성에서 가져온 것은 `ClaimsAwareWebFarm` 샘플.</span><span class="sxs-lookup"><span data-stu-id="32c22-133">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
