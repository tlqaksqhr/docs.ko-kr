---
title: "WCF의 &lt;faultPropagationQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f017b695b91a08c1126b48c944977c054c73affe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a>WCF의 &lt;faultPropagationQuery&gt;
활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리를 나타냅니다.  이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다. 활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다. 추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.  
  
 추적 프로필 쿼리에 대 한 자세한 내용은 참조 하십시오. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.  
  
 \<system.serviceModel >  
\<추적 >  
\<trackingProfile >  
\<워크플로 >  
\<faultPropagationQueries >  
\<faultPropagationQuery >  
  
## <a name="syntax"></a>구문  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|activityName|오류를 전파하는 오류 처리 활동의 이름을 지정하는 문자열입니다. 기본값은 *이며, 이는 모든 활동에 대해 오류 전파 레코드가 반환된다는 것을 나타냅니다.|  
|faultHandlerActivityName|오류의 출처인 활동의 이름을 지정하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<faultPropagationQueries >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 구성 요소 목록을 나타냅니다.  이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
