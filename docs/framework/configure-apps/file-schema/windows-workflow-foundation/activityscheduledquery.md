---
title: "&lt;activityScheduledQuery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;activityScheduledQuery&gt;
부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.  추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.  
  
 추적 프로필 쿼리에 대한 자세한 내용은 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)을 참조하세요.  
  
## 구문  
  
```vb  
  
<tracking>  
     <trackingProfile name="Name">  
       <workflow>  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
       </workflow>  
     </trackingProfile>  
</tracking>  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|activityName|취소를 요청하는 활동의 이름을 지정하는 문자열입니다.|  
|childActivityName|취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<activityScheduledQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.|  
  
## 참고 항목  
 [System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.ActivityScheduledQuery](assetId:///System.Activities.Tracking.ActivityScheduledQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)