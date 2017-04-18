---
title: "&lt;knownCertificates&gt;의 &lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 128aaabe-3f1a-4c3b-b59f-898d0f02910f
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;knownCertificates&gt;의 &lt;add&gt;
알려진 인증서 컬렉션에 X.509 인증서를 추가합니다.  
  
## 구문  
  
```  
  
<knownCertificates>   
   <add findValue="String"  
      storeLocation="CurrentUser/LocalMachine"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      x509FindType="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"/>  
</knownCertificates>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|findValue|문자열.  검색할 값입니다.|  
|storeLocation|열거형입니다.  검색할 두 저장소 위치 중 하나입니다.|  
|storeName|열거형입니다.  검색할 시스템 저장소 중 하나입니다.|  
|x509FindType|열거형입니다.  검색할 인증서 필드 중 하나입니다.|  
  
## findValue 특성  
  
|값|설명|  
|-------|--------|  
|문자열|이 값은 검색 중인 필드\(X509FindType 특성으로 지정\)에 따라 다릅니다.  예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.|  
  
## x509FindType 특성  
  
|값|설명|  
|-------|--------|  
|열거형|값에는 FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier가 있습니다.|  
  
## storeLocation 특성  
  
|값|설명|  
|-------|--------|  
|열거형|CurrentUser 또는 LocalMachine입니다.|  
  
## storeName 특성  
  
|값|설명|  
|-------|--------|  
|열거형|값에는 AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople 및 TrustedPublisher가 포함됩니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<knownCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)|보안 토큰의 유효성을 검사하기 위해 STS\(보안 토큰 서비스\)에서 제공하는 X.509 인증서 컬렉션을 나타냅니다.|  
  
## 설명  
 발급된 토큰 시나리오에는 3단계가 있습니다.  첫 번째 단계에서 서비스에 액세스하려는 클라이언트를 *보안 토큰 서비스*라고 합니다.  보안 토큰 서비스는 클라이언트를 인증한 다음 일반적으로 SAML\(Security Assertions Markup Language\) 토큰이라는 클라이언트 토큰을 발급합니다.  클라이언트는 토큰을 통해 서비스에 반환됩니다.  서비스는 토큰 및 해당 클라이언트를 인증할 수 있는 데이터의 토큰을 검사합니다.  토큰을 인증하려면 보안 토큰 서비스가 사용하는 인증서를 서비스가 인식해야 합니다.  
  
 [\<issuedTokenAuthentication\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md) 요소는 이러한 보안 토큰 서비스 인증서에 대한 리포지토리입니다.  인증서를 추가하려면 [\<knownCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)를 사용합니다.  다음 예제와 같이 각 인증서에 대해 [\<add\> element \<knownCertificates\> Element](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-knowncertificates.md)를 삽입합니다.  
  
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
  
## 예제  
 다음 예제에서는 모든 STS 인증서에 대해 리포지토리에 인증서를 추가합니다.  
  
```  
<serviceBehaviors>  
 <behavior name="myServiceBehavior">  
  <serviceCredentials>  
   <issuedTokenAuthentication>  
    <knownCertificates>  
     <add findValue="www.contoso.com" storeLocation="LocalMachine"   
           storeName="CertificateAuthority"  
           x509FindType="FindByIssuerName" />  
     </knownCertificates>  
    </issuedTokenAuthentication>  
   </serviceCredentials>  
  </behavior>  
 </serviceBehaviors>  
```  
  
## 참고 항목  
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AllowedAudienceUris%2A>   
 <xref:System.IdentityModel.Selectors.SamlSecurityTokenAuthenticator.AudienceUriMode%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenServiceElement.KnownCertificates%2A>   
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElementCollection>   
 <xref:System.ServiceModel.Configuration.X509CertificateTrustedIssuerElement>   
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential.KnownCertificates%2A>   
 [\<knownCertificates\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowncertificates.md)   
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [방법: 페더레이션 서비스에서 자격 증명 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)