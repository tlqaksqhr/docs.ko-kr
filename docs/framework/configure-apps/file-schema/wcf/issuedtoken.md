---
title: '&lt;issuedToken&gt;'
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 9a8d701e0806aae0a17a1c5ff7284606dd080f85
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750235"
---
# <a name="ltissuedtokengt"></a><span data-ttu-id="f515e-102">&lt;issuedToken&gt;</span><span class="sxs-lookup"><span data-stu-id="f515e-102">&lt;issuedToken&gt;</span></span>
<span data-ttu-id="f515e-103">서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-103">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="f515e-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f515e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f515e-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="f515e-105">\<behaviors></span></span>  
<span data-ttu-id="f515e-106">endpointBehaviors 섹션</span><span class="sxs-lookup"><span data-stu-id="f515e-106">endpointBehaviors section</span></span>  
<span data-ttu-id="f515e-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="f515e-107">\<behavior></span></span>  
<span data-ttu-id="f515e-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f515e-108">\<clientCredentials></span></span>  
<span data-ttu-id="f515e-109">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="f515e-109">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f515e-110">구문</span><span class="sxs-lookup"><span data-stu-id="f515e-110">Syntax</span></span>  
  
```xml  
<issuedToken   
   cacheIssuedTokens="Boolean"  
   defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"  
   issuedTokenRenewalThresholdPercentage = "0 to 100"  
   issuerChannelBehaviors="String"  
      localIssuerChannelBehaviors="String"  
   maxIssuedTokenCachingTime="TimeSpan"  
</issuedToken>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f515e-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f515e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f515e-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f515e-113">특성</span><span class="sxs-lookup"><span data-stu-id="f515e-113">Attributes</span></span>  
  
|<span data-ttu-id="f515e-114">특성</span><span class="sxs-lookup"><span data-stu-id="f515e-114">Attribute</span></span>|<span data-ttu-id="f515e-115">설명</span><span class="sxs-lookup"><span data-stu-id="f515e-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="f515e-116">토큰이 캐시되는지 여부를 지정하는 선택적 부울 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-116">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="f515e-117">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-117">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="f515e-118">핸드셰이크 작업에 사용되는 임의의 값(엔트로피)을 지정하는 선택적 문자열 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-118">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="f515e-119">값에는 `ClientEntropy`, `ServerEntropy` 및 `CombinedEntropy`가 포함되며, 기본값은 `CombinedEntropy`입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-119">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="f515e-120">이 특성은 <xref:System.ServiceModel.Security.SecurityKeyEntropyMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-120">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="f515e-121">토큰을 갱신하기 전에 경과할 수 있는 유효한 기간(토큰 발급자가 제공)의 백분율을 지정하는 선택적 정수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-121">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="f515e-122">값은 0부터 100까지이며,</span><span class="sxs-lookup"><span data-stu-id="f515e-122">Values are from 0 to 100.</span></span> <span data-ttu-id="f515e-123">기본값은 갱신을 시도하기 전에 60%의 시간 경과를 지정하는 60입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-123">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="f515e-124">발급자와 통신할 때 사용할 채널 동작을 지정하는 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-124">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="f515e-125">로컬 발급자와 통신할 때 사용할 채널 동작을 지정하는 선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-125">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="f515e-126">토큰 발급자(STS)가 시간을 지정하지 않은 경우 발급된 토큰이 캐시되는 기간을 지정하는 선택적 Timespan 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-126">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="f515e-127">기본값은 "10675199.02:48:05.4775807."</span><span class="sxs-lookup"><span data-stu-id="f515e-127">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f515e-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f515e-128">Child Elements</span></span>  
  
|<span data-ttu-id="f515e-129">요소</span><span class="sxs-lookup"><span data-stu-id="f515e-129">Element</span></span>|<span data-ttu-id="f515e-130">설명</span><span class="sxs-lookup"><span data-stu-id="f515e-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f515e-131">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="f515e-131">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="f515e-132">끝점과의 통신에 사용되는 토큰 및 바인딩의 로컬 발급자 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-132">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="f515e-133">\<issuerChannelBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f515e-133">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="f515e-134">로컬 발급자에 연결할 때 사용할 끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-134">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f515e-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f515e-135">Parent Elements</span></span>  
  
|<span data-ttu-id="f515e-136">요소</span><span class="sxs-lookup"><span data-stu-id="f515e-136">Element</span></span>|<span data-ttu-id="f515e-137">설명</span><span class="sxs-lookup"><span data-stu-id="f515e-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f515e-138">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="f515e-138">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="f515e-139">클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-139">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f515e-140">설명</span><span class="sxs-lookup"><span data-stu-id="f515e-140">Remarks</span></span>  
 <span data-ttu-id="f515e-141">발급된 토큰은 사용자 지정 자격 증명 형식으로, 예를 들어 페더레이션 시나리오에서 STS(보안 토큰 서비스)를 사용하여 인증할 때 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-141">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="f515e-142">기본적으로 토큰은 SAML 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-142">By default, the token is a SAML token.</span></span> <span data-ttu-id="f515e-143">자세한 내용은 참조 [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-143">For more information, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="f515e-144">및 [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-144">and [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="f515e-145">이 섹션에는 토큰 로컬 발급자를 구성하는 데 사용되는 요소 또는 보안 토큰 서비스에서 사용되는 동작이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-145">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="f515e-146">로컬 발급자를 사용 하는 클라이언트를 구성 하는 방법에 지침은 참조 하십시오. [하는 방법: 로컬 발급자 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f515e-146">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f515e-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f515e-147">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="f515e-148">보안 동작</span><span class="sxs-lookup"><span data-stu-id="f515e-148">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="f515e-149">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="f515e-149">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="f515e-150">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="f515e-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="f515e-151">클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="f515e-151">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="f515e-152">방법: 페더레이션 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="f515e-152">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="f515e-153">방법: 로컬 발급자 구성</span><span class="sxs-lookup"><span data-stu-id="f515e-153">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="f515e-154">페더레이션 및 발급된 토큰</span><span class="sxs-lookup"><span data-stu-id="f515e-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
