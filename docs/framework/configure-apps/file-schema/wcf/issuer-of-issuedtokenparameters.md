---
title: "&lt;issuedTokenParameters&gt;의 &lt;issuer&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;issuedTokenParameters&gt;의 &lt;issuer&gt;
보안 토큰을 발급하는 STS\(보안 토큰 서비스\)를 지정합니다.  
  
## 구문  
  
```  
  
<issuer address="Uri" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|address|필수 문자열입니다.  STS의 URL입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<headers\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|작성기에서 만들 수 있는 끝점의 주소 헤더 컬렉션입니다.|  
|[\<identity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|발급된 토큰을 사용하는 경우 클라이언트가 서버를 인증할 수 있도록 설정을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<issuedTokenParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|현재 발급된 토큰을 지정합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [사용자 지정 바인딩을 사용하는 보안 기능](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)   
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)   
 [사용자 지정 바인딩 보안](../../../../../docs/framework/wcf/samples/custom-binding-security.md)