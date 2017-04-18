---
title: "방법: WorkflowServiceHost를 사용하여 지속성 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 방법: WorkflowServiceHost를 사용하여 지속성 구성
이 항목에서는 구성 파일을 사용하여 <xref:System.ServiceHost.Activities.WorkflowServiceHost>에 호스트된 워크플로에 대해 지속성을 사용하도록 SQL 워크플로 인스턴스 저장소 기능을 구성하는 방법에 대해 설명합니다.  SQL 워크플로 인스턴스 저장소 기능을 사용하려면 먼저 워크플로 인스턴스를 유지하는 데 사용되는 SQL 데이터베이스를 만들어야 합니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][방법: 워크플로 및 워크플로 서비스에 SQL 지속성 사용](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).  
  
### 구성에서 SQL 워크플로 인스턴스 저장소를 구성하려면  
  
1.  SQL 워크플로 인스턴스 저장소의 속성은 XML 구성을 통해 설정을 변경하는 데 사용할 수 있는 서비스 동작인 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>를 통해 구성할 수 있습니다.  다음 구성 예제에서는 구성 파일에서 \<`sqlWorkflowInstanceStore`\> 동작 요소를 사용하여 SQL 워크플로 인스턴스 저장소를 구성하는 방법을 보여 줍니다.  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore   
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"   
                 runnableInstancesDetectionPeriod="00:00:05">  
            <sqlWorkflowInstanceStore/>  
        </behavior>  
    </serviceBehaviors>  
  
    ```  
  
     SQL 워크플로 인스턴스 저장소를 구성하는 방법에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [방법: 워크플로 및 워크플로 서비스에 SQL 지속성 사용](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)을 참조하세요.  \<`sqlWorkflowInstanceStore`\> 동작 요소의 개별 설정[!INCLUDE[crabout](../../../../includes/crabout-md.md)]은 [SQL 워크플로 인스턴스 저장소](../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md)를 참조하세요.  Windows Server AppFabric에서는 자체적으로 지속성 저장소를 제공합니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Windows Server App Fabric 지속성](http://go.microsoft.com/fwlink/?LinkId=193121)  
  
    > [!NOTE]
    >  위의 예제에서 사용하는 구성은 단순화된 구성입니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [단순화된 구성](../../../../docs/framework/wcf/simplified-configuration.md)  
  
### 코드에서 SQL 워크플로 인스턴스 저장소를 구성하려면  
  
1.  SQL 워크플로 인스턴스 저장소의 속성은 코드를 통해 설정을 변경하는 데 사용할 수 있는 서비스 동작인 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>를 통해 구성할 수 있습니다.  다음 예제에서는 코드에서 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> 동작 요소를 사용하여 SQL 워크플로 인스턴스 저장소를 구성하는 방법을 보여 줍니다.  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     SQL 워크플로 인스턴스 저장소를 구성하는 방법에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [방법: 워크플로 및 워크플로 서비스에 SQL 지속성 사용](../../../../docs/framework/windows-workflow-foundation//how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)을 참조하세요.  <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> 동작 요소의 개별 설정에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [SQL 워크플로 인스턴스 저장소](../../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md)를 참조하세요.  Windows Server AppFabric에서는 자체적으로 지속성 저장소를 제공합니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Windows Server App Fabric 지속성](http://go.microsoft.com/fwlink/?LinkId=193121)  
  
    > [!NOTE]
    >  위의 예제에서 사용하는 구성은 단순화된 구성입니다.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [단순화된 구성](../../../../docs/framework/wcf/simplified-configuration.md)  
  
     프로그래밍 방식으로 지속성을 구성하는 방법에 대한 예제는 [방법: 워크플로 및 워크플로 서비스에 지속성 사용](../../../../docs/framework/windows-workflow-foundation//how-to-enable-persistence-for-workflows-and-workflow-services.md)을 참조하세요.  
  
## 참고 항목  
 [워크플로 서비스](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [워크플로 유지](../../../../docs/framework/windows-workflow-foundation//workflow-persistence.md)   
 [Windows Server App Fabric 지속성](http://go.microsoft.com/fwlink/?LinkId=193121)