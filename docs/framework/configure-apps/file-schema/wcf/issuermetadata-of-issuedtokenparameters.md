---
title: "&lt;issuedTokenParameters&gt;의 &lt;issuerMetadata&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccd0417aeebbaf08d28457dd94a4d1698882c79e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="406ec-102">&lt;issuedTokenParameters&gt;의 &lt;issuerMetadata&gt;</span><span class="sxs-lookup"><span data-stu-id="406ec-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="406ec-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="406ec-103">\<system.serviceModel></span></span>  
<span data-ttu-id="406ec-104">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="406ec-104">\<bindings></span></span>  
<span data-ttu-id="406ec-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="406ec-105">\<customBinding></span></span>  
<span data-ttu-id="406ec-106">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="406ec-106">\<binding></span></span>  
<span data-ttu-id="406ec-107">\<보안 ></span><span class="sxs-lookup"><span data-stu-id="406ec-107">\<security></span></span>  
<span data-ttu-id="406ec-108">\<r s ></span><span class="sxs-lookup"><span data-stu-id="406ec-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="406ec-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="406ec-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="406ec-110">구문</span><span class="sxs-lookup"><span data-stu-id="406ec-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="406ec-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="406ec-111">Attributes and Elements</span></span>  
 <span data-ttu-id="406ec-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="406ec-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="406ec-113">특성</span><span class="sxs-lookup"><span data-stu-id="406ec-113">Attributes</span></span>  
  
|<span data-ttu-id="406ec-114">특성</span><span class="sxs-lookup"><span data-stu-id="406ec-114">Attribute</span></span>|<span data-ttu-id="406ec-115">설명</span><span class="sxs-lookup"><span data-stu-id="406ec-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="406ec-116">address</span><span class="sxs-lookup"><span data-stu-id="406ec-116">address</span></span>|<span data-ttu-id="406ec-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="406ec-117">Required.</span></span> <span data-ttu-id="406ec-118">끝점의 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="406ec-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="406ec-119">주소는 절대 URI이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="406ec-119">The address must be an absolute URI.</span></span> <span data-ttu-id="406ec-120">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="406ec-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="406ec-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="406ec-121">Child Elements</span></span>  
  
|<span data-ttu-id="406ec-122">요소</span><span class="sxs-lookup"><span data-stu-id="406ec-122">Element</span></span>|<span data-ttu-id="406ec-123">설명</span><span class="sxs-lookup"><span data-stu-id="406ec-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="406ec-124">\<헤더 ></span><span class="sxs-lookup"><span data-stu-id="406ec-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="406ec-125">주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="406ec-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="406ec-126">\<identity ></span><span class="sxs-lookup"><span data-stu-id="406ec-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="406ec-127">한 끝점에서 다른 끝점과 메시지를 교환할 때 상대 끝점을 인증할 수 있도록 하는 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="406ec-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="406ec-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="406ec-128">Parent Elements</span></span>  
  
|<span data-ttu-id="406ec-129">요소</span><span class="sxs-lookup"><span data-stu-id="406ec-129">Element</span></span>|<span data-ttu-id="406ec-130">설명</span><span class="sxs-lookup"><span data-stu-id="406ec-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="406ec-131">\<r s ></span><span class="sxs-lookup"><span data-stu-id="406ec-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="406ec-132">페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="406ec-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="406ec-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="406ec-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="406ec-134">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="406ec-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="406ec-135">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="406ec-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="406ec-136">사용자 지정 바인딩 사용 하는 보안 기능</span><span class="sxs-lookup"><span data-stu-id="406ec-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="406ec-137">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="406ec-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="406ec-138">바인딩</span><span class="sxs-lookup"><span data-stu-id="406ec-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="406ec-139">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="406ec-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="406ec-140">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="406ec-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="406ec-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="406ec-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="406ec-142">방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면</span><span class="sxs-lookup"><span data-stu-id="406ec-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="406ec-143">사용자 지정 바인딩 보안</span><span class="sxs-lookup"><span data-stu-id="406ec-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
