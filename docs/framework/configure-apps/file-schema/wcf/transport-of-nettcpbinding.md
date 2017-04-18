---
title: "&lt;netTcpBinding&gt;의 &lt;transport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &lt;netTcpBinding&gt;의 &lt;transport&gt;
[\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)로 구성된 끝점의 메시지 수준 보안 요구 사항 형식을 정의합니다.  
  
## 구문  
  
```  
<netTcpBinding>  
    <binding>  
        <security  
         mode="None|Transport|Message|TransportWithMessageCredential">  
            <transport clientCredentialType="None|Windows|Certificate"  
             protectionLevel="None|Sign|EncryptAndSign"  
             sslProtocols="Ssl3|Tls|Tls11|Tls12">  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</netTcpBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|clientCredentialType|선택 사항입니다.  전송 보안을 사용하여 클라이언트 인증을 수행할 때 사용되는 자격 증명의 형식을 지정합니다.<br /><br /> -   기본값은 `Windows`입니다.<br />-   이 특성은 <xref:System.ServiceModel.TcpClientCredentialType> 형식입니다.|  
|protectionLevel|선택 사항입니다.  TCP 전송의 수준에 보안을 정의합니다.  메시지 서명은 메시지 전송 과정에서 제3자가 메시지를 위조할 수 있는 위험을 줄입니다.  암호화는 전송 과정에서 데이터 수준의 개인 정보 보호를 제공합니다.<br /><br /> 기본값은 `EncryptAndSign`입니다.|  
|sslProtocols|지원되는 SslProtocols를 지정하는 SslProtocols 열거형 플래그 값입니다.  기본값은 Ssl3&#124;Tls&#124;Tls11&#124;Tls12입니다.|  
|policyEnforcement|이 열거형은 <xref:System.Security.Authentication.ExtendedProtectionPolicy>가 적용되는 경우를 지정합니다.<br /><br /> 1.  Never \- 정책이 적용되지 않습니다\(확장 보호가 사용되지 않음\).<br />2.  WhenSupported – 클라이언트에서 확장 보호를 지원하는 경우에만 정책이 적용됩니다.<br />3.  Always – 정책이 항상 적용됩니다.  확장 보호를 지원하지 않는 클라이언트는 인증되지 않습니다.|  
  
## clientCredentialType 특성  
  
|값|설명|  
|-------|--------|  
|없음|클라이언트는 익명입니다.  여기에는 서비스 인증서가 필요합니다.|  
|Windows|SP 협상\(Kerberos 협상\)을 사용하는 클라이언트의 Windows 인증을 지정합니다.|  
|인증서|클라이언트는 인증서를 사용하여 인증됩니다.  클라이언트에서는 SSL 협상을 사용하며 서비스 인증서가 필요합니다.|  
  
## protectionLevel 특성  
  
|값|설명|  
|-------|--------|  
|없음|보호되지 않습니다.|  
|Sign|메시지가 서명됩니다.|  
|EncryptAndSign|-   메시지가 암호화되고 서명됩니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<security\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|[\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)의 보안 기능을 지정합니다.|  
  
## 설명  
 SOAP 메시지의 무결성 및 기밀성과 상호 인증을 위해 전송 보안을 사용합니다.  바인딩에서 이 보안 모드를 선택하면 보안 전송을 사용하여 채널 스택이 구성되고 Windows\(협상\) 또는 SSL over TCP 같은 전송 보안을 사용하여 SOAP 메시지가 보안됩니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.TcpTransportSecurity>   
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.NetTcpTransportSecurityElement>   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)