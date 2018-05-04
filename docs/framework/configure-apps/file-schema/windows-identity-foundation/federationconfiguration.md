---
title: '&lt;federationConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 8b14054c-6d07-46ab-ab58-03f14beac0f2
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 44014d620dcd03e055eb58b50a1428b8e1b41186
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltfederationconfigurationgt"></a>&lt;federationConfiguration&gt;
구성에서 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM)를 사용 하 여 Ws-federation 프로토콜을 통해 인증을 페더레이션 합니다. 구성에서 <xref:System.Security.Claims.ClaimsAuthorizationManager> 사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 클레임 기반 액세스 제어를 제공 하는 클래스입니다.  
  
 \<system.identityModel.services >  
\<federationConfiguration >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|페더레이션이 구성 요소의 이름입니다. 이 특성은 주로 이후 프로토콜에 대 한 확장성 지점을 제공합니다. 선택 사항입니다.|  
|identityConfigurationName|에 지정 된 id 구성 섹션 이름은 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소를 사용 합니다. 이 특성을 지정 하지 않으면 기본 id 구성 섹션에 사용 됩니다. 선택 사항입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<cookieHandler >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|SAM에서 사용 하는 쿠키 처리기를 구성 합니다. 선택 사항입니다.|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|암호화 및 토큰 암호 해독 하는 데 사용 되는 인증서를 구성 합니다. 선택 사항입니다.|  
|[\<wsFederation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md)|WS-페더레이션 인증 모듈 (WSFAM)를 구성합니다. 선택 사항입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<system.identityModel.services>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)|Ws-federation 프로토콜을 사용 하 여 인증에 대 한 구성 섹션입니다.|  
  
## <a name="remarks"></a>설명  
 \<federationConfiguration > 요소는 두 가지 시나리오에서 설정을 제공 합니다.  
  
-   요소를 구성 하는 설정이 포함 되어 WS-페더레이션 수동 웹 응용 프로그램에서을 사용할 경우의 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM). 또한 보안 토큰 처리기 및 인증서 및 클레임 권한 부여 관리자와 클레임 인증 관리자와 같은 구성 요소를 구성 하는 데 사용할 id 구성을 참조 합니다.  
  
-   사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 의 요소는 클레임 권한 부여 관리자 및 권한 부여를 확인 하는 데 사용 되는 정책을 구성 하는 id 구성을 참조, 코드에서 클레임 기반 액세스 제어를 제공 하는 클래스 의사 결정 합니다. 이 수동 웹 시나리오; 하지 않은 시나리오에도 적용 예를 들어 Windows Communication Foundation (WCF) 응용 프로그램 또는 웹 기반 하지 않는 응용 프로그램입니다. 응용 프로그램 수동 웹 응용 프로그램이 아닌 경우는 [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) 요소 (및 해당 자식 정책 요소에 있는 경우)에서 참조 하는 id 구성을의 `<federationConfiguration>` 요소 설정만 적용 됩니다. 다른 특성은 모두 무시됩니다.  
  
 시나리오에 관계 없이 런타임에서 기본 페더레이션 구성을 로드합니다. 동작은 다음과 같이 정의 됩니다.  
  
1.  없는 경우 없는 `<federationConfiguration>` 있는 요소를 런타임 페더레이션 구성을 만들고 기본 값으로 채웁니다. 이 기본 페더레이션 구성은 기본 id 구성을 참조 합니다.  
  
2.  경우는 단일 `<federationConfiguration>` 요소가 있는지,이 요소는 명명 된 또는 명명 되지 않은 여부에 관계 없이 기본 페더레이션 구성 합니다. 하는 경우 해당 `identityConfiguration` 에 명명 된 identity 구성이 참조 되는 특성 지정 됩니다. 기본 id 구성을 참조 되는 그렇지 않은 경우.  
  
3.  명명 되지 않은 경우 `<federationConfiguration>` 요소가 있는지,이 요소는 기본 페더레이션 구성 합니다. 하는 경우 해당 `identityConfiguration` 에 명명 된 identity 구성이 참조 되는 특성 지정 됩니다. 기본 id 구성을 참조 되는 그렇지 않은 경우.  
  
4.  여러 명명 된 `<federationConfiguration>` 요소가 존재 하 고 명명 되지 `<federationConfiguration>` 요소, 예외가 throw 됩니다.  
  
 일반적으로 단일 `<federationConfiguration>` 섹션에서 정의 됩니다. 이 섹션에는 기본 페더레이션 구성입니다. 고유 하 게 명명 된 여러를 지정할 수 있습니다 `<federationConfiguration>` 요소; 그러나이 경우 이름 없는 것과 다른 페더레이션 구성을 로드 하려는 경우 제공 해야에 대 한 처리기는 합니다. <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated> 이벤트 집합과 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=nameWithType> 속성 처리기를 내는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 적절 한 값으로 초기화 된 개체 `<federationConfiguration>` 구성 파일의 요소입니다.  
  
 `<federationConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElement> 클래스입니다. 자체 구성 개체도 표시 됩니다는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 클래스입니다. 단일 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 에 설정 된 인스턴스는 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 속성 하 고 응용 프로그램에 대 한 페더레이션된 구성을 제공 합니다.  
  
## <a name="example"></a>예제  
 에서는 다음 XML는 `<federationConfiguration>` 요소는 WSFAM에 대 한 설정을 지정 하 고 지정 하는 기본 쿠키 처리기 (의 인스턴스는 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 클래스) SAM에서 사용할 수 있습니다.  
  
> [!WARNING]
>  이 예제에서는 쿠키 처리기 아니고 WSFAM 해야 HTTPS를 사용 합니다. ¿¡´는 `requireHttps` 특성에 `<wsFederation>` 요소 및 `requireSsl` 특성에 `<cookieHandlerElement>` 는 `false`합니다. 이러한 설정은 보안상 위험 해질 수 있습니다 때 대부분의 프로덕션 환경에 권장 되지 않습니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>  
 [\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)
