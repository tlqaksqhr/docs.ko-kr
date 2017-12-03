---
title: "&lt;knownCertificates&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30b3216842b602745ad40d1743175350aba78296
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltknowncertificatesgt"></a><span data-ttu-id="ee452-102">&lt;knownCertificates&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="ee452-102">&lt;add&gt; of &lt;knownCertificates&gt;</span></span>
<span data-ttu-id="ee452-103">알려진 인증서 컬렉션에 X.509 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-103">Adds an X.509 certificate to the collection of known certificates.</span></span>  
  
 <span data-ttu-id="ee452-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ee452-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ee452-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="ee452-105">\<behaviors></span></span>  
<span data-ttu-id="ee452-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="ee452-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="ee452-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="ee452-107">\<behavior></span></span>  
<span data-ttu-id="ee452-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="ee452-108">\<serviceCredentials></span></span>  
<span data-ttu-id="ee452-109">\<u t h ></span><span class="sxs-lookup"><span data-stu-id="ee452-109">\<issuedTokenAuthentication></span></span>  
<span data-ttu-id="ee452-110">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="ee452-110">\<knownCertificates></span></span>  
<span data-ttu-id="ee452-111">\<add></span><span class="sxs-lookup"><span data-stu-id="ee452-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee452-112">구문</span><span class="sxs-lookup"><span data-stu-id="ee452-112">Syntax</span></span>  
  
```xml  
<knownCertificates>   
   <add findValue="String"  
      storeLocation="CurrentUser/LocalMachine"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee452-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ee452-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ee452-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee452-115">특성</span><span class="sxs-lookup"><span data-stu-id="ee452-115">Attributes</span></span>  
  
|<span data-ttu-id="ee452-116">특성</span><span class="sxs-lookup"><span data-stu-id="ee452-116">Attribute</span></span>|<span data-ttu-id="ee452-117">설명</span><span class="sxs-lookup"><span data-stu-id="ee452-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee452-118">findValue</span><span class="sxs-lookup"><span data-stu-id="ee452-118">findValue</span></span>|<span data-ttu-id="ee452-119">문자열.</span><span class="sxs-lookup"><span data-stu-id="ee452-119">String.</span></span> <span data-ttu-id="ee452-120">검색할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-120">The value to search for.</span></span>|  
|<span data-ttu-id="ee452-121">storeLocation</span><span class="sxs-lookup"><span data-stu-id="ee452-121">storeLocation</span></span>|<span data-ttu-id="ee452-122">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-122">Enumeration.</span></span> <span data-ttu-id="ee452-123">검색할 두 저장소 위치 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-123">One of the two store locations to search.</span></span>|  
|<span data-ttu-id="ee452-124">storeName</span><span class="sxs-lookup"><span data-stu-id="ee452-124">storeName</span></span>|<span data-ttu-id="ee452-125">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-125">Enumeration.</span></span> <span data-ttu-id="ee452-126">검색할 시스템 저장소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-126">One of the system stores to search.</span></span>|  
|<span data-ttu-id="ee452-127">x509FindType</span><span class="sxs-lookup"><span data-stu-id="ee452-127">x509FindType</span></span>|<span data-ttu-id="ee452-128">열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-128">Enumeration.</span></span> <span data-ttu-id="ee452-129">검색할 인증서 필드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-129">One of the certificate fields to search.</span></span>|  
  
## <a name="findvalue-attribute"></a><span data-ttu-id="ee452-130">findValue 특성</span><span class="sxs-lookup"><span data-stu-id="ee452-130">findValue Attribute</span></span>  
  
|<span data-ttu-id="ee452-131">값</span><span class="sxs-lookup"><span data-stu-id="ee452-131">Value</span></span>|<span data-ttu-id="ee452-132">설명</span><span class="sxs-lookup"><span data-stu-id="ee452-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ee452-133">문자열</span><span class="sxs-lookup"><span data-stu-id="ee452-133">String</span></span>|<span data-ttu-id="ee452-134">이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-134">The value depends on the field (specified by the X509FindType attribute) being searched.</span></span> <span data-ttu-id="ee452-135">예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-135">For example, if searching for a thumbprint, the value must be a string of hexadecimal numbers.</span></span>|  
  
## <a name="x509findtype-attribute"></a><span data-ttu-id="ee452-136">x509FindType 특성</span><span class="sxs-lookup"><span data-stu-id="ee452-136">x509FindType Attribute</span></span>  
  
|<span data-ttu-id="ee452-137">값</span><span class="sxs-lookup"><span data-stu-id="ee452-137">Value</span></span>|<span data-ttu-id="ee452-138">설명</span><span class="sxs-lookup"><span data-stu-id="ee452-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ee452-139">열거형</span><span class="sxs-lookup"><span data-stu-id="ee452-139">Enumeration</span></span>|<span data-ttu-id="ee452-140">값에는 FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-140">Values include: FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier.</span></span>|  
  
## <a name="storelocation-attribute"></a><span data-ttu-id="ee452-141">storeLocation 특성</span><span class="sxs-lookup"><span data-stu-id="ee452-141">storeLocation Attribute</span></span>  
  
|<span data-ttu-id="ee452-142">값</span><span class="sxs-lookup"><span data-stu-id="ee452-142">Value</span></span>|<span data-ttu-id="ee452-143">설명</span><span class="sxs-lookup"><span data-stu-id="ee452-143">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ee452-144">열거형</span><span class="sxs-lookup"><span data-stu-id="ee452-144">Enumeration</span></span>|<span data-ttu-id="ee452-145">CurrentUser 또는 LocalMachine입니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-145">CurrentUser or LocalMachine.</span></span>|  
  
## <a name="storename-attribute"></a><span data-ttu-id="ee452-146">storeName 특성</span><span class="sxs-lookup"><span data-stu-id="ee452-146">storeName Attribute</span></span>  
  
|<span data-ttu-id="ee452-147">값</span><span class="sxs-lookup"><span data-stu-id="ee452-147">Value</span></span>|<span data-ttu-id="ee452-148">설명</span><span class="sxs-lookup"><span data-stu-id="ee452-148">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ee452-149">열거형</span><span class="sxs-lookup"><span data-stu-id="ee452-149">Enumeration</span></span>|<span data-ttu-id="ee452-150">값에는 AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople 및 TrustedPublisher가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-150">Values include: AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople, and TrustedPublisher.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee452-151">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ee452-151">Child Elements</span></span>  
 <span data-ttu-id="ee452-152">없음</span><span class="sxs-lookup"><span data-stu-id="ee452-152">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee452-153">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ee452-153">Parent Elements</span></span>  
  
|<span data-ttu-id="ee452-154">요소</span><span class="sxs-lookup"><span data-stu-id="ee452-154">Element</span></span>|<span data-ttu-id="ee452-155">설명</span><span class="sxs-lookup"><span data-stu-id="ee452-155">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee452-156">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="ee452-156">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|<span data-ttu-id="ee452-157">보안 토큰의 유효성을 검사하기 위해 STS(보안 토큰 서비스)에서 제공하는 X.509 인증서 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-157">Represents a collection of X.509 certificates that are provided by a Security Token Service (STS) for validation of security tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee452-158">설명</span><span class="sxs-lookup"><span data-stu-id="ee452-158">Remarks</span></span>  
 <span data-ttu-id="ee452-159">발급된 토큰 시나리오에는 3단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-159">The issued token scenario has three stages.</span></span> <span data-ttu-id="ee452-160">첫 번째 단계에서 서비스에 액세스 하려는 클라이언트 라고는 *보안 토큰 서비스*합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-160">In the first stage, a client trying to access a service is referred to a *secure token service*.</span></span> <span data-ttu-id="ee452-161">보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML(Security Assertions Markup Language) 토큰이라는 클라이언트 토큰을 발급합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-161">The secure token service then authenticates the client and subsequently issues the client a token, typically a Security Assertions Markup Language (SAML) token.</span></span> <span data-ttu-id="ee452-162">클라이언트는 토큰을 통해 서비스에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-162">The client then returns to the service with the token.</span></span> <span data-ttu-id="ee452-163">서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-163">The service examines the token for data that allows the service to authenticate the token and therefore the client.</span></span> <span data-ttu-id="ee452-164">토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-164">To authenticate the token, the certificate the secure token service uses must be known to the service.</span></span>  
  
 <span data-ttu-id="ee452-165">[ \<a u t h >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) 요소는 이러한 보안 토큰 서비스 인증서에 대 한 리포지토리입니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-165">The [\<issuedTokenAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) element is the repository for any such secure token service certificates.</span></span> <span data-ttu-id="ee452-166">인증서를 추가 하려면 사용 된 [ \<knownCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-166">To add certificates, use the [\<knownCertificates>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md).</span></span> <span data-ttu-id="ee452-167">삽입 된 [ \<추가 > 요소 \<knownCertificates > 요소](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) 다음 예제와 같이 각 인증서에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-167">Insert an [\<add> element \<knownCertificates> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md) for each certificate, as shown in the following example.</span></span>  
  
```xml  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 <span data-ttu-id="ee452-168">기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-168">By default, the certificates must be obtained from a secure token service.</span></span> <span data-ttu-id="ee452-169">이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-169">These "known" certificates ensure that only legitimate clients can access a service.</span></span>  
  
 <span data-ttu-id="ee452-170">이 구성 요소를 사용 하는 자세한 방법은 뿐만 아니라 페더레이션된 서비스에서 인증에 대 한 클라이언트에 필요한 조건, 참조 [하는 방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-170">To review conditions required for a client to be authenticated by a federated service, as well as more information on using this configuration element, see [How to: Configure Credentials on a Federation Service](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md).</span></span> <span data-ttu-id="ee452-171">페더레이션된 시나리오에 대 한 자세한 내용은 참조 [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-171">For more information about federated scenarios, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee452-172">예제</span><span class="sxs-lookup"><span data-stu-id="ee452-172">Example</span></span>  
 <span data-ttu-id="ee452-173">다음 예제에서는 모든 STS 인증서에 대해 리포지토리에 인증서를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ee452-173">The following example adds certificate to the repository for any STS certificates.</span></span>  
  
```xml  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <serviceCredentials>  
   <issuedTokenAuthentication>  
    <knownCertificates>  
     <add findValue="www.contoso.com" storeLocation="LocalMachine"   
           storeName="CertificateAuthority"  
           x509FindType="FindByIssuerName" />  
     </knownCertificates>  
    </issuedTokenAuthentication>  
   </serviceCredentials>  
  </behavior>  
 </serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee452-174">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee452-174">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>  
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>  
 [<span data-ttu-id="ee452-175">\<knownCertificates ></span><span class="sxs-lookup"><span data-stu-id="ee452-175">\<knownCertificates></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)  
 [<span data-ttu-id="ee452-176">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="ee452-176">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="ee452-177">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="ee452-177">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="ee452-178">방법: 페더레이션 서비스에서 자격 증명 구성</span><span class="sxs-lookup"><span data-stu-id="ee452-178">How to: Configure Credentials on a Federation Service</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="ee452-179">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="ee452-179">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
