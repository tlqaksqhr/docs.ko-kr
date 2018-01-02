---
title: '&lt;messageSenderAuthentication&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea62fc06-55fb-42e0-aa2b-8867bdf4b415
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 496542ca476d9af309a34b4b05a1c3c023c06124
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltmessagesenderauthenticationgt"></a>&lt;messageSenderAuthentication&gt;
메시지 발신자가 사용하는 피어 인증서에 대한 인증 설정을 지정합니다.  
  
 \<시스템입니다. ServiceModel >  
\<동작 >  
\<serviceBehaviors >  
\<동작 >  
\<serviceCredentials >  
\<피어 >  
\<messageSenderAuthentication >  
  
## <a name="syntax"></a>구문  
  
```xml  
<messageSenderAuthentication  
   customCertificateValidatorType="namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"  
   certificateValidationMode="ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"  
   revocationMode="NoCheck/Online/Offline"  
   trustedStoreLocation="CurrentUser/LocalMachine"   
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`certificateValidationMode`|선택적 열거형입니다. 자격 증명의 유효성을 검사하는 데 사용되는 5개 모드 중 하나를 지정합니다. 이 특성은 <xref:System.ServiceModel.Security.X509CertificateValidationMode> 형식입니다. `Custom`으로 설정되면 `customCertificateValidator`도 지정해야 합니다.|  
|`customCertificateValidatorType`|선택적 문자열입니다. 사용자 지정 형식의 유효성을 검사하는 데 사용되는 형식 및 어셈블리를 지정합니다. 이 특성은 `certificateValidationMode`가 `Custom`으로 설정되어 있을 때 설정해야 합니다. 이 특성은 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 형식입니다. [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서는 신뢰할 수 있는 사용자의 저장소를 대상으로 피어 인증서를 확인하는 기본 피어 인증서 유효성 검사기를 제공합니다. 이 검사기는 또한 인증서가 유효한 루트에 연결되었는지도 확인합니다. 사용자 지정 유효성 검사기를 사용하여 다른 동작을 지정하고, 이 특성을 사용하여 사용자 지정 유효성 검사기의 위치를 지정할 수 있습니다.|  
|`revocationMode`|선택적 열거형입니다. 인증서 해지 모드를 지정합니다. 이 특성은 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 형식입니다. 시스템에서는 해지된 인증서 목록에서 피어 인증서를 검색하여 해당 피어 인증서가 해지되지 않았는지를 확인합니다. 이러한 확인은 온라인으로 확인하거나 캐시된 해지 목록을 확인하여 이루어집니다. 이 특성을 NoCheck로 설정하면 해지 확인을 해제할 수 있습니다.|  
|`trustedStoreLocation`|선택적 열거형입니다. 피어 인증서의 유효성이 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 보안 시스템에 의해 확인되는, 신뢰할 수 있는 저장소의 위치를 지정합니다. 이 특성은 <xref:System.Security.Cryptography.X509Certificates.StoreLocation> 형식입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<피어 >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|피어 노드에 대한 현재 자격 증명을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 메시지 인증을 선택하면 이 요소를 구성해야 합니다. 제공 하는 인증서를 사용 하 여 각 메시지는 서명 하는 출력 채널에 대해 [ \<인증서 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)합니다. 모든 메시지는 응용 프로그램에 배달되기 전에 이 요소의 `customCertificateValidatorType` 특성에 지정된 유효성 검사기를 사용하여 메시지 자격 증명과 비교하여 검사됩니다. 유효성 검사기는 자격 증명을 수락하거나 거부할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>  
 <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>  
 <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>  
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [피어 채널 메시지 인증](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [피어 채널 사용자 지정 인증](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [피어 채널 응용 프로그램 보안](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
