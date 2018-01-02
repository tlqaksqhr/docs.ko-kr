---
title: '&lt;announcementEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034b7c69-a770-4502-8cef-38007bbcd025
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ae03b5d4a82c08978a3456e80428ba6ad8ac532a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltannouncementendpointgt"></a>&lt;announcementEndpoint&gt;
이 구성 요소는 고정 알림 계약이 있는 표준 끝점을 정의합니다. 서비스에서는 선택적으로 서비스가 열리거나 닫힐 때 각각 온라인 및 오프라인 알림 메시지를 보내 가용성을 알릴 수 있습니다. A [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 에 알림 끝점을 지정 하는 서비스는 [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) 공지를 수행 하려면 AnnouncementClient 사용 하 여 요소입니다. 다른 서비스에서 알림 역할을 실제로 수신 하려는 클라이언트는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ; 서비스를 해당 클라이언트에 대 한 알림 끝점을 구성 해야 하므로 [ \<서비스 >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 섹션.  
  
\<시스템입니다. ServiceModel >  
\<d a r d >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <announcementEndpoint>
      <standardEndpoint discoveryVersion="WSDiscovery11/WSDiscoveryApril2005" 
                        maxAnnouncementDelay="Timespan" 
                        name="String" />
    </announcementEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|discoveryVersion|WS-Discovery 프로토콜의 두 버전 중 하나를 지정하는 문자열입니다. 유효한 값은 WSDiscovery11 및 WSDiscoveryApril2005입니다. 이 값은 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion> 형식입니다.|  
|maxAnnouncementDelay|검색 프로토콜이 Hello 메시지가 전송될 때까지 대기하는 최대 지연 값을 지정하는 Timespan 값입니다. 메시지는 전송되기 전에 0에서 이 특성에 지정된 값 사이의 임의 시간 값 동안 대기합니다. 이 특성은 네트워크에 장애가 발생했다가 모든 서비스가 동시에 온라인 상태로 복구되는 경우에 네트워크 폭주가 발생하는 것을 방지하기 위해 임의의 짧은 지연 간격을 설정하기 위해 사용합니다.|  
|name|표준 끝점의 구성 이름을 지정하는 문자열입니다. 이 이름은 서비스 끝점의 `endpointConfiguration` 특성에서 표준 끝점을 해당 구성에 연결하기 위해 사용됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<d a r d >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.|  
  
## <a name="example"></a>예  
 다음 예제에서는 http 및 peernet을 통해 알림 메시지를 수신하는 클라이언트를 보여 줍니다.  
  
```xml  
<services>  
  <service name="ServiceAnnouncementListener">  
    <endpoint name="httpAnnouncementEndpoint"  
              kind="announcementEndpoint"  
              binding="basicHttpBinding"  
              address="announcements" />  
    <endpoint name="peerNetAnnouncementEndpoint"  
              kind="announcementEndpoint"  
              binding="peerTcpBinding"  
              address="net.p2p://discoveryMesh/multicast"  
              bindingConfiguration="discoveryPeerTcpBindingConfig" />  
  ...  
  </service>  
</services>  
  
<standardEndpoints>  
  <announcementEndpoint>  
    <standardEndpoint name="httpAnnouncementEndpoint"                         
                      version="WSDiscoveryApril2005" />  
    <standardEndpoint name="peerNetAnnouncementEndpoint"                         
                      version="WSDiscoveryApril2005" />  
   </announcementEndpoint>  
</standardEndpoints>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Discovery.AnnouncementEndpoint>
