---
title: "WIF 3.5를 사용하여 빌드된 응용 프로그램을 WIF 4.5로 마이그레이션하는 지침 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a32fe6e-5f68-4693-9371-19411fa8063c
caps.latest.revision: 12
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 12
---
# WIF 3.5를 사용하여 빌드된 응용 프로그램을 WIF 4.5로 마이그레이션하는 지침
## 적용 대상  
  
-   Microsoft ® Windows ® Identity 파운데이션 3.5 및 4.5 \(WIF\).  
  
## 개요  
 Windows Identity 기초 \(WIF\).NET 3.5 s p 1 시간 내에 처음 발표 되었습니다.  해당 버전의 WIF WIF 3.5 라고 합니다.  별도 런타임 및 SDK WIF 기반 응용 프로그램을 실행 하는 컴퓨터 마다 WIF 런타임을 설치 해야 개발자가 Visual Studio 템플릿을 가져오려면 WIF SDK를 설치 하 고 있는 설비 사용의 군 사용 응용 프로그램 개발 방식으로 출시 되었습니다.  .NET 4.5 부터는 군 완벽 하 게 통합 되었으며.NET Framework 있습니다.  더 이상 별도 런타임이 필요 하 고 Visual Studio 확장 관리자를 사용 하 여 Visual Studio 2012에서 WIF 공구 설비를 설치할 수 없습니다.  이 버전의 WIF WIF 4.5 라고 합니다.  
  
 WIF.NET 통합 군 API 화면에서 몇 가지 변경 사항이 필요한입니다.  새 네임 스페이스, Visual Studio 대 한 새로운 도구 및 구성 요소 변경 WIF 4.5에 포함 되어 있습니다.  이 여기서는 WIF 3.5 4.5 WIF를 사용 하 여 빌드된 응용 프로그램을 마이그레이션하는 데 사용할 수 있는 지침을 제공 합니다. WIF 3.5를 사용 하 여 Windows Server 2012 또는 Windows 8을 실행 하는 컴퓨터에서 레거시 응용 프로그램을 실행 해야 하는 시나리오가 있을 수 있습니다.  또한이 항목 WIF 3.5 이러한 운영 체제를 사용 하는 방법에 대 한 지침을 제공 합니다.  
  
## WIF 4.5에 필요한 변경  
 WIF 4.5 WIF 3.5 응용 프로그램을 마이그레이션하는 데 필요한 변경 내용을 설명 합니다.  
  
### 어셈블리 및 네임 스페이스 변경  
 WIF 3.5에 포함 된 모든 WIF 클래스는 `Microsoft.IdentityModel` 어셈블리 \(microsoft.identitymicrosoft.identitymodel.dll\).  WIF 4.5에서 WIF 클래스 분할 되어 다음 어셈블리: `mscorlib` \(mscorlib.dll\) `System.IdentityModel` \(System.IdentityModel.dll\) `System.IdentityModel.Services` \(System.IdentityModel.Services.dll\)와 `System.ServiceModel` \(System.ServiceModel.dll\).  
  
 3.5 WIF 클래스 중 하나에 포함 된 모두는 `Microsoft.IdentityModel` 네임 스페이스 for example, `Microsoft.IdentityModel`, `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Web`, and so on.  WIF 4.5 WIF 클래스는 이제 분산의 [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004) 네임 스페이스는 <xref:System.Security.Claims?displayProperty=fullName> 네임 스페이스 및 <xref:System.ServiceModel.Security?displayProperty=fullName> 네임 스페이스.  이 구성 외에도 일부 3.5 WIF 클래스 WIF 4.5에서 삭제 되었습니다.  
  
 다음 표에서 일부 중요 한 군 4.5 네임 스페이스 및 포함 하는 클래스의 종류를 보여 줍니다.  WIF 3.5와 4.5 WIF 및 네임 스페이스와 클래스 WIF 4.5에서 삭제 하는 방법에 대 한 네임 스페이스의 매핑 방법에 대 한 보다 자세한 정보를 보려면 [WIF 3.5와 WIF 4.5 간의 네임스페이스 매핑](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md).  
  
|WIF 4.5 네임 스페이스|설명|  
|---------------------|--------|  
|<xref:System.IdentityModel?displayProperty=fullName>|쿠키 변환, 보안 토큰 서비스 및 전문화 된 XML 사전 판독기를 나타내는 클래스를 포함 합니다.  다음 WIF 3.5 네임 스페이스의 클래스를 포함: `Microsoft.IdentityModel`, `Microsoft.IdentityModel.SecurityTokenService`, 및 `Microsoft.IdentityModel.Threading`.|  
|<xref:System.Security.Claims?displayProperty=fullName>|클레임, 클레임 기반 id를 클레임 기반 보안 주체 및 기타 클레임 기반 identity 모델 항목을 나타내는 클래스를 포함 합니다.  클래스에는 `Microsoft.IdentityModel.Claims` 네임 스페이스.|  
|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|보안 토큰, 보안 토큰 처리기 및 기타 보안 토큰 항목을 나타내는 클래스를 포함 합니다.  다음 WIF 3.5 네임 스페이스의 클래스를 포함: `Microsoft.IdentityModel.Tokens`, `Microsoft.IdentityModel.Tokens.Saml11`, 및 `Microsoft.IdentityModel.Tokens.Saml2`.|  
|<xref:System.IdentityModel.Services?displayProperty=fullName>|수동 \(WS\-페더레이션\) 시나리오에 사용 되는 클래스를 포함 합니다.  클래스에는 `Microsoft.IdentityModel.Web` 네임 스페이스.|  
|<xref:System.ServiceModel.Security?displayProperty=fullName>|WCF 계약, 채널, 호스트 서비스 및 활성 \(Ws\-trust\) 시나리오에 사용 되는 기타 항목을 나타내는 클래스이 네임이 됩니다.  이러한 클래스에 있던 군 3.5에서는 `Microsoft.IdentityModel.Protocols.WSTrust` 네임 스페이스.|  
  
> [!IMPORTANT]
>  다음 `System.IdentityModel` 네임 스페이스는 WCF 클레임 기반 id 모델을 구현 하는 클래스를 포함: <xref:System.IdentityModel.Claims?displayProperty=fullName>, <xref:System.IdentityModel.Policy?displayProperty=fullName>, 및 <xref:System.IdentityModel.Selectors?displayProperty=fullName>.  WCF의 클레임 기반 id 모델은 군으로 대체 됩니다.  WIF를 기반으로 솔루션을 빌드할 때 이러한 세 가지 네임 스페이스의 클래스를 사용 하지 해야 합니다.  
  
### .NET 통합으로 인해 변경  
 WIF는.NET Framework 통합 되었습니다.  이제 대부분의.NET identity 및 principal 클래스에서 파생 되 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 및 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>.  4.5 WIF에서에서 다음 변경 내용을 결과:  
  
-   지금 클레임, id 및 보안 주체를 나타내는 WIF 클래스에 존재 하는 <xref:System.Security.Claims?displayProperty=fullName> 네임 스페이스입니다.  
  
    > [!IMPORTANT]
    >  <xref:System.IdentityModel.Claims?displayProperty=fullName> WCF 클레임 기반 id 모델에서 아티팩트를 표시 하는 클래스를 포함 하는 네임 스페이스입니다.  이러한 클래스는 WIF 클래스입니다; 같은 이름을 예를 들어, `Claims`.  WIF를 기반으로 솔루션을 빌드할 때 이러한 클래스를 사용 하지 마십시오.  
  
-   이제.NET identity 및 principal 클래스에서 직접 파생 되 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 및 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>, 클레임 기반 id 및 사용자를 나타냅니다.  따라서 WIF 3.5 인터페이스 `IClaimsIdentity` 및 `IClaimsPrincipal` WIF 4.5에서 사용할 수 없는 및 더 이상 필요 합니다.  
  
-   Identity 및 principal 클래스와 같은 Because.NET <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName> 및 <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> 지금에서 파생 <xref:System.Security.Claims.ClaimsIdentity> 및 <xref:System.Security.Claims.ClaimsPrincipal>, 기본 제공 클레임 기능을 갖습니다.  이 원인, 클레임 관련 identity 및 principal 클래스와 같은 `WindowsClaimsIdentity` 및 `WindowsClaimsPrincipal` WIF 3.5에 했던 불필요 하며 WIF 4.5에서 존재 하지 않습니다.  
  
### 다른 군 기능 변경 사항  
 네임 스페이스 변경 및.NET의 통합으로 인해 변경 WIF 4.5에서 WIF 기능을 다음과 같이 일반 변경 발생합니다.  
  
-   `Microsoft.IdentityModel.ExceptionMapper` 클래스를 사용 하면 특정 SOAP 오류에 예외를 매핑하는 기능을 제공 하는 제거 됩니다.  
  
-   예외 화면 크게 줄었습니다.  
  
-   프로토콜이 나 WS\-정의 하는 클래스의 많은 \* 특정 상수가 제거 되었습니다. 예를 들어,에서 `Microsoft.IdentityModel.WSAddressing10Constants` Ws\-addressing 1.0과 관련 된 상수를 정의 하는 클래스입니다.  
  
-   클레임을 Windows 토큰 서비스 \(c2wts\) 및 관련된 클래스에는 `Microsoft.IdentityModel.WindowsTokenService` 네임 스페이스에서 제거 됩니다.  
  
### WIF 구성 변경  
 구성 파일에서의 변경 때문일 WIF 4.5 네임 스페이스 업데이트 합니다. 예를 들어 다음 WIF 3.5 항목에는 `<httpModules>` WS\-페더레이션 인증 관리자 응용 프로그램을 추가할 구역:  
  
```  
<add name="WSFederationAuthenticationModule" type="Microsoft.IdentityModel.Web.WSFederationAuthenticationModule, Microsoft.IdentityModel, Version=3.5.0.0, Culture=neutral, PublicKeyToken=abcd … 5678" />  
```  
  
 이 항목에서 WIF 4.5 새 네임 스페이스 및 어셈블리 버전을 포함 하도록 업데이트 되었습니다.  
  
```  
<add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcd … 5678"/>  
```  
  
 다음 목록에는 WIF 4.5에 대 한 주요 변경 내용을 구성 파일에 열거합니다.  
  
-   `<microsoft.identityModel>` 섹션은 이제는 [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) 섹션입니다.  
  
-   `<service>` 요소는 이제는 [\<identityConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소.  
  
-   새 섹션을 [\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md), 수동 \(WS\-페더레이션\) 경우 동작을 제어 하는 설정을 지정 하려면 추가 되었습니다.  
  
-   [\<federationConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 에서 이동 된 요소와 해당 자식 요소는 `<service>` 새 요소 WIF 3.5에서 `<system.identityModel.services>` 요소.  
  
-   서비스 수준에서 직접에서 지정할 수 있는 여러 요소는 `<service>` WIF 3.5에서 요소에서 지정 되 고 제한 된의 [\<securityTokenHandlerConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 요소. \(아래 계속 지정 될 수 있습니다는 [\<identityConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) WIF 4.5에서 이전 버전과 호환성에 대 한 요소입니다.\)  
  
 4.5 WIF 구성 요소의 전체 목록은 참조 [WIF 구성 스키마](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md).  
  
### Visual Studio 도구 변경 내용  
 WIF 3.5 SDK 제공 하는 독립 실행형 페더레이션 유틸리티 FedUtil.exe \(FedUtil\) 보안 토큰 서비스 \(STS\)에 군 사용 응용 프로그램에 id 관리 아웃소싱에 사용할 수 있습니다.  이 도구는 WIF 설정을 응용 프로그램을 하나 이상의 Sts에서 보안 토큰을 가져올 수 있도록 응용 프로그램 구성 파일에 추가 통해 Visual Studio 표시 된 해당  **STS 서비스 참조 추가** 단추.  FedUtil은 WIF 4.5 함께 제공 되지 않습니다. 대신, WIF 4.5 STS에 id 관리 아웃소싱에 필요한 군 설정을 사용 하 여 응용 프로그램의 구성 파일을 수정 하는 데 사용할 수 있는 Visual Studio 2012에 대 한 Id 및 액세스 도구 라는 새 Visual Studio 확장을 지원 합니다.  Id 및 액세스 도구 또한 군 사용 응용 프로그램을 테스트 하는 데 사용할 수 있는 로컬 STS를 호출 하는 STS를 구현 합니다.  대부분의 경우에서이 기능은 필요성 빌드 사용자 지정 Sts는 WIF 3.5 개발 중인 솔루션을 테스트 하는 경우가 종종 있었습니다.  따라서 STS 템플릿이 더 이상 지원 2012 Visual Studio. 그러나 Sts의 개발을 지 원하는 클래스는 WIF 4.5에서 사용할 수 있습니다.  
  
 Id 및 액세스 도구 확장 및 Visual Studio 업데이트 관리자를 설치할 수 있습니다 또는 다음 페이지 코드 갤러리에서 다운로드할 수 있습니다: [Id와 코드 갤러리에서 Visual Studio 2012에 대 한 액세스 도구](http://go.microsoft.com/fwlink/?LinkID=245849).  Visual Studio 도구 변경 다음 목록에 요약 되어 있습니다.  
  
-   STS 서비스 참조 추가 기능이 제거 됩니다.  대체 Id 및 액세스 도구입니다.  
  
-   Visual Studio STS 서식 파일이 제거 됩니다.  WIF를 사용 하 여 개발 된 id 솔루션을 테스트 하려면 Id와 액세스 도구를 통해 사용할 수 있는 로컬 STS를 사용할 수 있습니다.  클레임을 사용 하는 사용자 지정 로컬 STS 구성을 수정할 수 있습니다.  
  
-   독립 실행형 페더레이션 유틸리티 \(FedUtil\) 군 4.5에서 사용할 수 없는 경우 STS에 대 한 id 관리 아웃소싱에 구성 파일을 수정 하려면 Id와 액세스 도구를 사용할 수 있습니다.  
  
 Id 및 액세스 도구에 대 한 자세한 내용은 참조 하십시오.[Visual Studio 2012용 ID 및 액세스 도구](../../../docs/framework/security/identity-and-access-tool-for-vs.md)  
  
<a name="BKMK_ToolingChanges"></a>   
### 수동 \(WS\-페더레이션\) 시나리오.  
  
-   이동 된 패시브 시나리오를 지 원하는 클래스는 <xref:System.IdentityModel.Services?displayProperty=fullName> 네임 스페이스입니다.  이러한 클래스에 있던 군 3.5에서는 `Microsoft.IdentityModel.Web` 네임 스페이스.  
  
-   클래스에는 `Microsoft.IdentityModel.Web.Configuration` 네임 스페이스에 이동 되었습니다 <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>.  이러한 클래스는 패시브 시나리오에서 구성에 특정 개체를 나타냅니다.  
  
-   `FederatedPasssiveSignInControl` 더 이상 지원 되지. 모든 클래스에는 `Microsoft.IdentityModel.Web.Controls` 네임 스페이스 WIF 4.5에서 제거 되었습니다.  
  
-   WS\-페더레이션 인증 모듈 \(<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>\) 로그 아웃 기능은 WIF 3.5 다.  WIF 4.5에서 로그 아웃 어떻게 작동에 대 한 자세한 내용은 참조는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 클래스 항목입니다.  
  
### 활성 \(WCF\/WS\-트러스트\) 시나리오.  
  
-   `Microsoft.IdentityModel.Protocols.WSTrust` 주로 WIF 4.5에서 두 개의 네임 스페이스를 네임 스페이스 나눠진. Ws\-trust 프로토콜에 관련 된 항목을 나타내는 클래스에 됩니다 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>.  같은 클래스 포함 <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>.  서비스 계약, 채널, 호스트 서비스 및 WS\-트러스트를 사용 하 여 WCF 응용 프로그램에서에 관련 된 기타 항목을 나타내는 클래스에 이동 된 <xref:System.ServiceModel.Security?displayProperty=fullName>. 예를 들어,에서 <xref:System.ServiceModel.Security.IWSTrust13AsyncContract> 인터페이스입니다.  
  
-   WIF를 사용 하 여 WCF 응용 프로그램 구성 크게 단순화 되었습니다.  이전에 `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement` 동작 확장으로 추가 해야 합니다.이 기능 서비스 동작을 지정 하 여 WIF을 쐐기를 사용 했습니다는 `<federatedServiceHostConfiguration>` 요소.  WIF 4.5 WCF와 보다 긴밀 하 게 통합 되었으며.  지정 하 여 WCF 서비스에 WIF를 사용 하면 이제는 `useIdentityConfiguration` 특성은 `<system.serviceModel>`\/`<behaviors>`\/`<serviceBehaviors>`\/`<serviceCredentials>` 다음 XML와 같이 요소:  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
-   WIF 4.5 서비스에서에서 인증서는 현재 \(WCF\) 서비스에서 사용 하는 서비스 호스트에 지정 되어야 합니다.  구성에서이를 수행할 수 있습니다의 `<system.serviceModel>`\/`<behaviors>`\/`<serviceBehaviors>`\/`<serviceCredentials>`\/`<serviceCertificate>` 위의 예제와 같이 요소입니다.  WIF 3.5 서비스 인증서를 통해 지정 될 수도 있는 `<serviceCertificate>` 는 WIF의 자식 요소 `<service>` 요소.  WIF 4.5;에이 기능이 적용 되지 않습니다. 지정 된 `<serviceCertificate>` 요소는 `<serviceCredentials>` 요소 대신.  
  
-   이상으로 WCF 3.5 WIF 쐐기를 사용 하는 클래스가 존재 합니다.  다음 클래스에 포함 된 `Microsoft.IdentityModel.Tokens` 네임 스페이스: `FederatedSecurityTokenManager`, `FederatedServiceCredentials`, 및 `IdentityModelServiceAuthorizationManager`, 뿐 `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement` 클래스.  
  
## Windows 8에서에서 3.5 WIF를 사용 하도록 설정  
 WIF 4.5 4.5.NET의 일부 이기 때문에 Windows 8 및 Windows Server 2012 실행 하는 컴퓨터에서 자동으로 활성화 및 4.5 WIF를 사용 하 여 빌드된 응용 프로그램은 기본적으로 Windows Server 2012 또는 Windows 8에서 실행 합니다.  그러나 WIF 3.5를 사용 하 여 Windows 또는 Windows Server 2012 실행 하는 컴퓨터에서 작성 된 응용 프로그램을 실행 해야 합니다.  이 경우 대상 컴퓨터에 3.5 WIF를 사용 하도록 설정 해야 합니다.  Windows 8을 실행 하는 컴퓨터에서 배포 이미지 서비스 및 관리 \(DISM\)를 사용 하 여이 수행할 수 있습니다.  Windows Server 2012 실행 하는 컴퓨터에서 DISM 도구를 사용 하면 또는 Windows PowerShell 사용할 수 있습니다 `Add-WindowsFeature` cmdlet입니다.  두 경우 모두 적절 한 명령을 호출할 수 있습니다 명령줄에서 또는에서 Windows PowerShell 환경.  
  
 또는 명령줄에서 DISM 도구를 사용 하는 방법을 보여 줍니다 다음 명령을 Windows PowerShell 환경.  기본적으로 DISM PowerShell 모듈 8 Windows 및 Windows Server 2012 포함 하 고 가져올 필요는 없습니다.  Windows PowerShell 사용 하 여 DISM을 사용 하는 방법에 대 한 자세한 내용은 참조 [방법을 사용 하 여 Windows PowerShell는 DISM](http://go.microsoft.com/fwlink/?LinkId=254419).  
  
 WIF 3.5 DISM을 사용 하 여 사용할 수 있도록 합니다.  
  
```  
dism /online /enable-feature:windows-identity-foundation  
```  
  
 DISM을 사용 하 여 WIF 3.5를 사용 하지 않으려면:  
  
```  
dism /online /disable-feature:windows-identity-foundation  
```  
  
 확인 하려면 기능을 설정 하거나 DISM을 사용 하 여 사용할 수 없습니다.  
  
```  
dism /online /get-features  
```  
  
 또한 Windows Server 2012 실행 하는 컴퓨터에서 사용할 수 있습니다 3.5 WIF Windows PowerShell 사용 하 여 `Add-WindowsFeature` cmdlet입니다.  명령줄에서 이렇게 하려면 다음 명령을 입력할 수 있습니다.  
  
```  
powershell "add-windowsfeature windows-identity-foundation"  
```  
  
 Windows PowerShell 환경 내에서 명령을 직접 입력:  
  
```  
add-windowsfeature windows-identity-foundation  
```  
  
> [!NOTE]
>  WIF 3.5와 4.5 WIF를 함께 사용할 때 동일한 이름을 공유할 여러 WIF 3.5 및 4.5 WIF 클래스 때문에 정규화 된 클래스 이름을 사용 하거나 클래스 WIF 3.5에서와 4.5 WIF를 구분 하기 위해 네임 스페이스 별칭을 사용 해야 합니다.  
  
## 참고 항목  
 [WIF 구성 스키마](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md)   
 [WIF 3.5와 WIF 4.5 간의 네임스페이스 매핑](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)   
 [Windows Identity Foundation 4.5의 새로운 기능](../../../docs/framework/security/whats-new-in-wif.md)   
 [Visual Studio 2012용 ID 및 액세스 도구](../../../docs/framework/security/identity-and-access-tool-for-vs.md)