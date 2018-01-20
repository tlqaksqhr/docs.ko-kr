---
title: "&lt;clientCredentials&gt; 요소의 &lt;peer&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c3479b52c6e06b7b9ebd69d46780e8dca70d2ef7
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a>&lt;clientCredentials&gt; 요소의 &lt;peer&gt;
피어 투 피어 클라이언트를 인증할 때 사용하는 자격 증명을 지정합니다.  
  
 \<system.ServiceModel>  
\<동작 >  
\<endpointBehaviors>  
\<동작 >  
\<clientCredentials>  
\<peer>  
  
## <a name="syntax"></a>구문  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<certificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|피어 투 피어 클라이언트의 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 지정합니다. 이어야 합니다.|  
|[\<peerAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|피어 클라이언트에 대한 인증 옵션을 지정합니다.|  
|[\<messageSenderAuthentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|메시지 발신자에 대한 인증 옵션을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|클라이언트를 서비스에 인증할 때 사용되는 자격 증명을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 구성 요소는 피어 노드가 메시에서 다른 노드로부터 인증을 얻는 데 사용하는 자격 증명과 피어 노드가 다른 피어 노드를 인증하는 데 사용하는 인증 설정을 지정합니다. 자세한 내용은 참조 [피어 채널 메시지 인증](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95) 및 [피어 채널 응용 프로그램 보안](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [피어 투 피어 네트워킹](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)  
 [피어 채널 메시지 인증](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [피어 채널 사용자 지정 인증](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [피어 채널 응용 프로그램 보안](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
