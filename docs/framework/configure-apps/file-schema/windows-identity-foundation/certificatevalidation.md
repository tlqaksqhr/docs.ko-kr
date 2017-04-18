---
title: "&lt;certificateValidation&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;certificateValidation&gt;
토큰 처리기를 사용 하 여 인증서의 유효성을 검사 하는 설정을 제어 합니다.  특정 처리기는 고유한 유효성 검사기로 구성 된 경우이 설정은 무시 됩니다.  
  
## 구문  
  
```  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|certificateValidationMode|<xref:System.ServiceModel.Security.X509CertificateValidationMode> 에 대 한 X.509 인증서를 사용 하는 유효성 검사 모드를 지정 하는 값입니다.  기본값은 "PeerOrChainTrust"입니다.  사용자 지정 유효성 검사기를 지정 하려면이 특성을 "사용자 정의" 설정 하 고 사용 하 여 유효성 검사기를 지정은 [\<certificateValidator\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) 요소입니다.  선택적 요소.|  
|revocationMode|<xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 에 대 한 X.509 인증서를 사용 하는 해지 모드를 지정 하는 값입니다.  기본값은 "온라인"입니다.  선택적 요소.|  
|trustedStoreLocation|A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소를 지정 하는 값입니다.  기본값은 "LocalMachine"입니다.  선택적 요소.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<certificateValidator\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|인증서 유효성 검사에 대 한 사용자 지정 형식을 지정합니다.  이 이와 같은 경우에 사용 되는 `certificateValidationMode` 특성의의 [\<certificateValidation\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) 요소를 "사용자 지정"으로 설정 됩니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identityConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|서비스 수준 id 설정을 지정합니다.|  
|[\<securityTokenHandlerConfiguration\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|구성 컬렉션의 보안에 대 한 토큰 처리기를 제공합니다.|  
  
## 설명  
 A `<certificateValidation>` 요소를 지정 하는 서비스 수준에서 `<identityConfiguration>` 요소 또는 보안 토큰 처리기 컬렉션 수준에서의 `<securityTokenHandlerConfiguration>` 요소.  설정을 토큰 처리기 컬렉션에서 서비스에 지정 된 설정을 무시 합니다.  일부 토큰 처리기 구성에서는 인증서 유효성 검사 설정을 지정할 수 있습니다.  서비스 수준 및 보안 토큰 처리기 컬렉션에서 지정 된 개별 토큰 처리기의 설정을 재정의합니다.  
  
## 예제  
  
```  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```