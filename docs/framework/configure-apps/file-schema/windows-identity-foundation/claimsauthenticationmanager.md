---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 4d4a91e0ed1f437089e26e5902515f73a15d94a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755242"
---
# <a name="ltclaimsauthenticationmanagergt"></a>&lt;claimsAuthenticationManager&gt;
들어오는 클레임에 대 한 클레임 인증 관리자를 등록합니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<claimsAuthenticationManager >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|type|파생 되는 사용자 지정 형식을 지정 된 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스입니다. 지정 하는 방법에 대 한 자세한 내용은 `type` 특성 [사용자 지정 형식 참조]를 참조 하십시오.|  
  
### <a name="child-elements"></a>자식 요소  
 없을 경우 없습니다 `type` 특성 또는 경우에는 `type` 특성 참조는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않는; 클래스에서 파생 되는 반면 <xref:System.Security.Claims.ClaimsAuthenticationManager> 자식 구성 요소를 정의할 수 있습니다.  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 기본 동작을 통해 제공 되는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 들어오는 클레임을 에코 하는 클래스입니다. 되지 않은 경우 `type` 특성이 지정 된 경우는 `type` 특성 지정는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthenticationManager>` 요소는 자식 요소를 사용 하지 않습니다. 지정할 수는 `type` 에서 파생 된 특성 형식을 등록 하는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 사용자 지정 동작을 구현 하는 클래스입니다. 파생된 클래스의 자식 요소를 통해 구성을 지원할 수 있습니다는 `<claimsAuthenticationManager>` 재정의 하 여 요소는 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 메서드 이러한 요소를 처리 합니다. 디자이너 클래스의 최대는 자식 요소에 대해 정의 된 스키마가입니다.  
  
 `<claimsAuthenticationManager>` 요소 집합에서 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> 속성입니다.  
  
## <a name="example"></a>예제  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
