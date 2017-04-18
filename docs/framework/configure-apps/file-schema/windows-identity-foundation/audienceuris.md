---
title: "&lt;audienceUris&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# &lt;audienceUris&gt;
신뢰 당사자 \(RP\)의 허용 가능한 식별자 Uri 집합을 지정 합니다.  토큰은 허용된 대상 Uri 중 하나를 범위가 지정 되지 않으면 허용 하지 않습니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|mode|<xref:System.IdentityModel.Selectors.AudienceUriMode> 는 들어오는 토큰을 대상 제한이 적용 되는지 여부를 지정 하는 값입니다.  가능한 값은 "항상", "없음" 및 "BearerKeyOnly"입니다.  기본값은 "항상"입니다.  선택적 요소.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|`<add value=xs:string>`|지정 된 URI를 추가 `value` audienceUris 컬렉션에 특성.  `value` 특성은 필수적 요소입니다.  URI를 대\/소문자 구분입니다.|  
|`<clear>`|AudienceUris 컬렉션을 지웁니다.  모든 식별자의 컬렉션에서 제거 됩니다.|  
|`<remove value=xs:string>`|지정 된 URI의 제거는 `value` audienceUris 컬렉션에서 특성.  `value` 특성은 필수적 요소입니다.  URI를 대\/소문자 구분입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## 설명  
 기본적으로이 컬렉션이 비어 있습니다. 사용 `<add>`, `<clear>`, 및 `<remove>` 요소 컬렉션을 수정할 수 있습니다.  <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>및 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 개체 구성 대상 URI 컬렉션에서에서 값 허용 대상 URI 제한 사용 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체입니다.  
  
 `<audienceUris>` 요소가 표시 되는 <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> 클래스입니다.  표시 되며 컬렉션에 추가 된 개별 URI는 <xref:System.IdentityModel.Configuration.AudienceUriElement> 클래스입니다.  
  
> [!NOTE]
>  사용은 `<audienceUris>` 요소를 자식 요소로 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소가 되지 않습니다, 있지만 이전 버전과 호환성을 위해 여전히 지원 됩니다.  설정에는 `<securityTokenHandlerConfiguration>` 요소의 대체에 `<identityConfiguration>` 요소입니다.  
  
## 예제  
 다음과 같은 XML 응용 프로그램에 대 한 적절 한 대상 Uri를 구성 하는 방법을 보여 줍니다.  단일 URI를 구성 하는이 예제입니다.  이 URI에 대해 범위가 지정 된 토큰 허용 됩니다, 그리고 나머지는 모두 거부 됩니다.  
  
```  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```