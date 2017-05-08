---
title: "&lt;nameClaimType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 17514d95-f0f5-4789-8e28-346640dc227c
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;nameClaimType&gt;
지정 하는 클레임 형식을 설정 하는 <xref:System.Security.Principal.IIdentity.Name%2A> 속성.  클레임 형식에 대 한 검색에 사용 되는 <xref:System.Security.Claims.Claim> 컬렉션의 <xref:System.Security.Claims.ClaimsIdentity> 반환한 개체는 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 이 토큰 처리기 메서드.  일치 하는 클레임의 값은 다음 이름으로 설정 되어 있는 <xref:System.Security.Principal.IIdentity> 이 토큰 처리기에서 생성 합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement>  
          <nameClaimType value=xs:string>  
          </nameClaimType>  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|value|클레임 유형을 사용 하는 클레임을 나타내는 URI를 지정 하는 문자열을 <xref:System.Security.Principal.IIdentity.Name%2A> 속성.  필수 요소.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|구성에 대 한 제공의 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는이 클래스의 파생된 클래스.|  
  
## 설명  
 `<nameClaimType>` 요소 집합의 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A> 속성 경우는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 에서 구성 개체를 초기화 합니다.  
  
## 예제  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement>  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
    </samlSecurityTokenRequirement>  
</add>  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement.NameClaimType%2A>