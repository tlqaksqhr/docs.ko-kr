---
title: "&lt;peerAuthentication&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;peerAuthentication&gt; 요소
피어 투 피어 클라이언트에 대한 인증 옵션을 지정합니다.  
  
 피어 투 피어 프로그래밍[!INCLUDE[crabout](../../../../../includes/crabout-md.md)] [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)을 참조하세요.  
  
## 구문  
  
```  
  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`customCertificateValidatorType`|선택적 문자열입니다.  사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다.  이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.|  
|`certifcateValidationMode`|선택적 열거형입니다.  자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다.  `Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.  기본값은 `ChainTrust`입니다.|  
|`revocationMode`|선택적 열거형입니다.  CRL\(해지된 인증서 목록\)을 검사하는 데 사용되는 모드 중 하나입니다.  기본값은 `Online`입니다.|  
|`trustedStoreLocation`|선택적 열거형입니다.  시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다.  서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다.  지정한 저장소 위치의 **신뢰된 사용자** 저장소에 대해 유효성 검사가 수행됩니다.  기본값은 `CurrentUser`입니다.|  
  
## customCertificateValidatorType 특성  
  
|값|설명|  
|-------|--------|  
|문자열|형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다.  적어도 네임스페이스 및 형식 이름이 필요합니다.  선택적 정보로는 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰이 있습니다.|  
  
## certificateValidationMode 특성  
  
|값|설명|  
|-------|--------|  
|열거형|`None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom` 값 중 하나입니다.  기본값은 `ChainTrust`입니다.<br /><br /> 자세한 내용은 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.|  
  
## revocationMode 특성  
  
|값|설명|  
|-------|--------|  
|열거형|`NoCheck`, `Online`, `Offline` 값 중 하나입니다.  기본값은 `Online`입니다.<br /><br /> 자세한 내용은 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)을 참조하세요.|  
  
## trustedStoreLocation 특성  
  
|값|설명|  
|-------|--------|  
|열거형|`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다.  기본값은 `CurrentUser`입니다.  시스템 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다.  사용자 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|피어 서비스에 대해 클라이언트를 인증하는 데 사용되는 자격 증명을 지정합니다.|  
  
## 설명  
 `<authentication>` 요소는 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 클래스에 해당합니다.  이 요소는 메시의 환경 간 인증 중에 호출되는 유효성 검사기를 지정합니다.  새 피어는 환경 연결을 설정하려고 할 때 응답 피어에 해당 자격 증명을 전달합니다.  원격 상대방의 자격 증명의 유효성 검사를 위해 응답자의 유효성 검사기가 호출됩니다.  메시에서 피어 연결이 설정될 때마다 두 피어는 상호 인증됩니다. 즉, 양쪽에서 유효성 검사기가 호출됩니다.  
  
## 예제  
 다음 코드에서는 인증서 유효성 검사 모드를 `PeerOrChainTrust`로 설정합니다.  
  
```  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
     <peerAuthentication   
          certificateValidationMode="PeerOrChainTrust" />  
     <messageSenderAuthentication certificateValidationMode="None" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>   
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>   
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>   
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>   
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)   
 [Peer Channel Message Authentication](http://msdn.microsoft.com/ko-kr/80e73386-514e-4c30-9e4a-b9ca8c173a95)   
 [Peer Channel Custom Authentication](http://msdn.microsoft.com/ko-kr/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)   
 [피어 채널 응용 프로그램 보안](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)