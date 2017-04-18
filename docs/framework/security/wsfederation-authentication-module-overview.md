---
title: "WSFederation 인증 모듈 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 02c4d5e8-f0a7-49ee-9cf5-3647578510ad
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# WSFederation 인증 모듈 개요
Windows Identity 기초 \(WIF\)는 WS\-Federated 인증 모듈 \(FAM WS\)를 통해 ASP.NET 응용 프로그램에서 페더레이션된 인증 지원 합니다.  이 항목은 방식이 페더레이션된 인증 작동 및 사용 하는 방법을 이해 하는 데 도움이 됩니다.  
  
### 페더레이션된 인증 개요  
 페더레이션된 인증을 서비스 STS \(보안 토큰\) 트러스트 도메인에서 두 도메인 간에 트러스트 관계가 있을 때 다른 트러스트 도메인의 STS에 인증 정보를 제공할 수 있습니다.  이러한 예는 다음 그림에 표시 됩니다.  
  
 ![페더레이션 인증 시나리오](../../../docs/framework/security/media/federatedauthentication.png "FederatedAuthentication")  
  
1.  Fabrikam 트러스트 도메인의 클라이언트가 트러스트 도메인 Contoso의 신뢰 당사자 \(RP\) 응용 프로그램에 요청을 보냅니다.  
  
2.  RP 클라이언트를 신뢰 Contoso 도메인의 STS로 리디렉션합니다.  이 STS는 클라이언트가 알지 못합니다.  
  
3.  Contoso STS 클라이언트를 Contoso 도메인 트러스트는 트러스트 관계가 Fabrikam 트러스트 도메인의 STS로 리디렉션합니다.  
  
4.  Fabrikam STS 클라이언트의 id를 확인 하 고 Contoso STS에는 보안 토큰을 발급 합니다.  
  
5.  Contoso STS RP로 보냅니다 RP에서 사용할 수 있는 고유한 토큰을 만들 Fabrikam 토큰을 사용 합니다.  
  
6.  RP 보안 토큰에서 클라이언트의 클레임을 추출 하 고 권한 부여를 결정 합니다.  
  
### ASP.NET을 사용 하 여 페더레이션된 인증 모듈을 사용 하 여  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>페더레이션된 인증을 추가할 수 있는 HTTP 모듈 \(FAM WS\)는 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 응용 프로그램입니다.  페더레이션된 인증을 사용 하면 인증 논리를 STS와 비즈니스 논리 작성에 집중할 수 있도록 하 여 처리할 수 있습니다.  
  
 인증 되지 않은 요청을 리디렉션할 STS를 지정 하 고 WS FAM을 구성 합니다.  WIF에서는 두 가지 방법으로 사용자를 인증할 수 있습니다.  
  
1.  수동 리디렉션: 시기는 인증 되지 않은 사용자가 보호 된 리소스에 액세스 하려고 고 하기만 하면 로그인 페이지 없이 STS를 리디렉션하려면 다음 올바른 접근 방법입니다.  STS는 사용자의 id를 확인 하 고 해당 사용자에 대 한 적절 한 클레임을 포함 하는 보안 토큰을 발급 합니다.  이 옵션을 사용 하려면 HTTP 모듈이 파이프라인에 추가 되도록 WS FAM.  Id 및 액세스 도구를 Visual Studio 2012 WS FAM을 STS를 사용 하 여 페더레이션 응용 프로그램의 구성 파일을 수정 하는 데 사용할 수 있습니다.  자세한 내용은 [Visual Studio 2012용 ID 및 액세스 도구](../../../docs/framework/security/identity-and-access-tool-for-vs.md)을 참조하십시오.  
  
2.  호출할 수 있는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignIn%2A?displayProperty=fullName> 메서드 또는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectToIdentityProvider%2A> RP 응용 프로그램의 로그인 페이지에 대 한 코드 숨김 파일에서 메서드.  
  
 수동 리디렉션 모든 통신은 클라이언트 \(브라우저\)의 응답\/리디렉션을 통해 수행 됩니다.  WS FAM 위치 감시에 인증 되지 않은 사용자 요청 하 고 사용자를 리디렉션합니다 응용 프로그램의 HTTP 파이프라인에 추가할 수 있습니다 STS를 지정 합니다.  
  
 WS FAM의 기능을 사용자 지정할 수 있는 여러 이벤트를 발생 한 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 응용 프로그램입니다.  
  
### WS FAM의 작동 방식  
 WS FAM에서 구현 되는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 클래스입니다.  일반적으로, WS FAM의 HTTP 파이프라인에 추가 하면 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] RP 응용 프로그램.  인증 되지 않은 사용자는 보호 된 리소스에 액세스를 시도할 때 RP에서 "401 인증이 거부 되었습니다" HTTP 응답을 반환 합니다.  WS FAM 가로채이 응답을 받으려는 클라이언트 허용 하는 대신 다음 사용자 지정 된 STS로 리디렉션합니다.  STS WS FAM 다시 차단 하는 보안 토큰을 발급 합니다.  WS FAM 토큰의 인스턴스를 사용 하 여 <xref:System.Security.Claims.ClaimsPrincipal> 인증 된 사용자를 통해 보통 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 권한 부여 메커니즘을 작동 합니다.  
  
 HTTP는 상태 비저장 이므로 사용자가 보호 되는 다른 리소스에 액세스 하려고 할 때마다가 모든 과정을 반복 하지 않도록 하는 방법을 해야 합니다.  여기서는의 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 제공 합니다.  STS 사용자에 대 한 보안 토큰을 발급 하는 경우 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 또한 세션 보안 토큰을 생성 하 고 쿠키에 저장 합니다.  후속 요청은 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 이 쿠키를 차단 하 고 사용자를 다시 만드는 데 사용 <xref:System.Security.Claims.ClaimsPrincipal>.  
  
 다음 다이어그램은 수동 리디렉션 경우에서 전체 정보 흐름을 보여 줍니다.  요청은 로그인 페이지 없이 자격 증명을 설정 하려면 STS를 통해 자동으로 리디렉션됩니다.  
  
 ![수동 리디렉션을 사용한 로그인을 위한 타이밍 다이어그램](../../../docs/framework/security/media/signinusingpassiveredirect.png "SignInUsingPassiveRedirect")  
  
 다음 다이어그램은 사용자가 STS에 인증 하는 경우에 보다 세부적으로 표시에서 보안 토큰을 처리 하 고 있는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>.  
  
 ![수동 리디렉션을 사용한 토큰 처리를 위한 타이밍](../../../docs/framework/security/media/signinusingpassiveredirect-tokenprocessing.png "SignInUsingPassiveRedirect\_TokenProcessing")  
  
 다음 다이어그램은 쿠키에 serialize 되어 있는 사용자의 보안 토큰에 의해 차단 됩니다 때 발생 하는 것에 보다 세부적으로 표시 된 <xref:System.IdentityModel.Services.SessionAuthenticationModule>.  
  
 ![컨트롤을 사용한 로그인을 보여 주는 SAM 타이밍 다이어그램](../../../docs/framework/security/media/signinusingconrols-sam.png "SignInUsingConrols\_SAM")  
  
### 이벤트  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> <xref:System.IdentityModel.Services.SessionAuthenticationModule>, 해당 부모 클래스와 <xref:System.IdentityModel.Services.HttpModuleBase>, HTTP 요청 처리의 여러 단계에서 이벤트를 발생 시킵니다.  이러한 이벤트를 처리할 수는 `global.asax` 파일에 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 응용 프로그램.  
  
-   ASP.NET 인프라에서 호출 하는 모듈의 <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> 모듈을 초기화 하는 방법입니다.  
  
-   <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated?displayProperty=fullName> ASP.NET 인프라를 호출 하면 이벤트가 발생 하면 <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> 방법에서 파생 되는 응용 프로그램의 모듈 중 하나에 처음으로 <xref:System.IdentityModel.Services.HttpModuleBase>.  이 메서드는 정적 액세스 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> 속성을 사용 하면 Web.config 파일에서 로드 되도록 구성 됩니다.  이 이벤트가 처음이이 속성에 액세스할 때만 발생.  <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 구성에서 초기화 되는 개체를 통해 액세스할 수 있는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=fullName> 이벤트 처리기의 속성.  모든 모듈에 적용 되기 전에 구성을 수정 하려면이 이벤트를 사용할 수 있습니다.  Application\_Start 메서드에서이 이벤트 처리기를 추가할 수 있습니다.  
  
    ```  
    void Application_Start(object sender, EventArgs e)  
    {  
        FederatedAuthentication.FederationConfigurationCreated += new EventHandler<FederationConfigurationCreatedEventArgs>(FederatedAuthentication_FederationConfigurationCreated);  
    }  
    ```  
  
     우선 각 모듈은 <xref:System.IdentityModel.Services.HttpModuleBase.InitializeModule%2A?displayProperty=fullName> 및 <xref:System.IdentityModel.Services.HttpModuleBase.InitializePropertiesFromConfiguration%2A?displayProperty=fullName> 추상 메서드.  이러한 메서드의 첫 번째 모듈에 있는 ASP.NET 파이프라인 이벤트의 처리기를 추가 합니다.  대부분의 경우에서 모듈의 기본 구현은 만으로도 충분 합니다.  이러한 메서드 중 두 번째 모듈의 속성 초기화의 <xref:System.IdentityModel.Services.HttpModuleBase.FederationConfiguration%2A?displayProperty=fullName> 속성입니다. \(이전에 로드 된 구성의 복사본입니다.\) 파생 된 클래스에 새 속성 구성에서 초기화를 지원 하려는 경우이 두 번째 메서드를 재정의 해야 할 수 있습니다 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 또는 <xref:System.IdentityModel.Services.SessionAuthenticationModule>.  이런 경우에도 해야 추가 구성 속성을 지원 하기 위해 적절 한 구성 개체에서 파생 for example, from <xref:System.IdentityModel.Configuration.IdentityConfiguration>, <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration>, or <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>.  
  
-   WS FAM 발생 하면 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenReceived> 이벤트는 STS에 의해 발급 된 보안 토큰을 가로채는 경우.  
  
-   WS FAM 발생 하면 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenValidated> 토큰 유효성 검사가 완료 후 이벤트.  
  
-   <xref:System.IdentityModel.Services.SessionAuthenticationModule> 발생 하면 <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenCreated> 이벤트 세션 보안 토큰을 만들 때.  
  
-   <xref:System.IdentityModel.Services.SessionAuthenticationModule> 발생 하면 <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenReceived> 이벤트 세션 보안 토큰을 포함 하는 쿠키를 사용 하 여 후속 요청을 가로채는 경우.  
  
-   WS FAM 발급자로 사용자가 리디렉션됩니다를 전에 발생 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> 이벤트입니다.  WS\-페더레이션 로그인 요청을 통해 사용할 수는 <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs.SignInRequestMessage%2A> 속성의 <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs> 이벤트에 전달 합니다.  요청이이 고 발행자에 게 보내기 전에 수정할 수 있습니다.  
  
-   WS FAM 발생 하면 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignedIn> 쿠키 성공적으로 기록 되 고 사용자가 로그인 했을 때 이벤트.  
  
-   WS FAM 발생 하면 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SigningOut> 이벤트 세션으로 세션 당 한 번 닫히는 각 사용자에 대해.  세션이 닫힐 클라이언트 쪽에서 \(예를 들어, 세션 쿠키 삭제\)가 발생 하지 않습니다.  SSO 환경에서는 IP STS 각 RP 너무 아웃 로그인을 요청할 수 있습니다.  또한이 이벤트를 발생 하므로 <xref:System.IdentityModel.Services.SigningOutEventArgs.IsIPInitiated%2A> 설정 `true`.  
  
> [!NOTE]
>  사용 안 하는 <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=fullName> 속성에 의해 발생 하는 이벤트 동안 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 또는 <xref:System.IdentityModel.Services.SessionAuthenticationModule>.  즉, <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=fullName> 이벤트는 인증 프로세스 동안 발생 하는 동안 인증 프로세스가 완료 된 후 설정 됩니다.  
  
### 페더레이션된 인증 구성  
 WS FAM 및 SAM를 통해 구성 되는 [\<federationConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소.  [\<wsFederation\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md) WS FAM 속성에 대 한 기본값을 구성 하는 자식 요소 와 같은 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Issuer%2A> 속성 및 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Realm%2A> 속성입니다. \(이러한 값 변경할 수 있습니다 요청 별로 WS FAM 사건의 일부에 대 한 처리기를 제공 하 여 예를 들어, <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>.\) SAM에 의해 사용 되는 쿠키 처리기를 통해 구성 된 [\<cookieHandler\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md) 자식 요소.  WIF에서 구현 되는 기본 쿠키 처리기를 제공 하면 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 청크 크기를 통해 설정할 수 있는 클래스는 [\<chunkedCookieHandler\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md) 요소.  `<federationConfiguration>` 요소 참조는 <xref:System.IdentityModel.Configuration.IdentityConfiguration>, 다른 군 구성 요소와 같은 응용 프로그램에서 사용 하는 구성을 제공 하는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 및 <xref:System.Security.Claims.ClaimsAuthorizationManager>.  Identity 구성 명명 된 지정 하 여 명시적으로 참조 될 수 있습니다 [\<identityConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소에는 `identityConfigurationName` 의 특성은 `<federationConfiguration>` 요소.  Identity 구성 명시적으로 참조 하지 않는 경우 identity 기본 구성이 사용 됩니다.  
  
 다음 XML 신뢰 당사자 \(RP\) 응용 프로그램에서 ASP.NET의 구성을 보여줍니다.  <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> 및 <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> 구성 섹션에 추가 되는 `<configSections>` 요소.  SAM와 WS FAM에서 HTTP 모듈에 추가 되는 `<system.webServer>`\/`<modules>` 요소.  WIF 구성 요소에서 마지막 구성의 `<system.identityModel>`\/`<identityConfiguration>` 및 `<system.identityModel.services>`\/`<federationConfiguration>` 요소.  이 구성은 기본 쿠키 처리기 고 지정 쿠키 처리기 형식이 아니므로 청크 쿠키 처리기를 지정 하면 `<cookieHandler>` 요소.  
  
> [!WARNING]
>  다음 예제에서 모두는 `requireHttps` 특성의 `<wsFederation>` 요소와 `requireSsl` 특성의 `<cookieHandler>` 요소는 `false`.  이 보안상 위험할 수 있습니다.  프로덕션 환경에서 이러한 값을 모두 설정 해야 `true`.  
  
```  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  ...  
  
  <system.webServer>  
    <modules>  
      <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
    </modules>  
  </system.webServer>  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost:50969/" />  
      </audienceUris>  
      <certificateValidation certificateValidationMode="None" />  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
        <trustedIssuers>  
          <add thumbprint="9B74CB2F320F7AAFC156E1252270B1DC01EF40D0" name="LocalSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
    </identityConfiguration>  
  </system.identityModel>  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:15839/wsFederationSTS/Issue" realm="http://localhost:50969/" reply="http://localhost:50969/" requireHttps="false" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
</configuration>  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>   
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 [\<federationConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)