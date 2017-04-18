---
title: "&lt;netNamedPipeBinding&gt;의 &lt;transport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# &lt;netNamedPipeBinding&gt;의 &lt;transport&gt;
명명된 파이프에 대한 전송 보안 설정을 정의합니다.  
  
## 구문  
  
```  
  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|protectionLevel|명명된 파이프의 보호 수준을 정의합니다.  메시지 서명은 메시지 전송 과정에서 제3자가 메시지를 위조할 수 있는 위험을 줄입니다.  암호화는 전송 과정에서 데이터 수준의 개인 정보 보호를 제공합니다.  유효한 값은 다음과 같습니다.<br /><br /> -   None: 보호되지 않습니다.<br />-   Sign: 메시지가 서명됩니다.<br />-   EncryptAndSign: 메시지가 암호화되고 서명됩니다.<br /><br /> 기본값은 EncryptAndSign입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<security\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|바인딩에 대한 보안 설정을 정의합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>   
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)