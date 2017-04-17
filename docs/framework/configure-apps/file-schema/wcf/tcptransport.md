---
title: "&lt;tcpTransport&gt; | Microsoft Docs"
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
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;tcpTransport&gt;
사용자 지정 바인딩에 대한 메시지를 전송하기 위해 채널이 사용할 수 있는 TCP 전송을 정의합니다.  
  
## 구문  
  
```  
  
<tcpTransport   
    listenBacklog="Integer"  
        portSharingEnabled="Boolean"  
    teredoEnabled="Boolean"  
    transferMode=”Buffered/Streamed”  
        <connectionPoolSettings  
          groupName=”String”  
        idleTimeout"TimeSpan"  
        leaseTimeout="TimeSpan"  
        maxOutboundConnectionsPerEndpopint=”Integer” />  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|channelInitializationTimeout|연결이 끊어지기 전에 채널이 초기화 상태를 유지할 수 있는 최대 시간\(초\)입니다.  이 할당량에는 TCP 연결이 .Net 메시지 프레이밍 프로토콜을 사용하여 자체 인증하는 데 걸릴 수 있는 시간이 포함됩니다.  서버가 인증을 수행하는 데 충분한 정보를 가지려면 클라이언트가 몇 가지 초기 데이터를 보내야 합니다.  기본값은 30초입니다.|  
|listenBacklog|웹 서비스에 대해 보류할 수 있는 최대 대기 중인 연결 요청 수입니다.  `connectionLeaseTimeout` 특성은 연결 예외가 throw되기 전에 클라이언트가 연결을 대기하는 시간을 제한합니다.  웹 서비스에 대해 보류할 수 있는 최대 대기 중인 연결 요청 수를 제어하는 소켓 수준 속성입니다.  ListenBacklog 값이 너무 낮으면 WCF는 요청 수락을 중지하므로 서버가 기존의 대기 중인 연결 일부를 인식할 때까지 새 연결을 삭제합니다. 기본값은 16 \* 프로세서 수입니다.|  
|portSharingEnabled|이 연결에서 TCP 포트 공유를 사용하는지를 지정하는 부울 값입니다.  이 값이 `false`이면 바인딩마다 자체 단독 포트가 사용됩니다.  기본값은 `false`입니다.<br /><br /> 이 설정은 서비스에만 적용되며,  클라이언트는 영향을 받지 않습니다.<br /><br /> 이 설정을 사용하려면 WCF\(Windows Communication Foundation\) TCP 포트 공유 서비스의 시작 유형을 수동 또는 자동으로 변경하여 서비스를 사용하도록 설정해야 합니다|  
|teredoEnabled|Teredo\(방화벽으로 보호되는 클라이언트의 주소를 지정하는 기술\)의 사용 여부를 지정하는 부울 값입니다.  기본값은 `false`입니다.<br /><br /> 이 속성은 내부 TCP 소켓에 대해 Teredo를 활성화합니다.  자세한 내용은 [Teredo 개요](http://go.microsoft.com/fwlink/?LinkId=95339)\(영문\)를 참조하세요.<br /><br /> 이 속성은 [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] 및 [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)]에만 적용됩니다.  [!INCLUDE[wv](../../../../../includes/wv-md.md)]에는 시스템 수준의 Teredo 구성 옵션이 있으므로 Vista를 실행할 경우 이 속성이 무시됩니다.  Teredo를 사용할 경우 클라이언트와 서비스 시스템 모두에 Microsoft IPv6 스택을 설치하고 Teredo 사용에 적합하도록 구성해야 합니다.  Teredo 구성에 대한 자세한 내용은 [Teredo 개요](http://go.microsoft.com/fwlink/?LinkId=95339)\(영문\)를 참조하세요.  자세한 내용은 [Windows Server 2003 기술 센터](http://go.microsoft.com/fwlink/?LinkId=49888)를 참조하세요.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<binding\>](../../../../../docs/framework/misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## 설명  
 이 전송은 "net.tcp:\/\/hostname:port\/path" 형식의 URI를 사용합니다.  다른 URI 구성 요소는 선택적입니다.  
  
 `tcpTransport` 요소는 TCP 전송 프로토콜을 구현하는 사용자 지정 바인딩을 만들기 위한 시작점입니다.  이 전송은 WCF와 WCF 사이의 통신을 위해 최적화됩니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.TcpTransportElement>   
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [전송](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [전송 선택](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [바인딩](../../../../../docs/framework/wcf/bindings.md)   
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)