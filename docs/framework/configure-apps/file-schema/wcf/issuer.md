---
title: "&lt;발급자&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c49c6ae-fa1a-4179-a84b-613c3216dcde
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 235888aa97238489a51c2ea065efa0575e0d3724
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuergt"></a><span data-ttu-id="a45ef-102">&lt;발급자&gt;</span><span class="sxs-lookup"><span data-stu-id="a45ef-102">&lt;issuer&gt;</span></span>
<span data-ttu-id="a45ef-103">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="a45ef-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a45ef-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a45ef-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="a45ef-105">\<bindings></span></span>  
<span data-ttu-id="a45ef-106">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a45ef-106">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="a45ef-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="a45ef-107">\<binding></span></span>  
<span data-ttu-id="a45ef-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="a45ef-108">\<security></span></span>  
<span data-ttu-id="a45ef-109">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="a45ef-109">\<message></span></span>  
<span data-ttu-id="a45ef-110">\<발급자 ></span><span class="sxs-lookup"><span data-stu-id="a45ef-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a45ef-111">구문</span><span class="sxs-lookup"><span data-stu-id="a45ef-111">Syntax</span></span>  
  
```xml  
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
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a45ef-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a45ef-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a45ef-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a45ef-114">특성</span><span class="sxs-lookup"><span data-stu-id="a45ef-114">Attributes</span></span>  
  
|<span data-ttu-id="a45ef-115">특성</span><span class="sxs-lookup"><span data-stu-id="a45ef-115">Attribute</span></span>|<span data-ttu-id="a45ef-116">설명</span><span class="sxs-lookup"><span data-stu-id="a45ef-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a45ef-117">address</span><span class="sxs-lookup"><span data-stu-id="a45ef-117">address</span></span>|<span data-ttu-id="a45ef-118">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-118">Required string.</span></span> <span data-ttu-id="a45ef-119">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a45ef-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a45ef-120">Child Elements</span></span>  
  
|<span data-ttu-id="a45ef-121">요소</span><span class="sxs-lookup"><span data-stu-id="a45ef-121">Element</span></span>|<span data-ttu-id="a45ef-122">설명</span><span class="sxs-lookup"><span data-stu-id="a45ef-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a45ef-123">\<헤더 ></span><span class="sxs-lookup"><span data-stu-id="a45ef-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="a45ef-124">작성기에서 만들 수 있는 끝점의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="a45ef-125">\<identity ></span><span class="sxs-lookup"><span data-stu-id="a45ef-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="a45ef-126">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a45ef-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a45ef-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a45ef-128">요소</span><span class="sxs-lookup"><span data-stu-id="a45ef-128">Element</span></span>|<span data-ttu-id="a45ef-129">설명</span><span class="sxs-lookup"><span data-stu-id="a45ef-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a45ef-130">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="a45ef-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="a45ef-131">에 대 한 메시지 수준 보안에 대 한 설정을 정의 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a45ef-131">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a45ef-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a45ef-132">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.Issuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 [<span data-ttu-id="a45ef-133">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="a45ef-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a45ef-134">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="a45ef-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a45ef-135">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="a45ef-135">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a45ef-136">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="a45ef-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a45ef-137">사용자 지정 바인딩 사용 하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="a45ef-137">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="a45ef-138">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="a45ef-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
