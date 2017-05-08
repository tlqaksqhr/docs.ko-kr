---
title: "&lt;services&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;services&gt;
서비스는 구성 파일의 `services` 섹션에 정의됩니다.  서비스별로 해당 `service` 구성 섹션이 있습니다.  
  
 \<system.ServiceModel\>  
  
## 구문  
  
```  
  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<service\>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|특정 서비스의 서비스 계약, 동작 및 끝점을 정의합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|모든 WCF\(Windows Communication Foundation\) 구성 요소의 루트 요소입니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.ServicesSection>