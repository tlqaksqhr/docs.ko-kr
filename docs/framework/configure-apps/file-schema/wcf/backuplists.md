---
title: "&lt;backupLists&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 593b3390-f65b-4684-ad40-0596b62f0954
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;backupLists&gt;
오류 처리에서 사용되는 백업 서비스 집합을 정의하기 위한 구성 섹션을 나타냅니다.  각 자식 요소는 라우팅 서비스에서 기본 끝점에 도달할 수 없을 때 사용할 수 있도록 할 끝점 집합을 열거하는 백업 목록입니다. 목록의 첫 번째 끝점이 다운되는 경우 라우팅 서비스는 자동으로 목록의 그다음 끝점으로 장애 조치\(failover\)됩니다. 따라서 이를 통해 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 응용 프로그램에 지정할 필요 없이 응용 프로그램의 안정성을 빠르게 강화할 수 있습니다.  
  
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
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)|라우팅 서비스에서 기본 끝점에 도달할 수 없을 때 사용할 수 있도록 할 끝점의 목록을 포함합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|들어오는 메시지 및 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의하는 라우팅 테이블을 평가할 때 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터 집합을 정의하기 위한 구성 섹션을 나타냅니다.|  
  
## 참고 항목  
 [System.ServiceModel.Routing.Configuration.BackupListCollection](assetId:///System.ServiceModel.Routing.Configuration.BackupListCollection?qualifyHint=False&amp;autoUpgrade=True)