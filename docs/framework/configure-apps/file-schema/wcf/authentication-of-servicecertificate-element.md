---
title: "&lt;serviceCertificate&gt; 요소의 &lt;authentication&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 733b67b4-08a1-4d25-9741-10046f9357ef
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cb2f567b47f66b378cc6e0a5d5e96441ea65c1ac
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltauthenticationgt-of-ltservicecertificategt-element"></a><span data-ttu-id="33b79-102">&lt;serviceCertificate&gt; 요소의 &lt;authentication&gt;</span><span class="sxs-lookup"><span data-stu-id="33b79-102">&lt;authentication&gt; of &lt;serviceCertificate&gt; Element</span></span>
<span data-ttu-id="33b79-103">SSL/TLS 협상을 사용하여 가져온 서비스 인증서를 인증하기 위해 클라이언트 프록시에서 사용하는 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-103">Specifies the settings used by the client proxy to authenticate service certificates that are obtained using SSL/TLS negotiation.</span></span>  
  
 <span data-ttu-id="33b79-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="33b79-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="33b79-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="33b79-105">\<behaviors></span></span>  
<span data-ttu-id="33b79-106">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="33b79-106">endpointBehaviors section</span></span>  
<span data-ttu-id="33b79-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="33b79-107">\<behavior></span></span>  
<span data-ttu-id="33b79-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="33b79-108">\<clientCredentials></span></span>  
<span data-ttu-id="33b79-109">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="33b79-109">\<serviceCertificate></span></span>  
<span data-ttu-id="33b79-110">\<인증 ></span><span class="sxs-lookup"><span data-stu-id="33b79-110">\<authentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33b79-111">구문</span><span class="sxs-lookup"><span data-stu-id="33b79-111">Syntax</span></span>  
  
```xml  
<authentication customCertificateValidatorType="String" certificateValidationMode="None/PeerTrust/ChainTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"   
trustedStoreLocation="LocalMachine/CurrentUser" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="33b79-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="33b79-112">Attributes and Elements</span></span>  
 <span data-ttu-id="33b79-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="33b79-114">특성</span><span class="sxs-lookup"><span data-stu-id="33b79-114">Attributes</span></span>  
  
|<span data-ttu-id="33b79-115">특성</span><span class="sxs-lookup"><span data-stu-id="33b79-115">Attribute</span></span>|<span data-ttu-id="33b79-116">설명</span><span class="sxs-lookup"><span data-stu-id="33b79-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="33b79-117">customCertificateValidatorType</span><span class="sxs-lookup"><span data-stu-id="33b79-117">customCertificateValidatorType</span></span>|<span data-ttu-id="33b79-118">문자열.</span><span class="sxs-lookup"><span data-stu-id="33b79-118">String.</span></span> <span data-ttu-id="33b79-119">사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-119">A type and assembly used to validate a custom type.</span></span>|  
|<span data-ttu-id="33b79-120">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="33b79-120">certificateValidationMode</span></span>|<span data-ttu-id="33b79-121">자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-121">Specifies one of three modes used to validate credentials.</span></span> <span data-ttu-id="33b79-122">`Custom`으로 설정되면 customCertificateValidator도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-122">If set to `Custom`, then a customCertificateValidator must also be supplied.</span></span> <span data-ttu-id="33b79-123">기본값은 `ChainTrust`입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-123">The default is `ChainTrust`.</span></span>|  
|<span data-ttu-id="33b79-124">revocationMode</span><span class="sxs-lookup"><span data-stu-id="33b79-124">revocationMode</span></span>|<span data-ttu-id="33b79-125">CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-125">One of the modes used to check for a revoked certificate lists (CRL).</span></span> <span data-ttu-id="33b79-126">기본값은 `Online`입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-126">The default is `Online`.</span></span>|  
|<span data-ttu-id="33b79-127">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="33b79-127">trustedStoreLocation</span></span>|<span data-ttu-id="33b79-128">시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-128">One of the two system store locations: `LocalMachine` or `CurrentUser`.</span></span> <span data-ttu-id="33b79-129">서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-129">This value is used when a service certificate is negotiated to the client.</span></span> <span data-ttu-id="33b79-130">에 대해 유효성 검사가 수행 되는 **신뢰할 수 있는 사용자** 지정한 저장소 위치에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-130">Validation is performed against the **Trusted People** store in the specified store location.</span></span> <span data-ttu-id="33b79-131">기본값은 `CurrentUser`입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-131">The default is `CurrentUser`.</span></span>|  
  
## <a name="customcertificatevalidator-attribute"></a><span data-ttu-id="33b79-132">customCertificateValidator 특성</span><span class="sxs-lookup"><span data-stu-id="33b79-132">customCertificateValidator Attribute</span></span>  
  
|<span data-ttu-id="33b79-133">값</span><span class="sxs-lookup"><span data-stu-id="33b79-133">Value</span></span>|<span data-ttu-id="33b79-134">설명</span><span class="sxs-lookup"><span data-stu-id="33b79-134">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33b79-135">문자열</span><span class="sxs-lookup"><span data-stu-id="33b79-135">String</span></span>|<span data-ttu-id="33b79-136">형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-136">Specifies the type name and assembly and other data used to find the type.</span></span>|  
  
## <a name="certificatevalidationmode-attribute"></a><span data-ttu-id="33b79-137">certificateValidationMode 특성</span><span class="sxs-lookup"><span data-stu-id="33b79-137">certificateValidationMode Attribute</span></span>  
  
|<span data-ttu-id="33b79-138">값</span><span class="sxs-lookup"><span data-stu-id="33b79-138">Value</span></span>|<span data-ttu-id="33b79-139">설명</span><span class="sxs-lookup"><span data-stu-id="33b79-139">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33b79-140">열거형</span><span class="sxs-lookup"><span data-stu-id="33b79-140">Enumeration</span></span>|<span data-ttu-id="33b79-141">None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-141">One of the following values: None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom.</span></span><br /><br /> <span data-ttu-id="33b79-142">자세한 내용은 참조 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-142">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="revocationmode-attribute"></a><span data-ttu-id="33b79-143">revocationMode 특성</span><span class="sxs-lookup"><span data-stu-id="33b79-143">revocationMode Attribute</span></span>  
  
|<span data-ttu-id="33b79-144">값</span><span class="sxs-lookup"><span data-stu-id="33b79-144">Value</span></span>|<span data-ttu-id="33b79-145">설명</span><span class="sxs-lookup"><span data-stu-id="33b79-145">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33b79-146">열거형</span><span class="sxs-lookup"><span data-stu-id="33b79-146">Enumeration</span></span>|<span data-ttu-id="33b79-147">NoCheck, Online, Offline 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-147">One of the following values: NoCheck, Online, Offline.</span></span><br /><br /> <span data-ttu-id="33b79-148">자세한 내용은 참조 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-148">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>|  
  
## <a name="trustedstorelocation-attribute"></a><span data-ttu-id="33b79-149">trustedStoreLocation 특성</span><span class="sxs-lookup"><span data-stu-id="33b79-149">trustedStoreLocation Attribute</span></span>  
  
|<span data-ttu-id="33b79-150">값</span><span class="sxs-lookup"><span data-stu-id="33b79-150">Value</span></span>|<span data-ttu-id="33b79-151">설명</span><span class="sxs-lookup"><span data-stu-id="33b79-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="33b79-152">열거형</span><span class="sxs-lookup"><span data-stu-id="33b79-152">Enumeration</span></span>|<span data-ttu-id="33b79-153">LocalMachine 또는 CurrentUser 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-153">One of the following values: LocalMachine or CurrentUser.</span></span> <span data-ttu-id="33b79-154">기본값은 CurrentUser입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-154">The default is CurrentUser.</span></span> <span data-ttu-id="33b79-155">시스템 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 LocalMachine에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-155">If the client application is running under a system account, then the certificate is typically under LocalMachine.</span></span> <span data-ttu-id="33b79-156">사용자 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 CurrentUser에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-156">If the client application is running under a user account, then the certificate is typically in CurrentUser.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="33b79-157">자식 요소</span><span class="sxs-lookup"><span data-stu-id="33b79-157">Child Elements</span></span>  
 <span data-ttu-id="33b79-158">없음</span><span class="sxs-lookup"><span data-stu-id="33b79-158">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="33b79-159">부모 요소</span><span class="sxs-lookup"><span data-stu-id="33b79-159">Parent Elements</span></span>  
  
|<span data-ttu-id="33b79-160">요소</span><span class="sxs-lookup"><span data-stu-id="33b79-160">Element</span></span>|<span data-ttu-id="33b79-161">설명</span><span class="sxs-lookup"><span data-stu-id="33b79-161">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="33b79-162">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="33b79-162">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|<span data-ttu-id="33b79-163">클라이언트에 대해 서비스를 인증할 때 사용할 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-163">Specifies a certificate to use when authenticating a service to the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="33b79-164">설명</span><span class="sxs-lookup"><span data-stu-id="33b79-164">Remarks</span></span>  
 <span data-ttu-id="33b79-165">이 구성 요소의 `certificateValidationMode` 특성은 인증서를 인증하는 데 사용되는 신뢰 수준을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-165">The `certificateValidationMode` attribute of this configuration element specifies the level of trust used to authenticate certificates.</span></span> <span data-ttu-id="33b79-166">기본적으로 수준은 `ChainTrust`로 설정되며 이는 각 인증서가 체인 맨 위의 신뢰할 수 있는 인증 기관에서 종료되는 인증서 계층 구조에 있어야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-166">By default, the level is set to `ChainTrust`, which specifies that each certificate must be found in a hierarchy of certificates ending in a trusted certification authority at the top of the chain.</span></span> <span data-ttu-id="33b79-167">이 모드가 가장 안전한 모드입니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-167">This is the most secure mode.</span></span> <span data-ttu-id="33b79-168">또한 값을 `PeerOrChainTrust`로 설정할 수 있으며, 이는 자체 발급된 인증서(신뢰 피어)가 신뢰 체인에 있는 인증서와 함께 수락됨을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-168">You can also set the value to `PeerOrChainTrust`, which specifies that self-issued certificates (peer trust) are accepted as well as certificates that are in a trusted chain.</span></span> <span data-ttu-id="33b79-169">자체 발급 인증서를 신뢰할 수 있는 기관에서 구입할 필요 없기 때문에 클라이언트 및 서비스를 개발 및 디버깅하는 경우 이 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-169">This value is used when developing and debugging clients and services because self-issued certificates need not be purchased from a trusted authority.</span></span> <span data-ttu-id="33b79-170">클라이언트를 배포하는 경우 `ChainTrust` 값을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-170">When deploying a client, use the `ChainTrust` value instead.</span></span> <span data-ttu-id="33b79-171">또한 값을 `Custom` 또는 `None`으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-171">You can also set the value to `Custom` or `None`.</span></span> <span data-ttu-id="33b79-172">`Custom` 값을 사용하려면 `customCertificateValidator` 특성을 인증서의 유효성을 검사하는 데 사용된 어셈블리 및 형식으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-172">To use the `Custom` value, you must also set the `customCertificateValidator` attribute to an assembly and type used to validate the certificate.</span></span> <span data-ttu-id="33b79-173">사용자 지정 유효성 검사기를 직접 만들려면 추상 X509CertificateValidator 클래스에서 상속해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-173">To create your own custom validator, you must inherit from the abstract X509CertificateValidator class.</span></span> <span data-ttu-id="33b79-174">자세한 내용은 참조 [하는 방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-174">For more information, see [How to: Create a Service that Employs a Custom Certificate Validator](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md).</span></span>  
  
 <span data-ttu-id="33b79-175">`revocationMode` 특성은 해지를 위해 인증서를 검사하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-175">The `revocationMode` attribute specifies how certificates are checked for revocation.</span></span> <span data-ttu-id="33b79-176">기본값은 `online`이며, 이는 인증서가 해지를 위해 자동으로 검사됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-176">The default is `online` which indicates that certificates will be checked automatically for revocation.</span></span> <span data-ttu-id="33b79-177">자세한 내용은 참조 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-177">For more information, see [Working with Certificates](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33b79-178">예제</span><span class="sxs-lookup"><span data-stu-id="33b79-178">Example</span></span>  
 <span data-ttu-id="33b79-179">다음 예제에서는 두 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-179">The following example does two tasks.</span></span> <span data-ttu-id="33b79-180">먼저 도메인 이름이 www.contoso.com인 끝점과 HTTP 프로토콜을 통해 통신할 때 클라이언트가 사용할 서비스 인증서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-180">It first specifies a service certificate for the client to use when communicating with endpoints whose domain name is www.contoso.com over the HTTP protocol.</span></span> <span data-ttu-id="33b79-181">그런 다음 인증 중에 사용되는 해지 모드 및 저장소 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="33b79-181">Second, it specifies the revocation mode and store location used during authentication.</span></span>  
  
```xml  
<serviceCertificate>  
  <defaultCertificate findValue="www.contoso.com"   
                      storeLocation="LocalMachine"  
                      storeName="TrustedPeople"   
                      x509FindType="FindByIssuerDistinguishedName" />  
  <scopedCertificates>  
     <add targetUri="http://www.contoso.com"   
          findValue="www.contoso.com" storeLocation="LocalMachine"  
                  storeName="Root" x509FindType="FindByIssuerName" />  
  </scopedCertificates>  
  <authentication revocationMode="Online"   
   trustedStoreLocation="LocalMachine" />  
</serviceCertificate>  
```  
  
## <a name="see-also"></a><span data-ttu-id="33b79-182">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33b79-182">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.Authentication%2A>  
 <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>  
 [<span data-ttu-id="33b79-183">보안 동작</span><span class="sxs-lookup"><span data-stu-id="33b79-183">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="33b79-184">인증서 작업</span><span class="sxs-lookup"><span data-stu-id="33b79-184">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="33b79-185">방법: 사용자 지정 인증서 유효성 검사기를 사용 하는 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="33b79-185">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 [<span data-ttu-id="33b79-186">\<인증 ></span><span class="sxs-lookup"><span data-stu-id="33b79-186">\<authentication></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)  
 [<span data-ttu-id="33b79-187">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="33b79-187">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="33b79-188">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="33b79-188">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
