---
title: "&lt;samlSecurityTokenRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;samlSecurityTokenRequirement&gt;
구성에 대 한 제공의 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 클래스는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> 클래스 또는이 클래스의 파생된 클래스.  표시 되는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 클래스입니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|mapToWindows|토큰 처리기 들어오는 UPN 클레임을 사용 하 여 유효성 검사 토큰을 Windows 계정에 매핑되어야 합니다 여부를 지정 합니다.  기본값은 "false"입니다.|  
|issuerCertificateRevocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 에 대 한 X.509 인증서를 사용 하는 해지 모드를 지정 하는 값입니다.  기본값은 "온라인"입니다.|  
|issuerCertificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> 사용에 대 한 X.509 인증서 유효성 검사 모드를 지정 하는 값입니다.  기본값은 "PeerOrChainTrust"입니다.|  
|issuerCertificateTrustedStoreLocation|A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소를 지정 하는 값입니다.  기본값은 "LocalMachine"입니다.|  
|issuerCertificateValidator|사용자 지정 형식에서 파생 된 <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  경우는 `issuerCertificateValidationMode` 특성 "사용자 지정",이 형식의 인스턴스를 발급자 인증서 유효성 검사에 사용 됩니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<nameClaimType\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|지정 하는 클레임 형식을 설정 하는 <xref:System.Security.Principal.IIdentity.Name%2A> 속성.|  
|[\<roleClaimType\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|역할 형식 클레임의 컬렉션을 정의 하는 클레임 형식을 지정 <xref:System.Security.Claims.ClaimsIdentity> 개체를 반환 하는 <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> 토큰 처리기의 메서드.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|지정 된 보안 토큰 처리기는 토큰 처리기 컬렉션에 추가합니다.|  
  
## 설명  
 `<samlSecurityTokenRequirement>` 요소가 표시 되는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> 클래스에 개체 모델 및 구성 하는 데 사용 되는 `SamlSecurityTokenRequirement` 속성에는 <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> 또는 <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.  
  
## 예제  
  
```  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```