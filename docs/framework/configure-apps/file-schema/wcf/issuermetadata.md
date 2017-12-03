---
title: '&lt;issuerMetadata&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7eae2c0-cc17-4281-af59-e4eb8d54f92a
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3d2a4669c86142a66500407edbdda44e9dec81a0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuermetadatagt"></a><span data-ttu-id="a1a85-102">&lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="a1a85-102">&lt;issuerMetadata&gt;</span></span>
<span data-ttu-id="a1a85-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a1a85-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a1a85-104">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="a1a85-104">\<bindings></span></span>  
<span data-ttu-id="a1a85-105">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a1a85-105">\<wsFederationHttpBinding></span></span>  
<span data-ttu-id="a1a85-106">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="a1a85-106">\<binding></span></span>  
<span data-ttu-id="a1a85-107">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="a1a85-107">\<security></span></span>  
<span data-ttu-id="a1a85-108">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="a1a85-108">\<message></span></span>  
<span data-ttu-id="a1a85-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="a1a85-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1a85-110">구문</span><span class="sxs-lookup"><span data-stu-id="a1a85-110">Syntax</span></span>  
  
```xml  
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
                  x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
      <dns value="String"/>  
      <rsa value="String"/>  
      <servicePrincipalName value="String"/>  
      <usePrincipalName value="String"/>  
   </identity>  
</issuerMetadata>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1a85-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a1a85-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a1a85-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a85-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1a85-113">특성</span><span class="sxs-lookup"><span data-stu-id="a1a85-113">Attributes</span></span>  
  
|<span data-ttu-id="a1a85-114">특성</span><span class="sxs-lookup"><span data-stu-id="a1a85-114">Attribute</span></span>|<span data-ttu-id="a1a85-115">설명</span><span class="sxs-lookup"><span data-stu-id="a1a85-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1a85-116">address</span><span class="sxs-lookup"><span data-stu-id="a1a85-116">address</span></span>|<span data-ttu-id="a1a85-117">필수 `string` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a85-117">Required `string` attribute.</span></span><br /><br /> <span data-ttu-id="a1a85-118">끝점의 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a85-118">Specifies the address of the endpoint.</span></span> <span data-ttu-id="a1a85-119">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a85-119">The address must be an absolute URI.</span></span> <span data-ttu-id="a1a85-120">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a85-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1a85-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a1a85-121">Child Elements</span></span>  
  
|<span data-ttu-id="a1a85-122">요소</span><span class="sxs-lookup"><span data-stu-id="a1a85-122">Element</span></span>|<span data-ttu-id="a1a85-123">설명</span><span class="sxs-lookup"><span data-stu-id="a1a85-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1a85-124">\<헤더 ></span><span class="sxs-lookup"><span data-stu-id="a1a85-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="a1a85-125">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a85-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="a1a85-126">\<identity ></span><span class="sxs-lookup"><span data-stu-id="a1a85-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="a1a85-127">한 끝점에서 다른 끝점과 메시지를 교환할 때 상대 끝점을 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a85-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a1a85-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a1a85-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a1a85-129">요소</span><span class="sxs-lookup"><span data-stu-id="a1a85-129">Element</span></span>|<span data-ttu-id="a1a85-130">설명</span><span class="sxs-lookup"><span data-stu-id="a1a85-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1a85-131">\<메시지 ></span><span class="sxs-lookup"><span data-stu-id="a1a85-131">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-wsfederationhttpbinding.md)|<span data-ttu-id="a1a85-132">에 대 한 메시지 수준 보안에 대 한 설정을 정의 [ \<wsFederationHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a85-132">Defines the settings for the message-level security for the [\<wsFederationHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1a85-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1a85-133">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.IssuerMetadataAddress%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.IssuerMetadata%2A>  
 [<span data-ttu-id="a1a85-134">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="a1a85-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="a1a85-135">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="a1a85-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="a1a85-136">사용자 지정 바인딩 사용 하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="a1a85-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="a1a85-137">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="a1a85-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
