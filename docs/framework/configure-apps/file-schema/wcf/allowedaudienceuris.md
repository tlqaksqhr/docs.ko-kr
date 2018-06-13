---
title: '&lt;a d d&gt;'
ms.date: 03/30/2017
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
ms.openlocfilehash: b7a4ae230e9b8788d9ac23147a3fcf21637dadaf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754082"
---
# <a name="ltallowedaudienceurisgt"></a><span data-ttu-id="92116-102">&lt;a d d&gt;</span><span class="sxs-lookup"><span data-stu-id="92116-102">&lt;allowedAudienceUris&gt;</span></span>
<span data-ttu-id="92116-103"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92116-103">Represents a collection of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>  
  
 <span data-ttu-id="92116-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="92116-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="92116-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="92116-105">\<behaviors></span></span>  
<span data-ttu-id="92116-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="92116-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="92116-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="92116-107">\<behavior></span></span>  
<span data-ttu-id="92116-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="92116-108">\<serviceCredentials></span></span>  
<span data-ttu-id="92116-109">\<u t h ></span><span class="sxs-lookup"><span data-stu-id="92116-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="92116-110">\<a d d ></span><span class="sxs-lookup"><span data-stu-id="92116-110">\<allowedAudienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92116-111">구문</span><span class="sxs-lookup"><span data-stu-id="92116-111">Syntax</span></span>  
  
```xml  
<allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
</allowedAudienceUris>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="92116-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="92116-112">Attributes and Elements</span></span>  
 <span data-ttu-id="92116-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92116-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="92116-114">특성</span><span class="sxs-lookup"><span data-stu-id="92116-114">Attributes</span></span>  
 <span data-ttu-id="92116-115">없음</span><span class="sxs-lookup"><span data-stu-id="92116-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="92116-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="92116-116">Child Elements</span></span>  
  
|<span data-ttu-id="92116-117">요소</span><span class="sxs-lookup"><span data-stu-id="92116-117">Element</span></span>|<span data-ttu-id="92116-118">설명</span><span class="sxs-lookup"><span data-stu-id="92116-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92116-119">\<add></span><span class="sxs-lookup"><span data-stu-id="92116-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<span data-ttu-id="92116-120"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="92116-120">Adds a target Uri for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="92116-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="92116-121">Parent Elements</span></span>  
  
|<span data-ttu-id="92116-122">요소</span><span class="sxs-lookup"><span data-stu-id="92116-122">Element</span></span>|<span data-ttu-id="92116-123">설명</span><span class="sxs-lookup"><span data-stu-id="92116-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="92116-124">\<u t h ></span><span class="sxs-lookup"><span data-stu-id="92116-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="92116-125">서비스 자격 증명으로 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92116-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92116-126">설명</span><span class="sxs-lookup"><span data-stu-id="92116-126">Remarks</span></span>  
 <span data-ttu-id="92116-127">STS(보안 토큰 서비스)를 사용하여 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 보안 토큰을 발급하는 페더레이션 응용 프로그램에서는 이 컬렉션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92116-127">You should use this collection in a federated application that utilizes a security token service (STS) that issues <xref:System.IdentityModel.Tokens.SamlSecurityToken> security tokens.</span></span> <span data-ttu-id="92116-128">STS는 보안 토큰을 발급할 때 보안 토큰에 <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>을 추가하여 보안 토큰을 사용할 웹 서비스의 URI를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92116-128">When the STS issues the security token, it can specify the URI of the Web services for which the security token is intended by adding a <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> to the security token.</span></span> <span data-ttu-id="92116-129">따라서 발급된 보안 토큰이 해당 웹 서비스용인지 검사하도록 지정하여 수신자 웹 서비스의 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>가 이를 확인하도록 할 수 있습니다. 이렇게 하려면 다음을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="92116-129">That allows the <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> for the recipient Web service to verify that the issued security token is intended for this Web service by specifying that this check should happen by doing the following:</span></span>  
  
-   <span data-ttu-id="92116-130">`audienceUriMode`의 `<issuedTokenAuthentication>` 특성을 <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> 또는 <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="92116-130">Set the `audienceUriMode` attribute of `<issuedTokenAuthentication>` to <xref:System.IdentityModel.Selectors.AudienceUriMode.Always> or <xref:System.IdentityModel.Selectors.AudienceUriMode.BearerKeyOnly>.</span></span>  
  
-   <span data-ttu-id="92116-131">이 컬렉션에 URI를 추가하여 유효한 URI 집합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92116-131">Specify the set of valid URIs, by adding the URIs to this collection.</span></span>  
  
 <span data-ttu-id="92116-132">자세한 내용은 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="92116-132">For more information, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>.</span></span>  
  
 <span data-ttu-id="92116-133">이 구성 요소를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="92116-133">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92116-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92116-134">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>  
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>  
 [<span data-ttu-id="92116-135">\<u t h ></span><span class="sxs-lookup"><span data-stu-id="92116-135">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="92116-136">\<add></span><span class="sxs-lookup"><span data-stu-id="92116-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)  
 [<span data-ttu-id="92116-137">보안 동작</span><span class="sxs-lookup"><span data-stu-id="92116-137">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="92116-138">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="92116-138">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="92116-139">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="92116-139">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
