---
title: "&lt;netPeerBinding&gt;의 &lt;security&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# &lt;netPeerBinding&gt;의 &lt;security&gt;
메시지 전송에 사용되는 인증 형식 및 보안을 비롯하여 [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)의 보안 설정을 정의합니다.  
  
## 구문  
  
```  
  
<netPeerBinding>  
    <binding>  
        <security mode="Message/None/Transport//TransportWithMessageCredential">  
            <transport credentialType="Certificate/Password" />  
        </security>  
    </binding>  
</netPeerBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|모드|선택 사항입니다.  이 바인딩으로 구성된 피어에서 사용하는 보안 형식을 지정합니다.  기본값은 `Message`입니다.  이 특성은 <xref:System.ServiceModel.SecurityMode> 형식입니다.|  
  
## mode 특성  
  
|값|설명|  
|-------|--------|  
|메시지|SOAP 전송은 무결성, 기밀성 및 인증을 제공합니다.|  
|없음|보안이 해제되어 있습니다.|  
|전송|HTTPS를 사용하여 보안이 제공됩니다.|  
|TransportWithMessageCredential|HTTPS는 인증 및 기밀성을 제공합니다.  SOAP 메시지는 다양한 자격 증명 형식을 제공합니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<transport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netpeertcpbinding.md)|이 바인딩으로 구성된 피어에서 보낸 보안 메시지의 전송 형식을 정의합니다.  이 요소는 <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement> 형식입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<binding\>](../../../../../docs/framework/misc/binding.md)|[\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)의 모든 바인딩 기능을 정의합니다.|  
  
## 설명  
 보안은 메시지 또는 전송별로 고유할 수 있습니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.PeerSecurityElement>   
 <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>   
 <xref:System.ServiceModel.PeerSecuritySettings>   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [자격 증명 형식 선택](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)