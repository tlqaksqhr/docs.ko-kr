---
title: "&lt;issuerNameRegistry&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 12
---
# &lt;issuerNameRegistry&gt;
발급자 이름 레지스트리 사용 하 여 컬렉션에 있는 토큰 처리기 처리기를 구성 합니다.  
  
## 구문  
  
```  
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
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|type|형식에서 파생 되는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스입니다.  사용자 지정 하는 방법에 대 한 자세한 내용은 `type`를 참조 하십시오 [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md#BKMK_CustomTypeReferences).|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|때의 `type` 레지스트리 구성을 기반으로 하는 발급자 이름 특성을 지정 \(의 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스\), [\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) 요소를 지정 해야 합니다.  [\<trustedIssuers\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) 요소를 걸릴 수 있습니다 `<add>`, `<clear>`, 또는 `<remove>` 요소를 자식 요소로 서.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안 토큰 처리기를 제공합니다.|  
  
## 설명  
 모든 발급자 토큰 발급자 이름 레지스트리를 사용 하 여 유효성이 검사 됩니다.  이 개체에서 파생 되는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 클래스.  발급자 이름 레지스트리를 니모닉 이름과 암호화 서명 생성 해당 발급자가 토큰을 확인 하는 데 필요한 재료를 연결 하는 데 사용 됩니다.  발급자 이름 레지스트리는 신뢰 당사자 \(RP\) 응용 프로그램에서 신뢰할 수 있는 발급자의 목록을 유지 관리 합니다.  발급자 이름 레지스트리 유형을 사용 하 여 지정 되는 `type` 특성.  `<issuerNameRegistry>` 요소는 지정 된 형식에 대 한 구성을 제공 하는 하나 이상의 자식 요소를 가질 수 있습니다.  재정의 하 여이 하위 요소를 처리 하는 논리를 제공는 <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> 메서드가 있습니다.  
  
 싸 우 자 제공 된 단일 발급자 이름 레지스트리 형식 상자에서 부족의 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스입니다.  이 클래스는 구성에 지정 된 신뢰할 수 있는 발급자 인증서 집합을 사용 합니다.  자식 구성 요소를 필요한 `<trustedIssuers>`에서 신뢰할 수 있는 발급자 인증서의 컬렉션을 구성 합니다.  인증서 사용의 ASN.1 인코딩된 인증서 손도장의 양식 및 추가 하거나 사용 하 여 컬렉션에서 제거할 지정 된 신뢰할 수 있는 `<add>`, `<clear>`, 또는 `<remove>` 요소입니다.  
  
 `<issuerNameRegistry>` 요소가 표시 되는 <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> 클래스입니다.  
  
> [!NOTE]
>  지정 하는 `<issuerNameRegistry>` 의 자식 요소로 요소는 [\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 요소가 되지 않습니다, 있지만 이전 버전과 호환성을 위해 여전히 지원 됩니다.  설정에는 `<securityTokenHandlerConfiguration>` 요소의 대체에 `<identityConfiguration>` 요소입니다.  
  
## 예제  
 다음 XML 이름 레지스트리 구성을 기반으로 하는 발급자를 지정 하는 방법을 보여 줍니다.  
  
```  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>   
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>