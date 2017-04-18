---
title: "&lt;clientCertificate&gt; 요소의 &lt;certificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00297efb-a7f2-4e03-bc2b-943d545610fc
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;clientCertificate&gt; 요소의 &lt;certificate&gt;
메시지 서명 및 암호화에 사용되는 X.509 인증서를 지정합니다.  
  
## 구문  
  
```  
  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`findValue`|X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다.  이 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.  기본값은 빈 문자열입니다.|  
|`storeLocation`|클라이언트가 서버 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소 위치를 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   LocalMachine: 로컬 시스템에 할당된 인증서 저장소입니다.<br />-   CurrentUser: 현재 사용자에게 할당된 인증서 저장소입니다.<br /><br /> 기본값은 LocalMachine입니다.|  
|`storeName`|열려는 X.509 인증서 저장소의 이름을 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   AddressBook: 다른 사용자용 인증서 저장소입니다.<br />-   AuthRoot: 제3의 CA\(인증 기관\)용 인증서 저장소입니다.<br />-   CertificationAuthority: 중개 CA\(인증 기관\)용 인증서 저장소입니다.<br />-   Disallowed: 해지된 인증서용 인증서 저장소입니다.<br />-   My: 개인 인증서용 인증서 저장소입니다.<br />-   Root: 신뢰할 수 있는 루트 CA\(인증 기관\)용 인증서 저장소입니다.<br />-   TrustedPeople: 직접 신뢰할 수 있는 사람 및 리소스용 인증서 저장소입니다.<br />-   TrustedPublisher: 직접 신뢰할 수 있는 게시자용 인증서 저장소입니다.<br /><br /> 기본값은 My입니다.|  
|`X509FindType`|실행할 X.509 검색의 유형을 정의합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   FindByThumbPrint<br />-   FindBySubjectName<br />-   FindBySubjectDistinguishedName<br />-   FindByIssuerName<br />-   FindByIssuerDistinguishedName<br />-   FindBySerialNumber<br />-   FindByTimeValid<br />-   FindByTimeNotYetValid<br />-   FindByTemplateName<br />-   FindByApplicationPolicy<br />-   FindByCertificatePolicy<br />-   FindByExtension<br />-   FindByKeyUsage<br />-   FindBySubjectKeyIdentifier<br /><br /> `findValue` 특성에 포함된 형식은 지정된 X509FindType에 대한 요구 사항을 충족해야 합니다.<br /><br /> 기본값은 FindBySubjectDistinguishedName입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<clientCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)||  
  
## 설명  
 서비스가 클라이언트와 안전하게 통신하기 위해 클라이언트의 인증서가 필요한 경우 `<certificate>` 요소를 사용합니다.  이는 양방향 통신 패턴을 사용하는 경우 발생합니다.  대부분의 일반적인 요청\/응답 패턴의 경우 클라이언트는 요청 시 서비스가 클라이언트에게 해당 응답을 암호화 및 서명하는 데 사용하는 인증서를 포함합니다.  그러나 이중 통신 패턴에서는 서비스에 클라이언트의 요청이 없으므로 클라이언트에게 보내는 메시지 보안을 위해 클라이언트의 인증서가 사전에 필요합니다.  따라서 클라이언트 인증서를 out\-of\-band 협상 방식으로 가져와서 이 요소를 사용하여 인증서를 지정해야 합니다.  이중 서비스에 대한 자세한 내용은 [방법: 이중 계약 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)를 참조하세요.  
  
## 예제  
 다음 코드에서는 적절한 X.509 인증서와 `<authentication>` 요소의 사용자 지정 유효성 검사 형식을 찾는 방법을 지정합니다.  
  
```  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <clientCertificate>  
   <certificate   
         findValue="www.cohowinery.com"   
         storeLocation="CurrentUser"   
         storeName="TrustedPeople"  
         x509FindType="FindByIssuerName" />  
   <authentication customCertificateValidatorType="MyTypes.Coho"  
    certificateValidationMode="Custom"   
    revocationMode="Offline"  
    includeWindowsGroups="false"   
    mapClientCertificateToWindowsAccount="true" />  
  </clientCertificate>  
 </behavior>  
</serviceBehaviors>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Certificate%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Certificate%2A>   
 <xref:System.ServiceModel.Configuration.X509ClientCertificateCredentialsElement>   
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)   
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)