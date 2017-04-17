---
title: "&lt;clientCertificate&gt; 요소의 &lt;authentication&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4a55eea2-1826-4026-b911-b7cc9e9c8bfe
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &lt;clientCertificate&gt; 요소의 &lt;authentication&gt;
서비스에서 사용되는 클라이언트 인증서에 대한 인증 동작을 지정합니다.  
  
## 구문  
  
```  
  
<authentication  
customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
includeWindowsGroups="Boolean"  
mapClientCertificateToWindowsAccount="Boolean"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|customCertificateValidatorType|선택적 문자열입니다.  사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.  이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.|  
|certificateValidationMode|선택적 열거형입니다.  자격 증명의 유효성을 검사하는 데 사용되는 모드 중 하나를 지정합니다.  이 특성은 [System.Servicemodel.Security.X509CertificateValidationMode](assetId:///System.Servicemodel.Security.X509CertificateValidationMode?qualifyHint=False&amp;autoUpgrade=True) 형식입니다.  `Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.  기본값은 `ChainTrust`입니다.|  
|includeWindowsGroups|선택적 부울입니다.  Windows 그룹이 보안 컨텍스트에 포함될지 여부를 지정합니다.  이 특성을 `true`로 설정하면 전체 그룹이 확장되므로 성능에 영향을 줍니다.  사용자가 속한 그룹의 목록을 설정할 필요가 없으면 이 특성을 `false`로 설정합니다.|  
|mapClientCertificateToWindowsAcccount|부울입니다.  클라이언트가 인증서를 사용하여 Windows ID에 매핑될 수 있는지 여부를 지정합니다.  이 작업을 위해서는 Active Directory를 사용할 수 있어야 합니다.|  
|revocationMode|선택적 열거형입니다.  RCL\(해지된 인증서 목록\)을 검사하는 데 사용되는 모드 중 하나입니다.  기본값은 `Online`입니다.  이 값은 HTTP 전송 보안을 사용할 때 무시됩니다.|  
|trustedStoreLocation|선택적 열거형입니다.  시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.  서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.  지정한 저장소 위치의 **신뢰된 사용자** 저장소에 대해 유효성 검사가 수행됩니다.  기본값은 `CurrentUser`입니다.|  
  
## customCertificateValidatorType 특성  
  
|값|설명|  
|-------|--------|  
|문자열|형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.|  
  
## certificateValidationMode 특성  
  
|값|설명|  
|-------|--------|  
|열거형|None, PeerTrust, ChainTrust, PeerOrChainTrust, Custom 값 중 하나입니다.<br /><br /> 자세한 내용은 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.|  
  
## revocationMode 특성  
  
|값|설명|  
|-------|--------|  
|열거형|NoCheck, Online, Offline 값 중 하나입니다.  자세한 내용은 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.|  
  
## trustedStoreLocation 특성  
  
|값|설명|  
|-------|--------|  
|열거형|`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.  기본값은 `CurrentUser`입니다.  시스템 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.  사용자 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<clientCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)|서비스에 클라이언트를 인증하는 데 사용되는 X.509 인증서를 정의합니다.|  
  
## 설명  
 `<authentication>` 요소는 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 클래스에 해당합니다.  이것은 클라이언트가 인증되는 방법을 사용자 지정할 수 있습니다.  `certificateValidationMode` 특성을 `None`, `ChainTrust`, `PeerOrChainTrust`, `PeerTrust` 또는 `Custom`으로 설정할 수 있습니다.  기본적으로 해당 수준은 `ChainTrust`로 설정되며, 이는 각 인증서가 체인 맨 위의 *루트 기관*에서 종료되는 인증서의 계층 구조에 있어야 함을 지정합니다.  이 모드가 가장 안전한 모드입니다.  또한 값을 `PeerOrChainTrust`로 설정할 수 있으며, 이는 자체 발급된 인증서\(신뢰 피어\)가 신뢰 체인에 있는 인증서와 함께 수락됨을 지정합니다.  자체 발급 인증서를 신뢰할 수 있는 기관에서 구입할 필요 없기 때문에 클라이언트 및 서비스를 개발 및 디버깅하는 경우 이 값이 사용됩니다.  클라이언트를 배포하는 경우 `ChainTrust` 값을 대신 사용합니다.  
  
 또한 값을 `Custom`으로 설정할 수도 있습니다.  `Custom` 값으로 설정할 경우 `customCertificateValidatorType` 특성도 인증서 유효성을 검사하는 데 사용되는 어셈블리 및 형식으로 설정해야 합니다.  사용자 지정 유효성 검사기를 만들려면 추상 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 클래스에서 상속해야 합니다.  자세한 내용은 [방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)를 참조하세요.  
  
## 예제  
 다음 코드에서는 X.509 인증서와 `<authentication>` 요소의 사용자 지정 유효성 검사 형식을 지정합니다.  
  
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
 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>   
 <xref:System.ServiceModel.Security.X509CertificateValidationMode>   
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.Authentication%2A>   
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement.Authentication%2A>   
 <xref:System.ServiceModel.Configuration.X509ClientCertificateAuthenticationElement>   
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [방법: 사용자 지정 인증서 유효성 검사기를 사용하는 서비스 만들기](../../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)   
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)