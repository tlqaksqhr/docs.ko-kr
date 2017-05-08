---
title: "&lt;serviceCredentials&gt;의 &lt;serviceCertificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 597ae6d5-4938-4950-9f5e-b2280e816182
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;serviceCredentials&gt;의 &lt;serviceCertificate&gt;
메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.  
  
## 구문  
  
```  
  
<serviceCertificate findValue="String"   
    storeLocation="LocalMachine/CurrentUser"  
    storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`findValue`|X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.  이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.  기본값은 빈 문자열입니다.|  
|`storeLocation`|클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   LocalMachine: 로컬 시스템에 할당된 인증서 저장소입니다.<br />-   CurrentUser: 현재 사용자에게 할당된 인증서 저장소입니다.<br /><br /> 기본값은 LocalMachine입니다.|  
|`storeName`|열려는 X.509 인증서 저장소의 이름을 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   AddressBook: 다른 사용자용 인증서 저장소입니다.<br />-   AuthRoot: 제3의 CA\(인증 기관\)용 인증서 저장소입니다.<br />-   CertificatAuthority: 중개 CA\(인증 기관\)용 인증서 저장소입니다.<br />-   Disallowed: 해지된 인증서용 인증서 저장소입니다.<br />-   My: 개인 인증서용 인증서 저장소입니다.<br />-   Root: 신뢰할 수 있는 루트 CA\(인증 기관\)용 인증서 저장소입니다.<br />-   TrustedPeople: 직접 신뢰할 수 있는 사람 및 리소스용 인증서 저장소입니다.<br />-   TrustedPublisher: 직접 신뢰할 수 있는 게시자용 인증서 저장소입니다.<br /><br /> 기본값은 My입니다.|  
|`X509FindType`|실행할 X.509 검색의 유형을 정의합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   FindByThumbprint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> `findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.<br /><br /> 기본값은 FindBySubjectDistinguishedName입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 확인 관련 설정을 지정합니다.|  
  
## 설명  
 이 요소를 사용하여 메시지 보안 모드를 사용하는 클라이언트에 대한 서비스를 인증하는 데 사용할 X.509 인증서를 지정합니다.  주기적으로 갱신되는 인증서를 사용하는 경우 지문이 변경됩니다.  이러한 경우 인증서를 동일한 주체 이름으로 다시 발급할 수 있기 때문에 주체 이름으로 `X509FindType`을 사용합니다.  
  
 요소 사용에 대한 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]는 [방법: 클라이언트 자격 증명 값 지정](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ServiceCertificate%2A>   
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>   
 <xref:System.ServiceModel.Description.ServiceCredentials.ServiceCertificate%2A>   
 [방법: 클라이언트 자격 증명 값 지정](../../../../../docs/framework/wcf/how-to-specify-client-credential-values.md)   
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)