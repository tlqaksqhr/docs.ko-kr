---
title: "&lt;netMsmqBinding&gt;의 &lt;message&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;netMsmqBinding&gt;의 &lt;message&gt;
이 `netMsmqBinding` 바인딩에 대한 SOAP 메시지 보안 설정을 정의합니다.  
  
## 구문  
  
```  
  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|algorithmSuite|MSMQ 전송을 통해 전송되는 메시지에 메시지 기반 보안을 적용하는 데 사용되는 메시지 암호화 및 키 랩 알고리즘을 설정합니다.<br /><br /> 기본값은 `Aes256`입니다.  이 특성은 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 형식입니다.|  
|clientCredentialType|MSMQ 전송을 통해 전송되는 메시지에 대해 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   None: 서비스와 익명 클라이언트가 상호 작용할 수 있습니다.  서비스와 클라이언트 모두 자격 증명이 필요하지 않습니다.<br />-   Windows: Windows 자격 증명의 인증된 컨텍스트에서 SOAP 교환을 수행할 수 있습니다.  이 설정은 항상 Kerberos 기반 인증을 수행합니다.<br />-   UserName: 서비스에서 UserName 자격 증명을 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.  이 경우 `clientCredentials` 동작을 사용하여 자격 증명을 지정해야 합니다. **Caution:**  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]는 암호 다이제스트를 보내거나 암호를 사용하여 키를 파생하고 메시지 보안에 이러한 키를 사용하는 것을 지원하지 않습니다.  따라서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]는 UserName 자격 증명을 사용할 때 교환에 보호를 적용합니다.  이 모드에서는 `clientCredential` 동작 및 `serviceCertificate`를 사용하여 클라이언트에 서비스 인증서를 지정해야 합니다. <br /><br /> -   Certificate: 서비스에서 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.  이 경우 `clientCredentials` 동작을 사용하여 클라이언트 자격 증명을 지정해야 합니다.  이 경우 `serviceCertificate`를 지정하여 `clientCredentials` 동작을 통해 서비스 자격 증명을 지정해야 합니다.<br />-   CardSpace: 이를 통해 서비스에서 CardSpace를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.  `clientCredential` 동작에 `serviceCertiifcate`가 제공되어야 합니다.<br /><br /> 기본값은 `Windows`입니다.  이 특성은 <xref:System.ServiceModel.MessageCredentialType> 형식입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<security\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|바인딩에 대한 보안 설정을 정의합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>   
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>   
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>   
 <xref:System.ServiceModel.MessageSecurityOverMsmq>   
 [WCF의 큐](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)