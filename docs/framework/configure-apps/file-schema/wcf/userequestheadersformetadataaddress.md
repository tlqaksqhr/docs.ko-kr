---
title: "&lt;useRequestHeadersForMetadataAddress&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;useRequestHeadersForMetadataAddress&gt;
요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.  
  
## 구문  
  
```  
  
<useRequestHeadersForMetadataAddress>  
   <defaultPorts>  
      <add scheme="http" port="integer" />  
   </defaultPorts>  
</useRequestHeadersForMetadataAddress>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<defaultPorts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|클라이언트 응용 프로그램에서 수신하는 기본 통신 끝점을 나열하는 기본 포트의 컬렉션입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<behavior\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|동작 요소를 지정합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>