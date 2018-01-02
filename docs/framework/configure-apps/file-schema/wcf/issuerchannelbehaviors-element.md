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
ms.workload: dotnet
ms.openlocfilehash: bb90b318f99816a3886056394559fdc80fa986ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltissuerchannelbehaviorsgt-element"></a><span data-ttu-id="0ca30-102">&lt;issuerChannelBehaviors&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="0ca30-102">&lt;issuerChannelBehaviors&gt; Element</span></span>
<span data-ttu-id="0ca30-103">지정한 서비스 토큰 서비스와 통신할 때 사용할 구성에 정의된 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트 끝점 동작 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca30-103">Contains a collection of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="0ca30-104">정의 된 동작은 포함할 수 없습니다 [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0ca30-104">The defined behaviors cannot include any [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elements.</span></span>  
  
 <span data-ttu-id="0ca30-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0ca30-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="0ca30-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0ca30-106">\<behaviors></span></span>  
<span data-ttu-id="0ca30-107">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="0ca30-107">endpointBehaviors section</span></span>  
<span data-ttu-id="0ca30-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0ca30-108">\<behavior></span></span>  
<span data-ttu-id="0ca30-109">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="0ca30-109">\<clientCredentials></span></span>  
<span data-ttu-id="0ca30-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="0ca30-110">\<issuedToken></span></span>  
<span data-ttu-id="0ca30-111">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0ca30-111">\<issuerChannelBehaviors></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ca30-112">구문</span><span class="sxs-lookup"><span data-stu-id="0ca30-112">Syntax</span></span>  
  
```xml  
<issuerChannelBehaviors>  
      <add behaviorConfiguraton="string"  
                issuerAddress="string" />  
</issuerChannelBehaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ca30-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0ca30-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0ca30-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca30-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ca30-115">특성</span><span class="sxs-lookup"><span data-stu-id="0ca30-115">Attributes</span></span>  
 <span data-ttu-id="0ca30-116">없음</span><span class="sxs-lookup"><span data-stu-id="0ca30-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0ca30-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0ca30-117">Child Elements</span></span>  
  
|<span data-ttu-id="0ca30-118">요소</span><span class="sxs-lookup"><span data-stu-id="0ca30-118">Element</span></span>|<span data-ttu-id="0ca30-119">설명</span><span class="sxs-lookup"><span data-stu-id="0ca30-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ca30-120">\<add></span><span class="sxs-lookup"><span data-stu-id="0ca30-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-issuerchannelbehaviors.md)|<span data-ttu-id="0ca30-121">동작을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca30-121">Adds a behavior to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0ca30-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0ca30-122">Parent Elements</span></span>  
  
|<span data-ttu-id="0ca30-123">요소</span><span class="sxs-lookup"><span data-stu-id="0ca30-123">Element</span></span>|<span data-ttu-id="0ca30-124">설명</span><span class="sxs-lookup"><span data-stu-id="0ca30-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0ca30-125">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="0ca30-125">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="0ca30-126">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca30-126">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ca30-127">설명</span><span class="sxs-lookup"><span data-stu-id="0ca30-127">Remarks</span></span>  
 <span data-ttu-id="0ca30-128">`<clientCredentials>` 요소를 포함하는 동작을 제외한 동작을 서비스와 통신하는 데 사용하는 경우 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca30-128">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="0ca30-129">예를 들어 경우는 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) 동작 요소를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0ca30-129">For example, if a [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) behavior element must be included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ca30-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ca30-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="0ca30-131">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="0ca30-131">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="0ca30-132">보안 동작</span><span class="sxs-lookup"><span data-stu-id="0ca30-132">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="0ca30-133">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="0ca30-133">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="0ca30-134">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0ca30-134">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="0ca30-135">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="0ca30-135">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="0ca30-136">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="0ca30-136">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="0ca30-137">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="0ca30-137">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="0ca30-138">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="0ca30-138">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
