---
title: '&lt;system.identityModel.services&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ca108d7dd0498b0d7c08bb632ab45c7229ff58c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757049"
---
# <a name="ltsystemidentitymodelservicesgt"></a>&lt;system.identityModel.services&gt;
Ws-federation 프로토콜을 사용 하 여 인증에 대 한 구성 섹션입니다.  
  
 \<system.identityModel.services >  
  
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
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|구성 하는 설정이 포함 된 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) 및 <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP 모듈입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
 없음  
  
## <a name="remarks"></a>설명  
 추가 `<system.identityModel.services>` SAM 및 WSFAM에 대 한 설정을 제공 하려면 응용 프로그램의 구성 파일에 섹션.  
  
> [!IMPORTANT]
>  사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드 클레임 권한 부여 관리자에서에서 클레임 기반 액세스 제어를 제공 하는 클래스 (<xref:System.Security.Claims.ClaimsAuthorizationManager>) 및 권한 부여 결정 하는 데 사용 되는 정책을 통해 구성 되는 `<identityConfiguration>` 암시적 또는 명시적으로 참조 하는 요소는 `<federationConfiguration>` 이 섹션에 있는 요소입니다. 자세한 내용은 참조는 **주의** 아래는 [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소입니다.  
  
 `<system.identityModel.services>` 섹션으로 표시 됩니다는 <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> 클래스입니다. 자식 컬렉션 `<federationConfiguration>` 섹션에 구성 요소는으로 표시 됩니다는 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 XML에 추가 하는 방법을 보여 줍니다는 `<system.identityModel.services>` 구성 파일에 섹션. 둘 다에 대 한 섹션 선언을 추가 해야는 `<system.identityModel.services>` 섹션 및 `<system.identityModel>` 섹션. (추가 하는 경우는 `<system.identityModel.services>` 섹션을 추가 해야에 대 한 선언을 `<system.identityModel>` 기본 되도록 섹션 `<identityConfiguration>` 필요한 경우 런타임에서 섹션을 만들 수 있습니다.) 섹션 선언에 추가 된 후 페더레이션된 인증 설정을 구성할 수 있습니다는 `<system.identityModel.services>` 요소입니다.  
  
```xml  
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
