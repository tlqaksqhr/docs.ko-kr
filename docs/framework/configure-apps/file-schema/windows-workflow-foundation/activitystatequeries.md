---
title: "&lt;activityStateQueries&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;activityStateQueries&gt;
워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.  예를 들어 워크플로 인스턴스 내에서 "전자 메일 보내기" 활동이 완료될 때마다 추적할 수 있습니다.  추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.  구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.  
  
 추적 프로필 쿼리에 대한 자세한 내용은 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)을 참조하세요.  
  
## 구문  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <activityStateQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
          </activityStateQueries>  
       </workflow>  
   </trackingProfile>  
</tracking>  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<activityStateQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리입니다.  이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<workflow\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|**activityDefinitionId** 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.|  
  
## 참고 항목  
 [System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection](assetId:///System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.ActivityStateQuery](assetId:///System.Activities.Tracking.ActivityStateQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)