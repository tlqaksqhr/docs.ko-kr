---
title: '&lt;issuedTokenParameters&gt;의 &lt;issuer&gt;'
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 459f2f43d3ef9426fbce7e0a0dd067250eb2cc4b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748574"
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="c1da5-102">&lt;issuedTokenParameters&gt;의 &lt;issuer&gt;</span><span class="sxs-lookup"><span data-stu-id="c1da5-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="c1da5-103">보안 토큰을 발급하는 STS(보안 토큰 서비스)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da5-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="c1da5-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c1da5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c1da5-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="c1da5-105">\<bindings></span></span>  
<span data-ttu-id="c1da5-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c1da5-106">\<customBinding></span></span>  
<span data-ttu-id="c1da5-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="c1da5-107">\<binding></span></span>  
<span data-ttu-id="c1da5-108">\<security></span><span class="sxs-lookup"><span data-stu-id="c1da5-108">\<security></span></span>  
<span data-ttu-id="c1da5-109">\<r s ></span><span class="sxs-lookup"><span data-stu-id="c1da5-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="c1da5-110">\<발급자 ></span><span class="sxs-lookup"><span data-stu-id="c1da5-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1da5-111">구문</span><span class="sxs-lookup"><span data-stu-id="c1da5-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1da5-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c1da5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c1da5-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da5-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1da5-114">특성</span><span class="sxs-lookup"><span data-stu-id="c1da5-114">Attributes</span></span>  
  
|<span data-ttu-id="c1da5-115">특성</span><span class="sxs-lookup"><span data-stu-id="c1da5-115">Attribute</span></span>|<span data-ttu-id="c1da5-116">설명</span><span class="sxs-lookup"><span data-stu-id="c1da5-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1da5-117">address</span><span class="sxs-lookup"><span data-stu-id="c1da5-117">address</span></span>|<span data-ttu-id="c1da5-118">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c1da5-118">Required string.</span></span> <span data-ttu-id="c1da5-119">STS의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="c1da5-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1da5-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c1da5-120">Child Elements</span></span>  
  
|<span data-ttu-id="c1da5-121">요소</span><span class="sxs-lookup"><span data-stu-id="c1da5-121">Element</span></span>|<span data-ttu-id="c1da5-122">설명</span><span class="sxs-lookup"><span data-stu-id="c1da5-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1da5-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="c1da5-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="c1da5-124">작성기에서 만들 수 있는 끝점의 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c1da5-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="c1da5-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="c1da5-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="c1da5-126">발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da5-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1da5-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c1da5-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c1da5-128">요소</span><span class="sxs-lookup"><span data-stu-id="c1da5-128">Element</span></span>|<span data-ttu-id="c1da5-129">설명</span><span class="sxs-lookup"><span data-stu-id="c1da5-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1da5-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="c1da5-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="c1da5-131">현재 발급된 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c1da5-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1da5-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1da5-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="c1da5-133">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="c1da5-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="c1da5-134">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="c1da5-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="c1da5-135">사용자 지정 바인딩을 사용하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="c1da5-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="c1da5-136">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="c1da5-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="c1da5-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="c1da5-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="c1da5-138">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="c1da5-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="c1da5-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="c1da5-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="c1da5-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c1da5-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="c1da5-141">방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기</span><span class="sxs-lookup"><span data-stu-id="c1da5-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="c1da5-142">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="c1da5-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
