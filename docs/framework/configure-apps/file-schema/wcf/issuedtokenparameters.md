---
title: '&lt;r s&gt;'
ms.date: 03/30/2017
ms.assetid: 120b3f37-7331-4816-b712-d6aab39655a4
ms.openlocfilehash: 550b3412b193b996b8de800856d6833369fc4bc7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltissuedtokenparametersgt"></a>&lt;r s&gt;
페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.  
  
 \<system.serviceModel>  
\<바인딩 >  
\<customBinding>  
\<바인딩 >  
\<security>  
\<r s >  
  
## <a name="syntax"></a>구문  
  
```xml  
<issuedTokenParameters   
      DefaultMessageSecurityVersion="System.ServiceModel.MessageSecurityVersion"  
      inclusionMode="AlwaysToInitiator/AlwaysToRecipient/Never/Once"  
      keySize="Integer"  
   keyType="AsymmetricKey/BearerKey/SymmetricKey"  
      tokenType="String" >  
   <additionalRequestParameters />  
      <claimTypeRequirements>  
            <add claimType="URI"  
           isOptional="Boolean" />  
      </claimTypeRequirements>  
      <issuer address="String"   
                      binding=" " />  
      <issuerMetadata address="String" />   
</issuedTokenParameters>  
```  
  
## <a name="type"></a>형식  
 `Type`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|defaultMessageSecurityVersion|바인딩에서 지원해야 하는 보안 사양(WS-Security, WS-Trust, WS-Secure Conversation, WS-Security Policy) 버전을 지정합니다. 이 값은 <xref:System.ServiceModel.MessageSecurityVersion> 형식입니다.|  
|inclusionMode|토큰 포함 요구 사항을 지정합니다. 이 특성은 <xref:System.ServiceModel.Security.Tokens.SecurityTokenInclusionMode> 형식입니다.|  
|keySize|토큰 키 크기를 지정하는 정수입니다. 기본값은 256입니다.|  
|keyType|키 형식을 지정하는 유효한 <xref:System.IdentityModel.Tokens.SecurityKeyType> 값입니다. 기본값은 `SymmetricKey`입니다.|  
|tokenType|토큰 형식을 지정하는 문자열입니다. 기본값은 "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAML"입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<additionalRequestParameters >](../../../../../docs/framework/configure-apps/file-schema/wcf/additionalrequestparameters-element.md)|추가 요청 매개 변수를 지정하는 구성 요소 컬렉션입니다.|  
|[\<claimTypeRequirements>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|필요한 클레임 형식의 컬렉션을 지정합니다.<br /><br /> 페더레이션 시나리오에서 서비스는 들어오는 자격 증명에 대한 요구 사항을 기술합니다. 예를 들어, 들어오는 자격 증명은 특정 집합의 클레임 형식이어야 합니다. 이 컬렉션의 각 요소는 페더레이션 자격 증명에 표시되어야 하는 필수 클레임 및 선택적 클레임의 형식을 지정합니다.|  
|[\<issuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer-of-issuedtokenparameters.md)|현재 토큰을 발급하는 끝점을 지정하는 구성 요소입니다.|  
|[\<issuerMetadata>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata-of-issuedtokenparameters.md)|토큰 발급자의 메타데이터의 끝점 주소를 지정하는 구성 요소입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<secureConversationBootstrap >](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|보안 대화 서비스 개시에 사용되는 기본값을 지정합니다.|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)|사용자 지정 바인딩에 대한 보안 옵션을 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [사용자 지정 바인딩 보안](../../../../../docs/framework/wcf/samples/custom-binding-security.md)  
 [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [사용자 지정 바인딩을 사용하는 보안 기능](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
