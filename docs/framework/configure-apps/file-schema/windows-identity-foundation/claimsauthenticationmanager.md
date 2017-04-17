---
title: "&lt;claimsAuthenticationManager&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 5
---
# &lt;claimsAuthenticationManager&gt;
들어오는 클레임에 대 한 클래임 인증 관리자에 등록합니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|type|파생 되는 사용자 지정 형식 지정을 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스입니다.  지정 하는 방법에 대 한 자세한 내용은 `type` 특성에 참조 하십시오 [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferencess).|  
  
### 자식 요소  
 있으면 없음 `type` 특성을 경우는 `type` 특성을 참조는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthenticationManager>` 요소는 자식 요소입니다; 변수를 사용 하지 않습니다 그러나 클래스에서 파생 된 <xref:System.Security.Claims.ClaimsAuthenticationManager> 하위 구성 요소를 정의할 수 있습니다.  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
  
## 설명  
 기본 동작을 통해 제공 되는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 들어오는 클레임을 에코.  그렇지 않은 경우 `type` 특성이 지정 되어 경우는 `type` 특성을 지정의 <xref:System.Security.Claims.ClaimsAuthenticationManager> 클래스는 `<claimsAuthenticationManager>` 요소의 자식 요소를 사용 하지 않습니다.  지정할 수 있습니다의 `type` 에서 파생 특성의 형식을 등록 하는 <xref:System.Security.Claims.ClaimsAuthenticationManager> 사용자 지정 동작을 구현 하는 클래스.  파생된 클래스의 자식 요소를 통해 구성을 지원할 수는 `<claimsAuthenticationManager>` 를 재정의 하 여 요소는 <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> 이러한 요소를 처리 하는 메서드.  자식 요소에 대해 정의 된 스키마 클래스의 디자이너에 있습니다.  
  
 `<claimsAuthenticationManager>` 요소 집합은 <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=fullName> 속성입니다.  
  
## 예제  
  
```  
<system.identityModel>  
    <identityConfiguration name=”MyIdentity”>  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```