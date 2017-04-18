---
title: "&lt;claimsAuthorizationManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;claimsAuthorizationManager&gt;
들어오는 클레임에는 클레임 권한 부여 관리자를 등록합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|type|사용자 지정 형식에서 파생 되는 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스.  지정 하는 방법에 대 한 자세한 내용은 `type` 특성, 볼 [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### 자식 요소  
 있으면 없음 `type` 특성 또는 if는 `type` 특성 참조의 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthorizationManager>` 요소는 자식 요소입니다; 변수를 사용 하지 않습니다 그러나 클래스에서 파생 된 <xref:System.Security.Claims.ClaimsAuthorizationManager> 자식 구성 요소를 정의할 수 있습니다.  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
  
## 설명  
 통해 제공 하는 기본 동작을 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스 들어오는 클레임 항상 권한을 부여 합니다.  그렇지 않은 경우 `type` 특성을 지정 또는 if는 `type` 특성을 지정의 <xref:System.Security.Claims.ClaimsAuthorizationManager> 클래스는 `<claimsAuthorizationManager>` 요소는 자식 요소 변수를 사용 하지 않습니다.  지정할 수는 `type` 형식을 등록할 특성에서 파생의 <xref:System.Security.Claims.ClaimsAuthorizationManager> 사용자 지정 동작을 구현 하는 클래스.  파생된 클래스의 자식 요소를 통해 구성을 지원할 수는 `<claimsAuthorizationManager>` 를 재정의 하 여 요소는 <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> 이러한 요소를 처리 하는 메서드.  자식 요소에 대해 정의 된 스키마 클래스의 디자이너까지입니다.  
  
> [!IMPORTANT]
>  사용 하는 경우는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> 또는 <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> 코드에서 참조 되는 identity 구성 클레임 기반 액세스 제어를 제공 하는 클래스는 `<federationConfiguration>` 의 클레임 권한 부여 관리자와 권한 부여 결정을 만드는 데 사용 하는 정책 요소를 구성 합니다.  수동 웹 시나리오, 예를 들어 Windows 통신 Foundation \(WCF\) 응용 프로그램 또는 웹 기반 된 응용 프로그램이 없는 경우에도 마찬가지입니다.  응용 프로그램이 수동 웹 응용 프로그램이 없는 경우는 `<claimsAuthorizationManager>` 요소와 해당 자식 정책 요소에 있는 경우 참조 된 identity 구성에 적용 되는 유일한 설정입니다.  다른 모든 설정은 모두 무시됩니다.  자세한 내용은 [\<federationConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 요소를 참조하십시오.  
  
 이 요소를 설정에서 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=fullName> 속성입니다.  
  
## 예제  
 다음 XML 구성 클레임 권한 부여에 대 한 각 요청자 자원에 작업을 수행할 수 있어야만 하는 클레임의 부울 조합을 지정 리소스와 동작 쌍으로 구성 된 정책을 구현 하는 관리자를 보여 줍니다.  이 정책을 사용할 수 있는 클레임 권한 부여 관리자를 구현 하는 코드에서 찾을 수 있습니다의 `ClaimsBasedAuthorization` 샘플입니다.  
  
```  
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