---
title: "&lt;standardEndpoints&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;standardEndpoints&gt;
이 구성 섹션에서는 다시 사용할 수 있는 미리 구성된 끝점인 표준 끝점의 컬렉션을 정의할 수 있습니다.  표준 끝점에는 고정 값으로 설정된 하나 이상의 주소, 바인딩 및 계약 특성이 있습니다.  예를 들어 검색 끝점에서는 계약이 고정됩니다.  표준 끝점을 사용자 지정 바인딩 정의와 유사한 새 속성과 함께 사용하여 서비스 끝점을 확장할 수도 있습니다.  
  
 \<system.ServiceModel\>  
  
## 구문  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
  
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<announcementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|고정 알림 계약이 있는 표준 끝점을 정의합니다.  서비스에서는 선택적으로 서비스가 열리거나 닫힐 때 각각 온라인 및 오프라인 알림 메시지를 보내 가용성을 알릴 수 있습니다.  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스에서는 [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) 요소에서 알림 끝점을 지정하고 AnnouncementClient를 사용하여 알림을 수행합니다.  다른 서비스에서 알림을 수신하려는 클라이언트는 실제로 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스로 동작하므로 [\<services\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) 섹션에서 해당 클라이언트에 대한 알림 끝점을 구성해야 합니다.|  
|[\<discoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|고정 검색 계약이 있는 표준 끝점을 정의합니다.  서비스 구성에 추가되면 검색 메시지를 수신하는 위치를 지정합니다.  클라이언트 구성에 추가되면 검색 쿼리를 보내는 위치를 지정합니다.|  
|[\<dynamicEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/dynamicendpoint.md)|이 구성 요소는 응용 프로그램이 런타임에 끝점 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 끝점을 정의합니다.|  
|[\<mexEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/mexendpoint.md)|고정 IMetadataExchange 계약이 있는 표준 끝점을 정의합니다.  모든 메타데이터 교환 끝점이 IMetadataExchange를 계약으로 지정하므로 고유의 끝점을 정의하는 대신 이 표준 지점을 사용할 수 있습니다.|  
|[\<udpAnnoucementEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|서비스에서 UDP 바인딩을 통해 알림 메시지를 보내는 데 사용하는 표준 끝점을 정의합니다.  고정된 계약이 있으며 두 가지 버전의 검색을 지원합니다.  또한 WS\-Discovery 사양\(WS\-Discovery April 2005 또는 WS\-Discovery 버전 1.1\)에 지정된 고정된 UDP 바인딩 및 기본 주소 값이 있습니다.  알림 메시지를 보내고 받는 데 사용할 멀티캐스트 주소를 지정할 수 있습니다.|  
|[\<udpDiscoveryEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|UDP 멀티캐스트 바인딩을 통한 검색 작업에 대해 미리 구성된 표준 끝점을 정의합니다.  이 끝점에는 고정된 계약이 있으며 두 가지 버전의 WS\-Discovery 프로토콜을 지원합니다.  또한 WS\-Discovery 사양\(WS\-Discovery April 2005 또는 WS\-Discovery V1.1\)에 지정된 고정된 UDP 바인딩 및 기본 주소가 있습니다.|  
|[\<webHttpEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpendpoint.md)|[\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) 동작을 자동으로 추가하는 고정 [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 바인딩을 사용하여 표준 끝점을 정의합니다.  REST 서비스를 작성할 때는 이 끝점을 사용합니다.|  
|[\<webScriptEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webscriptendpoint.md)|[\<enableWebScript\>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) 동작을 자동으로 추가하는 고정 [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) 바인딩을 사용하여 표준 끝점을 정의합니다.  ASP.NET AJAX 응용 프로그램에서 호출되는 서비스를 기록할 때 이 끝점을 사용합니다.|  
|[\<workflowControlEndpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowcontrolendpoint.md)|워크플로 인스턴스의 실행\(만들기, 실행, 일시 중단, 종료 등\)을 제어하기 위한 표준 끝점을 정의합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|\<system.ServiceModel\>|모든 WCF 구성 요소의 루트 요소입니다.|  
  
## 참고 항목  
 [표준 끝점](../../../../../docs/framework/wcf/feature-details/standard-endpoints.md)