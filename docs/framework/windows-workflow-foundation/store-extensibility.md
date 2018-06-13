---
title: 저장소 확장성
ms.date: 03/30/2017
ms.assetid: 7c3f4a46-4bac-4138-ae6a-a7c7ee0d28f5
ms.openlocfilehash: 8cfbf96256d4b8416beb526875a1e9ac09c3bfbb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517922"
---
# <a name="store-extensibility"></a><span data-ttu-id="62d6b-102">저장소 확장성</span><span class="sxs-lookup"><span data-stu-id="62d6b-102">Store Extensibility</span></span>
<span data-ttu-id="62d6b-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>를 사용하면 사용자가 지속성 데이터베이스의 인스턴스를 쿼리하는 데 사용할 수 있는 응용 프로그램별 사용자 지정 속성을 승격할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-103"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> allows users to promote custom, application-specific properties that can be used to query for instances in the persistence database.</span></span> <span data-ttu-id="62d6b-104">속성을 승격하면 값을 데이터베이스의 특수 뷰 내에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-104">The act of promoting a property causes the value to be available within a special view in the database.</span></span> <span data-ttu-id="62d6b-105">사용자 쿼리에 사용할 수 있는 이러한 승격된 속성은 단순 형식(예: Guid, String, DateTime 등)이거나 serialize된 이진 형식(byte[])일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-105">These promoted properties (properties that can be used in user queries) can be of simple types such as Int64, Guid, String, and DateTime or of a serialized binary type (byte[]).</span></span>  
  
 <span data-ttu-id="62d6b-106"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 클래스에는 속성을 쿼리에서 사용할 수 있는 속성으로 승격시키는 데 사용할 수 있는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-106">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> class has the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore.Promote%2A> method that you can use to promote a property as a property that can be used in queries.</span></span> <span data-ttu-id="62d6b-107">다음은 저장소 확장에 대한 종단 간 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-107">The following example is an end-to-end example of store extensibility.</span></span>  
  
1.  <span data-ttu-id="62d6b-108">이 예제 시나리오에서 DP(문서 처리) 응용 프로그램에는 문서 처리를 위해 사용자 지정 활동을 사용하는 워크플로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-108">In this example scenario, a document processing (DP) application has workflows, each of which uses custom activities for document processing.</span></span> <span data-ttu-id="62d6b-109">이러한 워크플로에는 최종 사용자에게 표시되어야 하는 상태 변수 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-109">These workflows have a set of state variables that need to be made visible to the end user.</span></span> <span data-ttu-id="62d6b-110">이를 위해 DP 응용 프로그램은 활동에서 상태 변수를 제공하는 데 사용되는 <xref:System.Activities.Persistence.PersistenceParticipant> 형식의 인스턴스 확장을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-110">To achieve this, the DP application provides an instance extension of type <xref:System.Activities.Persistence.PersistenceParticipant>, which is used by activities to supply the state variables.</span></span>  
  
    ```  
    class DocumentStatusExtension : PersistenceParticipant  
    {  
        public string DocumentId;  
        public string ApprovalStatus;  
        public string UserName;  
        public DateTime LastUpdateTime;  
    }  
    ```  
  
2.  <span data-ttu-id="62d6b-111">그러면 호스트에 새 확장이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-111">The new extension is then added to the host.</span></span>  
  
    ```  
    static Activity workflow = CreateWorkflow();  
    WorkflowApplication application = new WorkflowApplication(workflow);  
    DocumentStatusExtension documentStatusExtension = new DocumentStatusExtension ();  
    application.Extensions.Add(documentStatusExtension);  
    ```  
  
     <span data-ttu-id="62d6b-112">사용자 지정 지 속성 참가자를 추가 하는 방법에 대 한 자세한 내용은 참조는 [지 속성 참가자](../../../docs/framework/windows-workflow-foundation/persistence-participants.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="62d6b-112">For more details about adding a custom persistence participant, see the [Persistence Participants](../../../docs/framework/windows-workflow-foundation/persistence-participants.md) sample.</span></span>  
  
3.  <span data-ttu-id="62d6b-113">DP 응용 프로그램의 사용자 지정 활동의 다양 한 상태 필드를 채우는 **Execute** 메서드.</span><span class="sxs-lookup"><span data-stu-id="62d6b-113">The custom activities in the DP application populate various status fields in the **Execute** method.</span></span>  
  
    ```  
    public override void Execute(CodeActivityContext context)  
    {  
        // ...  
        context.GetExtension<DocumentStatusExtension>().DocumentId = Guid.NewGuid();  
        context.GetExtension<DocumentStatusExtension>().UserName = "John Smith";  
        context.GetExtension<DocumentStatusExtension>().ApprovalStatus = "Approved";  
        context.GetExtension<DocumentStatusExtension>().LastUpdateTime = DateTime.Now();  
        // ...  
    }  
    ```  
  
4.  <span data-ttu-id="62d6b-114">워크플로 인스턴스가 유지 지점에 도달 하면는 **CollectValues** 의 메서드는 **DocumentStatusExtension** 지 속성 참석자는 지 속성 데이터에 이러한 속성을 저장 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-114">When a workflow instance reaches a persistence point, the **CollectValues** method of the **DocumentStatusExtension** persistence participant saves these properties into the persistence data collection.</span></span>  
  
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
    >  <span data-ttu-id="62d6b-115">이러한 모든 속성에 전달 되 **SqlWorkflowInstanceStore** 통해 지 속성 프레임 워크에 의해는 **SaveWorkflowCommand.InstanceData** 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-115">All these properties are passed to **SqlWorkflowInstanceStore** by the persistence framework through the **SaveWorkflowCommand.InstanceData** collection.</span></span>  
  
5.  <span data-ttu-id="62d6b-116">DP 응용 프로그램은 SQL 워크플로 인스턴스 저장소를 초기화 하 고 호출에서 **승격** 이 데이터를 승격 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="62d6b-116">The DP application initializes the SQL Workflow Instance Store and invokes the **Promote** method to promote this data.</span></span>  
  
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
  
     <span data-ttu-id="62d6b-117">이 프로 모션 정보에 따라 **SqlWorkflowInstanceStore** 데이터 속성의 열에 배치 된 [InstancePromotedProperties](#InstancePromotedProperties) 보기.</span><span class="sxs-lookup"><span data-stu-id="62d6b-117">Based on this promotion information, **SqlWorkflowInstanceStore** places the data properties in the columns of the [InstancePromotedProperties](#InstancePromotedProperties) view.</span></span>
  
6.  <span data-ttu-id="62d6b-118">승격 테이블에서 데이터 하위 집합을 쿼리하기 위해 DP 응용 프로그램은 승격 뷰의 맨 위에 사용자 지정된 뷰를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-118">To query a subset of the data from the promotion table, the DP application adds a customized view on top of the promotion view.</span></span>  
  
    ```  
    create view [dbo].[DocumentStatus] with schemabinding  
    as  
        select  P.[InstanceId] as [InstanceId],  
            P.Value1 as [UserName],  
            P.Value2 as [ApprovalStatus],  
            P.Value3 as [DocumentId],  
            P.Value4 as [LastUpdatedTime]  
    from [System.Activities.DurableInstancing].[InstancePromotedProperties] as P  
    where P.PromotionName = N'DocumentStatus'  
    go  
    ```  
  
##  <a name="InstancePromotedProperties"></a> <span data-ttu-id="62d6b-119">[System.Activities.DurableInstancing.InstancePromotedProperties] 뷰</span><span class="sxs-lookup"><span data-stu-id="62d6b-119">[System.Activities.DurableInstancing.InstancePromotedProperties] view</span></span>  
  
|<span data-ttu-id="62d6b-120">열 이름</span><span class="sxs-lookup"><span data-stu-id="62d6b-120">Column Name</span></span>|<span data-ttu-id="62d6b-121">열 유형</span><span class="sxs-lookup"><span data-stu-id="62d6b-121">Column Type</span></span>|<span data-ttu-id="62d6b-122">설명</span><span class="sxs-lookup"><span data-stu-id="62d6b-122">Description</span></span>|  
|-----------------|-----------------|-----------------|  
|<span data-ttu-id="62d6b-123">InstanceId</span><span class="sxs-lookup"><span data-stu-id="62d6b-123">InstanceId</span></span>|<span data-ttu-id="62d6b-124">GUID</span><span class="sxs-lookup"><span data-stu-id="62d6b-124">GUID</span></span>|<span data-ttu-id="62d6b-125">이 승격이 속하는 워크플로 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-125">The workflow instance that this promotion belongs to.</span></span>|  
|<span data-ttu-id="62d6b-126">PromotionName</span><span class="sxs-lookup"><span data-stu-id="62d6b-126">PromotionName</span></span>|<span data-ttu-id="62d6b-127">nvarchar(400)</span><span class="sxs-lookup"><span data-stu-id="62d6b-127">nvarchar(400)</span></span>|<span data-ttu-id="62d6b-128">승격 자체의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-128">The name of the promotion itself.</span></span>|  
|<span data-ttu-id="62d6b-129">Value1, Value2, Value3,..,Value32</span><span class="sxs-lookup"><span data-stu-id="62d6b-129">Value1, Value2, Value3,..,Value32</span></span>|<span data-ttu-id="62d6b-130">sql_variant</span><span class="sxs-lookup"><span data-stu-id="62d6b-130">sql_variant</span></span>|<span data-ttu-id="62d6b-131">승격된 속성 자체의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-131">The value of the promoted property itself.</span></span> <span data-ttu-id="62d6b-132">길이가 8000바이트를 초과하는 이진 BLOB와 문자열을 제외한 대부분의 SQL 기본 데이터 형식이 sql_variant에 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-132">Most SQL primitive data types except binary blobs and strings over 8000 bytes in length can fit in sql_variant.</span></span>|  
|<span data-ttu-id="62d6b-133">Value33, Value34, Value35, …, Value64</span><span class="sxs-lookup"><span data-stu-id="62d6b-133">Value33, Value34, Value35, …, Value64</span></span>|<span data-ttu-id="62d6b-134">varbinary(max)</span><span class="sxs-lookup"><span data-stu-id="62d6b-134">varbinary(max)</span></span>|<span data-ttu-id="62d6b-135">varbinary(max)로 명시적으로 선언되는 승격된 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="62d6b-135">The value of promoted properties that are explicitly declared as varbinary(max).</span></span>|
