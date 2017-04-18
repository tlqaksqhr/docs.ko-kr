---
title: "&lt;peerTransport&gt;의 &lt;transport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;peerTransport&gt;의 &lt;transport&gt;
이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 지정합니다.  
  
## 구문  
  
```  
  
<security>  
   <transport credentialType="Certificate/Password" />  
</security>         
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|credentialType|선택 사항입니다.  피어 전송을 통해 보내는 메시지를 확인할 때 사용되는 자격 증명 형식을 지정합니다.  이 특성은 <xref:System.ServiceModel.PeerTransportCredentialType> 형식입니다.|  
  
## credentialType 특성  
  
|값|설명|  
|-------|--------|  
|인증서|피어 채널 전송을 인증하려면 X509 인증서가 필요합니다.|  
|암호|피어 채널 전송을 인증하려면 올바른 암호가 필요합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<security\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|피어 전송의 보안 설정을 정의합니다.|  
  
## 설명  
 이 요소는 [\<security\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)의 mode 특성이 `Transport` 또는 `TransportWithMessageCredential`로 설정된 경우에만 설정됩니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>   
 <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>   
 <xref:System.ServiceModel.PeerTransportSecuritySettings>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [전송 보안](../../../../../docs/framework/wcf/feature-details/transport-security.md)   
 [전송](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [전송 선택](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)