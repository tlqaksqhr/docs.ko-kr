---
title: "&lt;userNameSecurityTokenHandlerRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ec3bac1-b014-49ae-843c-c54518cb709a
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;userNameSecurityTokenHandlerRequirement&gt;
구성에 제공 된 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스 또는 파생된 클래스.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
        <userNameSecurityTokenHandlerRequirement membershipProviderName=xs:string >  
        </userNameSecurityTokenHandlerRequirement>  
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
|membershipProviderName|지정 된 <xref:System.Web.Security.MembershipProvider> 보안 토큰 처리기에서 사용 해야 합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|지정 된 보안 토큰 처리기는 토큰 처리기 컬렉션에 추가합니다.|  
  
## 설명  
 `<userNameSecurityTokenHandlerRequirement>` 요소 집합의 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler.MembershipProvider%2A> 속성 경우는 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 에서 구성 개체를 초기화 합니다.  
  
## 예제  
  
```  
<add type="System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler, System.IdentityModel.Services">  
    <userNameSecurityTokenHandlerRequirement membershipProviderName="AspNetSqlProvider/>  
</add>  
```