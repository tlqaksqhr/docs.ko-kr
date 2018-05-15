---
title: '&lt;knownCertificates&gt;'
ms.date: 03/30/2017
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
ms.openlocfilehash: 394ae246ad29a0747f3814b36fae2557b04c235a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltknowncertificatesgt"></a><span data-ttu-id="36e47-102">&lt;knownCertificates&gt;</span><span class="sxs-lookup"><span data-stu-id="36e47-102">&lt;knownCertificates&gt;</span></span>
<span data-ttu-id="36e47-103">STS(보안 토큰 서비스)에서 발급한 보안 자격 증명을 인증하기 위해 제공된 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-103">Represents a collection of X.509 certificates that are provided to authenticate security credentials issued from a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="36e47-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="36e47-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="36e47-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="36e47-105">\<behaviors></span></span>  
<span data-ttu-id="36e47-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="36e47-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="36e47-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="36e47-107">\<behavior></span></span>  
<span data-ttu-id="36e47-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="36e47-108">\<serviceCredentials></span></span>  
<span data-ttu-id="36e47-109">\<u t h ></span><span class="sxs-lookup"><span data-stu-id="36e47-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="36e47-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="36e47-110">\<knownCertificates></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36e47-111">구문</span><span class="sxs-lookup"><span data-stu-id="36e47-111">Syntax</span></span>  
  
```xml  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36e47-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="36e47-112">Attributes and Elements</span></span>  
 <span data-ttu-id="36e47-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36e47-114">특성</span><span class="sxs-lookup"><span data-stu-id="36e47-114">Attributes</span></span>  
 <span data-ttu-id="36e47-115">없음</span><span class="sxs-lookup"><span data-stu-id="36e47-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="36e47-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="36e47-116">Child Elements</span></span>  
  
|<span data-ttu-id="36e47-117">요소</span><span class="sxs-lookup"><span data-stu-id="36e47-117">Element</span></span>|<span data-ttu-id="36e47-118">설명</span><span class="sxs-lookup"><span data-stu-id="36e47-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36e47-119">\<add></span><span class="sxs-lookup"><span data-stu-id="36e47-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|<span data-ttu-id="36e47-120">컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-120">Adds an X.509 certificate to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36e47-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="36e47-121">Parent Elements</span></span>  
  
|<span data-ttu-id="36e47-122">요소</span><span class="sxs-lookup"><span data-stu-id="36e47-122">Element</span></span>|<span data-ttu-id="36e47-123">설명</span><span class="sxs-lookup"><span data-stu-id="36e47-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36e47-124">\<u t h ></span><span class="sxs-lookup"><span data-stu-id="36e47-124">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|<span data-ttu-id="36e47-125">서비스 자격 증명으로 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-125">Specifies a token issued as a service credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36e47-126">설명</span><span class="sxs-lookup"><span data-stu-id="36e47-126">Remarks</span></span>  
 <span data-ttu-id="36e47-127">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-127">The issued token scenario has three stages.</span></span> <span data-ttu-id="36e47-128">첫 번째 단계에서 서비스에 액세스 하려는 클라이언트 라고는 *보안 토큰 서비스*합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-128">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="36e47-129">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-129">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="36e47-130">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-130">The client then returns to the service with the token.</span></span> <span data-ttu-id="36e47-131">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-131">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="36e47-132">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-132">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="36e47-133">[ \<a u t h >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) 요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-133">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="36e47-134">인증서를 추가 하려면 사용 된 [ \<knownCertificates > 요소](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-134">To add certificates, use the [\<knownCertificates> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="36e47-135">삽입 된 [ \<추가 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) 다음 예제와 같이 각 인증서에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-135">Insert an [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="36e47-136">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-136">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="36e47-137">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-137">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="36e47-138">이 구성 요소를 사용 하는 자세한 방법은 뿐만 아니라 페더레이션된 서비스에서 인증에 대 한 클라이언트에 필요한 조건, 참조 [하는 방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-138">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="36e47-139">페더레이션된 시나리오에 대 한 자세한 내용은 참조 [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-139">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="36e47-140">구성에서 컬렉션을 채우는 방법을 보여 주는 예제를 보려면 [ \<추가 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36e47-140">For an example that shows how to populate the collection in configuration, see [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36e47-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36e47-141">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="36e47-142">\<add></span><span class="sxs-lookup"><span data-stu-id="36e47-142">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="36e47-143">\<u t h ></span><span class="sxs-lookup"><span data-stu-id="36e47-143">\<issuedTokenAuthentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)  
 [<span data-ttu-id="36e47-144">보안 동작</span><span class="sxs-lookup"><span data-stu-id="36e47-144">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="36e47-145">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="36e47-145">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="36e47-146">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="36e47-146">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="36e47-147">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="36e47-147">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="36e47-148">\<add></span><span class="sxs-lookup"><span data-stu-id="36e47-148">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)  
 [<span data-ttu-id="36e47-149">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="36e47-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
