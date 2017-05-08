---
title: "&lt;securityTokenHandlers&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
caps.latest.revision: 5
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;securityTokenHandlers&gt;
끝점을 등록 하는 보안 토큰 처리기의 컬렉션을 지정 합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|토큰 처리기 컬렉션의 이름을 지정합니다.  프레임 워크에서 인식할 수 있는 유일한 값은 "ActAs" 및 "OnBehalfOf"입니다.  토큰 처리기 컬렉션 이러한 이름 중 하나를 지정 하지 않으면 컬렉션 각각 토큰 ActAs 또는 Onbehalfof를 처리 하는 경우 사용 됩니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|보안 토큰 처리기 토큰 처리기 컬렉션에 추가합니다.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|모든 보안 토큰 처리기에서 토큰 처리기 컬렉션을 지웁니다.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|보안 토큰 처리기 토큰 처리기 컬렉션에서 제거합니다.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|토큰 처리기의 컬렉션에 대 한 구성을 제공합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
  
## 설명  
 서비스 구성에는 하나 이상의 명명 된 각종 보안 토큰 처리기를 지정할 수 있습니다.  사용 하 여 컬렉션의 이름을 지정할 수 있는 `name` 특성.  프레임 워크 처리만 이름은 "ActAs" 및 "OnBehalfOf"입니다.  처리기는이 컬렉션에 존재 하는 경우 이러한 보안 토큰 서비스 \(STS\)가 기본 처리기 대신 처리 하는 동안 사용 됩니다 `ActAs` 및 `OnBehalfOf` 토큰입니다.  
  
 기본적으로 컬렉션의 다음 처리기 유형으로 채워질: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, 및 <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.  컬렉션을 사용 하 여 수정할 수 있는 `<add>`, `<remove>`, 및 `<clear>` 요소.  사용자는 단일 처리기는 특정 형식의 컬렉션에 존재 하는지 확인 해야 합니다.  예를 들어, 처리기에서 파생 하는 경우는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스는 처리기 또는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 단일 컬렉션에 있지만 둘 다 구성할 수 있습니다.  
  
 사용의 `<securityTokenHandlerConfiguration>` 요소는 처리기에 대 한 구성 설정 컬렉션에 지정할 수 있습니다.  이 요소를 통해 지정 된 설정을 재정의 통해 서비스에 지정 된 해당 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.  몇 가지 기본 제공 처리기 형식 등 일부 처리기의 자식 요소를 통해 추가 구성을 지원할 수 있는 `<add>` 요소입니다.  처리기를 지정 하는 설정 컬렉션 또는 서비스에 지정 된 해당 설정을 재정의 합니다.