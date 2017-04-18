---
title: "&lt;ws2007HttpBinding&gt;의 &lt;message&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9ffd8db6-84a8-4b38-a9fe-2cb1a87a1c97
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;ws2007HttpBinding&gt;의 &lt;message&gt;
[\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) 요소의 메시지 수준 보안 설정을 정의합니다.  
  
## 구문  
  
```  
  
<ws2007HttpBinding>  
 <binding >  
  <security>  
   <message clientCredentialType =  
    "None/Windows/UserName/Certificate/IssuedToken"  
    establishSecurityContext="Boolean"  
    negotiateServiceCredential="Boolean"  
    algorithmSuite= Enumeration. See algorithmSuite Attribute below.  
    defaultProtectionLevel="None/Sign/EncryptionAndSign" />  
  </security>  
 </binding>  
</ws2007HttpBinding>  
```  
  
## 형식  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`algorithmSuite`|메시지 암호화 및 키 래핑 알고리즘을 설정합니다.  알고리즘과 키 크기는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 클래스로 결정됩니다.  이러한 알고리즘은 WS\-SecurityPolicy\(Security Policy Language\) 사양에 지정된 알고리즘에 매핑됩니다.<br /><br /> 기본값은 Basic256입니다.|  
|`clientCredentialType`|선택 사항입니다.  `Message` 또는 `TransportWithMessageCredentials` 보안 모드를 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.  다음 표에서 열거형 값을 참조하세요.  기본값은 Windows입니다.<br /><br /> 이 특성은 <xref:System.ServiceModel.MessageCredentialType> 형식입니다.|  
|`establishSecurityContext`|보안 채널이 보안 세션을 설정할지 여부를 결정하는 값입니다.  보안 세션은 응용 프로그램 메시지를 교환하기 전에 SCT\(보안 컨텍스트 토큰\)를 설정합니다.  SCT가 설정되면 보안 채널은 상위 채널에 대한 <xref:System.ServiceModel.Channels.ISession> 인터페이스를 제공합니다.  보안 세션을 사용하는 방법은 [방법: 보안 세션 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)를 참조하세요.<br /><br /> 기본값은 `true`입니다.|  
|`negotiateServiceCredential`|선택 사항입니다.  서비스 자격 증명이 클라이언트에서 out\-of\-band 방식으로 제공되는지 아니면 협상 프로세스를 통해 서비스에서 클라이언트로 전달되는지를 지정하는 값입니다.  그러한 협상은 일반적인 메시지 교환에 앞서 수행됩니다.<br /><br /> `clientCredentialType` 특성이 None, Username 또는 Certificate일 경우 이 특성을 `false`로 설정하면 클라이언트에서 out\-of\-band 방식으로 서비스 자격 증명을 사용할 수 있으며 클라이언트는 [\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) 서비스 동작에서 [\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)를 사용하여 서비스 인증서를 지정해야 합니다.  이 모드는 WS\-Trust 및 WS\-SecureConversation을 구현하는 SOAP 스택과 상호 운용할 수 있습니다.<br /><br /> `ClientCredentialType` 특성이 `Windows`로 설정된 경우 이 특성을 `false`로 설정하면 Kerberos 기반 인증이 지정됩니다.  이것은 클라이언트와 서비스가 동일한 Kerberos 도메인에 속해야 함을 의미합니다.  이 모드는 Kerberos 토큰 프로필\(OASIS WSS TC에서 정의\) 그리고 WS\-Trust 및 WS\-SecureConversation을 구현하는 SOAP 스택과 상호 운용할 수 있습니다.<br /><br /> 이 특성이 `true`일 경우 SOAP 메시지를 통한 <xref:System.ServiceModel.Security.Tokens.ServiceModelSecurityTokenTypes.Spnego%2A> 교환을 터널링하는 .NET SOAP 협상이 수행됩니다.<br /><br /> 기본값은 `true`입니다.|  
  
## algorithmSuite 특성  
  
|값|설명|  
|-------|--------|  
|Basic128|Aes128 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa\-oaep\-mgf1p를 사용합니다.|  
|Basic192|Aes192 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa\-oaep\-mgf1p를 사용합니다.|  
|Basic256|Aes256 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa\-oaep\-mgf1p를 사용합니다.|  
|Basic256Rsa15|메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.|  
|Basic192Rsa15|메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.|  
|TripleDes|TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa\-oaep\-mgf1p를 사용합니다.|  
|Basic128Rsa15|메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.|  
|TripleDesRsa15|TripleDes 암호화, 메시지 다이제스트의 경우 Sha1, 키 래핑의 경우 Rsa15를 사용합니다.|  
|Basic128Sha256|메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa\-oaep\-mgf1p를 사용합니다.|  
|Basic192Sha256|메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa\-oaep\-mgf1p를 사용합니다.|  
|Basic256Sha256|메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa\-oaep\-mgf1p를 사용합니다.|  
|TripleDesSha256|메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa\-oaep\-mgf1p를 사용합니다.|  
|Basic128Sha256Rsa15|메시지 암호화의 경우 Aes128, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.|  
|Basic192Sha256Rsa15|메시지 암호화의 경우 Aes192, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.|  
|Basic256Sha256Rsa15|메시지 암호화의 경우 Aes256, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.|  
|TripleDesSha256Rsa15|메시지 암호화의 경우 TripleDes, 메시지 다이제스트의 경우 Sha256, 키 래핑의 경우 Rsa15를 사용합니다.|  
  
## clientCredentialType 특성  
  
|값|설명|  
|-------|--------|  
|`None`|이를 통해 서비스와 익명 클라이언트가 상호 작용할 수 있습니다.  서비스 쪽에서는 서비스가 클라이언트 자격 증명을 요구하지 않음을 의미하고  클라이언트 쪽에서는 클라이언트가 클라이언트 자격 증명을 제공하지 않음을 의미합니다.|  
|`Certificate`|서비스에서 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.  `message` 보안 모드가 사용되고 `negotiateServiceCredential` 특성이 `false`로 설정되면 서비스 인증서를 사용하여 클라이언트를 구축해야 합니다.|  
|`IssuedToken`|일반적으로 STS\(보안 토큰 서비스\)에서 발급하는 사용자 지정 토큰을 지정합니다.|  
|`UserName`|서비스에서 `UserName` 자격 증명을 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.  [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]는 암호 다이제스트를 보내거나 암호를 사용하여 키를 파생하고 메시지 보안에 이러한 키를 사용하는 것을 지원하지 않습니다.  따라서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에서는 `UserName` 자격 증명을 사용할 때 전송에 보안을 적용합니다.  이 자격 증명 모드에서는 상호 운용이 가능한 교환 또는 `negotiateServiceCredential` 특성을 기반으로 하는 상호 운용이 불가능한 협상이 수행됩니다.|  
|`Windows`|`Windows` 자격 증명의 인증된 컨텍스트에서 SOAP 교환을 수행할 수 있습니다.  `negotiateServiceCredential` 특성이 `true`로 설정되면 SSPI 협상 또는 Kerberos\(상호 운용 가능 표준\)가 수행됩니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<security\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|[\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)에 대한 보안 설정을 정의합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Message%2A>   
 <xref:System.ServiceModel.WSHttpSecurity.Message%2A>   
 <xref:System.ServiceModel.Configuration.NonDualMessageSecurityOverHttpElement>   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)