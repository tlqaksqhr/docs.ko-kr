---
title: "&lt;backupList&gt;의 &lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;backupList&gt;의 &lt;add&gt;
백업 끝점 요소를 정의하는 구성 요소를 나타냅니다.  
  
## 구문  
  
```vb  
  
<routing>  
  <backupLists>  
    <backupList name="String">  
      <add endpointName="String" />  
    </backupList>    
  </backupLists>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|백업 끝점의 이름을 지정하는 문자열입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|라우팅 서비스에서 기본 끝점에 도달할 수 없을 때 사용할 수 있도록 할 끝점의 목록을 포함합니다.|  
  
## 참고 항목  
 [System.ServiceModel.Routing.Configuration.BackupEndpointElement](assetId:///System.ServiceModel.Routing.Configuration.BackupEndpointElement?qualifyHint=False&amp;autoUpgrade=True)