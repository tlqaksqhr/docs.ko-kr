---
title: "&lt;activityStateQuery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;activityStateQuery&gt;
워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리를 나타냅니다.  예를 들어 워크플로 인스턴스 내에서 "전자 메일 보내기" 활동이 완료될 때마다 추적할 수 있습니다.  추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.  구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.  
  
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
  
|특성|설명|  
|--------|--------|  
|activityName|<xref:System.Activities.Tracking.ActivityStateRecord> 인스턴스를 필터링할 활동의 이름을 지정하는 문자열입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|이 활동 쿼리와 연결되는 인수의 컬렉션입니다.|  
|[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.|  
|[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|이 활동 쿼리와 연결되는 변수의 컬렉션입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<faultPropagationQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.  추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.|  
  
## 설명  
 ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.  이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.   [\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 및 [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 요소를 사용하여 워크플로의 모든 활동에서 변수 또는 인수를 추출할 수 있습니다. 다음 예제에서는 활동의 `Closed` 추적 레코드를 내보낼 때 변수 및 인수를 추출하는 활동 상태 쿼리를 보여 줍니다.  변수 및 인수는 ActivityStateRecord를 사용해서만 추출할 수 있으므로 [\<activityStateQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)를 사용하여 추적 프로필 내에서 구독합니다.  
  
```  
  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
  
```  
  
## 참고 항목  
 [System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.ActivityStateQuery](assetId:///System.Activities.Tracking.ActivityStateQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)