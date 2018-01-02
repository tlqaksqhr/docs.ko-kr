---
title: "&lt;tcpTransport&gt;의 &lt;connectionPoolSettings&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0e9c4d34caa16f41e874b7a3880325a6585c230
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltconnectionpoolsettingsgt-of-lttcptransportgt"></a>&lt;tcpTransport&gt;의 &lt;connectionPoolSettings&gt;
TCP 전송에 대한 추가 연결 풀 설정을 지정합니다.  
  
 \<system.serviceModel >  
\<바인딩 >  
\<customBinding >  
\<바인딩 >  
\<tcpTransport >  
\<connectionPoolSettings >  
  
## <a name="syntax"></a>구문  
  
```xml  
<connectionPoolSettings  
    groupName="String"  
    idleTimeout"TimeSpan"  
        leaseTimeout="TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`groupName`|나가는 채널에 사용되는 연결 풀의 이름을 정의하는 문자열입니다. 스트리밍 모드에서는 연결이 공유되지 않습니다. 즉 연결 풀링이 사용되지 않습니다. 기본값은 "default" 문자열입니다. 이 값을 수정하여 특정 클라이언트의 연결을 별도의 그룹으로 격리할 수 있습니다.|  
|`idleTimeout`|연결이 끊어지기 전에 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다. 기본값은 00:02:00입니다.|  
|`leaseTimeout`|활성 연결이 종료되는 유휴 시간을 지정하는 <xref:System.TimeSpan>입니다. 기본값은 00:05:00입니다.<br /><br /> 활성 전송 중이 아니라 연결 캐시로 돌아온 후에 연결이 닫힙니다. TCP 전송에 사용되는 연결 캐시는 `maxOutboundConnectionsPerEndpoint.`로 설정된 캐시 제한까지 각 끝점에 필요한 새 연결을 만듭니다.|  
|`maxOutboundConnectionsPerEndpoint`|서비스에서 시작된 원격 끝점과의 최대 연결 수를 지정하는 양의 정수 값입니다. 이 제한을 초과하는 연결은 채널 수가 제한 아래로 내려갈 때까지 큐에 대기됩니다. `idleTimeout`은 예외가 throw되기 전에 연결이 큐에 대기할 수 있는 시간을 제한합니다. 기본값은 10입니다.<br /><br /> 이 특성은 클라이언트에서 특정 서비스 끝점으로의 동시 활성 연결 수를 제한합니다. 활성 클라이언트 연결 수가 이 값을 초과할 경우 해당 서비스가 클라이언트에 응답하지 않는 것처럼 보일 수 있습니다. 이러한 경우 이 값을 특정 끝점에 대해 예상되는 동시 클라이언트 최대 연결 수보다 크게 조정해야 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<namedPipeTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|채널이 명명된 파이프를 사용하여 메시지를 전송하게 하는 전송을 정의합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [전송](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [전송 선택](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
