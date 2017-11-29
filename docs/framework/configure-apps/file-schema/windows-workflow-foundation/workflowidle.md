---
title: '&lt;workflowIdle&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5f9b4989de57204d9ec97d69475121c30ae82644
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowidlegt"></a>&lt;workflowIdle&gt;
유휴 워크플로 인스턴스가 언로드되고 유지되는 시간을 제어하는 서비스 동작입니다.  
  
\<시스템입니다. ServiceModel >  
\<동작 >  
\<serviceBehaviors >  
\<동작 >  
\<workflowIdle >  
  
## <a name="syntax"></a>구문  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|timeToPersist|워크플로가 유휴 상태가 되 고 유지 하는 시간 사이의 기간을 지정 하는 Timespan 값입니다. 기본값은 TimeSpan.MaxValue 합니다.<br /><br /> 워크플로 인스턴스가 유휴 상태가 되면 기간이 경과되기 시작합니다. 이 특성은 가능한 한 오랫동안 메모리에 인스턴스를 그대로 유지 하면서 워크플로 인스턴스를 적극적으로 유지 하려는 경우에 유용 합니다. 이 특성은 해당 값이 유효한만 보다 작은 **timeToUnload** 특성입니다. 이보다 크면 무시됩니다. 이 특성에 지정 된 값 되기 전에 경과 하는 경우는 **timeToUnload** 특성, 지 속성 워크플로가 언로드되기 전에 완료 해야 합니다. 이것은 워크플로가 유지될 때까지 언로드 작업이 지연될 수 있음을 의미합니다. 지속성 계층은 일시적인 오류가 발생할 경우 재시도를 처리하고 복구할 수 없는 오류가 발생하는 경우에만 예외를 throw하는 역할을 담당합니다. 따라서 유지 중에 throw되는 예외는 심각한 예외로 간주되며 워크플로 인스턴스가 중단됩니다.|  
|timeToUnload|워크플로가 유휴 상태가 되고 언로드되는 시간 간의 기간을 지정하는 Timespan 값입니다. 기본값은 1분입니다.<br /><br /> 워크플로를 언로드한다는 것은 이를 유지한다는 의미이기도 합니다. 이 특성은 워크플로 인스턴스가 유지 되 고 후 즉시 언로드됩니다 0으로 설정 하는 경우 워크플로가 유휴 상태가 됩니다. 언로드 작업이 해제 timespan.maxvalue 효과적으로이 특성을 설정 합니다. 즉, 유휴 워크플로 인스턴스가 언로드되지 않습니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >의 \<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|동작 요소를 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
