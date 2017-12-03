---
title: "&lt;serviceCredentials&gt;의 &lt;clientCertificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc2dfd94ffbf8ce08dee9c14421f389861e99e77
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltclientcertificategt-of-ltservicecredentialsgt"></a>&lt;serviceCredentials&gt;의 &lt;clientCertificate&gt;
이중 통신 패턴에서 서비스의 클라이언트에 대한 메시지를 서명 및 암호화하는 데 사용하는 X.509 인증서를 정의합니다.  
  
 \<시스템입니다. ServiceModel >  
\<동작 >  
\<serviceBehaviors >  
\<serviceBehaviors >  
\<동작 >  
\<serviceCredentials >  
\<clientCertificate >  
  
## <a name="syntax"></a>구문  
  
```xml  
<clientCertificate>  
 <certificate/>  
 <authentication/>  
</clientCertificate>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<인증 >](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|클라이언트 인증서의 인증 옵션을 지정합니다.|  
|[\<인증서 >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|사용할 인증서를 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|서비스를 인증하는 데 사용되는 자격 증명 및 클라이언트 자격 증명 유효성 검사 관련 설정을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 이 요소는 서비스가 클라이언트와 안전하게 통신하기 위해 클라이언트의 인증서가 필요한 경우 사용됩니다. 이는 양방향 통신 패턴을 사용하는 경우 발생합니다. 대부분의 일반적인 요청/응답 패턴의 경우 클라이언트는 요청 시 서비스가 클라이언트에게 해당 응답을 암호화 및 서명하는 데 사용하는 인증서를 포함합니다. 그러나 이중 통신 패턴에서는 서비스에 클라이언트의 요청이 없으므로 클라이언트에게 보내는 메시지 보안을 위해 클라이언트의 인증서가 사전에 필요합니다. 따라서 클라이언트 인증서를 out-of-band 협상 방식으로 가져와서 이 요소를 사용하여 인증서를 지정해야 합니다. 이중 서비스에 대 한 자세한 내용은 참조 [하는 방법: 이중 계약 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)합니다.  
  
 이 요소에 설정된 인증서는 `MutualCertificateDuplex` 메시지 보안 인증 모드와 함께 구성되는 바인딩용 클라이언트에 보내는 메시지를 암호화하는 데 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>  
 [방법: 이중 계약 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [인증서 작업](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
