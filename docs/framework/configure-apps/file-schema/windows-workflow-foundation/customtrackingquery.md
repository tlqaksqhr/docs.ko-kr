---
title: "&lt;customTrackingQuery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;customTrackingQuery&gt;
코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.  추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.  
  
 추적 프로필 쿼리에 대한 자세한 내용은 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)을 참조하세요.  
  
## 구문  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
       </workflow>  
   </trackingProfile>  
</tracking>  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|activityName|추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.|  
|name|내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<customTrackingQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.|  
  
## 참고 항목  
 [System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection](assetId:///System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.CustomTrackingQuery](assetId:///System.Activities.Tracking.CustomTrackingQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)