---
title: "방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# 방법: WorkflowServiceHost를 사용하여 워크플로의 처리되지 않은 예외 동작 구성
<xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>는 <xref:System.ServiceModel.Activities.WorkflowServiceHost>에서 호스팅되는 워크플로 내에서 처리되지 않은 예외가 발생할 경우 수행할 작업을 지정할 수 있도록 하는 동작입니다.이 항목에서는 구성 파일에서 이 동작을 구성하는 방법을 보여 줍니다.  
  
### WorkflowUnhandledExceptionBehavior를 구성하려면  
  
1.  다음 예제와 같이 처리되지 않은 예외가 발생할 경우 수행할 작업을 지정하는 `action` 특성을 사용하여 \<`serviceBehaviors`\> 요소 내의 \<`behavior`\> 요소에 \<`workflowUnhandledException`\> 요소를 추가합니다.  
  
    ```  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    ```  
  
    > [!NOTE]
    >  위의 샘플에서 사용하는 구성은 단순화된 구성입니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][단순화된 구성](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     이 동작은 다음 예제와 같이 코드에서 구성할 수 있습니다.  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
  
    ```  
  
     \<`workflowUnhandledException`\> 요소의 `action` 특성은 다음 값 중 하나로 설정할 수 있습니다.  
  
     **abandon**  
     유지되는 인스턴스 상태를 변경하지 않고 메모리에서 인스턴스를 중단합니다. 즉, 마지막 유지 지점으로 롤백합니다.  
  
     **abandonAndSuspend**  
     메모리에서 인스턴스를 중단하고 유지되는 인스턴스가 일시 중단되도록 업데이트합니다.  
  
     **cancel**  
     인스턴스에 대한 취소 처리기를 호출하고 메모리에서 인스턴스를 완료합니다. 이 경우 인스턴스가 인스턴스 저장소에서 제거될 수도 있습니다.  
  
     **terminate**  
     메모리에서 인스턴스를 완료하고 인스턴스 저장소에서 제거합니다.  
  
     <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> [!INCLUDE[crabout](../../../../includes/crabout-md.md)] [워크플로 서비스 호스트 확장](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)을 참조하십시오.  
  
## 참고 항목  
 [워크플로 서비스 호스트 확장](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)   
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)