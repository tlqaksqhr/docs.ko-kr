---
title: "WIF 클레임 프로그래밍 모델 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 149cb875-9b1c-4695-b88a-fbf1725a02f9
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# WIF 클레임 프로그래밍 모델
ASP입니다.일반적으로 NET 및 Windows 통신 Foundation \(WCF\) 개발자가 사용자의 id 정보를 이용한 작동 하도록 IIdentity 및 IPrincipal 인터페이스를 사용 합니다.  에 나타납니다.NET 4.5, Windows Identity 파운데이션 \(싸 우 자\)가 되어 통합 청구 이제 항상 다음 다이어그램에서 볼 수 있듯이 모든 보안 주체에 대 한 표시 되도록:  
  
 ![WIF 클레임 프로그래밍 모델](../../../docs/framework/security/media/wifclaimsprogrammingmodel.png "WIFClaimsProgrammingModel")  
  
 에 나타납니다.NET 4.5, System.Security.Claims \(위 다이어그램 참조\)에서는 새로운 Claimsprincipal와 ClaimsIdentity 클래스를 포함 합니다.  모든 보안 주체에.NET 이제 Claimsprincipal에서 파생 됩니다.  FormsIdentity asp와 같은 모든 기본 제공 identity 클래스NET 및 Windowsidentity에 지금 Claimsidentity에서 파생 됩니다.  마찬가지로, 모든 기본 제공 보안 주체 클래스 GenericPrincipal 및 WindowsPrincipal Claimsprincipal에서 파생 됩니다.  
  
 클레임을 나타내는 <xref:System.Security.Claims.Claim> 클래스입니다.  이 클래스는 다음과 같은 중요 한 속성이 있습니다.  
  
-   <xref:System.Security.Claims.Claim.Type%2A>클레임의 형식을 나타내며 일반적으로 URI입니다.  예를 들어, 전자 메일 주소 클레임으로 표시 됩니다 `http://schemas.microsoft.com/ws/2008/06/identity/claims/email`.  
  
-   <xref:System.Security.Claims.Claim.Value%2A>클레임의 값을 포함 하 고 string으로 표현 됩니다.  예를 들어, 전자 메일 주소는 "someone@contoso.com"로 표현할 수 있습니다.  
  
-   <xref:System.Security.Claims.Claim.ValueType%2A>클레임 값 유형을 나타내며 일반적으로 URI입니다.  문자열 형식으로 표시 됩니다 예를 들어, `http://www.w3.org/2001/XMLSchema#string`.  값 형식을 XML 스키마에 따라 QName 이어야 합니다.  값의 형식 이어야 합니다. `namespace#format` 싸 우 자가 유효한 QName 값을 출력할 수 있도록 합니다.  네임 스페이스는 잘 정의 된 네임 스페이스가 없으면 되지 않으므로 해당 네임 스페이스에 게시 된 XSD 파일 생성 된 XML 스키마 유효성 검사, 아마도 수 없습니다.  기본 값 형식인 `http://www.w3.org/2001/XMLSchema#string`.  참조 하십시오 [http:\/\/www.w3.org\/2001\/XMLSchema](http://go.microsoft.com/fwlink/?LinkId=209155) 는 잘 알려진 값을 형식에 대 한 안전 하 게 사용할 수 있습니다.  
  
-   <xref:System.Security.Claims.Claim.Issuer%2A>클레임이 발급 되는 보안 토큰 서비스 \(STS\)의 식별자가입니다.  이 URL STS 또는 같은 STS를 나타내는 이름으로 표현 될 수 있습니다 `https://sts1.contoso.com/sts`.  
  
-   <xref:System.Security.Claims.Claim.OriginalIssuer%2A>원래 얼마나 Sts에 관계 없이, 클레임을 발급 하는 STS의 식별자에 체인입니다.  이 처럼 표시 됩니다 <xref:System.Security.Claims.Claim.Issuer%2A>.  
  
-   <xref:System.Security.Claims.Claim.Subject%2A>id를 검사 하는 주제가입니다.  여기에 포함 된 <xref:System.Security.Claims.ClaimsIdentity>.  
  
-   <xref:System.Security.Claims.Claim.Properties%2A>개발자 수는 사전 연결의 다른 속성을 함께 전송 될 수 있는 응용 프로그램별 데이터를 제공 하 고 사용자 지정 유효성 검사를 사용할 수 있습니다.  
  
## Identity 위임  
 중요 한 속성의 <xref:System.Security.Claims.ClaimsIdentity> 입니다 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>.  이 속성의 자격 증명 위임을 다중 계층 시스템의 백 엔드 서비스에 요청 하는 클라이언트와 중간 계층 역할 수 있습니다.  
  
### 클레임 부여를 통해 액세스  
 현재 사용자의 클레임 집합을 RP 응용 프로그램에 액세스할 수 `Thread.CurrentPrincipal`.  
  
 다음 코드 예제에서는이 메서드는 system.security.claims.claimsidentity의 사용을 보여 줍니다.  
  
```  
ClaimsPrincipal claimsPrincipal = Thread.CurrentPrincipal as ClaimsPrincipal;  
  
```  
  
 자세한 내용은 <xref:System.Security.Claims>를 참조하십시오.  
  
### 역할 클레임 유형  
 RP 응용 프로그램 구성의 일부인 어떤 역할을 확인 하려면 클레임 형식 이어야 합니다.  이 클레임 유형은 system.security.claims.claimsprincipal.isinrole\(system.string\)에서 사용 됩니다.  클레임 기본 형식인 `http://schemas.microsoft.com/ws/2008/06/identity/claims/role`.  
  
### Windows Identity 토대에서 서로 다른 토큰에서 추출 된 클레임  
 싸 우 자 조합을 여러 인증 메커니즘을 지원합니다.  다음 표에서 싸 우 자는 토큰 종류에서 추출 된 클레임을 나열 합니다.  
  
||||  
|-|-|-|  
|토큰 형식|클레임 생성|Windows 액세스 토큰 맵|  
|SAML 1.1|1.  System.identitymodel.securitytokenservice.getoutputclaimsidentity\(system.security.claims.claimsprincipal,system.identitymodel.protocols.wstrust.requestsecuritytoken,system.identitymodel.scope\)에서 모든 클레임입니다.<br />2.  `http://schemas.microsoft.com/ws/2008/06/identity/claims/confirmationkey` 증명 토큰을 토큰을 포함 하는 경우 XML serialization 확인 키를 포함 하는 클레임입니다.<br />3.  `http://schemas.microsoft.com/ws/2008/06/identity/claims/samlissuername` 클레임 발급자 요소입니다.<br />4.  토큰을 인증 하는 문을 포함 하는 경우 AuthenticationMethod 및 AuthenticationInstant 청구 합니다.|청구 이외에 나열 된 "SAML" 형식에서 1.1, 클레임을 제외 하 고 `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name`, Windows 인증 관련 클레임 추가 하 고 id를 Windowsclaimsidentity로 표시 됩니다.|  
|SAML 2.0|"SAML 1.1"와 동일 합니다.|"SAML 1.1 Windows 계정에 매핑할"와 동일 합니다.|  
|X509|1.  요청과 함께 X 500 고유 emailName, dnsName, SimpleName, UpnName, 들어 UrlName RsaKey \(이 수 수 추출에서 X509Certificate2.PublicKey.Key 속성의 RSACryptoServiceProvider.ExportParameters 메서드를 사용 하 여\), DsaKey \(이 수 수 추출에서 X509Certificate2.PublicKey.Key 속성의 DSACryptoServiceProvider.ExportParameters 메서드를 사용 하 여\), 지문, 일련 번호 속성에서 x509 인증서.<br />2.  AuthenticationMethod 클레임 값이 `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/x509`.  AuthenticationInstant 클레임 XmlSchema DateTime 형식으로 인증서의 유효성이 검사 된 경우입니다.|1.  Windows 계정의 정규화 된 도메인 이름으로 사용 하는 `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name` 값을 요구 합니다.  .<br />2.  X509 인증서를 매핑할 수 없습니다 창에서에서 클레임 및 클레임 Windows에 인증서를 매핑하여 얻은 windows 계정입니다.|  
|UPN|1.  클레임 청구 Windows 인증 섹션에서 유사합니다.<br />2.  AuthenticationMethod 클레임 값이 `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/password`.  AuthenticationInstant 클레임 XmlSchema DateTime 형식으로 암호를 유효성이 검사 된 경우입니다.||  
|Windows \(Kerberos 또는 NTLM\)|1.  액세스 토큰에서 생성 된 클레임: PrimarySID, DenyOnlyPrimarySID, PrimaryGroupSID, DenyOnlyPrimaryGroupSID, GroupSID, DenyOnlySID, 및 이름<br />2.  값을 갖는 AuthenticationMethod `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/windows`.  Windows 토큰을 액세스할 때 시간 값을 갖는 AuthenticationInstant XMLSchema DateTime 형식으로 만들어졌습니다.||  
|RSA 키 쌍|1.  `http://schemas.xmlsoap.org/ws/2005/05/identity/claims/rsa` RSAKeyValue 값을 요구 합니다.<br />2.  AuthenticationMethod 클레임 값이 `http://schemas.microsoft.com/ws/2008/06/identity/authenticationmethod/signature`.  AuthenticationInstant 청구 되었습니다 때 RSA 키를 인증 하는 시간 값 \(즉, 서명을 확인 하였습니다\) XMLSchema DateTime 형식에서입니다.||  
  
|||  
|-|-|  
|인증 유형|URI에서 "AuthenticationMethod" 클레임 생성|  
|암호|`urn:oasis:names:tc:SAML:1.0:am:password`|  
|Kerberos|`urn:ietf:rfc:1510`|  
|SecureRemotePassword|`urn:ietf:rfc:2945`|  
|TLSClient|`urn:ietf:rfc:2246`|  
|X509|`urn:oasis:names:tc:SAML:1.0:am:X509-PKI`|  
|PGP|`urn:oasis:names:tc:SAML:1.0:am:PGP`|  
|Spki|`urn:oasis:names:tc:SAML:1.0:am:SPKI`|  
|XmlDSig|`urn:ietf:rfc:3075`|  
|지정하지 않습니다.|`urn:oasis:names:tc:SAML:1.0:am:unspecified`|