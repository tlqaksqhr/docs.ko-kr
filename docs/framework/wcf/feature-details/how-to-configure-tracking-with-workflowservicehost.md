---
title: '방법: WorkflowServiceHost를 사용하여 추적 구성'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e1de3349bb9766beeee95b9934fc1ca11fc7006f
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a>방법: WorkflowServiceHost를 사용하여 추적 구성
이 항목에서는 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]에서 호스트되는 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 워크플로에 대해 추적을 구성하는 방법에 대해 설명합니다. 이러한 추적 기능은 Web.config 파일에서 서비스 동작을 지정하여 구성됩니다.  
  
### <a name="configure-tracking-in-configuration"></a>구성에서 추적 구성  
  
1.  다음 예제와 같이 구성 파일에서 <<xref:System.Activities.Tracking.EtwTrackingParticipant>> 요소를 사용하여 `behavior`를 추가합니다.  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
    ```  
  
    > [!NOTE]
    >  위의 샘플에서 사용하는 구성은 단순화된 구성입니다. 자세한 내용은 참조 [단순화 된 구성](../../../../docs/framework/wcf/simplified-configuration.md)합니다.  
  
     위의 구성 샘플에서는 <xref:System.Activities.Tracking.EtwTrackingParticipant>를 추가하고 추적 프로필 이름을 지정합니다. 추적 프로필은 <`trackingProfile`> 요소 내의 <`tracking`> 요소에 만들어집니다. 추적 프로필에는 추적 참가자가 런타임에 워크플로 인스턴스 상태가 변경될 때 발생하는 워크플로 이벤트를 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다. 다음 예제에서는 추적 프로필을 만드는 방법을 보여 줍니다.  
  
    ```xml  
    <system.serviceModel>  
        <tracking>   
         <trackingProfile name="Sample Tracking Profile">  
            <workflow activityDefinitionId="*">  
               <workflowInstanceQueries>  
                 <workflowInstanceQuery>  
                    <states>  
                       <state name="Started"/>  
                       <state name="Completed"/>  
                    </states>  
                </workflowInstanceQuery>  
             </workflowInstanceQueries>  
           </workflow>  
         </trackingProfile>   
       </tracking>  
    </system.serviceModel>  
    ```  
  
     추적 프로필에 대 한 자세한 내용은 참조 [추적 프로필](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.  
  
     일반적으로 추적 하는 방법에 대 한 자세한 내용은 참조 [워크플로 추적 및 트레이싱](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)합니다.  
  
### <a name="configure-tracking-in-code"></a>코드에서 추적 구성  
  
1.  다음 예제와 같이 코드에서 <xref:System.Activities.Tracking.EtwTrackingParticipant> 동작을 사용하여 <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>를 추가합니다.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     위의 코드 샘플에서는 <xref:System.Activities.Tracking.EtwTrackingParticipant>를 추가하고 추적 프로필 이름을 지정합니다. 추적 프로필은 이전 단원에 표시된 것과 같이 <`trackingProfile`> 요소 내의 <`tracking`> 요소에 만들어집니다.  
  
     추적 프로필에 대 한 자세한 내용은 참조 [추적 프로필](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.  
  
     일반적으로 추적 하는 방법에 대 한 자세한 내용은 참조 [워크플로 추적 및 트레이싱](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)합니다. 프로그래밍 방식으로 추적 구성의 예에 대 한 참조 [워크플로에 대 한 추적 구성](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WCF 서비스를 위한 단순화된 구성](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [추적 프로필](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
