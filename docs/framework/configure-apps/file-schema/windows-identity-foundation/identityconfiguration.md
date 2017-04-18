---
title: "&lt;identityConfiguration&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# &lt;identityConfiguration&gt;
서비스 수준 id 설정을 지정합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|Identity 구성 섹션의 이름입니다.  이 이름은 특정 구성 섹션을 참조할 수 있습니다.  그렇지 않은 경우 `name` 특성을 지정한 경우 기본 구성 섹션을 정의 합니다.  패시브 페더레이션 시나리오에 대 한 기본 구성은 항상 사용 합니다.  자세한 내용은 [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소를 참조하십시오.|  
|saveBootstrapContext|부트스트랩 하는 토큰의 세션 토큰이 포함 되는지 여부를 지정 합니다.  값을 설정 하 여도 토큰 처리기 컬렉션에 설정할 수 있습니다는 `saveBootstrapContext` 특성에 있는 [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 요소입니다.  토큰 처리기 컬렉션에 설정한 값은 서비스에 설정 된 값 보다 우선 합니다.|  
|maximumClockSkew|A <xref:System.TimeSpan> 는 허용 되는 최대 클럭 기울이기를 지정 합니다.  허용 되는 최대 클럭 기울이기 로그인 세션의 만료 시간을 확인 하는 것과 같은 시간에 민감한 작업을 수행 하는 경우를 제어 합니다.  기본값은 5 분입니다 "00: 05: 00"입니다.  지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값을 참조 하십시오. [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_TimespanValues).  최대 시계 기울이기를 토큰 처리기 컬렉션을 설정 하 여 설정 해야는 `maximumClockSkew` 특성에 있는 [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 요소입니다.  토큰 처리기 컬렉션에 설정한 값은 서비스에 설정 된 값 보다 우선 합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<caches\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|세션 토큰 및 토큰 재생 검색에 사용 되는 캐시를 등록 합니다.  보안 토큰 처리기 컬렉션 또는 서비스 수준에서 지정할 수 있습니다.  선택적 요소.|  
|[\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|토큰 처리기를 사용 하 여 인증서의 유효성을 검사 하는 설정을 제어 합니다.  보안 토큰 처리기 컬렉션 또는 서비스 수준에서 지정할 수 있습니다.  선택적 요소.|  
|[\<claimsAuthenticationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|들어오는 클레임에는 클레임 인증 관리자에 등록합니다.  선택적 요소.|  
|[\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|들어오는 클레임에는 클레임 권한 부여 관리자를 등록합니다.  선택적 요소.|  
|[\<claimTypeRequired\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|들어오는 보안 토큰에 대 한 필요한 클레임 집합을 지정합니다.  선택적 요소.|  
|[\<securityTokenHandlers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|보안 토큰 처리기의 컬렉션을 지정합니다.  0 개 이상의 각종 보안 토큰 처리기를 지정할 수 있습니다.  선택적 요소.|  
|[\<tokenReplayDetection\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|토큰 재생 검색을 사용 하 고 토큰에 대 한 만료 시간을 지정 합니다.  보안 토큰 처리기 컬렉션 또는 서비스 수준에서 지정할 수 있습니다.  선택적 요소.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<system.identityModel\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|응용 프로그램에서 Windows Identity 파운데이션 \(싸 우 자\) 옵션을 사용 하는 구성을 제공 합니다.|  
  
## 설명  
 구성을 정의 될 수 있습니다, 여러 각각 고유한 이름을 가진 id입니다.  동작은 다음과 같습니다.  
  
1.  그렇지 않은 경우 `<identityConfiguration>` 요소를 지정 합니다.  런타임에 기본 identity 구성 만들어지고 기본 값으로 채워집니다.  
  
2.  단일 경우 `<identityConfiguration>` 요소를 지정 합니다.  요소는 기본 identity 구성입니다.  명명 된 범위나 명명 되지 않은 여부를 중요 하지 않습니다.  
  
3.  여러 개인 경우 `<identityConfiguration>` 요소에서 지정 됩니다.  기본 identity 구성 명명 되지 않은 요소를 지정합니다.  여러 개 지정 하면 것이 좋습니다 `<identityConfiguration>` 요소 중 하나가 없습니다 명명 된.  
  
> [!WARNING]
>  여러 개 지정 된 경우 `<identityConfiguration>` 요소 중 하나가 없습니다 명명 된.  명명 되지 않은 요소는 기본값 identity 구성 됩니다.  
  
 지정 된 설정 중 일부는 `<identityConfiguration>` 요소를 보안 토큰 처리기 컬렉션에서 설정 하거나 개별 보안 토큰 처리기의 설정을 재정의할 수 있습니다.  
  
> [!IMPORTANT]
>  사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 참조 되는 identity 구성 클레임 기반 액세스 제어를 제공 하는 클래스는 `<federationConfiguration>` 의 클레임 권한 부여 관리자와 권한 부여 결정을 만드는 데 사용 하는 정책 요소를 구성 합니다.  수동 웹 시나리오, 예를 들어 Windows 통신 Foundation \(WCF\) 응용 프로그램 또는 웹 기반 된 응용 프로그램이 없는 경우에도 마찬가지입니다.  응용 프로그램이 수동 웹 응용 프로그램이 없는 경우는 [\<claimsAuthorizationManager\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) 요소와 해당 자식 정책 요소에 있는 경우 참조 된 identity 구성에 적용 되는 유일한 설정입니다.  다른 모든 설정은 모두 무시됩니다.  자세한 내용은 [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소를 참조하십시오.  
  
 `<identityConfiguration>` 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> 클래스입니다.  Identity 구성 섹션에 표시 되는 <xref:System.IdentityModel.Configuration.IdentityConfiguration> 클래스입니다.  
  
> [!IMPORTANT]
>  다음 요소를 자식 요소로 지정 하는 `<identityConfiguration>` 요소가 되지 않습니다, 동작은 이전 버전과 호환성을 위해 계속 지원 되지만.  이러한 요소에서 대신 지정 해야 하 고, 해당 [\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 요소.  
>   
>  -   [\<audienceUris\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## 예제  
 다음 예제에서는 "alternateConfiguration" 명명 된 identity 구성을 만듭니다.  Identity 구성 기본 설정을 지정합니다.  
  
```  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>   
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>