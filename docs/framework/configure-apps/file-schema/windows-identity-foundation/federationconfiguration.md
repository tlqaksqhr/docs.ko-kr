---
title: "&lt;federationConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# &lt;federationConfiguration&gt;
구성의 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\)와 <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\)를 사용 하는 경우 페더레이션 WS\-페더레이션 프로토콜을 통해 인증 합니다.  구성의 <xref:System.Security.Claims.ClaimsAuthorizationManager> 사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 클레임 기반 액세스 제어를 제공 하는 클래스입니다.  
  
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
  
|특성|설명|  
|--------|--------|  
|name|이 페더레이션 구성 요소의 이름입니다.  이 특성은 주로 위한 확장성 지점을 향후 프로토콜을 제공합니다.  선택적 요소.|  
|identityConfigurationName|Identity 구성 섹션에 지정 된 대로 이름을 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소를 사용 합니다.  이 특성을 지정 하지 않으면 기본 identity 구성 섹션이 사용 됩니다.  선택적 요소.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<cookieHandler\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|사용 하 여 SAM 쿠키 처리기를 구성 합니다.  선택적 요소.|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|암호화 하 고 토큰을 해독 하는 데 사용 되는 인증서를 구성 합니다.  선택적 요소.|  
|[\<wsFederation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|WS\-페더레이션 인증 모듈 \(WSFAM\)를 구성합니다.  선택적 요소.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<system.identityModel.services\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|WS\-페더레이션 프로토콜을 사용 하 여 인증을 위해 구성 섹션입니다.|  
  
## 설명  
 \<federationConfiguration\> 요소 설정에는 두 가지 시나리오를 제공합니다.  
  
-   WS\-페더레이션 수동 웹 응용 프로그램에서 사용 하는 경우 요소는 구성 설정을 포함의 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\)와 <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).  또한 보안 토큰 처리기 및 인증서 및 클레임 권한 부여 관리자 및 클레임 인증 관리자 구성 요소를 구성 하는 데는 identity 구성을 참조 합니다.  
  
-   사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 클레임 기반 액세스 제어를 제공 하는 클래스, 클레임 권한 부여 관리자와 권한 부여 결정을 만드는 데 사용 하는 정책을 구성 하는 identity 구성 요소를 참조 합니다.  수동 웹 시나리오 없는 경우에도 마찬가지입니다. 예를 들어, Windows 통신 Foundation \(WCF\) 응용 프로그램 또는 웹 기반 된 응용 프로그램입니다.  응용 프로그램이 수동 웹 응용 프로그램이 없는 경우는 [\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) 요소와 해당 자식 정책 요소에 있는 경우 identity 구성 참조는 `<federationConfiguration>` 요소에만 설정이 적용 됩니다.  다른 멤버는 모두 무시됩니다.  
  
 시나리오에 관계 없이 런타임에서 기본 페더레이션 구성을 로드합니다.  동작은 다음과 같이 정의 됩니다.  
  
1.  있으면 없음 `<federationConfiguration>` 요소가 존재, 런타임에서 페더레이션 구성을 만들고 기본 값을 채웁니다.  이 기본 페더레이션 구성 기본 identity 구성을 참조 합니다.  
  
2.  단일 경우 `<federationConfiguration>` 요소 존재, 그 이라는 또는 명명 되지 않은 있는지 여부에 관계 없이 기본 페더레이션 구성 됩니다.  경우 해당 `identityConfiguration` 특성을 지정한 경우 명명 된 identity 구성 참조 됩니다. 그렇지 않으면 기본 identity 구성 참조 됩니다.  
  
3.  이름 없는 경우 `<federationConfiguration>` 요소가 존재,이 기본 페더레이션 구성 됩니다.  경우 해당 `identityConfiguration` 특성을 지정한 경우 명명 된 identity 구성 참조 됩니다. 그렇지 않으면 기본 identity 구성 참조 됩니다.  
  
4.  여러 명명 된 경우 `<federationConfiguration>` 요소가 존재 하 고 더 명명 되지 않은 `<federationConfiguration>` 요소가 존재 이므로 예외가 throw 됩니다.  
  
 일반적으로 한 번만 `<federationConfiguration>` 단면을 정의 합니다.  이 섹션에서는 기본 페더레이션 구성입니다.  여러 개의 고유한 이름의 지정 될 수 있습니다 `<federationConfiguration>` 요소입니다. 그러나 명명 되지 않은 다른 페더레이션 구성을 로드 하려는 경우이 경우 처리기를 제공 해야를 합니다.  <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated>이벤트 및 집합은 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=fullName> 속성 처리기에 내는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 개체의 적절 한 값으로 초기화 `<federationConfiguration>` 구성 파일의 요소.  
  
 `<federationConfiguration>` 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> 클래스입니다.  구성 개체가 표시 되는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 클래스입니다.  단일 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 인스턴스 설정의 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> 속성 및 응용 프로그램에 대 한 페더레이션된 구성을 제공 합니다.  
  
## 예제  
 다음 XML 표시는 `<federationConfiguration>` 는 WSFAM에 대 한 설정을 지정 하 고 지정 하는 요소 쿠키 기본 처리기 \(의 인스턴스는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스\) SAM에서 사용.  
  
> [!WARNING]
>  이 예제에서는 쿠키 처리기 아니고 WSFAM 하는 데 필요한 HTTPS를 사용 합니다.  되므로 이런는 `requireHttps` 특성에 `<wsFederation>` 요소와 `requireSsl` 특성에 `<cookieHandlerElement>` 는 `false`.  이러한 보안 위험이 존재할 수 있습니다 대로 이러한 설정은 대부분의 프로덕션 환경에 권장 되지 않습니다.  
  
```  
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
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>   
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName>   
 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)