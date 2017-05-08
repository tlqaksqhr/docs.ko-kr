---
title: "&lt;system.identityModel.services&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# &lt;system.identityModel.services&gt;
WS\-페더레이션 프로토콜을 사용 하 여 인증을 위해 구성 섹션입니다.  
  
 \<system.identityModel.services\>  
  
## 구문  
  
```  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|구성 설정이 포함의 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\)와 <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\) HTTP 모듈입니다.|  
  
### 부모 요소  
 없음  
  
## 설명  
 추가 된 `<system.identityModel.services>` SAM 및 WSFAM에 대 한 설정을 제공 하는 응용 프로그램의 구성 파일에 섹션.  
  
> [!IMPORTANT]
>  사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드, 클레임 권한 부여 관리자에서에서 클레임 기반 액세스 제어를 제공 하는 클래스 \(<xref:System.Security.Claims.ClaimsAuthorizationManager>\) 및 권한 부여 결정을 만드는 데 사용 하는 정책을 통해 구성 된는 `<identityConfiguration>` 에서 암시적 또는 명시적으로 참조 하는 요소는 `<federationConfiguration>` 이 단원의 요소.  자세한 내용은  **설명** 아래는 [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소.  
  
 `<system.identityModel.services>` 섹션 표시 되는 <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> 클래스입니다.  컬렉션의 자식 `<federationConfiguration>` 섹션에 구성 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> 클래스입니다.  
  
## 예제  
 다음 XML을 추가 하는 방법을 보여 줍니다 있는 `<system.identityModel.services>` 구성 파일의 섹션.  섹션 선언 모두에 대해 먼저 추가 해야 해당 `<system.identityModel.services>` 섹션 및 `<system.identityModel>` 섹션.  \(추가 하면는 `<system.identityModel.services>` 섹션을 해야 합니다 추가할 수도 대 한 선언을 `<system.identityModel>` 섹션으로 실행 되도록 기본 `<identityConfiguration>` 섹션 필요한 경우 런타임에 만들 수 있습니다.\) 선언 섹션을 추가한 후 아래 페더레이션된 인증 설정을 구성 하는 `<system.identityModel.services>` 요소.  
  
```  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```