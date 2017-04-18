---
title: "&lt;trustedIssuers&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d818c917-07b4-40db-9801-8676561859fd
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;trustedIssuers&gt;
신뢰할 수 있는 발급자 인증서 발급자 구성 기반 이름을 레지스트리에 사용 목록 구성 \(<xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>\).  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry>  
          <trustedIssuers>  
            <add thumbprint=xs:string name=xs:string>  
            <clear>  
            <remove thumbprint=xs:string>  
          </trustedIssuers>  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|`<add thumbprint=xs:string name=xs:string>`|인증서를 신뢰할 수 있는 발급자의 컬렉션에 추가합니다.  인증서에 지정 된 해당 `thumbprint` 특성.  이 특성은 필수 이며 인코딩된 ASN.1 형태의 인증서 지문 포함 되어야 합니다.  `name` 특성은 선택적 이며 인증서에 사용할 이름을 지정 하려면 사용할 수 있습니다.|  
|`<clear>`|모든 인증서를 신뢰할 수 있는 발급자의 컬렉션을 지웁니다.|  
|`<remove thumbprint=xs:string>`|인증서는 신뢰할 수 있는 발급자의 컬렉션에서 제거합니다.  인증서에 지정 된 해당 `thumbprint` 특성.  이 특성은 필수입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<issuerNameRegistry\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|발급자 이름 레지스트리를 구성합니다. **Important:**  `type` 특성의는 `<issuerNameRegistry>` 요소를 참조 해야는 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스에 `<trustedIssuers>` 유효한 요소.|  
  
## 설명  
 Windows Identity 파운데이션 \(싸 우 자\)의 단일화 된 구현을 제공의 <xref:System.IdentityModel.Tokens.IssuerNameRegistry> 상자에서 클래스를 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스.  발급자 이름 구성 레지스트리 구성에서 로드 되는 신뢰할 수 있는 발급자의 목록을 유지 관리 합니다.  X.509 인증서 토큰 발급자가 생성의 서명을 확인 하는 데 필요한 각 발급자 이름 목록이 연결 합니다.  신뢰할 수 있는 발급자의 인증서 목록에서 지정 된는 `<trustedIssuers>` 요소입니다.  X.509 인증서 토큰 생성 해당 발급자가 서명을 확인 하는 데 필요한 니모닉 발급자 이름 목록의 각 요소를 연결 합니다.  신뢰할 수 있는 인증서 사용의 ASN.1 인코딩된 인증서 지문 형태의 지정 및 컬렉션을 사용 하 여 추가 `<add>` 요소입니다.  비우거나 사용 하 여 발급자 \(인증서\) 목록에서 제거할 수 있는 `<clear>` 및 `<remove>` 요소.  
  
 `type` 특성의는 `<issuerNameRegistry>` 요소를 참조 해야는 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> 클래스에 `<trustedIssuers>` 유효한 요소.  
  
## 예제  
 다음 XML 이름 레지스트리 구성을 기반으로 하는 발급자를 지정 하는 방법을 보여 줍니다.  
  
```  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB2F32 … B1DC01EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>   
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>