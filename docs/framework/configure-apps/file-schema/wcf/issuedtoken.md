---
title: '&lt;issuedToken&gt;'
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 9a8d701e0806aae0a17a1c5ff7284606dd080f85
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuedtokengt"></a>&lt;issuedToken&gt;
서비스에 대해 클라이언트를 인증할 때 사용되는 사용자 지정 토큰을 지정합니다.  
  
 \<system.ServiceModel>  
\<동작 >  
endpointBehaviors 섹션  
\<동작 >  
\<clientCredentials>  
\<issuedToken >  
  
## <a name="syntax"></a>구문  
  
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
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`cacheIssuedTokens`|토큰이 캐시되는지 여부를 지정하는 선택적 부울 특성입니다. 기본값은 `true`입니다.|  
|`defaultKeyEntropyMode`|핸드셰이크 작업에 사용되는 임의의 값(엔트로피)을 지정하는 선택적 문자열 특성입니다. 값에는 `ClientEntropy`, `ServerEntropy` 및 `CombinedEntropy`가 포함되며, 기본값은 `CombinedEntropy`입니다. 이 특성은 <xref:System.ServiceModel.Security.SecurityKeyEntropyMode> 형식입니다.|  
|`issuedTokenRenewalThresholdPercentage`|토큰을 갱신하기 전에 경과할 수 있는 유효한 기간(토큰 발급자가 제공)의 백분율을 지정하는 선택적 정수 특성입니다. 값은 0부터 100까지이며, 기본값은 갱신을 시도하기 전에 60%의 시간 경과를 지정하는 60입니다.|  
|`issuerChannelBehaviors`|발급자와 통신할 때 사용할 채널 동작을 지정하는 선택적 특성입니다.|  
|`localIssuerChannelBehaviors`|로컬 발급자와 통신할 때 사용할 채널 동작을 지정하는 선택적 특성입니다.|  
|`maxIssuedTokenCachingTime`|토큰 발급자(STS)가 시간을 지정하지 않은 경우 발급된 토큰이 캐시되는 기간을 지정하는 선택적 Timespan 특성입니다. 기본값은 "10675199.02:48:05.4775807."|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<localIssuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|끝점과의 통신에 사용되는 토큰 및 바인딩의 로컬 발급자 주소를 지정합니다.|  
|[\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|로컬 발급자에 연결할 때 사용할 끝점 동작을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 발급된 토큰은 사용자 지정 자격 증명 형식으로, 예를 들어 페더레이션 시나리오에서 STS(보안 토큰 서비스)를 사용하여 인증할 때 사용됩니다. 기본적으로 토큰은 SAML 토큰입니다. 자세한 내용은 참조 [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)합니다. 및 [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)합니다.  
  
 이 섹션에는 토큰 로컬 발급자를 구성하는 데 사용되는 요소 또는 보안 토큰 서비스에서 사용되는 동작이 포함되어 있습니다. 로컬 발급자를 사용 하는 클라이언트를 구성 하는 방법에 지침은 참조 하십시오. [하는 방법: 로컬 발급자 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)  
 [방법: 페더레이션 클라이언트 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [방법: 로컬 발급자 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
