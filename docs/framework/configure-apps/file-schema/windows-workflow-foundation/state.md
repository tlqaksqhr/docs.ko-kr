---
title: "&lt;state&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;state&gt;
추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.  
  
 추적 프로필 쿼리에 대한 자세한 내용은 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)을 참조하세요.  
  
## 구문  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <workflowInstanceQueries>  
             <workflowInstanceQuery>  
                <states>  
                   <state name="Name"/>  
                </states>  
            </workflowInstanceQuery>  
         </workflowInstanceQueries>  
       </workflow>  
   </trackingProfile>  
</tracking>  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태를 지정하는 문자열입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.|  
  
## 설명  
 반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.  
  
 가능한 상태 값은 다음 표에 설명되어 있습니다.  
  
|상태|설명|  
|--------|--------|  
|Aborted|워크플로 인스턴스가 중단되었습니다.|  
|Completed|워크플로 인스턴스가 완료되었습니다.|  
|삭제됨|워크플로 인스턴스가 삭제되었습니다.|  
|Idle|워크플로 인스턴스가 유휴 상태입니다.|  
|Persisted|워크플로 인스턴스가 지속되었습니다.|  
|Resumed|워크플로 인스턴스가 다시 시작되었습니다.|  
|Started|워크플로 인스턴스가 시작되었습니다.|  
|UnhandledException|워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.|  
|Unloaded|워크플로 인스턴스가 언로드되었습니다.|  
|Canceled|워크플로 인스턴스가 취소되었습니다.|  
|Suspended|워크플로 인스턴스가 일시 중단된 경우|  
|Terminated|워크플로 인스턴스가 종료됩니다.|  
|Unsuspended|워크플로 인스턴스의 일시 중단이 해제됩니다.|  
  
## 예제  
 다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.  
  
```  
  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
  
```  
  
## 참고 항목  
 [System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.ServiceModel.Activities.Tracking.Configuration.StateElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.StateElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.WorkflowInstanceQuery](assetId:///System.Activities.Tracking.WorkflowInstanceQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)