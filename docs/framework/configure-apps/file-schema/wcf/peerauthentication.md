---
title: '&lt;peerAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad545e6f-f06e-4549-ac92-09d758d5c636
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a900a1f3fc2e07cffe04833cc3c7d3ccd063e24a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltpeerauthenticationgt"></a>&lt;peerAuthentication&gt;
피어 노드에서 사용하는 피어 인증서에 대한 인증 설정을 지정합니다.  
  
 \<system.ServiceModel>  
\<동작 >  
\<serviceBehaviors>  
\<동작 >  
\<serviceCredentials>  
\<peer>  
\<peerAuthentication>  
  
## <a name="syntax"></a>구문  
  
```xml  
<peerAuthentication  
      customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
      certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
      revocationMode="NoCheck/Online/Offline"  
      trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`certificateValidationMode`|선택적 열거형입니다. 자격 증명의 유효성을 검사하는 데 사용되는 세 가지 모드 중 하나를 지정합니다. 이 특성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 형식입니다. `Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.|  
|`customCertificateValidatorType`|선택적 문자열입니다. 사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리를 지정합니다. 이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다. 이 특성은 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 형식입니다. [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서는 신뢰할 수 있는 사용자의 저장소를 대상으로 피어 인증서를 확인하는 기본 피어 인증서 유효성 검사기를 제공합니다. 이 검사기는 또한 인증서가 유효한 루트에 연결되었는지도 확인합니다. 사용자 지정 유효성 검사기를 사용하여 다른 동작을 지정하고, 이 특성을 사용하여 사용자 지정 유효성 검사기의 위치를 지정할 수 있습니다.|  
|`revocationMode`|선택적 열거형입니다. 인증서 해지 모드를 지정합니다. 이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 형식입니다. 시스템에서는 해지된 인증서 목록에서 피어 인증서를 검색하여 해당 피어 인증서가 해지되지 않았는지를 확인합니다. 이러한 확인은 온라인으로 확인하거나 캐시된 해지 목록을 확인하여 이루어집니다. 이 특성을 NoCheck로 설정하면 해지 확인을 해제할 수 있습니다.|  
|`trustedStoreLocation`|선택적 열거형입니다. 피어 인증서의 유효성이 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 보안 시스템에 의해 확인되는, 신뢰할 수 있는 저장소의 위치를 지정합니다. 이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<peer>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|피어 노드에 대한 현재 자격 증명을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 `<authentication>` 요소는 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication> 클래스에 해당합니다. 이 요소는 메시의 환경 간 인증 중에 호출되는 유효성 검사기를 지정합니다. 새 피어는 환경 연결을 설정하려고 할 때 응답 피어에 해당 자격 증명을 전달합니다. 원격 상대방의 자격 증명의 유효성 검사를 위해 응답자의 유효성 검사기가 호출됩니다. 메시에서 피어 연결이 설정될 때마다 두 피어는 상호 인증됩니다. 즉, 양쪽에서 유효성 검사기가 호출됩니다.  
  
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
