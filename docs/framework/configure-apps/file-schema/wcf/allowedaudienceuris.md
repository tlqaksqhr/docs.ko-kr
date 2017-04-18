---
title: "&lt;allowedAudienceUris&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f4dc73d-d95d-4193-9755-7df4cf2b8e1c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;allowedAudienceUris&gt;
<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 보안 토큰의 대상 URI 컬렉션을 나타냅니다.  
  
## 구문  
  
```  
  
<allowedAudienceUris>  
      <add allowedAudienceUri="String"/>  
</allowedAudienceUris>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)|<xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator> 인스턴스에서 유효한 대상으로 지정할 수 있는 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 보안 토큰의 대상 URI를 추가합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|서비스 자격 증명으로 발급된 토큰을 지정합니다.|  
  
## 설명  
 STS\(보안 토큰 서비스\)를 사용하여 <xref:System.IdentityModel.Tokens.SamlSecurityToken> 보안 토큰을 발급하는 페더레이션 응용 프로그램에서는 이 컬렉션을 사용해야 합니다.  STS는 보안 토큰을 발급할 때 보안 토큰에 <xref:System.IdentityModel.Tokens.SamlAudienceRestrictionCondition>을 추가하여 보안 토큰을 사용할 웹 서비스의 URI를 지정할 수 있습니다.  따라서 발급된 보안 토큰이 해당 웹 서비스용인지 검사하도록 지정하여 수신자 웹 서비스의 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>가 이를 확인하도록 할 수 있습니다. 이렇게 하려면 다음을 수행하세요.  
  
-   `<issuedTokenAuthentication>`의 `audienceUriMode` 특성을 <xref:System.IdentityModel.Selectors.AudienceUriMode> 또는 <xref:System.IdentityModel.Selectors.AudienceUriMode>로 설정합니다.  
  
-   이 컬렉션에 URI를 추가하여 유효한 URI 집합을 지정합니다.  
  
 자세한 내용은 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>을 참조하세요.  
  
 이 구성 요소 사용에 대한 자세한 내용은 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.AllowedAudienceUris%2A>   
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElementCollection>   
 <xref:System.ServiceModel.Configuration.AllowedAudienceUriElement>   
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.AllowedAudienceUris%2A>   
 [\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowedaudienceuris.md)   
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)