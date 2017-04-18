---
title: "&lt;extensions&gt; 섹션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;extensions&gt; 섹션
이 구성 섹션에는 사용자 정의 바인딩, 동작 및 확장의 기타 측면을 만들 수 있도록 하는 확장 컬렉션이 들어 있습니다.  
  
 \<system.ServiceModel\>  
  
## 구문  
  
```  
  
<system.serviceModel>  
    <extensions>  
      <bindingExtensions>  
      </bindingExtensions>  
      <behaviorExtensions>  
      </behaviorExtensions>  
      <bindingElementExtensions>  
      </bindingElementExtensions>  
      <endpointExtensions>  
      </endpointExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<behaviorExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviorextensions.md)|이 섹션에는 서비스 또는 끝점 동작을 사용자 지정할 수 있도록 하는 동작 확장을 지정하는 자식 요소가 포함됩니다.|  
|[\<bindingElementExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingelementextensions.md)|이 섹션은 시스템 또는 응용 프로그램 구성 파일의 사용자 지정 요소를 사용할 수 있도록 합니다.|  
|[\<bindingExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindingextensions.md)|이 섹션에는 바인딩을 사용자 지정할 수 있도록 하는 바인딩 확장을 지정하는 자식 요소가 포함되어 있습니다.|  
|[\<endpointExtensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointextensions.md)|이 섹션에는 표준 끝점을 등록하는 자식 요소가 포함됩니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|system.ServiceModel|모든 WCF 구성 요소의 루트 요소입니다.|