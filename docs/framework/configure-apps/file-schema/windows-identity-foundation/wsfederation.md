---
title: '&lt;wsFederation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c537f770-68bd-4f82-96ad-6424ad91369f
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7fd4e12d77380942204d37b59644c46aed3a0148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltwsfederationgt"></a>&lt;wsFederation&gt;
에 대 한 구성을 제공 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM).  
  
\<system.identityModel.services >  
\<federationConfiguration >  
\<wsFederation >  
  
## <a name="syntax"></a>구문  
  
```xml
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
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|authenticationType|인증 유형을 지정 하는 URI입니다. Ws-federation 로그인 요청 wauth 매개 변수를 설정합니다. 선택 사항입니다. 기본값은 빈 문자열 지정 wauth 매개 변수는 요청에 포함 되지 않습니다.|  
|새로 고침|원하는의 최대 수명 인증 요청 (분)에서입니다. Ws-federation 로그인 요청 wfresh 매개 변수를 설정합니다. 선택 사항입니다. 기본값은 0입니다. 선택 사항입니다. **경고:** .NET Framework 4.5의 다음 릴리스에서 `freshness` 특성 유형 중 하나가 됩니다 `xs:string` 값이 기본값으로 됩니다 `null`합니다.|  
|homeRealm|인증에 사용할 id 공급자 (IP)의 홈 영역입니다. Ws-federation 로그인 요청 whr 매개 변수를 설정합니다. 선택 사항입니다. 기본값은 빈 문자열 지정 whr 매개 변수는 요청에 포함 되지 않습니다.|  
|issuer|원하는 토큰 발급자의 URI입니다. 기본 URL의 Ws-federation 로그인 요청을 설정 하는 데 필요한 로그 아웃 요청입니다.|  
|persistentCookiesOnPassiveRedirects|영구 쿠키 인증에 수행 되는 여부를 지정 합니다. 선택 사항입니다. 기본값은 "false", 쿠키를 발급 되지 않은 합니다.|  
|passiveRedirectEnabled|자동으로 STS를 권한이 없는 요청을 리디렉션하는 WSFAM 사용 되는지 여부를 지정 합니다. 선택 사항입니다. 기본값은 "true", 권한이 없는 요청이 자동으로 리디렉션됩니다.|  
|정책|로그인으로 요청에서 사용 하는 관련 정책의 위치를 지정 하는 URL입니다. 기본값은 빈 문자열입니다. Ws-federation 로그인 요청 wp 매개 변수를 설정합니다. 선택 사항입니다. 기본값은 빈 문자열 지정 wp 매개 변수는 요청에 포함 되지 않습니다.|  
|realm|요청 영역의 URI를 지정 합니다. (보안 토큰 서비스 (STS)에 RP (신뢰 당사자)를 식별 하는 URI입니다.) 요청 wtrealm Ws-federation 로그인 요청 매개 변수를 설정합니다. 필수.|  
|회신|신뢰 당사자 (RP) 응용 프로그램을는 보안 토큰 서비스 (STS)에서 회신을 수신 하겠다고 주소를 식별 하는 URL입니다. Ws-federation 로그인 요청 wreply 매개 변수를 설정합니다. 선택 사항입니다. 기본값은 빈 문자열 지정 wreply 매개 변수는 요청에 포함 되지 않습니다.|  
|요청|토큰 발급 요청입니다. Ws-federation 로그인 요청 wreq 매개 변수를 설정합니다. 선택 사항입니다. 기본값은 빈 문자열 지정 wreq 매개 변수는 요청에 포함 되지 않습니다. 요청에는 wreq 또는 wreqptr 매개 변수를 포함 하지 않고 STS 발급 토큰의 종류를 알고 있어야 한다는 것을 의미 합니다.|  
|requestPtr|토큰 발급 요청의 위치를 지정 하는 URL입니다. 요청 wreqptr 매개 변수를 설정합니다. 선택 사항입니다. 기본값은 빈 문자열 지정 wreqptr 매개 변수는 요청에 포함 되지 않습니다. 요청에는 wreq 또는 wreqptr 매개 변수를 포함 하지 않고 STS 발급 토큰의 종류를 알고 있어야 한다는 것을 의미 합니다.|  
|requireHttps|보안 토큰 서비스 (STS)와 통신에 HTTPS 프로토콜을 사용 해야 하는지 여부를 지정 합니다. 선택 사항입니다. 기본값은 "true", HTTPS를 사용 해야 합니다.|  
|리소스|에 RP (신뢰 당사자), 액세스 되는 리소스를 식별 하는 URI는 보안 토큰 서비스 (STS)에 있습니다. 선택 사항입니다. Ws-federation 로그인 요청 wres 매개 변수를 설정합니다. 선택 사항입니다. 기본값은 빈 문자열 지정 wres 매개 변수는 요청에 포함 되지 않습니다. **참고:** wres 레거시 매개 변수입니다. 지정 된 `realm` wtrealm 매개 변수를 대신 사용 하는 특성입니다.|  
|signInQueryString|Ws-federation 로그인 요청 URL에 정의 된 응용 프로그램이 쿼리 매개 변수를 지정 하는 확장성 지점을 제공 합니다. 선택 사항입니다. 기본값은 추가 매개 변수는 요청에 포함할지를 지정 하는 빈 문자열입니다. 다음 형식을 사용 하 여 쿼리 문자열 조각으로 지정 된 매개 변수: `"param1=value1&param2=value2&param3=value3"` 등입니다. **참고:** 구성 파일에는 ' & "쿼리 문자열의 문자는 엔터티 참조를 사용 하 여 지정 해야 `&`합니다.|  
|signOutQueryString|Ws-federation 로그인 요청 URL에 정의 된 응용 프로그램이 쿼리 매개 변수를 지정 하는 확장성 지점을 제공 합니다. 선택 사항입니다. 기본값은 추가 매개 변수는 요청에 포함할지를 지정 하는 빈 문자열입니다. 다음 형식을 사용 하 여 쿼리 문자열 조각으로 지정 된 매개 변수: `"param1=value1&param2=value2&param3=value3"` 등입니다. **참고:** 구성 파일에는 ' & "쿼리 문자열의 문자는 엔터티 참조를 사용 하 여 지정 해야 `&`합니다.|  
|signOutReply|수동 Ws-federation 프로토콜을 통해 로그 아웃 하는 동안에 보안 토큰 서비스 (STS)에서 클라이언트를 리디렉션할 URL을 지정 합니다. Ws-federation 로그 아웃 요청에서 wreply 매개 변수를 설정합니다. 선택 사항입니다. 기본값은 추가 매개 변수는 요청에 포함할지를 지정 하는 빈 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|구성 하는 설정이 포함 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM).|  
  
## <a name="remarks"></a>설명  
 사용할 수는 `<wsFederation>` 는 WSFAM에 대 한 기본 Ws-federation 매개 변수 설정 및 기본 동작을 구성 하는 요소입니다. 아래에 정의 된 WS-페더레이션 매개 변수 설정을 `<wsFederation>` 에 의해 노출 되는 해당 속성을 설정 하는 요소는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 클래스입니다. 이러한 속성은 WSFAM에서 발급 한 모든 요청에 대해 동일 하 게 유지 합니다. 요청 WSFAM; 노출 하는 이벤트에 대 한 이벤트 처리기를 추가 하 여 처리 하는 동안 Ws-federation 매개 변수를 동적으로 변경 예를 들어는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> 이벤트입니다. 자세한 내용은 참조에 대 한 설명서는 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 클래스입니다.  
  
 `<wsFederation>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Services.Configuration.WSFederationElement> 클래스입니다. 자체 구성 개체도 표시 됩니다는 <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> 클래스입니다. 단일 <xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration> 에 설정 된 인스턴스는 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 통해 액세스 되는 개체는 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType> 속성은 WSFAM에 대 한 구성을 제공 합니다.  
  
## <a name="example"></a>예  
 XML은 다음 한 `<wsFederation>` 는 WSFAM에 대 한 설정을 지정 하는 요소입니다.  
  
> [!WARNING]
>  이 예제에서는 WSFAM HTTPS를 사용 하지 않아도 됩니다. 때문에 이것이 `requireHttps` 특성에 `<wsFederation>` 요소 설정 `false`합니다. 이 설정은 보안 위험이 있습니다 대로 하지 대부분의 프로덕션 환경에 좋습니다.  
  
```xml
<wsFederation passiveRedirectEnabled="true"   
              issuer="http://localhost:15839/wsFederationSTS/Issue"   
              realm="http://localhost:50969/"   
              reply="http://localhost:50969/"   
              requireHttps="false"   
              signOutReply="http://localhost:50969/SignedOutPage.html"   
              signOutQueryString="Param1=value2&Param2=value2"   
              persistentCookiesOnPassiveRedirects="true" />
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>  
 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=nameWithType>
