---
title: "&lt;issuedTokenParameters&gt;의 &lt;issuer&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1eae3b472e33d4d0504ba487c8c871165af8cdf9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="3a91a-102">&lt;issuedTokenParameters&gt;의 &lt;issuer&gt;</span><span class="sxs-lookup"><span data-stu-id="3a91a-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="3a91a-103">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a91a-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="3a91a-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3a91a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3a91a-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3a91a-105">\<bindings></span></span>  
<span data-ttu-id="3a91a-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3a91a-106">\<customBinding></span></span>  
<span data-ttu-id="3a91a-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3a91a-107">\<binding></span></span>  
<span data-ttu-id="3a91a-108">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="3a91a-108">\<security></span></span>  
<span data-ttu-id="3a91a-109">\<r s ></span><span class="sxs-lookup"><span data-stu-id="3a91a-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="3a91a-110">\<발급자 ></span><span class="sxs-lookup"><span data-stu-id="3a91a-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a91a-111">구문</span><span class="sxs-lookup"><span data-stu-id="3a91a-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a91a-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3a91a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3a91a-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3a91a-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a91a-114">특성</span><span class="sxs-lookup"><span data-stu-id="3a91a-114">Attributes</span></span>  
  
|<span data-ttu-id="3a91a-115">특성</span><span class="sxs-lookup"><span data-stu-id="3a91a-115">Attribute</span></span>|<span data-ttu-id="3a91a-116">설명</span><span class="sxs-lookup"><span data-stu-id="3a91a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a91a-117">address</span><span class="sxs-lookup"><span data-stu-id="3a91a-117">address</span></span>|<span data-ttu-id="3a91a-118">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3a91a-118">Required string.</span></span> <span data-ttu-id="3a91a-119">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="3a91a-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a91a-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3a91a-120">Child Elements</span></span>  
  
|<span data-ttu-id="3a91a-121">요소</span><span class="sxs-lookup"><span data-stu-id="3a91a-121">Element</span></span>|<span data-ttu-id="3a91a-122">설명</span><span class="sxs-lookup"><span data-stu-id="3a91a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a91a-123">\<헤더 ></span><span class="sxs-lookup"><span data-stu-id="3a91a-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="3a91a-124">작성기에서 만들 수 있는 끝점의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3a91a-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="3a91a-125">\<identity ></span><span class="sxs-lookup"><span data-stu-id="3a91a-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="3a91a-126">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a91a-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a91a-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3a91a-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3a91a-128">요소</span><span class="sxs-lookup"><span data-stu-id="3a91a-128">Element</span></span>|<span data-ttu-id="3a91a-129">설명</span><span class="sxs-lookup"><span data-stu-id="3a91a-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a91a-130">\<r s ></span><span class="sxs-lookup"><span data-stu-id="3a91a-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="3a91a-131">현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a91a-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a91a-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a91a-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="3a91a-133">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="3a91a-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="3a91a-134">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="3a91a-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="3a91a-135">사용자 지정 바인딩 사용 하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="3a91a-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="3a91a-136">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="3a91a-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="3a91a-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="3a91a-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3a91a-138">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="3a91a-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="3a91a-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="3a91a-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="3a91a-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="3a91a-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="3a91a-141">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3a91a-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="3a91a-142">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="3a91a-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
