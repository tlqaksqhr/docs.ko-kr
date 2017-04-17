---
title: "저장소 확장성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# 저장소 확장성
<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 사용하면 사용자가 지속성 데이터베이스의 인스턴스를 쿼리하는 데 사용할 수 있는 응용 프로그램별 사용자 지정 속성을 승격할 수 있습니다.속성을 승격하면 값을 데이터베이스의 특수 뷰 내에서 사용할 수 있습니다.사용자 쿼리에 사용할 수 있는 이러한 승격된 속성은 단순 형식\(예: Guid, String, DateTime 등\)이거나 serialize된 이진 형식\(byte\[\]\)일 수 있습니다.  
  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 클래스에는 속성을 쿼리에서 사용할 수 있는 속성으로 승격시키는 데 사용할 수 있는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> 메서드가 있습니다.다음은 저장소 확장에 대한 종단 간 예제입니다.  
  
1.  이 예제 시나리오에서 DP\(문서 처리\) 응용 프로그램에는 문서 처리를 위해 사용자 지정 활동을 사용하는 워크플로가 있습니다.이러한 워크플로에는 최종 사용자에게 표시되어야 하는 상태 변수 집합이 있습니다.이를 위해 DP 응용 프로그램은 활동에서 상태 변수를 제공하는 데 사용되는 <xref:System.Activities.Persistence.PersistenceParticipant> 형식의 인스턴스 확장을 제공합니다.  
  
    ```  
  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        public string DocumentId;  
        public string ApprovalStatus;  
        public string UserName;  
        public DateTime LastUpdateTime;  
    }  
  
    ```  
  
2.  그러면 호스트에 새 확장이 추가됩니다.  
  
    ```  
    static Activity workflow = CreateWorkflow();  
    WorkflowApplication application = new WorkflowApplication(workflow);  
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();  
    application.Extensions.Add(documentStatusExtension);  
  
    ```  
  
     사용자 지정 지속성 참가자를 추가하는 방법은 [지속성 참석자](../../../docs/framework/windows-workflow-foundation//persistence-participants.md) 샘플을 참조하십시오.  
  
3.  DP 응용 프로그램의 사용자 지정 활동은 **Execute** 메서드의 다양한 상태 필드를 채웁니다.  
  
    ```  
  
    public override void Execute(CodeActivityContext context)  
    {  
        // ...  
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();  
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";  
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = “Approved”;  
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();  
        // ...  
    }  
  
    ```  
  
4.  워크플로 인스턴스가 유지 지점에 도달하면 **DocumentStatusExtension** 지속성 참가자의 **CollectValues** 메서드가 이러한 속성을 지속성 데이터 컬렉션에 저장합니다.  
  
    ```  
  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        const XNamespace xNS = XNamespace.Get("http://contoso.com/DocumentStatus");  
  
        protected override void CollectValues(out IDictionary<XName, object> readWriteValues, out IDictionary<XName, object> writeOnlyValues)  
        {  
            readWriteValues = new Dictionary<XName, object>();  
            readWriteValues.Add(xNS.GetName("UserName"), this.UserName);  
            readWriteValues.Add(xNS.GetName("ApprovalStatus"), this.ApprovalStatus);  
            readWriteValues.Add(xNS.GetName("DocumentId"), this.DocumentId);  
            readWriteValues.Add(xNS.GetName("LastModifiedTime"), this.LastUpdateTime);  
  
            writeOnlyValues = null;  
        }  
        // ...  
    }  
  
    ```  
  
    > [!NOTE]
    >  이러한 모든 속성은 지속성 프레임워크에 의해 **SaveWorkflowCommand.InstanceData** 컬렉션을 통해 **SqlWorkflowInstanceStore**로 전달됩니다.  
  
5.  DP 응용 프로그램은 SQL 워크플로 인스턴스 저장소를 초기화하고 **Promote** 메서드를 호출하여 이 데이터를 승격시킵니다.  
  
    ```  
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);  
  
    List<XName> variantProperties = new List<XName>()   
    {   
        xNS.GetName("UserName"),   
        xNS.GetName("ApprovalStatus"),   
        xNS.GetName("DocumentId"),   
        xNS.GetName("LastModifiedTime")   
    };  
  
    store.Promote("DocumentStatus", variantProperties, null);  
    ```  
  
     이 승격 정보를 기반으로 **SqlWorkflowInstanceStore**는 [[System.Activities.DurableInstancing.InstancePromotedProperties] 뷰](../Topic/Store%20Extensibility.md#InstancePromotedProperties)의 열에 데이터 속성을 배치합니다.  
  
6.  승격 테이블에서 데이터 하위 집합을 쿼리하기 위해 DP 응용 프로그램은 승격 뷰의 맨 위에 사용자 지정된 뷰를 추가합니다.  
  
    ```  
  
    create view [dbo].[DocumentStatus] with schemabinding  
    as  
        select  P.[InstanceId] as [InstanceId],  
            P.Value1 as [UserName],  
            P.Value2 as [ApprovalStatus],  
            P.Value3 as [DocumentId],  
            P.Value4 as [LastUpdatedTime]  
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P  
    where P.PromotionName = N'DocumentStatus'  
    go  
  
    ```  
  
##  <a name="InstancePromotedProperties"></a> \[System.Activities.DurableInstancing.InstancePromotedProperties\] 뷰  
  
|열 이름|열 유형|설명|  
|----------|----------|--------|  
|InstanceId|GUID|이 승격이 속하는 워크플로 인스턴스입니다.|  
|PromotionName|nvarchar\(400\)|승격 자체의 이름입니다.|  
|Value1, Value2, Value3,..,Value32|sql\_variant|승격된 속성 자체의 값입니다.길이가 8000바이트를 초과하는 이진 BLOB와 문자열을 제외한 대부분의 SQL 기본 데이터 형식이 sql\_variant에 저장될 수 있습니다.|  
|Value33, Value34, Value35, …, Value64|varbinary\(max\)|varbinary\(max\)로 명시적으로 선언되는 승격된 속성의 값입니다.|