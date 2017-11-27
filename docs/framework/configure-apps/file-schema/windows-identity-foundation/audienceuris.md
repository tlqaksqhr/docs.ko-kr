---
title: '&lt;audienceUris&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3ce884c19d205df4727dcce96ffdf34144ff1dd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltaudienceurisgt"></a>&lt;audienceUris&gt;
신뢰 당사자 (RP)의 식별자를 허용 하는 Uri의 집합을 지정 합니다. 허용 되는 대상 Uri 중 하나에 대해 범위가 지정 되지 않는 한 토큰을 허용 하지 않습니다.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<audienceUris >  
  
## <a name="syntax"></a>구문  
  
```xml  
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
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|모드|<xref:System.IdentityModel.Selectors.AudienceUriMode> audience 제한 들어오는 토큰을 적용할지 여부를 지정 하는 값입니다. 가능한 값은 "항상", "Never" 및 "BearerKeyOnly"입니다. 기본값은 "Always". 선택 사항입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`<add value=xs:string>`|추가 하 여 지정 된 URI는 `value` audienceUris 컬렉션에 특성입니다. `value` 특성이 필요합니다. URI는 대/소문자 구분 합니다.|  
|`<clear>`|AudienceUris 컬렉션을 지웁니다. 모든 식별자는 컬렉션에서 제거 됩니다.|  
|`<remove value=xs:string>`|제거 하 여 지정 된 URI는 `value` audienceUris 컬렉션에서 특성입니다. `value` 특성이 필요합니다. URI는 대/소문자 구분 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 기본적으로 컬렉션은 비어 있습니다. 사용 하 여 `<add>`, `<clear>`, 및 `<remove>` 요소 컬렉션을 수정할 수 있습니다. <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>및 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 개체가 사용을 구성 하려면 대상 그룹 URI 컬렉션의에서 값 허용 대상 그룹 URI 제한 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 개체입니다.  
  
 `<audienceUris>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> 클래스입니다. 컬렉션에 추가 하는 개별 URI로 표시 됩니다는 <xref:System.IdentityModel.Configuration.AudienceUriElement> 클래스입니다.  
  
> [!NOTE]
>  사용은 `<audienceUris>` 의 자식 요소로 요소는 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소, 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다. 설정에는 `<securityTokenHandlerConfiguration>` 요소에서 재정의 된 `<identityConfiguration>` 요소입니다.  
  
## <a name="example"></a>예제  
 다음 XML에는 응용 프로그램에 대해 허용 가능한 대상 그룹 Uri를 구성 하는 방법을 보여 줍니다. 이 예제에서는 단일 URI를 구성 합니다. 이 URI에 대해 범위가 지정 된 토큰 수락, 다른 항목을 모두 거부 됩니다.  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
