---
title: '&lt;issuerNameRegistry&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0c0552e06564e09832cf78afeb8f183a0a0dc94c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuernameregistrygt"></a>&lt;issuerNameRegistry&gt;
토큰 처리기 컬렉션에 대 한 처리기가 사용 되는 발급자 이름 레지스트리를 구성 합니다.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<securityTokenHandlers >  
\<securityTokenHandlerConfiguration >  
\<issuerNameRegistry >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
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
|type|파생 되는 형식을 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스입니다. 사용자 지정 하는 방법에 대 한 자세한 내용은 `type`, [사용자 지정 형식 참조]를 참조 하세요.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<r s >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|경우는 `type` 특성 지정 구성 기반 발급자 이름 레지스트리 (의 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스), [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) 요소를 지정 해야 합니다. [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) 요소 표시 되려면 `<add>`, `<clear>`, 또는 `<remove>` 자식 요소로 요소입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## <a name="remarks"></a>설명  
 모든 발급자 토큰 발급자 이름 레지스트리를 사용 하 여 유효성이 검사 됩니다. 이것은 개체에서 파생 되는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스입니다. 발급자 이름 레지스트리 해당 발급자에 의해 생성 되는 토큰의 서명을 확인 하는 데 필요한 암호화 자료에 니모닉 이름을 연결 하는 데 사용 됩니다. 발급자 이름 레지스트리 신뢰 당사자 (RP) 응용 프로그램에서 신뢰할 수 있는 발급자 목록을 유지 관리 합니다. 사용 하 여 지정 된 발급자 이름 레지스트리 형식은 `type` 특성입니다. `<issuerNameRegistry>` 요소는 지정된 된 형식에 대 한 구성 정보를 제공 하는 하나 이상의 자식 요소를 포함할 수 있습니다. 재정의 하 여 이러한 하위 요소를 처리 하는 논리를 제공 하는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> 메서드.  
  
 WIF 형식을 제공 하는 단일 발급자 이름 레지스트리 기본적으로 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스입니다. 이 클래스는 구성에 지정 된 신뢰할 수 있는 발급자 인증서 집합을 사용 합니다. 자식 구성 요소 필요 `<trustedIssuers>`에서 신뢰할 수 있는 발급자 인증서 컬렉션에 구성 됩니다. ASN.1를 사용 하 여 인증서 지 문의 폼 인코딩 및 추가 또는 사용 하 여 컬렉션에서 제거할 지정 된 인증서를 신뢰할 수 있는 `<add>`, `<clear>`, 또는 `<remove>` 요소입니다.  
  
 `<issuerNameRegistry>` 에서 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> 클래스입니다.  
  
> [!NOTE]
>  지정 하는 `<issuerNameRegistry>` 의 자식 요소로 요소는 [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소, 되지 않지만 이전 버전과 호환성을 위해 계속 지원 됩니다. 설정에는 `<securityTokenHandlerConfiguration>` 요소에서 재정의 된 `<identityConfiguration>` 요소입니다.  
  
## <a name="example"></a>예제  
 다음 XML 기반 구성 발급자를 지정 하는 방법을 이름 레지스트리를 보여 줍니다.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
