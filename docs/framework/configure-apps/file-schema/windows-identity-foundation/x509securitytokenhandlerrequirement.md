---
title: "&lt;x509SecurityTokenHandlerRequirement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# &lt;x509SecurityTokenHandlerRequirement&gt;
선택적 구성에 제공 된 <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> 클래스 또는 파생된 클래스.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
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
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> 사용에 대 한 X.509 인증서 유효성 검사 모드를 지정 하는 값입니다.  기본값은 "PeerOrChainTrust"입니다.|  
|mapToWindows|토큰 처리기 들어오는 UPN 클레임을 사용 하 여 유효성 검사 토큰을 Windows 계정에 매핑되어야 합니다 여부를 지정 합니다.  기본값은 "false"입니다.|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 에 대 한 X.509 인증서를 사용 하는 해지 모드를 지정 하는 값입니다.  기본값은 "온라인"입니다.|  
|trustedStoreLocation|A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소를 지정 하는 값입니다.  기본값은 "LocalMachine"입니다.|  
|certificateValidator|사용자 지정 형식에서 파생 된 <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  경우는 `certificateValidationMode` 특성 "사용자 지정",이 형식의 인스턴스를 발급자 인증서 유효성 검사에 사용 됩니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|지정 된 보안 토큰 처리기는 토큰 처리기 컬렉션에 추가합니다.|  
  
## 예제  
  
```  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```