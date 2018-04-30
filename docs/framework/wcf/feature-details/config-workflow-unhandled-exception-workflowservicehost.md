---
title: '방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a49b3d42e51ed7a0a57deb392f5728f407909b00
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a>방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에서 호스팅되는 워크플로 내에서 처리되지 않은 예외가 발생할 경우 수행할 작업을 지정할 수 있도록 하는 동작입니다. 이 항목에서는 구성 파일에서 이 동작을 구성하는 방법을 보여 줍니다.  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a>WorkflowUnhandledExceptionBehavior를 구성하려면  
  
1.  추가 <`workflowUnhandledException`> 요소에는 <`behavior`> 내에서 요소는 <`serviceBehaviors`> 요소를 사용 하 여는 `action` 특성 예제에 나와 있는 것 처럼 처리 되지 않은 예외가 발생할 때 수행할 동작을 지정 하 합니다.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  위의 샘플에서 사용하는 구성은 단순화된 구성입니다. 자세한 내용은 참조 [단순화 된 구성](../../../../docs/framework/wcf/simplified-configuration.md)합니다.  
  
     이 동작은 다음 예제와 같이 코드에서 구성할 수 있습니다.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     `action` 특성에는 <`workflowUnhandledException`> 요소는 다음 값 중 하나로 설정할 수 있습니다.  
  
     **중단**  
     유지되는 인스턴스 상태를 변경하지 않고 메모리에서 인스턴스를 중단합니다. 즉, 마지막 유지 지점으로 롤백합니다.  
  
     **abandonAndSuspend**  
     메모리에서 인스턴스를 중단하고 유지되는 인스턴스가 일시 중단되도록 업데이트합니다.  
  
     **cancel**  
     인스턴스에 대한 취소 처리기를 호출하고 메모리에서 인스턴스를 완료합니다. 이 경우 인스턴스가 인스턴스 저장소에서 제거될 수도 있습니다.  
  
     **terminate**  
     메모리에서 인스턴스를 완료하고 인스턴스 저장소에서 제거합니다.  
  
     에 대 한 자세한 내용은 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, 참조 [워크플로 서비스 호스트 확장명](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [워크플로 서비스 호스트 확장성](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)
