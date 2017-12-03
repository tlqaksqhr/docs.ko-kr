---
title: '&lt;discoveryEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fae2f48b-a635-4e4b-859d-a1432ac37e1c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be4dc40327f7d1bfa713cefe80908cdba5bc7101
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltdiscoveryendpointgt"></a>&lt;discoveryEndpoint&gt;

이 구성 요소는 고정 검색 계약이 있는 표준 끝점을 정의합니다. 서비스 구성에 추가되면 검색 메시지를 수신하는 위치를 지정합니다. 클라이언트 구성에 추가되면 검색 쿼리를 보내는 위치를 지정합니다.  
  
\<system.serviceModel >  
\<d a r d >  
  
## <a name="syntax"></a>구문

```xml
<system.serviceModel>
  <standardEndpoints>
    <discoveryEndpoint>
      <standardEndpoint discoveryMode="Adhoc/Managed" 
                        discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxResponseDelay="Timespan" 
                        name="String" />
    </discoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성

| 특성        | 설명 |  
| ---------------- | ----------- |  
| discoveryMode    | 검색 프로토콜의 모드를 지정하는 문자열입니다. 유효한 값은 "Adhoc" 및 "Managed"입니다. 관리 모드에서는 프로토콜이 검색 가능한 서비스의 리포지토리로 작동하는 검색 프록시를 사용하고, 애드혹 모드에서는 프로토콜이 UDP 멀티캐스트 메커니즘을 사용하여 사용 가능한 서비스를 찾아야 합니다. 속성에 대 한 자세한 내용은 참조 하십시오. <xref:System.ServiceModel.Discovery.DiscoveryEndpoint.DiscoveryMode%2A>합니다. |  
| discoveryVersion | WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다. 유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다. 이 값은 <xref:System.ServiceModel.Discovery.DiscoveryVersion> 형식입니다. |  
| maxResponseDelay | 검색 프로토콜이 Probe Match 또는 Resolve Match 같은 특정 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다.<br /><br /> 모든 Probe Match가 동시에 전송되는 경우 네트워크 폭주가 발생할 수 있습니다. 이러한 현상이 발생하는 것을 방지하기 위해 각 Probe Match 사이에 임의의 지연 간격을 두고 Probe Match가 전송됩니다. 0에서 이 특성에 의해 설정되는 값까지의 범위 내에서 임의의 지연 간격이 설정됩니다. 이 특성이 0으로 설정되면 Probe Match 메시지가 지연 간격 없이 연속하여 전송됩니다. 그렇지 않으면 모든 Probe Match 메시지를 보내는 데 걸리는 총 시간이 maxResponseDelay를 초과하지 않는 범위 내에서 Probe Match 메시지가 약간의 임의의 지연 간격을 두고 전송됩니다. 이 값은 서비스에만 관련된 것으로 클라이언트에서 사용되는 값은 아닙니다. |  
| `name`           | 표준 끝점의 구성 이름을 지정하는 문자열입니다. 이 이름은 서비스 끝점의 `endpointConfiguration` 특성에서 표준 끝점을 해당 구성에 연결하기 위해 사용됩니다. |  
  
### <a name="child-elements"></a>자식 요소

없음  
  
### <a name="parent-elements"></a>부모 요소

| 요소 | 설명 |  
| ------- | ----------- |  
| [\<d a r d >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md) | 하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다. |  
  
## <a name="example"></a>예제

다음 예제에서는 피어 넷 멀티캐스트 전송을 통해 검색 메시지를 수신하는 서비스를 보여 줍니다. 이 예제에서는 WS-Discovery April 2005 버전을 명시적으로 지정합니다.  
  
표준 끝점 구성이 서비스별로 정의되고 서비스 간에 공유될 수 없습니다. 따라서 다른 서비스에서 동일한 검색 끝점을 사용하려는 경우 해당 서비스의 섹션에 동일한 구성을 추가해야 합니다.  
  
```xml
<services>  
  <service name="CalculatorService"
           behaviorConfiguration="CalculatorServiceBehavior">
    <endpoint binding="basicHttpBinding" 
              address="calculator" 
              contract="ICalculatorService" />  
    <endpoint name="peerNetDiscovery"  
              binding="peerTcpBinding"  
              address="net.p2p://discoveryMesh/multicast"  
              kind="discoveryEndpoint"  
              endpointConfiguration="peerTcpDiscoveryEndpointConfiguration"  
              bindingConfiguration="discoveryPeerTcpBindingConfig" />      
  </service>  
</services>  
<standardEndpoints>  
  <discoveryEndpoint>  
    <standardEndpoint name="peerTcpDiscoveryEndpointConfiguration"                         
                      version="WSDiscoveryApril2005" />  
  </discoveryEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a>참고 항목

<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>
