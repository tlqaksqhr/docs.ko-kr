---
title: "&lt;wsFederationHttpBinding&gt;의 &lt;message&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9d710389-d9d8-4454-9bf2-da4ccda31cec
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fb12cc0162cabd75f176c636b9cd4d00309bb594
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltmessagegt-element-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="d2ed9-102">&lt;wsFederationHttpBinding&gt;의 &lt;message&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="d2ed9-102">&lt;message&gt; element of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="d2ed9-103">에 대 한 메시지 수준 보안에 대 한 설정을 정의 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-103">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="d2ed9-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d2ed9-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-105">\<bindings></span></span>  
<span data-ttu-id="d2ed9-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="d2ed9-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-107">\<binding></span></span>  
<span data-ttu-id="d2ed9-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-108">\<security></span></span>  
<span data-ttu-id="d2ed9-109">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2ed9-110">구문</span><span class="sxs-lookup"><span data-stu-id="d2ed9-110">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
     <binding >  
         <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
                        <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
                          </headers>  
                              <identity>  
                              <certificate encodedValue="String"/>  
                                <certificateReference findValue="String"   
                                 isChainIncluded="Boolean"  
                            storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                                  storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                                   <dns value="String"/>  
                                <rsa value="String"/>  
                                <servicePrincipalName value="String"/>  
                                <usePrincipalName value="String"/>  
                              </identity>  
                        </issuer>  
                        <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
                        </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
         </message>  
      </security>  
   </binding>  
</wsFederationBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d2ed9-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d2ed9-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d2ed9-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d2ed9-113">특성</span><span class="sxs-lookup"><span data-stu-id="d2ed9-113">Attributes</span></span>  
  
|<span data-ttu-id="d2ed9-114">특성</span><span class="sxs-lookup"><span data-stu-id="d2ed9-114">Attribute</span></span>|<span data-ttu-id="d2ed9-115">설명</span><span class="sxs-lookup"><span data-stu-id="d2ed9-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d2ed9-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="d2ed9-116">algorithmSuite</span></span>|<span data-ttu-id="d2ed9-117">메시지 암호화 및 키 래핑 알고리즘을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="d2ed9-118">이 특성의 유효한 값은 "algorithmSuite 특성" 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-118">See the "algorithmSuite attribute" table for valid values of this attribute.</span></span> <span data-ttu-id="d2ed9-119">기본값은 `Basic256`입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-119">The default value is `Basic256`.</span></span><br /><br /> <span data-ttu-id="d2ed9-120">이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.</span></span> <span data-ttu-id="d2ed9-121">이러한 알고리즘은 WS-SecurityPolicy(Security Policy Language) 사양에 지정된 알고리즘에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-121">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span>|  
|<span data-ttu-id="d2ed9-122">issuedKeyType</span><span class="sxs-lookup"><span data-stu-id="d2ed9-122">issuedKeyType</span></span>|<span data-ttu-id="d2ed9-123">발급할 키 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-123">Specifies the type of key to be issued.</span></span> <span data-ttu-id="d2ed9-124">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-124">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d2ed9-125">-SymmetricKey</span><span class="sxs-lookup"><span data-stu-id="d2ed9-125">-   SymmetricKey</span></span><br /><span data-ttu-id="d2ed9-126">-PublicKey</span><span class="sxs-lookup"><span data-stu-id="d2ed9-126">-   PublicKey</span></span><br /><br /> <span data-ttu-id="d2ed9-127">기본값은 `SymmetricKey`입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-127">The default is `SymmetricKey`.</span></span> <span data-ttu-id="d2ed9-128">이 특성은 <xref:System.IdentityModel.Tokens.SecurityKeyType> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-128">This attribute is of type <xref:System.IdentityModel.Tokens.SecurityKeyType>.</span></span>|  
|<span data-ttu-id="d2ed9-129">issuedTokenType</span><span class="sxs-lookup"><span data-stu-id="d2ed9-129">issuedTokenType</span></span>|<span data-ttu-id="d2ed9-130">발급될 토큰 형식을 지정하는 URI가 들어 있는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-130">A string that contains a URI that specifies the type of token to be issued.</span></span> <span data-ttu-id="d2ed9-131">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-131">The default is `null`.</span></span>|  
|<span data-ttu-id="d2ed9-132">negotiateServiceCredential</span><span class="sxs-lookup"><span data-stu-id="d2ed9-132">negotiateServiceCredential</span></span>|<span data-ttu-id="d2ed9-133">서비스 자격 증명이 협상의 일부로 교환되는지 또는 out of band 방식으로 사용될 수 있는지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-133">A Boolean value that specifies whether the service credential should be exchanged as part of negotiation or is available out of band.</span></span> <span data-ttu-id="d2ed9-134">기본값은 서비스 자격 증명이 협상됨을 의미하는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-134">The default is `true`, which means that the service credential is negotiated.</span></span>|  
  
## <a name="algorithmsuite-attribute"></a><span data-ttu-id="d2ed9-135">algorithmSuite 특성</span><span class="sxs-lookup"><span data-stu-id="d2ed9-135">algorithmSuite Attribute</span></span>  
  
|<span data-ttu-id="d2ed9-136">값</span><span class="sxs-lookup"><span data-stu-id="d2ed9-136">Value</span></span>|<span data-ttu-id="d2ed9-137">설명</span><span class="sxs-lookup"><span data-stu-id="d2ed9-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d2ed9-138">Basic128</span><span class="sxs-lookup"><span data-stu-id="d2ed9-138">Basic128</span></span>|<span data-ttu-id="d2ed9-139">Basic128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-139">Use Basic128 encryption, Sha1 for message digest, and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-140">Basic192</span><span class="sxs-lookup"><span data-stu-id="d2ed9-140">Basic192</span></span>|<span data-ttu-id="d2ed9-141">Basic192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-141">Use Basic192 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-142">Basic256</span><span class="sxs-lookup"><span data-stu-id="d2ed9-142">Basic256</span></span>|<span data-ttu-id="d2ed9-143">Basic256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-143">Use Basic256 encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-144">Basic256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d2ed9-144">Basic256Rsa15</span></span>|<span data-ttu-id="d2ed9-145">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-145">Use Basic256 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-146">Basic192Rsa15</span><span class="sxs-lookup"><span data-stu-id="d2ed9-146">Basic192Rsa15</span></span>|<span data-ttu-id="d2ed9-147">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-147">Use Basic192 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-148">TripleDes</span><span class="sxs-lookup"><span data-stu-id="d2ed9-148">TripleDes</span></span>|<span data-ttu-id="d2ed9-149">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-149">Use TripleDes encryption, Sha1 for message digest, Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-150">Basic128Rsa15</span><span class="sxs-lookup"><span data-stu-id="d2ed9-150">Basic128Rsa15</span></span>|<span data-ttu-id="d2ed9-151">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-151">Use Basic128 for message encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-152">TripleDesRsa15</span><span class="sxs-lookup"><span data-stu-id="d2ed9-152">TripleDesRsa15</span></span>|<span data-ttu-id="d2ed9-153">TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-153">Use TripleDes encryption, Sha1 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-154">Basic128Sha256</span><span class="sxs-lookup"><span data-stu-id="d2ed9-154">Basic128Sha256</span></span>|<span data-ttu-id="d2ed9-155">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-155">Use Basic128 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-156">Basic192Sha256</span><span class="sxs-lookup"><span data-stu-id="d2ed9-156">Basic192Sha256</span></span>|<span data-ttu-id="d2ed9-157">메시지 암호화의 경우 Basic192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-157">Use Basic192 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-158">Basic256Sha256</span><span class="sxs-lookup"><span data-stu-id="d2ed9-158">Basic256Sha256</span></span>|<span data-ttu-id="d2ed9-159">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-159">Use Basic256 for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-160">TripleDesSha256</span><span class="sxs-lookup"><span data-stu-id="d2ed9-160">TripleDesSha256</span></span>|<span data-ttu-id="d2ed9-161">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa-oaep-mgf1p를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-161">Use TripleDes for message encryption, Sha256 for message digest and Rsa-oaep-mgf1p for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-162">Basic128Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d2ed9-162">Basic128Sha256Rsa15</span></span>|<span data-ttu-id="d2ed9-163">메시지 암호화의 경우 Basic128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-163">Use Basic128 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-164">Basic192Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d2ed9-164">Basic192Sha256Rsa15</span></span>|<span data-ttu-id="d2ed9-165">메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-165">Use Aes192 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-166">Basic256Sha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d2ed9-166">Basic256Sha256Rsa15</span></span>|<span data-ttu-id="d2ed9-167">메시지 암호화의 경우 Basic256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-167">Use Basic256 for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
|<span data-ttu-id="d2ed9-168">TripleDesSha256Rsa15</span><span class="sxs-lookup"><span data-stu-id="d2ed9-168">TripleDesSha256Rsa15</span></span>|<span data-ttu-id="d2ed9-169">메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-169">Use TripleDes for message encryption, Sha256 for message digest and Rsa15 for key wrap.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d2ed9-170">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d2ed9-170">Child Elements</span></span>  
  
|<span data-ttu-id="d2ed9-171">요소</span><span class="sxs-lookup"><span data-stu-id="d2ed9-171">Element</span></span>|<span data-ttu-id="d2ed9-172">설명</span><span class="sxs-lookup"><span data-stu-id="d2ed9-172">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2ed9-173">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-173">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="d2ed9-174">이 바인딩에 대한 클레임 형식 컬렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-174">Specifies a collection of claim types for this binding.</span></span> <span data-ttu-id="d2ed9-175">각 요소는 <xref:System.ServiceModel.Configuration.ClaimTypeElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-175">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span>|  
|<span data-ttu-id="d2ed9-176">issuer</span><span class="sxs-lookup"><span data-stu-id="d2ed9-176">issuer</span></span>|<span data-ttu-id="d2ed9-177">보안 토큰을 발급하는 끝점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-177">Specifies an endpoint that issues a security token.</span></span> <span data-ttu-id="d2ed9-178">이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-178">This element is of type <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>.</span></span>|  
|<span data-ttu-id="d2ed9-179">issuerMetadata</span><span class="sxs-lookup"><span data-stu-id="d2ed9-179">issuerMetadata</span></span>|<span data-ttu-id="d2ed9-180">발급자의 끝점 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-180">Specifies the endpoint address of the issuer.</span></span>|  
|[<span data-ttu-id="d2ed9-181">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-181">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="d2ed9-182">토큰 요청 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-182">A collection of token request parameters.</span></span> <span data-ttu-id="d2ed9-183">각 매개 변수는 XML 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-183">Each parameter is an XML element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d2ed9-184">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d2ed9-184">Parent Elements</span></span>  
  
|<span data-ttu-id="d2ed9-185">요소</span><span class="sxs-lookup"><span data-stu-id="d2ed9-185">Element</span></span>|<span data-ttu-id="d2ed9-186">설명</span><span class="sxs-lookup"><span data-stu-id="d2ed9-186">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d2ed9-187">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-187">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wsfederationhttpbinding.md)|<span data-ttu-id="d2ed9-188">바인딩에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d2ed9-188">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d2ed9-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2ed9-189">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>  
 <span data-ttu-id="d2ed9-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement`[서비스 및 클라이언트 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span><span class="sxs-lookup"><span data-stu-id="d2ed9-190">`System.ServiceModel.Configuration.FederatedMessageSecurityElement` [Securing Services and Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)</span></span>  
 [<span data-ttu-id="d2ed9-191">바인딩</span><span class="sxs-lookup"><span data-stu-id="d2ed9-191">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d2ed9-192">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="d2ed9-192">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="d2ed9-193">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d2ed9-193">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="d2ed9-194">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="d2ed9-194">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
