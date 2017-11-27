---
title: "&lt;certificate&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 87f016d8756daf72d93143e1432ae74a6852c953
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcertificategt-element"></a>&lt;certificate&gt; 요소
피어 투 피어 클라이언트의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다.  
  
 \<시스템입니다. ServiceModel >  
\<동작 >  
\<endpointBehaviors >  
\<동작 >  
\<clientCredentials >  
\<피어 >  
\<인증서 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<certificate findValue="String"   
  
storeLocation="LocalMachine/CurrentUser"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`findValue`|X.509 인증서 저장소에서 검색할 값을 포함하는 문자열입니다. 이 특성에 포함된 형식은 지정한 `x509FindType`의 요구 사항을 충족해야 합니다. 기본값은 빈 문자열입니다.|  
|`storeLocation`|클라이언트가 피어 인증서의 유효성을 검사하는 데 사용하는 X.509 인증서 저장소의 위치를 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -LocalMachine: 로컬 컴퓨터에 할당 된 인증서 저장소입니다.<br />-CurrentUser: 현재 사용자에 게 할당 된 인증서 저장소입니다.<br /><br /> 기본값은 LocalMachine입니다.|  
|`storeName`|열려는 X.509 인증서 저장소의 이름을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> -AddressBook: 다른 사용자에 대 한 인증서 저장소입니다.<br />-AuthRoot: 인증서 저장소 공급 업체 Ca (인증 기관)입니다.<br />-CertificateAuthority: 중개 Ca (인증 기관)에 대 한 인증서 저장소입니다.<br />-Disallowed: 해지 된 인증서에 대 한 저장소 인증서.<br />-인증서 저장소 my: 개인 인증서입니다.<br />-Root: 신뢰할 수 있는 루트 Ca (인증 기관)에 대 한 인증서 저장소입니다.<br />-TrustedPeople: 직접 신뢰할 수 있는 사용자 및 리소스에 대 한 인증서 저장소입니다.<br />-TrustedPublisher: 직접 신뢰할 수 있는 게시자에 대 한 인증서 저장소입니다.<br /><br /> 기본값은 My입니다.|  
|`X509FindType`|실행할 X.509 검색의 유형을 정의합니다. 유효한 값은 다음과 같습니다.<br /><br /> -FindByThumbPrint<br />-FindBySubjectName<br />-FindBySubjectDistinguishedName<br />-FindByIssuerName<br />-FindByIssuerDistinguishedName<br />-FindBySerialNumber<br />-FindByTimeValid<br />-FindByTimeNotYetValid<br />-FindByTemplateName<br />-FindByApplicationPolicy<br />-FindByCertificatePolicy<br />-FindByExtension<br />-FindByKeyUsage<br />-Findbysubjectkeyidentifier가<br /><br /> `findValue` 특성에 포함된 형식은 지정한 `X509FindType`의 요구 사항을 충족해야 합니다.<br /><br /> 기본값은 FindBySubjectDistinguishedName입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<피어 >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|피어 투 피어 클라이언트를 인증할 때 사용하는 자격 증명을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 구성 요소는 피어 메시에서 환경을 인증할 때 사용되는 X509Certificate2 인스턴스를 포함합니다.  
  
 피어 투 피어 프로그래밍에 대 한 자세한 내용은 참조 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 피어 투 피어 시나리오에서 사용된 인증서를 찾는 방법을 지정합니다.  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [피어 채널 메시지 인증](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [피어 채널 사용자 지정 인증](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [피어 채널 응용 프로그램 보안](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
