---
title: '&lt;identityConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1db76253-07da-447b-9e7a-3705c7228cf4
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 48f9eef329f5d2e0e751fd2a03b0d3af9ddc355c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltidentityconfigurationgt"></a>&lt;identityConfiguration&gt;
서비스 수준 id 설정을 지정합니다.  
  
 \<system.identityModel >  
\<identityConfiguration >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration  
      name=xs:string  
      saveBootstrapContext=xs:boolean>  
      maximumClockSkew=TimeSpan >  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|Id 구성 섹션의 이름입니다. 특정 구성 섹션을 참조 하려면이 이름을 사용할 수 있습니다. 되지 않은 경우 `name` 특성 지정, 섹션의 기본 구성을 정의 합니다. 기본 구성은 수동 페더레이션 시나리오에 대해 항상 사용 됩니다. 자세한 내용은 참조는 [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소입니다.|  
|saveBootstrapContext|세션 토큰에 부트스트랩 토큰이 포함할지 여부를 지정 합니다. 값 설정할 수도 있습니다 토큰 처리기 컬렉션에 설정 하 여는 `saveBootstrapContext` 특성에 [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 요소입니다. 토큰 처리기 컬렉션에 설정 된 값에는 서비스에 설정 된 값 보다 우선 합니다.|  
|maximumClockSkew|A <xref:System.TimeSpan> 최대 허용 된 클럭 오차를 지정 하는 합니다. 로그인 세션의 만료 시간 유효성 검사와 같은 시간에 민감한 작업을 수행할 때 최대 허용 된 클럭 오차를 제어 합니다. 기본값은 5 분 "00: 05:00"입니다. 지정 하는 방법에 대 한 자세한 내용은 <xref:System.TimeSpan> 값, 참조 [Timespan 값](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다. 최대 클럭 오차 설정할 수도 있습니다 토큰 처리기 컬렉션에 설정 하 여는 `maximumClockSkew` 특성에 [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 요소입니다. 토큰 처리기 컬렉션에 설정 된 값에는 서비스에 설정 된 값 보다 우선 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<캐시 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|세션 토큰에서 토큰 재생 검색에 사용 되는 캐시에 등록 합니다. 서비스 수준에서 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다. 선택 사항입니다.|  
|[\<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|토큰 처리기 인증서의 유효성을 검사 하기 위해 사용 하는 설정을 제어 합니다. 서비스 수준에서 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다. 선택 사항입니다.|  
|[\<claimsAuthenticationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthenticationmanager.md)|들어오는 클레임에 대 한 클레임 인증 관리자를 등록합니다. 선택 사항입니다.|  
|[\<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md)|들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록합니다. 선택 사항입니다.|  
|[\<claimTypeRequired >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimtyperequired.md)|들어오는 보안 토큰에 대 한 요구 된 클레임 집합을 지정합니다. 선택 사항입니다.|  
|[\<securityTokenHandlers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|보안 토큰 처리기의 컬렉션을 지정 합니다. 보안 토큰 처리기의 컬렉션을 0 개 이상 지정할 수 있습니다. 선택 사항입니다.|  
|[\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|토큰 재생 검색을 사용 하도록 설정 하 고 토큰에 대 한 만료 시간을 지정 합니다. 서비스 수준에서 또는 보안 토큰 처리기 컬렉션에 지정할 수 있습니다. 선택 사항입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<system.identityModel >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md)|응용 프로그램에서 Windows Identity Foundation (WIF) 옵션을 사용 하도록 설정 하는 것에 대 한 구성을 제공 합니다.|  
  
## <a name="remarks"></a>설명  
 고유 이름으로 각각 여러 identity 구성을 정의할 수 있습니다. 동작은 다음과 같습니다.  
  
1.  되지 않은 경우 `<identityConfiguration>` 요소를 지정 합니다. 기본 id 구성은 런타임 시 만들어지고 기본값으로 채워집니다.  
  
2.  경우는 단일 `<identityConfiguration>` 요소를 지정 합니다. 이 요소는 기본 identity 구성 합니다. 이름이 지정 되거나 명명 되지 않은 여부는 중요 하지 않습니다.  
  
3.  여러 개인 경우 `<identityConfiguration>` 요소가 지정 되어 있습니다. 명명 되지 않은 요소에는 기본 id 구성을 지정합니다. 것이 좋습니다 여러 개 지정 하는 경우 `<identityConfiguration>` 요소, 그 중 하나가 취소 해야 명명 합니다.  
  
> [!WARNING]
>  여러 개 지정 하는 경우 `<identityConfiguration>` 요소, 그 중 하나가 취소 해야 명명 합니다. 명명 되지 않은 요소에 기본 id 구성 됩니다.  
  
 에 지정 된 설정 중 일부는 `<identityConfiguration>` 요소는 보안 토큰 처리기 컬렉션에 대 한 설정에 따라 또는 개별 보안 토큰 처리기의 설정으로 재정의할 수 있습니다.  
  
> [!IMPORTANT]
>  사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 에서 참조 되는 id 구성 코드에서 클레임 기반 액세스 제어를 제공 하는 클래스는 `<federationConfiguration>` 요소는 클레임 권한 부여 관리자 및 정책을 확인 하는 데 사용 되는 구성 권한 부여 결정 합니다. 수동 웹 시나리오 예: Windows Communication Foundation (WCF) 응용 프로그램 또는 응용 프로그램은 웹 기반을 하지 않은 시나리오에도 마찬가지입니다. 응용 프로그램 수동 웹 응용 프로그램이 아닌 경우는 [ \<claimsAuthorizationManager >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/claimsauthorizationmanager.md) 요소 (및 해당 자식 정책 요소에 있는 경우)의 참조 된 id 구성이 적용 되는 유일한 설정 됩니다. 모든 다른 설정은 무시 됩니다. 자세한 내용은 참조는 [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소입니다.  
  
 `<identityConfiguration>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement> 클래스입니다. Id 구성 섹션으로 표시 됩니다는 <xref:System.IdentityModel.Configuration.IdentityConfiguration> 클래스입니다.  
  
> [!IMPORTANT]
>  자식 요소로 다음 요소를 지정 하는 `<identityConfiguration>` 요소는 사용 되지, 동작은 이전 버전과 호환성에 여전히 지원 됩니다. 이러한 요소는 아래 대신 지정 해야 합니다는 [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 요소입니다.  
>   
>  -   [\<audienceUris >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)  
> -   [\<issuerNameRegistry >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)  
> -   [\<issuerTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)  
> -   [\<serviceTokenResolver >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)  
  
## <a name="example"></a>예  
 다음 예제에서는 "alternateConfiguration" 라는 id 구성을 만듭니다. Id 구성에는 기본 설정을 지정합니다.  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="alternateConfiguration"/>  
</system.identityModel>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IdentityModel.Configuration.IdentityConfiguration>  
 <xref:System.IdentityModel.Configuration.IdentityConfigurationElement>
