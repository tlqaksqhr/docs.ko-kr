---
title: "&lt;filterTable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;filterTable&gt;
메시지를 평가할 필터 목록 및 필터가 true로 평가될 경우 메시지를 라우팅할 클라이언트 끝점을 포함하는 라우팅 테이블을 나타냅니다.  
  
## 구문  
  
```vb  
  
<routing>  
      <filterTables>  
        <filterTable name="String">  
          <entries>  
            <add backupList=”String”  
                 endpointName="String"   
                 filterName="String"   
                 priority="Integer" />  
          </entries>  
        </table>  
      </routingTables>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|요소|설명|  
|--------|--------|  
|name|이 구성 요소의 고유 이름을 포함하는 문자열입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<filters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<routing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|라우팅 테이블을 포함하는 구성 섹션입니다.|  
  
## 참고 항목  
 [System.ServiceModel.Routing.Configuration.RoutingSection](assetId:///System.ServiceModel.Routing.Configuration.RoutingSection?qualifyHint=False&amp;autoUpgrade=True)