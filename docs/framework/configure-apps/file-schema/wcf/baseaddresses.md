---
title: "&lt;baseAddresses&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;baseAddresses&gt;
자체 호스팅 환경의 서비스 호스트에 대한 기준 주소인 `baseAddress` 요소의 컬렉션을 나타냅니다.  기준 주소가 있는 경우 기준 주소에 대한 상대 주소로 끝점을 구성할 수 있습니다.  
  
## 구문  
  
```  
  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## 형식  
 `Type`  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<host\>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|서비스 호스트의 설정을 지정하는 구성 요소입니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.HostElement>   
 <xref:System.ServiceModel.ServiceHost>   
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>   
 [호스팅](../../../../../docs/framework/wcf/feature-details/hosting.md)