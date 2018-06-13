---
title: WCF의 &lt;activityStateQuery&gt;
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 6d837946808e0d78e98c9c3010d4690fdfac6fa4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754586"
---
# <a name="ltactivitystatequerygt-of-wcf"></a>WCF의 &lt;activityStateQuery&gt;
워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리를 나타냅니다. 예를 들어 다음 워크플로 인스턴스 내에서 "전자 메일 보내기" 활동이 완료 될 때마다 추적 하는 것이 좋습니다. 추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다. 구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.  
  
 추적 프로필 쿼리에 대 한 자세한 내용은 참조 하십시오. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.  
  
 \<system.serviceModel>  
\<tracking>  
\<trackingProfile>  
\<workflow>  
\<activityStateQueries >  
\<activityStateQuery >  
  
## <a name="syntax"></a>구문  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|activityName|<xref:System.Activities.Tracking.ActivityStateRecord> 인스턴스를 필터링할 활동의 이름을 지정하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<인수 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|이 활동 쿼리와 연결되는 인수의 컬렉션입니다.|  
|[\<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.|  
|[\<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|이 활동 쿼리와 연결되는 변수의 컬렉션입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<faultPropagationQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다. 추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.|  
  
## <a name="remarks"></a>설명  
 ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다. 이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다. 사용할 수는 [ \<인수 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 및 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 임의의 변수 또는 인수를 추출 하는 요소 워크플로의 모든 활동입니다. 다음 예에서는 변수 및 인수를 추출 하는 활동 상태 쿼리 때 활동의 `Closed` 추적 레코드를 내보냅니다. ActivityStateRecord 사용해 서만 추출할 수 있으므로 구독 하는 추적 내에서 변수 및 인수를 사용 하 여 프로 파일링 [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)합니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>    
 <xref:System.Activities.Tracking.ActivityStateQuery>     
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
