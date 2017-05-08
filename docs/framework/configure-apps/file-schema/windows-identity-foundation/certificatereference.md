---
title: "&lt;certificateReference&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
caps.latest.revision: 4
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 4
---
# &lt;certificateReference&gt;
찾기 및 인증서 저장소에서 X.509 인증서의 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.  
  
## 구문  
  
```  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference   
        storeName=”AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher”  
        storeLocation=”CurrentUser||LocalMachine”  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|storeName|X.509 인증서 저장소의 이름입니다.  기본값은 "My"입니다.  선택적 요소.|  
|storeLocation|A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> X.509 인증서 저장소의 위치를 지정 하는 값입니다.  기본값은 "LocalMachine"입니다.  선택적 요소.|  
|x509FindType|<xref:System.Security.Cryptography.X509Certificates.X509FindType> 실행할 검색의 유형을 지정 하는 값입니다.  기본값은 "FindBySubjectDistinguishedName"입니다.  선택적 요소.|  
|findValue|X.509 인증서 저장소에서 검색할 값입니다.  선택적 요소.|  
|isChainIncluded|인증서 체인을 사용 하 여 유효성 검사를 수행 해야 하는지 여부를 지정 합니다.  기본값은 "true"입니다. 유효성 검사에서 인증서 체인을 사용 하 여 수행 됩니다.  선택적 요소.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|암호화 하 고 토큰을 해독 하는 데 사용 되는 인증서를 구성 합니다.|  
  
## 설명  
 `<certificateReference>` 요소를 찾아 인증서 저장소에서 X.509 인증서의 유효성을 검사 하는 데 사용 되는 설정을 지정 합니다.  자식 요소로 지정 된 시기는 `<serviceCertficate>` 암호화 하 고 토큰을 해독 하는 데 사용 되는 X.509 인증서의 위치 및 확인 설정을 지정 요소.  `<certificateReference>` 요소가 표시 되는 <xref:System.ServiceModel.Configuration.CertificateReferenceElement> 클래스입니다.