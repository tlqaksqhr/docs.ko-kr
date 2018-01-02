---
title: "&lt;peerTransport&gt;의 &lt;security&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d08d839d0eb80c23b96f87cf26d3d68db7d358f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltpeertransportgt"></a>&lt;peerTransport&gt;의 &lt;security&gt;
메시지 전송에 사용되는 인증 형식 및 보안을 비롯하여 피어 채널과 연결된 보안 설정을 포함합니다.  
  
 \<system.serviceModel >  
\<바인딩 >  
\<customBinding >  
\<바인딩 >  
\<r t >  
\<보안 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">  
    <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
</security  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`mode`|적용할 보안 형식을 지정합니다. 기본값은 Message입니다. 이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.|  
  
## <a name="mode-attribute"></a>mode 특성  
  
|값|설명|  
|-----------|-----------------|  
|`None`|보안이 해제되어 있습니다.|  
|`Transport`|HTTPS를 사용하여 보안이 제공됩니다.|  
|`Message`|SOAP 전송은 무결성, 기밀성 및 인증을 제공합니다.|  
|`TransportWithMessageCredential`|HTTPS는 인증 및 기밀성을 제공합니다. SOAP 메시지는 다양한 자격 증명 형식을 제공합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<전송 >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-peertransport.md)|사용자 지정 바인딩에 대한 피어 전송을 정의합니다. 이 요소에는 서비스와 상호 작용할 때 사용되는 자격 증명을 지정하는 `clientCredentialType` 특성이 있습니다. 이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.<br /><br /> 이 요소는 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<r t >](../../../../../docs/framework/configure-apps/file-schema/wcf/peertransport.md)|사용자 지정 바인딩에 대한 피어 전송을 정의합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>  
 <xref:System.ServiceModel.PeerSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [전송 보안](../../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [전송](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [전송 선택](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
