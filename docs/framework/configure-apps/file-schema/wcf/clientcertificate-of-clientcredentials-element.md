---
title: "&lt;clientCredentials&gt; 요소의 &lt;clientCertificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b3fa000-3434-4142-a178-11903bdd2c5d
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;clientCredentials&gt; 요소의 &lt;clientCertificate&gt;
서비스에 클라이언트를 인증하는 데 사용되는 X.509 인증서를 정의합니다.  
  
## 구문  
  
```  
  
<clientCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`findValue`|X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.  이 특성에 포함된 형식은 `X509FindType` 특성 값의 요구 사항을 충족해야 합니다.  기본값은 빈 문자열입니다.|  
|`storeLocation`|클라이언트가 서비스에 자신을 인증하는 데 사용하는 X.509 인증서의 위치를 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   LocalMachine: 로컬 시스템에 할당된 인증서 저장소입니다.<br />-   CurrentUser: 현재 사용자에게 할당된 인증서 저장소입니다.<br /><br /> 기본값은 LocalMachine입니다.  이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.|  
|`storeName`|검색할 X.509 인증서 저장소의 이름을 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   AddressBook: 다른 사용자용 인증서 저장소입니다.<br />-   AuthRoot: 제3의 CA\(인증 기관\)용 인증서 저장소입니다.<br />-   CertificateAuthority: 중개 CA\(인증 기관\)용 인증서 저장소입니다.<br />-   Disallowed: 해지된 인증서용 인증서 저장소입니다.<br />-   My: 개인 인증서용 인증서 저장소입니다.<br />-   Root: 신뢰할 수 있는 루트 CA\(인증 기관\)용 인증서 저장소입니다.<br />-   TrustedPeople: 직접 신뢰할 수 있는 사람 및 리소스용 인증서 저장소입니다.<br />-   TrustedPublisher: 직접 신뢰할 수 있는 게시자용 인증서 저장소입니다.<br /><br /> 기본값은 My입니다.  이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreName> 형식입니다.|  
|X509FindType|실행할 X.509 검색의 유형을 정의합니다.  `findValue` 특성에 포함된 형식은 이 특성의 요구 사항을 충족해야 합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> 기본값은 FindBySubjectDistinguishedName입니다.  이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509FindType> 형식입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.|  
  
## 설명  
 이 구성 요소는 이 요소로 클라이언트를 인증하는 데 사용하는 인증서를 지정합니다.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [방법: 클라이언트 자격 증명 값 지정](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md).  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ClientCertificate%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.ClientCertificate%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>   
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [방법: 클라이언트 자격 증명 값 지정](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)   
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)