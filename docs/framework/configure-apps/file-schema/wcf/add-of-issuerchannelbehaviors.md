---
title: '&lt;issuerChannelBehaviors&gt;의 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: 75531e8ed50ae89f379db23d228804612f4bfccb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752457"
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a><span data-ttu-id="84273-102">&lt;issuerChannelBehaviors&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="84273-102">&lt;add&gt; of &lt;issuerChannelBehaviors&gt;</span></span>
<span data-ttu-id="84273-103">STS와 통신할 때 사용할 끝점 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="84273-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="84273-104">어떤 끝점 동작을 포함 하는 경우는 [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소에서 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84273-104">If any endpoint behavior contains a [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element, an exception will be thrown.</span></span>  
  
 <span data-ttu-id="84273-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="84273-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="84273-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="84273-106">\<behaviors></span></span>  
<span data-ttu-id="84273-107">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="84273-107">endpointBehaviors section</span></span>  
<span data-ttu-id="84273-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="84273-108">\<behavior></span></span>  
<span data-ttu-id="84273-109">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="84273-109">\<clientCredentials></span></span>  
<span data-ttu-id="84273-110">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="84273-110">\<issuedToken></span></span>  
<span data-ttu-id="84273-111">\<issuerChannelBehaviors > 요소</span><span class="sxs-lookup"><span data-stu-id="84273-111">\<issuerChannelBehaviors> Element</span></span>  
<span data-ttu-id="84273-112">\<add></span><span class="sxs-lookup"><span data-stu-id="84273-112">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84273-113">구문</span><span class="sxs-lookup"><span data-stu-id="84273-113">Syntax</span></span>  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84273-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="84273-114">Attributes and Elements</span></span>  
 <span data-ttu-id="84273-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="84273-115">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84273-116">특성</span><span class="sxs-lookup"><span data-stu-id="84273-116">Attributes</span></span>  
  
|<span data-ttu-id="84273-117">특성</span><span class="sxs-lookup"><span data-stu-id="84273-117">Attribute</span></span>|<span data-ttu-id="84273-118">설명</span><span class="sxs-lookup"><span data-stu-id="84273-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84273-119">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="84273-119">issuerAddress</span></span>|<span data-ttu-id="84273-120">통신할 보안 토큰 발급자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="84273-120">The URI of the security token issuer to communicate with.</span></span>|  
|<span data-ttu-id="84273-121">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="84273-121">behaviorConfiguration</span></span>|<span data-ttu-id="84273-122">동일한 구성 파일에 정의된 끝점 동작 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="84273-122">The name of an endpoint behavior defined in the same configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84273-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="84273-123">Child Elements</span></span>  
 <span data-ttu-id="84273-124">없음</span><span class="sxs-lookup"><span data-stu-id="84273-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84273-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="84273-125">Parent Elements</span></span>  
  
|<span data-ttu-id="84273-126">요소</span><span class="sxs-lookup"><span data-stu-id="84273-126">Element</span></span>|<span data-ttu-id="84273-127">설명</span><span class="sxs-lookup"><span data-stu-id="84273-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="84273-128">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="84273-128">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="84273-129">지정 된 서비스 토큰 서비스와 통신할 때 사용 되는 Windows Communication Foundation (WCF) 클라이언트 끝점 동작의 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="84273-129">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84273-130">설명</span><span class="sxs-lookup"><span data-stu-id="84273-130">Remarks</span></span>  
 <span data-ttu-id="84273-131">`issuerAddress`는 클라이언트가 통신하려는 보안 토큰 서비스의 URI를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="84273-131">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="84273-132">`behaviorConfiguration` 응용 프로그램이 Windows Communication Foundation (WCF)에서 만든 채널에 보안 토큰 서비스에서 발급 된 토큰을 가져오기 위해 사용 하는 끝점 동작을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="84273-132">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84273-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84273-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>  
 [<span data-ttu-id="84273-134">서비스 ID 및 인증</span><span class="sxs-lookup"><span data-stu-id="84273-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="84273-135">보안 동작</span><span class="sxs-lookup"><span data-stu-id="84273-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="84273-136">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="84273-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="84273-137">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="84273-137">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="84273-138">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="84273-138">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="84273-139">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="84273-139">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="84273-140">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="84273-140">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="84273-141">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="84273-141">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="84273-142">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="84273-142">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
