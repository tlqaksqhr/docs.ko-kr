---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 652cb551fb318d43d4284dbee48aeb994f056692
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746799"
---
# <a name="ltnamedpipetransportgt"></a>&lt;namedPipeTransport&gt;
사용자 지정 바인딩에 포함될 때 채널에서 명명된 파이프를 사용하여 메시지를 전송하도록 정의합니다.  
  
\<system.serviceModel>  
\<바인딩 >  
\<customBinding>  
\<바인딩 >  
\<namePipeTransport >  
  
## <a name="syntax"></a>구문  
  
```xml
<namedPipeTransport channelInitializationTimeout="TimeSpan"   
                    connectionBufferSize="Integer"   
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"  
                    manualAddressing="Boolean"   
                    maxBufferPoolSize="Integer"  
                    maxBufferSize="Integer"  
                    maxOutputDelay="TimeSpan"  
                    maxPendingAccepts="Integer"   
                    maxPendingConnections="Integer"  
                    maxReceivedMessageSize="Integer"   
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">  
  <connectionPoolSettings groupName="String" 
                          idleTimeout"TimeSpan"  
                          maxOutboundConnectionsPerEndpopint="Integer" />  
</namedPipeTransport>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|ChannelInitializationTimeout|가져오거나는 <xref:System.TimeSpan> 연결이 끊어지기 전에 채널 초기화 상태를 유지할 수 있는 최대 시간을 결정 하는 합니다.|  
|ConnectionBufferSize|통신 중에 클라이언트나 서비스로부터 serialize된 메시지 청크를 전송할 때 사용되는 버퍼의 크기를 가져오거나 설정합니다.|  
|hostNameComparisonMode|URI 비교 시 서비스에 액세스하는 데 호스트 이름이 사용되는지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|manualAddressing|메시지의 주소를 수동으로 지정해야 하는지 여부를 나타내는 값을 가져오거나 설정합니다.|  
|maxBufferPoolSize|바이트는 전송에서 사용할 수 있는 버퍼 풀의 최대 크기를 가져오거나 설정 합니다.|  
|maxBufferSize|사용할 버퍼의 최대 크기를 가져오거나 설정합니다. 스트리밍된 메시지의 경우 이 값은 버퍼링된 모드에서 읽어오는 메시지 헤더의 최대 예상 크기 이상이어야 합니다.|  
|maxOutputDelay|메시지 청크 또는 전체 메시지를 보내기 전에 메모리에 버퍼링된 상태로 유지할 수 있는 최대 시간 간격을 가져오거나 설정합니다.|  
|maxPendingAccepts|서비스는 서비스에 대 한 들어오는 연결 처리에 대 한 수신기에서 대기 시킬 수 채널의 최대 수를 가져오거나 설정 합니다.|  
|maxPendingConnections|서비스에서 디스패치를 대기하는 최대 연결 수를 가져오거나 설정합니다.|  
|maxReceivedMessageSize|가져오고 (바이트)을 받을 수 있는 최대 메시지 크기를 설정 합니다.|  
|transferMode|메시지가 연결 지향 전송을 사용하여 버퍼링되는지 아니면 스트리밍되는지를 나타내는 값을 가져오거나 설정합니다.|  
|[\<connectionPoolSettings >의 \<namedPipeTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|명명된 파이프 바인딩의 추가 연결 풀 설정을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.|  
  
## <a name="remarks"></a>설명  
이 전송은 "net.pipe://hostname/path" 형식의 URI를 사용합니다. 다른 URI 구성 요소는 선택적입니다.  
  
`namedPipeTransport` 요소는 명명된 파이프 전송 프로토콜을 구현하는 사용자 지정 바인딩을 만들기 위한 시작점입니다. 이 전송은 WCF(Windows Communication Foundation)와 WCF 사이의 컴퓨터 통신에 사용됩니다.  
  
## <a name="see-also"></a>참고 항목  
<xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
<xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
<xref:System.ServiceModel.Channels.TransportBindingElement>   
<xref:System.ServiceModel.Channels.CustomBinding>   
[전송](../../../../../docs/framework/wcf/feature-details/transports.md)   
[전송 선택](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
[바인딩](../../../../../docs/framework/wcf/bindings.md)   
[바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
[사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
[\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
