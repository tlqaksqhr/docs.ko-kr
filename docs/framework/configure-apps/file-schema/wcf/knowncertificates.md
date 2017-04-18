---
title: "&lt;knownCertificates&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 678e21b4-6493-47c3-8359-fcf0d37e2138
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# &lt;knownCertificates&gt;
STS\(보안 토큰 서비스\)에서 발급한 보안 자격 증명을 인증하기 위해 제공된 X.509 인증서 컬렉션을 나타냅니다.  
  
## 구문  
  
```  
  
<knownCertificates>   
      <add findValue="String"  
         storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
           x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)|컬렉션에 X.509 인증서를 추가합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)|서비스 자격 증명으로 발급된 토큰을 지정합니다.|  
  
## 설명  
 발급된 토큰 시나리오에는 3단계가 있습니다.  첫 번째 단계에서 서비스에 액세스하려는 클라이언트를 *보안 토큰 서비스*라고 합니다.  보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML\(Security Assertions Markup Language\) 토큰이라는 클라이언트 토큰을 발급합니다.  클라이언트는 토큰을 통해 서비스에 반환됩니다.  서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.  토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.  
  
 [\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) 요소는 이러한 보안 토큰 서비스 인증서에 대한 리포지토리입니다.  인증서를 추가하려면 [\<knownCertificates\> element](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)를 사용합니다.  다음 예제와 같이 각 인증서에 대해 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)를 삽입합니다.  
  
```  
<issuedTokenAuthentication>  
   <knownCertificates>  
      <add findValue="www.contoso.com"   
           storeLocation="LocalMachine" storeName="My"   
           X509FindType="FindBySubjectName" />  
    </knownCertificates>  
</issuedTokenAuthentication>  
```  
  
 기본적으로 인증서는 보안 토큰 서비스에서 가져와야 합니다.  이러한 "알려진" 인증서는 올바른 클라이언트만 서비스에 액세스할 수 있도록 합니다.  
  
 페더레이션 서비스가 클라이언트를 인증하기 위해 필요한 조건과 이 구성 요소 사용에 대한 자세한 내용은 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)을 참조하세요.  페더레이션 시나리오에 대한 자세한 내용은 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)을 참조하세요.  
  
 구성에서 컬렉션을 채우는 방법을 보여 주는 예제는 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)를 참조하세요.  
  
## 참고 항목  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>   
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>   
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>   
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)   
 [\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)   
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)   
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)