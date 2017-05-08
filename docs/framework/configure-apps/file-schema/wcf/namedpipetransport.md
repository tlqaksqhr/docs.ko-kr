---
title: "&lt;namedPipeTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;namedPipeTransport&gt;
사용자 지정 바인딩에 포함될 때 채널에서 명명된 파이프를 사용하여 메시지를 전송하도록 정의합니다.  
  
## 구문  
  
```  
  
<namedPipeTransport>  
      <connectionPoolSettings  
         groupName=”String”  
          idleTimeout"TimeSpan"  
        maxOutboundConnectionsPerEndpopint=”Integer” />  
</namedPipeTransport>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<namedPipeTransport\>의 \<connectionPoolSettings\>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|명명된 파이프 바인딩의 추가 연결 풀 설정을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<binding\>](../../../../../docs/framework/misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## 설명  
 이 전송은 "net.pipe:\/\/hostname\/path" 형식의 URI를 사용합니다.  다른 URI 구성 요소는 선택적입니다.  
  
 `namedPipeTransport` 요소는 명명된 파이프 전송 프로토콜을 구현하는 사용자 지정 바인딩을 만들기 위한 시작점입니다.  이 전송은 WCF\(Windows Communication Foundation\)와 WCF 사이의 컴퓨터 통신에 사용됩니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [전송](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [전송 선택](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)