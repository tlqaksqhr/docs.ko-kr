---
title: 쿼리에 주석 사용
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: 692bc965fb62996c205d4e3d1061d8483a4f652c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767052"
---
# <a name="using-annotation-in-queries"></a>쿼리에 주석 사용
주석을 사용하여 빌드 시간 후에 구성될 수 있는 값으로 추적 레코드에 임의 태그를 지정할 수 있습니다. 예를 들어 "Mail Server" 이라는 태그가 지정 되어야 하는 여러 워크플로에 걸쳐 여러 추적 레코드를 할 수 = = "Mail Server1"입니다. 이렇게 하면 나중에 추적 레코드를 쿼리할 때 이 태그를 사용하여 모든 레코드를 쉽게 찾을 수 있습니다.  
  
## <a name="adding-annotations"></a>주석 추가  
 다음 예제와 같이 추적 쿼리에 주석을 추가할 수 있습니다.  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
> [!NOTE]
>  이러한 추적 쿼리 요소를 사용하여 추적 프로필을 만들 수 있습니다. 추적 프로필은 구성이나 코드를 사용하여 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)  
 [워크플로 추적](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
