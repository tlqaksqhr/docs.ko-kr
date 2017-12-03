---
title: "&lt;issuerChannelBehaviors&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b73d090aa47e18792d313b3d086e7a667e74bb08
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="131b2-102">&lt;issuerChannelBehaviors&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="131b2-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="131b2-103">지정한 서비스 토큰 서비스와 통신할 때 사용할 구성에 정의된 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트 끝점 동작 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="131b2-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="131b2-104">정의 된 동작은 포함할 수 없습니다 [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="131b2-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="131b2-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="131b2-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="131b2-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="131b2-106">\<behaviors></span></span>  
<span data-ttu-id="131b2-107">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="131b2-107">endpointBehaviors section</span></span>  
<span data-ttu-id="131b2-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="131b2-108">\<behavior></span></span>  
<span data-ttu-id="131b2-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="131b2-109">\<clientCredentials></span></span>  
<span data-ttu-id="131b2-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="131b2-110">\<issuedToken></span></span>  
<span data-ttu-id="131b2-111">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="131b2-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="131b2-112">구문</span><span class="sxs-lookup"><span data-stu-id="131b2-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="131b2-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="131b2-113">Attributes and Elements</span></span>  
 <span data-ttu-id="131b2-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="131b2-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="131b2-115">특성</span><span class="sxs-lookup"><span data-stu-id="131b2-115">Attributes</span></span>  
 <span data-ttu-id="131b2-116">없음</span><span class="sxs-lookup"><span data-stu-id="131b2-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="131b2-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="131b2-117">Child Elements</span></span>  
  
|<span data-ttu-id="131b2-118">요소</span><span class="sxs-lookup"><span data-stu-id="131b2-118">Element</span></span>|<span data-ttu-id="131b2-119">설명</span><span class="sxs-lookup"><span data-stu-id="131b2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="131b2-120">\<add></span><span class="sxs-lookup"><span data-stu-id="131b2-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="131b2-121">동작을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="131b2-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="131b2-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="131b2-122">Parent Elements</span></span>  
  
|<span data-ttu-id="131b2-123">요소</span><span class="sxs-lookup"><span data-stu-id="131b2-123">Element</span></span>|<span data-ttu-id="131b2-124">설명</span><span class="sxs-lookup"><span data-stu-id="131b2-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="131b2-125">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="131b2-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="131b2-126">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="131b2-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="131b2-127">설명</span><span class="sxs-lookup"><span data-stu-id="131b2-127">Remarks</span></span>  
 <span data-ttu-id="131b2-128">`<clientCredentials>` 요소를 포함하는 동작을 제외한 동작을 서비스와 통신하는 데 사용하는 경우 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="131b2-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="131b2-129">예를 들어 경우는 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) 동작 요소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="131b2-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="131b2-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="131b2-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="131b2-131">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="131b2-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="131b2-132">보안 동작</span><span class="sxs-lookup"><span data-stu-id="131b2-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="131b2-133">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="131b2-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="131b2-134">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="131b2-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="131b2-135">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="131b2-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="131b2-136">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="131b2-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="131b2-137">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="131b2-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="131b2-138">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="131b2-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
