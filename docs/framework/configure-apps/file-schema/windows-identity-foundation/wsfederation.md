---
title: "&lt;wsFederation&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;wsFederation&gt;
구성에 대 한 제공의 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\).  
  
## 구문  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <wsFederation authenticationType=xs:string (URI)  
        freshness=xs:decimal  
        homerealm=xs:string (URI)  
        issuer=xs:string (URI)  
        persistentCookiesOnPassiveRedirects=xs:boolean  
        passiveRedirectEnabled=xs:boolean  
        policy=xs:string (URI)  
        realm=xs:string (URI)  
        reply=xs:string (URI)  
        request=xs:string (URI)  
        requestPtr=xs:string (URI)  
        requireHttps=xs:boolean  
        resource=xs:string (URI)  
        signInQueryString=xs:string  
        signOutQueryString=xs:string  
        signOutReply=xs:string (URL)  
    </wsFederation>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|authenticationType|인증 유형을 지정 하는 URI입니다.  WS\-페더레이션 로그인 요청 wauth 매개 변수를 설정합니다.  선택적 요소.  기본값은 wauth 매개 변수는 요청에 포함 하도록 지정 하는 빈 문자열입니다.|  
|만료 전 시간|원하는 최대의 나 인증 요청 분.  WS\-페더레이션 로그인 요청 wfresh 매개 변수를 설정합니다.  선택적 요소.  기본값은 0입니다.  선택적 요소. **Warning:**  다음 릴리스 합니다.NET Framework 4.5는 `freshness` 유형의 특성 수 `xs:string` 및 그 기본값은 `null`.|  
|homeRealm|인증에 사용 하는 id 공급자 \(IP\)의 홈 영역입니다.  WS\-페더레이션 로그인 요청 whr 매개 변수를 설정합니다.  선택적 요소.  기본 whr 매개 변수 요청에 포함 하도록 지정 하는 빈 문자열입니다.|  
|issuer|원하는 토큰 발급자의 URI입니다.  로그인 기본 URL의 WS\-페더레이션 요청 하 고 필요한 로그 아웃 요청을 설정 합니다.|  
|persistentCookiesOnPassiveRedirects|영구 쿠키 인증에서 발급 되었는지 여부를 지정 합니다.  선택적 요소.  기본값은 "false"입니다, 그리고 쿠키가 발급 됩니다.|  
|passiveRedirectEnabled|STS에 무단된 요청을 자동으로 리디렉션하려면 WSFAM를 사용할 수 있는지 여부를 지정 합니다.  선택적 요소.  기본값은 "true" 이며, 무단된 요청을 자동으로 리디렉션됩니다.|  
|policy|로그인 요청을 사용 하 여 관련 정책의 위치를 지정 하는 URL입니다.  기본값은 빈 문자열입니다.  WS\-페더레이션 로그인 요청 wp 매개 변수를 설정합니다.  선택적 요소.  기본 wp 매개 변수 요청에 포함 하도록 지정 하는 빈 문자열입니다.|  
|realm|URI 요청 하는 영역입니다.  \(보안 토큰 서비스 \(STS\) 신뢰 당사자 \(RP\)를 식별 하는 URI입니다.\) 요청 wtrealm WS\-페더레이션 로그인 요청 매개 변수를 설정합니다.  필수 요소.|  
|회신|에 신뢰 당사자 \(RP\) 응용 프로그램의 보안 토큰 서비스 \(STS에서\) 회신을 받을 주소를 식별 하는 URL입니다.  WS\-페더레이션 로그인 요청 wreply 매개 변수를 설정합니다.  선택적 요소.  기본값은 wreply 매개 변수는 요청에 포함 하도록 지정 하는 빈 문자열입니다.|  
|요청|토큰 발급 요청입니다.  WS\-페더레이션 로그인 요청 wreq 매개 변수를 설정합니다.  선택적 요소.  기본값은 wreq 매개 변수는 요청에 포함 하도록 지정 하는 빈 문자열입니다.  요청에는 wreq 또는 wreqptr 매개 변수를 포함 하지 않는 STS 발급할 토큰의 종류를 알고 의미 합니다.|  
|requestPtr|토큰 발급 요청의 위치를 지정 하는 URL입니다.  요청 wreqptr 매개 변수를 설정합니다.  선택적 요소.  기본값은 wreqptr 매개 변수는 요청에 포함 하도록 지정 하는 빈 문자열입니다.  요청에는 wreq 또는 wreqptr 매개 변수를 포함 하지 않는 STS 발급할 토큰의 종류를 알고 의미 합니다.|  
|requireHttps|보안 토큰 서비스 \(STS\)와 통신 HTTPS 프로토콜을 사용 해야 하는지 여부를 지정 합니다.  선택적 요소.  기본값은 "true"입니다, 그리고 HTTPS를 사용 해야 합니다.|  
|리소스\(resource\)|신뢰 당사자 \(RP\) 액세스 중인 리소스를 식별 하는 URI는 보안 토큰 서비스 \(STS\) 합니다.  선택적 요소.  WS\-페더레이션 로그인 요청 wres 매개 변수를 설정합니다.  선택적 요소.  기본값은 wres 매개 변수는 요청에 포함 하도록 지정 하는 빈 문자열입니다. **Note:**  wres는 레거시 매개 변수입니다.  지정은 `realm` wtrealm 매개 변수를 대신 사용 하는 특성입니다.|  
|signInQueryString|WS\-페더레이션 로그인 요청 URL에서 쿼리 매개 변수 정의 응용 프로그램을 지정 하기 위한 확장성 지점을 제공 합니다.  선택적 요소.  기본 매개 변수는 요청에 포함 되어야 함을 지정 합니다. 빈 문자열입니다.  매개 변수는 다음 형식으로 쿼리 문자열 조각으로 지정 됩니다: `“param1=value1&param2=value2&param3=value3”` 등. **Note:**  구성 파일에는 ' & "쿼리 문자열에서 문자 엔터티 참조를 사용 하 여 지정 해야 `&`.|  
|signOutQueryString|WS\-페더레이션 로그인 요청 URL에서 쿼리 매개 변수 정의 응용 프로그램을 지정 하기 위한 확장성 지점을 제공 합니다.  선택적 요소.  기본 매개 변수는 요청에 포함 되어야 함을 지정 합니다. 빈 문자열입니다.  매개 변수는 다음 형식으로 쿼리 문자열 조각으로 지정 됩니다: `“param1=value1&param2=value2&param3=value3”` 등. **Note:**  구성 파일에는 ' & "쿼리 문자열에서 문자 엔터티 참조를 사용 하 여 지정 해야 `&`.|  
|signOutReply|패시브 WS\-페더레이션 프로토콜을 통해 로그 아웃 하는 동안 클라이언트가 보안 토큰 서비스 \(STS\)에서 리디렉션할 URL을 지정 합니다.  WS\-페더레이션 로그 아웃 요청에 wreply 매개 변수를 설정합니다.  선택적 요소.  기본 매개 변수는 요청에 포함 되어야 함을 지정 합니다. 빈 문자열입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|구성 설정이 포함의 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WSFAM\)와 <xref:System.IdentityModel.Services.SessionAuthenticationModule> \(SAM\).|  
  
## 설명  
 사용할 수 있는 `<wsFederation>` WSFAM에 대 한 기본 WS\-페더레이션 매개 변수 설정 및 기본 동작을 구성 하는 요소입니다.  WS\-페더레이션 매개 변수 설정을 정의 `<wsFederation>` 집합 노출 하는 속성을 해당 하는 요소는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 클래스.  이러한 속성 WSFAM에서 발급 하는 모든 요청에 대해 동일 하 게 유지 합니다.  WS\-페더레이션 매개 변수를 동적으로 변경할 요청 WSFAM에 의해 노출 되는 이벤트에 대 한 이벤트 처리기를 추가 하 여 처리 하는 동안 수 있습니다. 예를 들어 있는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> 이벤트입니다.  자세한 내용은 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 클래스 설명서를 참조하십시오.  
  
 `<wsFederation>` 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.WSFederationElement> 클래스입니다.  구성 개체가 표시 되는 <xref:System.IdentityModel.Services.Configuration.WSFederationConfiguration> 클래스입니다.  단일 <xref:System.IdentityModel.Services.Configuration.WSFederationConfiguration> 인스턴스 설정의 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 를 통해 액세스 되는 개체는 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> 속성의 WSFAM에 대 한 구성을 제공 하 고.  
  
## 예제  
 다음 XML 표시는 `<wsFederation>` 는 WSFAM에 대 한 설정을 지정 하는 요소입니다.  
  
> [!WARNING]
>  이 예제에서는 HTTPS를 사용 하 여 WSFAM 필요는 없습니다.  이 있기 때문입니다 있는 `requireHttps` 특성에 `<wsFederation>` 요소 설정 `false`.  이 설정은 대부분의 프로덕션 환경에 대 한 권장에 따라이 보안 위험이 존재할 수 있습니다.  
  
```  
<wsFederation passiveRedirectEnabled="true"   
  issuer="http://localhost:15839/wsFederationSTS/Issue"   
  realm="http://localhost:50969/"   
  reply="http://localhost:50969/"   
  requireHttps="false"   
  signOutReply="http://localhost:50969/SignedOutPage.html"   
  signOutQueryString="Param1=value2&Param2=value2"   
  persistentCookiesOnPassiveRedirects="true" />  
  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName>