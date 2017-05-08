---
title: "&lt;scopes&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9a0dd3ce-e383-4ac3-b7be-7d604388304a
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;scopes&gt;
쿼리 중에 서비스 끝점을 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.  
  
## 구문  
  
```  
  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="String">  
      <endpointDiscovery enable="Boolean">  
        <scopes>  
          <add scope="URI"/>  
        </scopes>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|특성|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-scopes.md)|서비스를 찾기 위한 일치 기준으로 사용할 수 있는 끝점의 범위 정보를 추가합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<endpointDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 끝점에 대한 다양한 검색 설정을 지정합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>