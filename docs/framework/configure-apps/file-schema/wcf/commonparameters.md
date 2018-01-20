---
title: '&lt;commonParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dcce701d8c051381317173b37fd37b840bcfa89d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltcommonparametersgt"></a><span data-ttu-id="c9f7c-102">&lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="c9f7c-102">&lt;commonParameters&gt;</span></span>
<span data-ttu-id="c9f7c-103">여러 서비스에서 전역적으로 사용되는 매개 변수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-103">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="c9f7c-104">일반적으로 이 컬렉션에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-104">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="c9f7c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c9f7c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="c9f7c-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="c9f7c-106">\<behaviors></span></span>  
<span data-ttu-id="c9f7c-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c9f7c-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="c9f7c-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="c9f7c-108">\<behavior></span></span>  
<span data-ttu-id="c9f7c-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="c9f7c-109">\<workflowRuntime></span></span>  
<span data-ttu-id="c9f7c-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="c9f7c-110">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9f7c-111">구문</span><span class="sxs-lookup"><span data-stu-id="c9f7c-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9f7c-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c9f7c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c9f7c-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9f7c-114">특성</span><span class="sxs-lookup"><span data-stu-id="c9f7c-114">Attributes</span></span>  
 <span data-ttu-id="c9f7c-115">없음</span><span class="sxs-lookup"><span data-stu-id="c9f7c-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9f7c-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c9f7c-116">Child Elements</span></span>  
  
|<span data-ttu-id="c9f7c-117">요소</span><span class="sxs-lookup"><span data-stu-id="c9f7c-117">Element</span></span>|<span data-ttu-id="c9f7c-118">설명</span><span class="sxs-lookup"><span data-stu-id="c9f7c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9f7c-119">\<add></span><span class="sxs-lookup"><span data-stu-id="c9f7c-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="c9f7c-120">서비스에서 사용되는 일반 매개 변수의 이름-값 쌍을 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9f7c-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c9f7c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c9f7c-122">요소</span><span class="sxs-lookup"><span data-stu-id="c9f7c-122">Element</span></span>|<span data-ttu-id="c9f7c-123">설명</span><span class="sxs-lookup"><span data-stu-id="c9f7c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9f7c-124">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="c9f7c-124">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="c9f7c-125">워크플로 기반 <xref:System.Workflow.Runtime.WorkflowRuntime> 서비스를 호스트하기 위해 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]의 인스턴스에 대한 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9f7c-126">설명</span><span class="sxs-lookup"><span data-stu-id="c9f7c-126">Remarks</span></span>  
 <span data-ttu-id="c9f7c-127">`<commonParameters>` 요소는 여러 서비스에서 전역적으로 사용되는 모든 매개 변수를 정의합니다. 예를 들어 `ConnectionString`를 사용하는 경우 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9f7c-128">SQL 추적 서비스에서는 `ConnectionString` 값이 `<commonParameters>` 섹션에 지정된 경우 해당 값을 일관성 있게 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="c9f7c-129">`StateMachineWorkflowInstance.StateHistory` 속성을 검색하는 것과 같은 일부 작업이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="c9f7c-130">이 문제를 해결하려면 다음 예제와 같이 추적 공급자에 대한 구성 섹션에 `ConnectionString` 특성을 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="c9f7c-131">작업 일괄 처리를 지속성 저장소에 커밋하는 서비스(예: <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 및 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>)의 경우 다음 예제와 같이 `EnableRetries` 매개 변수를 사용하여 트랜잭션을 다시 시도하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 <span data-ttu-id="c9f7c-132">다음에 유의 `EnableRetries` 전역 수준에서 매개 변수를 설정할 수 있습니다 (에 표시 된 대로 *CommonParameters* 섹션) 개인에 대 한 지 원하는 서비스 또는 `EnableRetries` (에서처럼는 *서비스*섹션).</span><span class="sxs-lookup"><span data-stu-id="c9f7c-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="c9f7c-133">다음 샘플 코드에서는 일반 매개 변수를 프로그래밍 방식으로 변경하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-133">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="c9f7c-134">구성 파일을 사용 하 여의 동작을 제어 하는 방법에 대 한 자세한 내용은 <xref:System.Workflow.Runtime.WorkflowRuntime> 개체는 Windows Workflow Foundation 호스트 응용 프로그램의 참조 [워크플로 구성 파일](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)합니다.</span><span class="sxs-lookup"><span data-stu-id="c9f7c-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9f7c-135">예</span><span class="sxs-lookup"><span data-stu-id="c9f7c-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c9f7c-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9f7c-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [<span data-ttu-id="c9f7c-137">워크플로 구성 파일</span><span class="sxs-lookup"><span data-stu-id="c9f7c-137">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)  
 [<span data-ttu-id="c9f7c-138">\<add></span><span class="sxs-lookup"><span data-stu-id="c9f7c-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
