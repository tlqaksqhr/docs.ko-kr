---
title: '&lt;peerAuthentication&gt; 요소'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09a8a9ff-e395-42f6-8ceb-9d44bdc1cbe1
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9d8809378d8ad8bd5b62d6435919602e4ad0b042
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="ltpeerauthenticationgt-element"></a>&lt;peerAuthentication&gt; 요소
피어 투 피어 클라이언트에 대한 인증 옵션을 지정합니다.  
  
 피어 투 피어 프로그래밍에 대 한 자세한 내용은 참조 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)합니다.  
  
 \<system.ServiceModel>  
\<동작 >  
\<endpointBehaviors>  
\<동작 >  
\<clientCredentials>  
\<peer>  
\<PeerAuthentication >  
  
## <a name="syntax"></a>구문  
  
```xml  
<peerAuthentication  
customCertificateValidatorType = "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
revocationMode="NoCheck/Online/Offline"  
trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`customCertificateValidatorType`|선택적 문자열입니다. 사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리입니다. 이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다.|  
|`certifcateValidationMode`|선택적 열거형입니다. 자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다. `Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다. 기본값은 `ChainTrust`입니다.|  
|`revocationMode`|선택적 열거형입니다. CRL(해지된 인증서 목록)을 검사하는 데 사용되는 모드 중 하나입니다. 기본값은 `Online`입니다.|  
|`trustedStoreLocation`|선택적 열거형입니다. 시스템 저장소 위치 `LocalMachine` 또는 `CurrentUser` 중 하나입니다. 서비스 인증서가 클라이언트와 협상될 때 이 값이 사용됩니다. 에 대해 유효성 검사가 수행 되는 **신뢰할 수 있는 사용자** 지정한 저장소 위치에 저장 합니다. 기본값은 `CurrentUser`입니다.|  
  
## <a name="customcertificatevalidatortype-attribute"></a>customCertificateValidatorType 특성  
  
|값|설명|  
|-----------|-----------------|  
|문자열|형식 이름 및 어셈블리와 형식을 찾는 데 사용되는 기타 데이터를 지정합니다. 적어도 네임스페이스 및 형식 이름이 필요합니다. 선택적 정보로는 어셈블리 이름, 버전 번호, 문화권 및 공개 키 토큰이 있습니다.|  
  
## <a name="certificatevalidationmode-attribute"></a>certificateValidationMode 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|`None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom` 값 중 하나입니다. 기본값은 `ChainTrust`입니다.<br /><br /> 자세한 내용은 참조 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.|  
  
## <a name="revocationmode-attribute"></a>revocationMode 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|`NoCheck`, `Online`, `Offline` 값 중 하나입니다. 기본값은 `Online`입니다.<br /><br /> 자세한 내용은 참조 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)합니다.|  
  
## <a name="trustedstorelocation-attribute"></a>trustedStoreLocation 특성  
  
|값|설명|  
|-----------|-----------------|  
|열거형|`LocalMachine` 또는 `CurrentUser` 값 중 하나입니다. 기본값은 `CurrentUser`입니다. 시스템 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `LocalMachine`에 있습니다. 사용자 계정으로 클라이언트 응용 프로그램을 실행하는 경우 인증서는 대개 `CurrentUser`에 있습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|피어 서비스에 대해 클라이언트를 인증하는 데 사용되는 자격 증명을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 `<authentication>` 요소는 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 클래스에 해당합니다. 이 요소는 메시의 환경 간 인증 중에 호출되는 유효성 검사기를 지정합니다. 새 피어는 환경 연결을 설정하려고 할 때 응답 피어에 해당 자격 증명을 전달합니다. 원격 상대방의 자격 증명의 유효성 검사를 위해 응답자의 유효성 검사기가 호출됩니다. 메시에서 피어 연결이 설정될 때마다 두 피어는 상호 인증됩니다. 즉, 양쪽에서 유효성 검사기가 호출됩니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 인증서 유효성 검사 모드를 `PeerOrChainTrust`로 설정합니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.PeerAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [피어 채널 메시지 인증](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [피어 채널 사용자 지정 인증](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [피어 채널 응용 프로그램 보안](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
