---
title: "&lt;wsFederationHttpBinding&gt;의 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e5e854-b8dc-4921-843d-34b6a4a6a8ba
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: dd4f517c17efce85f7a83d7d8545cf58322d5373
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltwsfederationhttpbindinggt"></a><span data-ttu-id="4c7e7-102">&lt;wsFederationHttpBinding&gt;의 &lt;security&gt;</span><span class="sxs-lookup"><span data-stu-id="4c7e7-102">&lt;security&gt; of &lt;wsFederationHttpBinding&gt;</span></span>
<span data-ttu-id="4c7e7-103">보안 설정을 정의 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-103">Defines the security settings of the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md).</span></span>  
  
 <span data-ttu-id="4c7e7-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4c7e7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4c7e7-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="4c7e7-105">\<bindings></span></span>  
<span data-ttu-id="4c7e7-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="4c7e7-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="4c7e7-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="4c7e7-107">\<binding></span></span>  
<span data-ttu-id="4c7e7-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="4c7e7-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c7e7-109">구문</span><span class="sxs-lookup"><span data-stu-id="4c7e7-109">Syntax</span></span>  
  
```xml  
<wsFederationBinding>  
    <binding >  
       <security mode="None/Message/TransportWithMessageCredential">  
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
                                   X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c7e7-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4c7e7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4c7e7-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c7e7-112">특성</span><span class="sxs-lookup"><span data-stu-id="4c7e7-112">Attributes</span></span>  
  
|<span data-ttu-id="4c7e7-113">특성</span><span class="sxs-lookup"><span data-stu-id="4c7e7-113">Attribute</span></span>|<span data-ttu-id="4c7e7-114">설명</span><span class="sxs-lookup"><span data-stu-id="4c7e7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c7e7-115">모드</span><span class="sxs-lookup"><span data-stu-id="4c7e7-115">Mode</span></span>|<span data-ttu-id="4c7e7-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-116">Optional.</span></span> <span data-ttu-id="4c7e7-117">적용되는 보안 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="4c7e7-118">기본값은 `Message`입니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-118">The default value is `Message`.</span></span> <span data-ttu-id="4c7e7-119">이 특성은 <xref:System.ServiceModel.WSFederationHttpSecurityMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-119">This attribute is of type <xref:System.ServiceModel.WSFederationHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4c7e7-120">Mode 특성</span><span class="sxs-lookup"><span data-stu-id="4c7e7-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="4c7e7-121">값</span><span class="sxs-lookup"><span data-stu-id="4c7e7-121">Value</span></span>|<span data-ttu-id="4c7e7-122">설명</span><span class="sxs-lookup"><span data-stu-id="4c7e7-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4c7e7-123">없음</span><span class="sxs-lookup"><span data-stu-id="4c7e7-123">None</span></span>|<span data-ttu-id="4c7e7-124">SOAP 메시지의 경우 전송 중에는 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-124">The SOAP message is not secure during transfer.</span></span>|  
|<span data-ttu-id="4c7e7-125">메시지</span><span class="sxs-lookup"><span data-stu-id="4c7e7-125">Message</span></span>|<span data-ttu-id="4c7e7-126">SOAP 메시지 보안을 사용하여 무결성, 기밀성, 서버 인증 및 클라이언트 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-126">Integrity, confidentiality, server authentication and client authentication are provided using SOAP message security.</span></span> <span data-ttu-id="4c7e7-127">기본적으로 본문에는 암호화 및 서명이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-127">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="4c7e7-128">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-128">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="4c7e7-129">클라이언트 인증은 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-129">Client authentication is based on the token issued to the client by a security token service</span></span>|  
|<span data-ttu-id="4c7e7-130">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="4c7e7-130">TransportWithMessageCredential</span></span>|<span data-ttu-id="4c7e7-131">HTTPS를 사용하여 무결성, 기밀성 및 서버 인증을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-131">Integrity, confidentiality and server authentication are provided by HTTPS.</span></span> <span data-ttu-id="4c7e7-132">서비스는 인증서로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-132">The service needs to be configured with a certificate.</span></span> <span data-ttu-id="4c7e7-133">클라이언트 인증은 SOAP 메시지 보안을 통해 제공되며 보안 토큰 서비스가 클라이언트에 발급한 토큰에 따라 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-133">Client authentication is provided by means of SOAP message security and is based on the token issued to the client by a security token service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c7e7-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4c7e7-134">Child Elements</span></span>  
  
|<span data-ttu-id="4c7e7-135">요소</span><span class="sxs-lookup"><span data-stu-id="4c7e7-135">Element</span></span>|<span data-ttu-id="4c7e7-136">설명</span><span class="sxs-lookup"><span data-stu-id="4c7e7-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c7e7-137">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="4c7e7-137">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="4c7e7-138">메시지 수준 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-138">Defines the settings for the message-level security.</span></span> <span data-ttu-id="4c7e7-139">이 요소는 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-139">This element is of type <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c7e7-140">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4c7e7-140">Parent Elements</span></span>  
  
|<span data-ttu-id="4c7e7-141">요소</span><span class="sxs-lookup"><span data-stu-id="4c7e7-141">Element</span></span>|<span data-ttu-id="4c7e7-142">설명</span><span class="sxs-lookup"><span data-stu-id="4c7e7-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c7e7-143">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="4c7e7-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4c7e7-144">모든 바인딩 기능을 정의 [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4c7e7-144">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c7e7-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c7e7-145">See Also</span></span>  
 <xref:System.ServiceModel.WSFederationHttpSecurity>  
 <xref:System.ServiceModel.WSFederationHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement>  
 [<span data-ttu-id="4c7e7-146">방법: WSFederationHttpBinding 만들기</span><span class="sxs-lookup"><span data-stu-id="4c7e7-146">How to: Create a WSFederationHttpBinding</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 [<span data-ttu-id="4c7e7-147">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="4c7e7-147">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="4c7e7-148">자격 증명 유형 선택</span><span class="sxs-lookup"><span data-stu-id="4c7e7-148">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="4c7e7-149">바인딩</span><span class="sxs-lookup"><span data-stu-id="4c7e7-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4c7e7-150">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="4c7e7-150">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="4c7e7-151">바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="4c7e7-151">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="4c7e7-152">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="4c7e7-152">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
