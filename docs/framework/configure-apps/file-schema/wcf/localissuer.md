---
title: '&lt;localIssuer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6b11f5cbf2d70b4fff607ac42c2c98af7fb9542b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="8842c-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="8842c-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="8842c-103">보안 토큰을 가져오는 데 사용할 로컬 발급자의 주소 및 바인딩을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="8842c-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8842c-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="8842c-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8842c-105">\<behaviors></span></span>  
<span data-ttu-id="8842c-106">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="8842c-106">endpointBehaviors section</span></span>  
<span data-ttu-id="8842c-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="8842c-107">\<behavior></span></span>  
<span data-ttu-id="8842c-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="8842c-108">\<clientCredentials></span></span>  
<span data-ttu-id="8842c-109">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="8842c-109">\<issuedToken></span></span>  
<span data-ttu-id="8842c-110">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="8842c-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8842c-111">구문</span><span class="sxs-lookup"><span data-stu-id="8842c-111">Syntax</span></span>  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8842c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8842c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8842c-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8842c-114">특성</span><span class="sxs-lookup"><span data-stu-id="8842c-114">Attributes</span></span>  
  
|<span data-ttu-id="8842c-115">특성</span><span class="sxs-lookup"><span data-stu-id="8842c-115">Attribute</span></span>|<span data-ttu-id="8842c-116">설명</span><span class="sxs-lookup"><span data-stu-id="8842c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8842c-117">address</span><span class="sxs-lookup"><span data-stu-id="8842c-117">address</span></span>|<span data-ttu-id="8842c-118">필수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-118">Required string.</span></span> <span data-ttu-id="8842c-119">로컬 발급자의 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="8842c-120">바인딩</span><span class="sxs-lookup"><span data-stu-id="8842c-120">binding</span></span>|<span data-ttu-id="8842c-121">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-121">Optional string.</span></span> <span data-ttu-id="8842c-122">시스템에서 제공한 바인딩 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-122">One of the system-provided bindings.</span></span> <span data-ttu-id="8842c-123">목록에 대 한 참조 [시스템 제공 바인딩](../../../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="8842c-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="8842c-124">bindingConfiguration</span></span>|<span data-ttu-id="8842c-125">선택적 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-125">Optional string.</span></span> <span data-ttu-id="8842c-126">구성 파일에서 발견되는 바인딩 구성을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8842c-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8842c-127">Child Elements</span></span>  
  
|<span data-ttu-id="8842c-128">요소</span><span class="sxs-lookup"><span data-stu-id="8842c-128">Element</span></span>|<span data-ttu-id="8842c-129">설명</span><span class="sxs-lookup"><span data-stu-id="8842c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8842c-130">\<identity ></span><span class="sxs-lookup"><span data-stu-id="8842c-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8842c-131">로컬 발급자의 ID 정보를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="8842c-132">\<헤더 ></span><span class="sxs-lookup"><span data-stu-id="8842c-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="8842c-133">로컬 발급자의 주소를 올바로 지정하는 데 필요한 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="8842c-134">`add` 키워드를 사용하여 이 컬렉션에 헤더를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8842c-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8842c-135">Parent Elements</span></span>  
  
|<span data-ttu-id="8842c-136">요소</span><span class="sxs-lookup"><span data-stu-id="8842c-136">Element</span></span>|<span data-ttu-id="8842c-137">설명</span><span class="sxs-lookup"><span data-stu-id="8842c-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8842c-138">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="8842c-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="8842c-139">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8842c-140">설명</span><span class="sxs-lookup"><span data-stu-id="8842c-140">Remarks</span></span>  
 <span data-ttu-id="8842c-141">STS(보안 토큰 서비스)에서 발급된 토큰을 가져오려면 클라이언트 응용 프로그램에서 STS와 통신하는 데 사용할 주소 및 바인딩을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="8842c-142"><xref:System.ServiceModel.WSFederationHttpBinding>에서 보안 토큰 서비스에 대한 URL을 지정하지 않거나 페더레이션 바인딩의 발급자 주소가 http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous 또는 `null`인 경우 클라이언트의 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 채널에서는 `address` 및 `binding`에 지정된 값을 사용하여 STS와 통신하고 발급된 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`, the client's [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="8842c-143">로컬 발급자를 구성 하는 방법에 대 한 자세한 내용은 참조 하십시오. [하는 방법: 로컬 발급자 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8842c-144">예제</span><span class="sxs-lookup"><span data-stu-id="8842c-144">Example</span></span>  
 <span data-ttu-id="8842c-145">다음 예제에서는 `address`, `binding` 및 `bindingConfiguration` 요소의 `localIssuer` 특성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8842c-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>  
 <behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <issuedToken cacheIssuedTokens="false"   
                 defaultKeyEntropyMode="ClientEntropy">  
     <localIssuer address="net.tcp://cohowinery/tokens"   
                  binding="netTcpBinding"  
                  bindingConfiguration="myTcpBindingConfig" />  
    </issuedToken>  
   </clientCredentials>  
  </behavior>  
  </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8842c-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8842c-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="8842c-147">보안 동작</span><span class="sxs-lookup"><span data-stu-id="8842c-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="8842c-148">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="8842c-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="8842c-149">서비스 Id 및 인증</span><span class="sxs-lookup"><span data-stu-id="8842c-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="8842c-150">보안 동작</span><span class="sxs-lookup"><span data-stu-id="8842c-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="8842c-151">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="8842c-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="8842c-152">서비스 및 클라이언트 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8842c-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="8842c-153">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8842c-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="8842c-154">방법: 페더레이션된 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="8842c-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="8842c-155">페더레이션 및 발급 된 토큰</span><span class="sxs-lookup"><span data-stu-id="8842c-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
