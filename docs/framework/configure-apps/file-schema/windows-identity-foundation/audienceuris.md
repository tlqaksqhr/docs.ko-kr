---
title: '&lt;audienceUris&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 69c96698b309a789b4527c76e1fe8b8b99811a19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaudienceurisgt"></a><span data-ttu-id="72844-102">&lt;audienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="72844-102">&lt;audienceUris&gt;</span></span>
<span data-ttu-id="72844-103">신뢰 당사자 (RP)의 식별자를 허용 하는 Uri의 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72844-103">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="72844-104">허용 되는 대상 Uri 중 하나에 대해 범위가 지정 되지 않는 한 토큰을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72844-104">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="72844-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="72844-105">\<system.identityModel></span></span>  
<span data-ttu-id="72844-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="72844-106">\<identityConfiguration></span></span>  
<span data-ttu-id="72844-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="72844-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="72844-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="72844-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="72844-109">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="72844-109">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72844-110">구문</span><span class="sxs-lookup"><span data-stu-id="72844-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72844-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="72844-111">Attributes and Elements</span></span>  
 <span data-ttu-id="72844-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="72844-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72844-113">특성</span><span class="sxs-lookup"><span data-stu-id="72844-113">Attributes</span></span>  
  
|<span data-ttu-id="72844-114">특성</span><span class="sxs-lookup"><span data-stu-id="72844-114">Attribute</span></span>|<span data-ttu-id="72844-115">설명</span><span class="sxs-lookup"><span data-stu-id="72844-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="72844-116">모드</span><span class="sxs-lookup"><span data-stu-id="72844-116">mode</span></span>|<span data-ttu-id="72844-117"><xref:System.IdentityModel.Selectors.AudienceUriMode> audience 제한 들어오는 토큰을 적용할지 여부를 지정 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="72844-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="72844-118">가능한 값은 "항상", "Never" 및 "BearerKeyOnly"입니다.</span><span class="sxs-lookup"><span data-stu-id="72844-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="72844-119">기본값은 "Always".</span><span class="sxs-lookup"><span data-stu-id="72844-119">The default is "Always".</span></span> <span data-ttu-id="72844-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="72844-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72844-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="72844-121">Child Elements</span></span>  
  
|<span data-ttu-id="72844-122">요소</span><span class="sxs-lookup"><span data-stu-id="72844-122">Element</span></span>|<span data-ttu-id="72844-123">설명</span><span class="sxs-lookup"><span data-stu-id="72844-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="72844-124">추가 하 여 지정 된 URI는 `value` audienceUris 컬렉션에 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72844-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="72844-125">`value` 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="72844-125">The `value` attribute is required.</span></span> <span data-ttu-id="72844-126">URI는 대/소문자 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="72844-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="72844-127">AudienceUris 컬렉션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="72844-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="72844-128">모든 식별자는 컬렉션에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72844-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="72844-129">제거 하 여 지정 된 URI는 `value` audienceUris 컬렉션에서 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="72844-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="72844-130">`value` 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="72844-130">The `value` attribute is required.</span></span> <span data-ttu-id="72844-131">URI는 대/소문자 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="72844-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="72844-132">부모 요소</span><span class="sxs-lookup"><span data-stu-id="72844-132">Parent Elements</span></span>  
  
|<span data-ttu-id="72844-133">요소</span><span class="sxs-lookup"><span data-stu-id="72844-133">Element</span></span>|<span data-ttu-id="72844-134">설명</span><span class="sxs-lookup"><span data-stu-id="72844-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72844-135">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="72844-135">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="72844-136">구성 컬렉션의 보안 토큰 처리기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="72844-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72844-137">설명</span><span class="sxs-lookup"><span data-stu-id="72844-137">Remarks</span></span>  
 <span data-ttu-id="72844-138">기본적으로 컬렉션은 비어 있습니다. 사용 하 여 `<add>`, `<clear>`, 및 `<remove>` 요소 컬렉션을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72844-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="72844-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>및 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 개체가 사용을 구성 하려면 대상 그룹 URI 컬렉션의에서 값 허용 대상 그룹 URI 제한 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="72844-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="72844-140">`<audienceUris>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="72844-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="72844-141">컬렉션에 추가 하는 개별 URI로 표시 됩니다는 <xref:System.IdentityModel.Configuration.AudienceUriElement> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="72844-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="72844-142">사용은 `<audienceUris>` 의 자식 요소로 요소는 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소, 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72844-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="72844-143">설정에는 `<securityTokenHandlerConfiguration>` 요소에서 재정의 된 `<identityConfiguration>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="72844-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72844-144">예</span><span class="sxs-lookup"><span data-stu-id="72844-144">Example</span></span>  
 <span data-ttu-id="72844-145">다음 XML에는 응용 프로그램에 대해 허용 가능한 대상 그룹 Uri를 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="72844-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="72844-146">이 예제에서는 단일 URI를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="72844-146">This example configures a single URI.</span></span> <span data-ttu-id="72844-147">이 URI에 대해 범위가 지정 된 토큰 수락, 다른 항목을 모두 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72844-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
