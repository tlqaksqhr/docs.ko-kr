---
title: "&lt;endpointBehaviors&gt;의 &lt;behavior&gt; | Microsoft Docs"
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
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# &lt;endpointBehaviors&gt;의 &lt;behavior&gt;
`behavior` 요소는 끝점의 동작에 대한 설정 컬렉션을 포함합니다.  각 동작은 해당 `name`으로 인덱싱됩니다.  끝점은 이 이름을 통해 각 동작에 연결할 수 있습니다.  [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.  기본 구성 및 이름 없는 바인딩 및 동작에 대한 자세한 내용은 [단순화된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)을 참조하세요.  
  
## 구문  
  
```  
  
<system.ServiceModel>  
  <behaviors>  
    <endpointBehaviors>  
       <behavior name="String" />  
    </endpointBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|동작의 구성 이름을 포함하는 고유 문자열입니다.  이 값은 요소의 식별 문자열 역할을 하므로 고유한 사용자 정의 문자열이어야 합니다.  [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.  기본 구성 및 이름 없는 바인딩 및 동작에 대한 자세한 내용은 [단순화된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스를 위한 단순화된 구성](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)을 참조하세요.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|클라이언트를 서비스에 인증하는 데 사용되는 자격 증명을 지정합니다.|  
|[\<callbackDebug\>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbackdebug.md)|[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 콜백 개체의 서비스 디버깅을 지정합니다.|  
|[\<callbackTimeouts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbacktimeouts.md)|클라이언트 콜백에 대한 제한 시간을 지정합니다.|  
|[\<clientVia\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientvia.md)|메시지가 이동할 경로를 지정합니다.|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer.md)|DataContractSerializer에 대한 구성 데이터가 들어 있습니다.|  
|[\<dispatcherSynchronization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/dispatchersynchronization.md)|서비스에서 응답을 비동기적으로 보낼 수 있도록 하는 끝점 동작을 지정합니다.|  
|[\<enableWebScript\>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)|ASP.NET AJAX 웹 페이지에서 서비스를 사용할 수 있게 하는 끝점 동작을 설정합니다.  이 동작은 \<webHttpBinding\> 표준 바인딩 또는 \<webMessageEncoding\> 바인딩 요소와 함께 사용해야 합니다.|  
|[\<endpointDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 끝점에 대한 다양한 검색 설정을 지정합니다.|  
|[\<soapProcessing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)|서로 다른 바인딩 형식과 메시지 버전 간에 메시지 마샬링을 위해 사용되는 클라이언트 끝점 동작을 정의합니다.|  
|[\<synchronousReceive\>](../../../../../docs/framework/configure-apps/file-schema/wcf/synchronousreceive-element.md)|서비스 또는 클라이언트 응용 프로그램에서 메시지 수신을 위한 런타임 동작을 지정합니다.  이 구성 요소에는 특성이나 자식 요소가 없습니다.|  
|[\<transactedBatching\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactedbatching.md)|받기 작업에 트랜잭션 일괄 처리가 지원되는지 여부를 지정합니다.|  
|[\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)|구성을 통해 끝점에서 WebHttpBehavior를 지정합니다.  이 동작을 \<webHttpBinding\> 표준 바인딩과 함께 사용할 경우 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스에서 웹 프로그래밍 모델을 사용할 수 있습니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<endpointBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|끝점 동작 요소의 컬렉션입니다.|