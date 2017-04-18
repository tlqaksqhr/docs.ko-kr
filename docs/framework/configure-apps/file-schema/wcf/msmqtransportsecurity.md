---
title: "&lt;msmqTransportSecurity&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# &lt;msmqTransportSecurity&gt;
사용자 지정 바인딩에 MSMQ 전송 보안 설정을 지정합니다.  
  
## 구문  
  
```  
  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`msmqAuthenticationMode`|메시지가 MSMQ 전송에 의해 인증되는 방법을 지정합니다.  이 특성이 `None`으로 설정되면 `msmqProtectionLevel` 특성 값도 `None`으로 설정되어야 합니다.<br /><br /> 유효한 값은 다음과 같습니다.<br /><br /> -   None: 인증하지 않습니다.<br />-   Windows: 이 인증 메커니즘은 Active Directory를 사용하여 메시지와 연결된 SID의 X.509 인증서를 가져옵니다.  그런 다음 이 인증서는 사용자에게 큐에 대한 쓰기 권한이 있는지 확인하기 위해 큐의 ACL을 검사하는 데 사용됩니다.<br />-   Certificate: 채널은 인증서 저장소에서 인증서를 가져옵니다.<br /><br /> 기본값은 Windows입니다.  이 특성은 <xref:System.ServiceModel.MsmqAuthenticationMode> 형식입니다.|  
|`msmqEncryptionAlgorithm`|메시지 큐 관리자 간에 메시지를 전송할 때 통신 중에 메시지 암호화에 사용할 알고리즘을 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   RC4Stream<br />-   AES<br /><br /> 기본값은 RC4Stream입니다.  이 특성은 <xref:System.ServiceModel.MsmqEncryptionAlgorithm> 형식입니다.|  
|`msmqProtectionLevel`|메시지가 MSMQ 전송 수준에서 보호되는 방식을 지정합니다.  EncryptAndSign이 메시지 무결성 및 비부인을 보장하는 반면 암호화는 메시지 무결성을 보장합니다. 즉, 메시지는 실제로 보낸 사람으로부터 나오고 보낸 사람은 보낸 사람임을 밝히는 사람입니다.  유효한 값은 다음과 같습니다.<br /><br /> -   None: 보호되지 않습니다.<br />-   Sign: 메시지가 서명됩니다.<br />-   EncryptAndSign: 메시지가 암호화되고 서명됩니다.<br /><br /> 기본값은 Sign입니다.  이 특성은 <xref:System.Net.Security.ProtectionLevel> 형식입니다.|  
|`msmqSecureHashAlgorithm`|시그니처의 일부로 다이제스트를 계산하는 데 사용되는 알고리즘을 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> 기본값은 SHA1입니다.  이 특성은 <xref:System.ServiceModel.MsmqSecureHashAlgorithm> 형식입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<msmqIntegration\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|MSMQ\(메시지 큐\) 전송자 또는 수신자와의 상호 작용에 필요한 설정을 지정합니다.|  
|[\<msmqTransport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|네이티브 MSMQ 프로토콜을 사용하는 WCF\(Windows Communication Foundation\) 서비스에 대한 큐 통신 속성을 지정합니다.|  
  
## 설명  
 전송 보안 정책에 대한 자세한 내용은 [전송 보안](../../../../../docs/framework/wcf/feature-details/transport-security.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>   
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [WCF의 큐](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [전송](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [전송 선택](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [전송 보안](../../../../../docs/framework/wcf/feature-details/transport-security.md)