---
title: "&lt;scopedCertificates&gt; 요소의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e21c1ef8-d6d6-4bca-ac5a-6fbf4bd77412
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eff535f7eb779a69c2368f3ad815f1eb124946ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltscopedcertificatesgt-element"></a>&lt;scopedCertificates&gt; 요소의 &lt;add&gt;
범위가 지정된 인증서 컬렉션에 X.509 인증서를 추가합니다.  
  
 \<시스템입니다. ServiceModel >  
\<동작 >  
endpointBehaviors 섹션  
\<동작 >  
\<clientCredentials >  
\<serviceCertificate >  
\<scopedCertificates >  
\<추가 > 요소에 대 한 \<scopedCertificates >  
  
## <a name="syntax"></a>구문  
  
```xml  
<add findValue="String"  
          storeLocation="CurrentUser/LocalMachine"  
          storeName=" CurrentUser/LocalMachine"  
          targetUri="string"  
         x509Type="FindByThumbprint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindBySerialNumber/FindByTimeExpired/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"   
/>   
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|targetUri|문자열. 인증서와 연결된 서비스의 URI를 지정합니다.|  
|findValue|문자열. 검색할 값입니다.|  
|x509FindType|열거형입니다. 검색할 인증서 필드 중 하나입니다.|  
|storeLocation|열거형입니다. 검색할 두 저장소 위치 중 하나입니다.|  
|storeName|열거형입니다. 검색할 시스템 저장소 중 하나입니다.|  
  
## <a name="findvalue-attribute"></a>findValue 특성  
  
|값|설명|  
|-----------|-----------------|  
|문자열|이 값은 검색 중인 필드(X509FindType 특성으로 지정)에 따라 다릅니다. 예를 들어, 지문을 검색할 경우 이 값은 16진수 문자열이어야 합니다.|  
  
## <a name="x509findtype-attribute"></a>x509FindType 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|값에는 FindByThumbprint, FindBySubjectName, FindBySubjectDistinguishedName, FindByIssuerName, FindByIssuerDistinguishedName, FindBySerialNumber, FindByTimeValid, FindByTimeNotYetValid, FindBySerialNumber, FindByTimeExpired, FindByTemplateName, FindByApplicationPolicy, FindByCertificatePolicy, FindByExtension, FindByKeyUsage, FindBySubjectKeyIdentifier가 있습니다.|  
  
## <a name="storelocation-attribute"></a>storeLocation 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|CurrentUser 또는 LocalMachine입니다.|  
  
## <a name="storename-attribute"></a>storeName 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|값에는 AddressBook, AuthRoot, CertificateAuthority, Disallowed, My, Root, TrustedPeople 및 TrustedPublisher가 포함됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<scopedCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|인증에 대해 범위가 지정된 특정 서비스가 제공하는 X.509 인증서 컬렉션을 나타냅니다.|  
  
## <a name="remarks"></a>설명  
 이 요소를 사용하면 클라이언트가 통신할 서비스의 URL을 기반으로 사용할 서비스 인증서를 구성할 수 있습니다. 이는 클라이언트가 중간 보안 토큰 서비스뿐 아니라 끝 서비스 등의 여러 서비스와 통신할 수 있는 발급된 토큰 시나리오에서 특히 유용합니다. 인증서 기반 메시지 보안을 사용하는 바인딩의 경우 서비스에 보내는 메시지를 암호화하는 데 이 인증서를 사용하며, 서비스에서는 클라이언트로 보내는 회신에 서명하는 데 이 인증서를 사용해야 합니다.  
  
 바인딩을 수행할 때 서비스용 인증서가 필요하고 서비스 URL에 대한 특정 인증서를 ScopedCertificates에서 찾을 수 없는 경우, 기본 인증서가 사용됩니다.  
  
 자세한 내용은의 "범위가 지정 된 인증서" 섹션을 참조 하십시오. [하는 방법: 페더레이션 클라이언트 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 컬렉션에 X.509 인증서를 추가합니다.  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <serviceCertificate>  
     <scopedCertificates>  
      <add targetUri="http://www.contoso.com"   
       findValue="www.Contoso.com"   
       storeLocation="LocalMachine"  
       storeName="Root"   
       x509FindType="FindByIssuerName" />  
     </scopedCertificates>  
    </serviceCertificate>  
   </clientCredentials>  
  </behavior>  
 </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement.ScopedCertificates%2A>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElementCollection>  
 <xref:System.ServiceModel.Configuration.X509ScopedServiceCertificateElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential.ScopedCertificates%2A>  
 [방법: 페더레이션 클라이언트 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)  
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
