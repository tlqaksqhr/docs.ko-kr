---
title: '&lt;clientCredentials&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eaf46953d7b2c3f89e1f5b107dc9ddf5d1597875
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientcredentialsgt"></a>&lt;clientCredentials&gt;
클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.  
  
 \<시스템입니다. ServiceModel >  
\<동작 >  
\<endpointBehaviors >  
\<동작 >  
\<clientCredentials >  
  
## <a name="syntax"></a>구문  
  
```xml  
<clientCredentials type="String"  
      supportInteractive="Boolean" >  
   <clientCertificate>  
   </clientCertificate>  
   <digest>  
   </digest>  
   <isuedToken>  
   </isuedToken>  
   <peer>  
   </peer>  
   <serviceCertificate>  
   </serviceCertificate>  
   <windowsAuthentication>  
   </windowsAuthentication>  
</clientCredentials>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`supportInteractive`|런타임에 클라이언트 자격 증명을 선택할 때 대화형 사용자가 포함될 수 있는지 여부를 지정하는 부울 값입니다. 기본값은 `true`입니다.|  
|`type`|이 구성 요소의 형식을 지정하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|클라이언트를 서비스에 인증하는 데 사용되는 인증서를 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement> 형식입니다.|  
|[\<httpDigest >](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|클라이언트를 서비스에 인증하는 데 사용되는 다이제스트를 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.HttpDigestClientElement> 형식입니다.|  
|[\<issuedToken >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|클라이언트를 STS(보안 토큰 서비스)에 인증하는 데 사용되는 사용자 지정 토큰 형식을 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement> 형식입니다.|  
|[\<피어 >](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|현재 피어 자격 증명을 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.PeerCredentialElement> 형식입니다.|  
|[\<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|서비스를 클라이언트에 인증하는 데 사용되는 인증서를 지정하고 인증서 옵션을 설정하기 위한 구조를 제공합니다. 이 인증서는 서비스로부터 클라이언트에게 out-of-band로 제공되어야 합니다. 이 요소는 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement> 형식입니다.|  
|[\<windows >](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|Windows 자격 증명을 지정합니다. 기본값은 현재 스레드의 자격 증명입니다. 이 요소는 <xref:System.ServiceModel.Configuration.WindowsClientElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|끝점 동작을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 클라이언트 자격 증명은 상호 인증이 필요한 경우 서비스에 대해 클라이언트를 인증하는 데 사용됩니다. 또한 이 구성 섹션은 클라이언트가 서비스 인증서를 사용하여 서비스에 대한 메시지 보안을 유지해야 하는 경우 서비스 인증서를 지정하는 데 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)
