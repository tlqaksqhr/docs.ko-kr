---
title: "&lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;add&gt;
지정 된 보안 토큰 처리기 토큰 처리기 컬렉션에 추가합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
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
|type|추가할 토큰 처리기의 CLR 형식 이름입니다.  지정 하는 방법에 대 한 자세한 내용은 `type` 특성, 볼 [Custom Type References](http://msdn.microsoft.com/ko-kr/7286d2e3-c63d-49fd-abdc-ce2705f22c24).|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<samlSecurityTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|구성을 제공의 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는이 클래스의 파생된 클래스입니다.|  
|[\<sessionTokenRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|구성에 대 한 제공의 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스 또는 파생된 클래스입니다.|  
|[\<userNameSecurityTokenHandlerRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|구성에 대 한 제공의 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스 또는 파생된 클래스입니다.|  
|[\<x509SecurityTokenHandlerRequirement\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|선택적 구성에 대 한 제공의 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스 또는 파생된 클래스입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|끝점을 등록 하는 보안 토큰 처리기의 컬렉션을 지정 합니다.|  
  
## 설명  
 `<add>` 요소는 토큰 처리기 구성을 지정 하는 단일 자식 요소를 걸릴 수 있습니다.  이것 처리기 클래스를 통해 참조 여부에 달려 있습니다는 `type` 의 특성의 `<add>` 요소는이 기능에 대 한 지원을 제공 합니다.  이 기능을 제공 하는 토큰 처리기 클래스를 사용 하는 생성자를 노출 해야는 <xref:System.Xml.XmlElement> 개체입니다.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 몇 가지 기본 제공 된 보안 토큰 처리기 클래스는이 기능을 제공 하지.  These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.  
  
> [!IMPORTANT]
>  토큰 처리기 컬렉션만 주어진 형식의 단일 처리기를 포함할 수 있습니다.  파생 하는 처리기를 추가 하려는 경우, 예를 들어, 즉의 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 컬렉션에 먼저 제거 해야는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, 컬렉션에서 기본적으로 제공 됩니다.  사용할 수 있는 [\<remove\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) 컬렉션이 나 사용에서 단일 처리기를 제거할 요소는 [\<clear\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) 모든 처리기 컬렉션에서 제거할 요소.  
  
 처리기에 지정 된 설정을 토큰 처리기 컬렉션에서 지정 된 해당 설정을 재정의 하는 [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 요소 및 서비스 수준에서 지정 된는 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소.  
  
## 예제  
 다음 XML 사용을 보여 줍니다.의 `<add>` 및 `<remove>` 요소를 사용자 지정 하는 세션 토큰 처리기가 기본 세션 토큰 처리기를 대체할 수 있습니다.  XML을 가져온 것은 `ClaimsAwareWebFarm` 샘플입니다.  
  
```  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```