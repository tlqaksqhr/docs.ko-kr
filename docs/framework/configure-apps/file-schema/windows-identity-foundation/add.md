---
title: '&lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 6ee6403fcfe741d3e38bf44eddb1cf52cf856ec8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757855"
---
# <a name="ltaddgt"></a>&lt;add&gt;
토큰 처리기 컬렉션에 지정 된 보안 토큰 처리기를 추가합니다.  
  
 \<system.identityModel>  
\<identityConfiguration>  
\<securityTokenHandlers>  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|type|추가할 토큰 처리기의 CLR 형식 이름입니다. 지정 하는 방법에 대 한 자세한 내용은 `type` 특성을 참조 하십시오. [사용자 정의 형식 참조](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<samlSecurityTokenRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|에 대 한 구성을 제공 된 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스나 파생된 클래스의 이러한 클래스 중 하나입니다.|  
|[\<sessionTokenRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|에 대 한 구성을 제공 된 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 클래스나 파생된 클래스입니다.|  
|[\<userNameSecurityTokenHandlerRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|에 대 한 구성을 제공 된 <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> 클래스나 파생된 클래스입니다.|  
|[\<x509SecurityTokenHandlerRequirement>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|에 대 한 선택적 구성을 제공 된 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스나 파생된 클래스입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<securityTokenHandlers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|보안 토큰 처리기에 등록 된 끝점의 컬렉션을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 `<add>` 요소 토큰 처리기에 대 한 구성을 지정 하는 단일 자식 요소를 걸릴 수 있습니다. 이 처리기 클래스를 통해 참조 되는 여부에 따라 달라는 `type` 특성에는 `<add>` 요소는이 기능에 대 한 지원을 제공 합니다. 이 기능을 제공 하는 토큰 처리기 클래스를 취하는 생성자를 노출 해야 합니다는 <xref:System.Xml.XmlElement> 개체입니다.  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 이 기능을 제공 않는 몇 가지 기본 제공 보안 토큰 처리기 클래스입니다. 이러한 클래스는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, 및 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>합니다.  
  
> [!IMPORTANT]
>  토큰 처리기 컬렉션에 지정 된 형식의 단일 처리기만 포함할 수 있습니다. 즉, 예를 들어에서 파생 되는 처리기를 추가 하려는 경우는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 컬렉션을 먼저 제거 해야는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>는 컬렉션에서 기본적으로 제공 합니다. 사용할 수 있습니다는 [ \<제거 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) 컬렉션 또는 사용에서 단일 처리기를 제거 하는 요소는 [ \<지우기 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) 모든 처리기 컬렉션에서 제거할 요소입니다.  
  
 처리기에 지정 된 설정은 아래에 토큰 처리기 컬렉션에 지정 된 해당 설정은 재정의 [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) 에서 서비스 수준에서 지정 된 및 요소 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소입니다.  
  
## <a name="example"></a>예제  
 다음 XML에서는 `<add>` 및 `<remove>` 요소를 사용자 지정 세션 토큰 처리기의 기본 세션 토큰 처리기를 바꿉니다. XML에서 가져온 것은 `ClaimsAwareWebFarm` 샘플.  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
