---
title: "&lt;webSocketSettings&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;webSocketSettings&gt;
WebSocket 설정을 지정하는 데 사용되는 구성 요소입니다.  
  
## 구문  
  
```  
  
<netHttpBinding>  
   <binding>   
       <webSocketSettings createNotificationOnConnection="boolean"  
                              disablePayloadMasking="boolean"  
                              keepAliveInterval="TimeSpan"  
                              maxPendingConnections="Integer"  
                              receiveBufferSize="Integer"  
                              sendBufferSize="Integer"  
                              subProtocol="String"  
                              transportUsage="WhenDuplex/Always/Never"/>  
   </binding>  
</netHttpBinding>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|createNotificationOnConnection|연결 시 알림이 보내지는지 여부를 지정합니다.|  
|disablePayloadMasking|WebSocket 마스킹을 사용하지 않도록 설정할지 여부를 지정합니다.|  
|keepAliveInterval|상태 유지 간격을 지정합니다.|  
|maxPendingConnections|서비스에서 디스패치를 대기하는 최대 연결 수를 지정합니다.|  
|receiveBufferSize|수신 버퍼의 크기를 지정합니다.|  
|sendBufferSize|전송 버퍼의 크기를 지정합니다.|  
|subProtocol|WebSocket 하위 프로토콜을 지정합니다.|  
|transportUsage|WebSocket을 사용할 시기를 지정합니다.|  
  
## transportUsage 특성  
  
|값|설명|  
|-------|--------|  
|WhenDuplex|이중 계약인 경우 WebSocket 프로토콜을 사용합니다.|  
|Always|계약과 관계없이 항상 WebSocket 프로토콜을 사용합니다.|  
|Never|WebSocket 프로토콜을 사용하지 않습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|\<netHttpBinding\>|NetHttpBinding을 지정합니다.|  
  
## 예제  
 다음 예제에서는 \<webSocketSettings\> 요소를 사용하는 방법을 보여 줍니다.  
  
```xml  
<netHttpBinding>  
        <binding>  
          <webSocketSettings createNotificationOnConnection="true"  
                              disablePayloadMasking="false  
                              keepAliveInterval="00:10:00"  
                              maxPendingConnections="100"  
                              receiveBufferSize="1000"  
                              sendBufferSize="1000"  
                              subProtocol="Soap"  
                              transportUsage="WhenDuplex/Always/Never"/>  
  
        </binding>  
      </netHttpBinding>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.Binding>   
 <xref:System.ServiceModel.Channels.BindingElement>   
 <xref:System.ServiceModel.BasicHttpBinding>   
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [시스템 제공 바인딩 구성](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ko-kr/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<binding\>](../../../../../docs/framework/misc/binding.md)