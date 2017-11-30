---
title: '&lt;claimsAuthorizationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 4b4d86204d5f7225f167be125ce017488c851e98
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltclaimsauthorizationmanagergt"></a>&lt;claimsAuthorizationManager&gt;
들어오는 클레임에 대 한 클레임 권한 부여 관리자를 등록합니다.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<claimsAuthorizationManager >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|type|사용자 지정 형식에서 파생 되는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스입니다. 지정 하는 방법에 대 한 자세한 내용은 `type` 특성을 참조 하십시오. [사용자 정의 형식 참조](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없을 경우 없습니다 `type` 특성 또는 경우에는 `type` 특성 참조는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthorizationManager>` 요소는 자식 요소를 사용 하지 않는; 클래스에서 파생 되는 반면 <xref:System.Security.Claims.ClaimsAuthorizationManager> 자식 구성 요소를 정의할 수 있습니다.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 기본 동작을 통해 제공 되는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스에는 항상 들어오는 클레임 권한을 부여 합니다. 되지 않은 경우 `type` 특성이 지정 된 경우는 `type` 특성 지정는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스는 `<claimsAuthorizationManager>` 요소는 자식 요소를 사용 하지 않습니다. 지정할 수는 `type` 에서 파생 된 특성 형식을 등록 하는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 사용자 지정 동작을 구현 하는 클래스입니다. 파생된 클래스의 자식 요소를 통해 구성을 지원할 수 있습니다는 `<claimsAuthorizationManager>` 재정의 하 여 요소는 <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> 메서드 이러한 요소를 처리 합니다. 디자이너 클래스의 최대는 자식 요소에 대해 정의 된 스키마가입니다.  
  
> [!IMPORTANT]
>  사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 에서 참조 되는 id 구성 코드에서 클레임 기반 액세스 제어를 제공 하는 클래스는 `<federationConfiguration>` 요소는 클레임 권한 부여 관리자 및 정책을 확인 하는 데 사용 되는 구성 권한 부여 결정 합니다. 수동 웹 시나리오 예: Windows Communication Foundation (WCF) 응용 프로그램 또는 응용 프로그램은 웹 기반을 하지 않은 시나리오에도 마찬가지입니다. 응용 프로그램 수동 웹 응용 프로그램이 아닌 경우는 `<claimsAuthorizationManager>` 요소 (및 해당 자식 정책 요소에 있는 경우)의 참조 된 id 구성이 적용 되는 유일한 설정 됩니다. 모든 다른 설정은 무시 됩니다. 자세한 내용은 참조는 [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소입니다.  
  
 설정 하는이 요소는 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> 속성입니다.  
  
## <a name="example"></a>예제  
 다음 XML 클레임 권한 부여에 대 한 구성을 부울 조합을 요청자에 게 리소스에 대해 작업을 수행할 수 있어야 하는 클레임을 지정 하며 각 리소스 작업 쌍으로 구성 정책을 구현 하는 관리자를 보여 줍니다. 이 정책을 사용할 수 있는 클레임 권한 부여 관리자를 구현 하는 코드에서 찾을 수 있습니다는 `ClaimsBasedAuthorization` 샘플.  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
