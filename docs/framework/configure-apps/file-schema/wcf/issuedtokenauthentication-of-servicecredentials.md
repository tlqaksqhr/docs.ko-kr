---
title: "&lt;serviceCredentials&gt;의 &lt;issuedTokenAuthentication&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c2e288f-f603-4d13-839a-0fd6d1981bec
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2d8e3c7df0108c6f8656827c6c0795dcb9fe3a9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuedtokenauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="167b8-102">&lt;serviceCredentials&gt;의 &lt;issuedTokenAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="167b8-102">&lt;issuedTokenAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="167b8-103">서비스 자격 증명으로 발급된 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-103">Specifies a custom token issued as a service credential.</span></span>  
  
 <span data-ttu-id="167b8-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="167b8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="167b8-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="167b8-105">\<behaviors></span></span>  
<span data-ttu-id="167b8-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="167b8-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="167b8-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="167b8-107">\<behavior></span></span>  
<span data-ttu-id="167b8-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="167b8-108">\<serviceCredentials></span></span>  
<span data-ttu-id="167b8-109">\<u t h ></span><span class="sxs-lookup"><span data-stu-id="167b8-109">\<issuedTokenAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="167b8-110">구문</span><span class="sxs-lookup"><span data-stu-id="167b8-110">Syntax</span></span>  
  
```xml  
<issuedTokenAuthentication   
   allowUntrustedRsaIssuers="Boolean"  
   audienceUriMode="Always/BearerKeyOnly/Never"  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   samlSerializer="String"  
    trustedStoreLocation="CurrentUser/LocalMachine">  
      <allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
      </allowedAudienceUris>  
      <knownCertificates>   
         <add findValue="String"  
                 storeLocation="CurrentUser/LocalMachine"  
                storeName=" CurrentUser/LocalMachine"  
                x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
      </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="167b8-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="167b8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="167b8-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="167b8-113">특성</span><span class="sxs-lookup"><span data-stu-id="167b8-113">Attributes</span></span>  
  
|<span data-ttu-id="167b8-114">특성</span><span class="sxs-lookup"><span data-stu-id="167b8-114">Attribute</span></span>|<span data-ttu-id="167b8-115">설명</span><span class="sxs-lookup"><span data-stu-id="167b8-115">Description</span></span>|  
|---------------|-----------------|  
|`allowedAudienceUris`|<span data-ttu-id="167b8-116"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 보안 토큰의 대상 URI 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-116">Gets the set of target URIs for which the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token can be targeted for in order to be considered valid by a <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> instance.</span></span> <span data-ttu-id="167b8-117">이 특성 사용에 대한 자세한 내용은 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="167b8-117">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>.</span></span>|  
|`allowUntrustedRsaIssuers`|<span data-ttu-id="167b8-118">신뢰할 수 없는 RSA 인증서 발급자에 대한 허용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-118">A Boolean value that specifies if untrusted RSA certificate issuers are allowed.</span></span><br /><br /> <span data-ttu-id="167b8-119">인증서는 신뢰성 확인을 위해 CA(인증 기관)의 서명을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-119">Certificates are signed by certification authorities (CAs) to verify authenticity.</span></span> <span data-ttu-id="167b8-120">신뢰할 수 없는 발급자는 인증서 서명을 위한 신뢰성이 지정되지 않은 CA입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-120">An untrusted issuer is a CA that is not specified to be trusted to sign certificates.</span></span>|  
|`audienceUriMode`|<span data-ttu-id="167b8-121"><xref:System.IdentityModel.Tokens.SamlSecurityToken> 보안 토큰의 <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>에 대해 유효성을 검사해야 하는지 여부를 지정하는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-121">Gets a value that specifies whether the <xref:System.IdentityModel.Tokens.SamlSecurityToken> security token's <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition> should be validated.</span></span> <span data-ttu-id="167b8-122">이 값은 <xref:System.IdentityModel.Selectors.AudienceUriMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-122">This value is of type <xref:System.IdentityModel.Selectors.AudienceUriMode>.</span></span> <span data-ttu-id="167b8-123">이 특성 사용에 대한 자세한 내용은 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="167b8-123">For more information on using this attribute, see <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>.</span></span>|  
|`certificateValidationMode`|<span data-ttu-id="167b8-124">인증서 유효성 검사 모드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-124">Sets the certificate validation mode.</span></span> <span data-ttu-id="167b8-125"><xref:System.ServiceModel.Security.X509CertificateValidationMode>의 유효한 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-125">One of the valid values of <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span></span> <span data-ttu-id="167b8-126">`Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-126">If set to `Custom`, then a `customCertificateValidator` must also be supplied.</span></span> <span data-ttu-id="167b8-127">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-127">The default is `ChainTrust`.</span></span>|  
|`customCertificateValidatorType`|<span data-ttu-id="167b8-128">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-128">Optional string.</span></span> <span data-ttu-id="167b8-129">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-129">A type and assembly used to validate a custom type.</span></span> <span data-ttu-id="167b8-130">이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-130">This attribute must be set when `certificateValidationMode` is set to `Custom`.</span></span>|  
|`revocationMode`|<span data-ttu-id="167b8-131">해지 검사의 수행 여부 및 이를 온라인 또는 오프라인으로 수행할지를 지정하는 해지 모드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-131">Sets the revocation mode that specifies whether a revocation check occurs, and if it is performed online or offline.</span></span> <span data-ttu-id="167b8-132">이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-132">This attribute is of type <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span></span>|  
|`samlSerializer`|<span data-ttu-id="167b8-133">서비스 자격 증명에 사용되는 SamlSerializer의 형식을 지정하는 선택적 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-133">An optional string attribute that specifies the type of SamlSerializer that is used for the service credential.</span></span> <span data-ttu-id="167b8-134">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-134">The default is an empty string.</span></span>|  
|`trustedStoreLocation`|<span data-ttu-id="167b8-135">선택적 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-135">Optional enumeration.</span></span> <span data-ttu-id="167b8-136">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-136">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="167b8-137">자식 요소</span><span class="sxs-lookup"><span data-stu-id="167b8-137">Child Elements</span></span>  
  
|<span data-ttu-id="167b8-138">요소</span><span class="sxs-lookup"><span data-stu-id="167b8-138">Element</span></span>|<span data-ttu-id="167b8-139">설명</span><span class="sxs-lookup"><span data-stu-id="167b8-139">Description</span></span>|  
|-------------|-----------------|  
|`knownCertificates`|<span data-ttu-id="167b8-140">서비스 자격 증명에 대해 신뢰할 수 있는 발급자를 지정하는 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> 요소의 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-140">Specifies a collection of <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement> elements that specifies trusted issuers for the service credential.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="167b8-141">부모 요소</span><span class="sxs-lookup"><span data-stu-id="167b8-141">Parent Elements</span></span>  
  
|<span data-ttu-id="167b8-142">요소</span><span class="sxs-lookup"><span data-stu-id="167b8-142">Element</span></span>|<span data-ttu-id="167b8-143">설명</span><span class="sxs-lookup"><span data-stu-id="167b8-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="167b8-144">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="167b8-144">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="167b8-145">서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-145">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="167b8-146">설명</span><span class="sxs-lookup"><span data-stu-id="167b8-146">Remarks</span></span>  
 <span data-ttu-id="167b8-147">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-147">The issued token scenario has three stages.</span></span> <span data-ttu-id="167b8-148">첫 번째 단계에서 서비스에 액세스 하려는 클라이언트 라고는 *보안 토큰 서비스*합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-148">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="167b8-149">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-149">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="167b8-150">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-150">The client then returns to the service with the token.</span></span> <span data-ttu-id="167b8-151">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-151">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="167b8-152">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-152">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="167b8-153">이 요소는 이러한 보안 토큰 서비스 인증서에 대한 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-153">This element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="167b8-154">인증서를 추가 하려면 사용 된 [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-154">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="167b8-155">삽입 된 [ \<추가 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) 다음 예제와 같이 각 인증서에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-155">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthorization>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="167b8-156">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-156">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="167b8-157">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-157">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="167b8-158">이 구성 요소를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="167b8-158">For more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="167b8-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="167b8-159">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.IssuedTokenAuthentication%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
 [<span data-ttu-id="167b8-160">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="167b8-160">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="167b8-161">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="167b8-161">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)
