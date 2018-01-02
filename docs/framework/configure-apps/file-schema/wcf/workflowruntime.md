---
title: '&lt;workflowRuntime&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2860c7ddd5f3d2f0ce2749c36afebcf9abfeac3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowruntimegt"></a><span data-ttu-id="c89eb-102">&lt;workflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="c89eb-102">&lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="c89eb-103">워크플로 기반 <xref:System.Workflow.Runtime.WorkflowRuntime> 서비스를 호스트하기 위해 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]의 인스턴스에 대한 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span>  
  
 <span data-ttu-id="c89eb-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c89eb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c89eb-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="c89eb-105">\<behaviors></span></span>  
<span data-ttu-id="c89eb-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c89eb-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c89eb-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="c89eb-107">\<behavior></span></span>  
<span data-ttu-id="c89eb-108">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="c89eb-108">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c89eb-109">구문</span><span class="sxs-lookup"><span data-stu-id="c89eb-109">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"  
                                  enablePerformanceCounters="Boolean"  
                                  name="String"  
                                  validateOnCreate="Boolean">  
                 <commonParameters>  
                    <add name="String" value="String" />  
                 </commonParameters>  
                 <services>  
                    <add type="String"/>  
                 </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c89eb-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c89eb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c89eb-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c89eb-112">특성</span><span class="sxs-lookup"><span data-stu-id="c89eb-112">Attributes</span></span>  
  
|<span data-ttu-id="c89eb-113">특성</span><span class="sxs-lookup"><span data-stu-id="c89eb-113">Attribute</span></span>|<span data-ttu-id="c89eb-114">설명</span><span class="sxs-lookup"><span data-stu-id="c89eb-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c89eb-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="c89eb-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="c89eb-116">워크플로 인스턴스가 강제로 언로드되거나 중단되기 전에 메모리에 유휴 상태로 유지될 수 있는 최대 기간을 지정하는 선택적 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="c89eb-117">workflowruntime에 unloadOnIdle을 수행하는 `PersistenceService`가 있으면 이 특성이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="c89eb-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="c89eb-118">enablePerformanceCounters</span></span>|<span data-ttu-id="c89eb-119">성능 카운터를 사용하는지 여부를 지정하는 선택적 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="c89eb-120">성능 카운터는 다양한 워크플로 관련 통계에 대한 정보를 제공하지만 워크플로 런타임 엔진이 시작될 때 및 워크플로 인스턴스가 실행되고 있을 때 성능을 저하시킵니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="c89eb-121">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="c89eb-122">name</span><span class="sxs-lookup"><span data-stu-id="c89eb-122">name</span></span>|<span data-ttu-id="c89eb-123">워크플로 런타임 엔진의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="c89eb-124">이름은 시스템(예: 성능 카운터)에서 실행 중일 수 있는 다른 런타임과 이 런타임을 구분하기 위해 출력에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="c89eb-125">기본값은 빈 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="c89eb-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="c89eb-126">validateOnCreate</span></span>|<span data-ttu-id="c89eb-127">WorkflowServiceHost가 열릴 때 워크플로 정의의 유효성 검사를 실시할지 여부를 지정하는 선택적 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="c89eb-128">이 특성을 `true`로 설정하면 `WorkflowServiceHost.Open`을 호출할 때마다 워크플로 유효성 검사가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="c89eb-129">유효성 검사 오류가 발견되면 <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> 오류가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="c89eb-130">이 속성을 `false`로 설정하면 워크플로 정의 유효성 검사가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="c89eb-131">이 속성의 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c89eb-132">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c89eb-132">Child Elements</span></span>  
  
|<span data-ttu-id="c89eb-133">요소</span><span class="sxs-lookup"><span data-stu-id="c89eb-133">Element</span></span>|<span data-ttu-id="c89eb-134">설명</span><span class="sxs-lookup"><span data-stu-id="c89eb-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c89eb-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="c89eb-135">commonParameters</span></span>|<span data-ttu-id="c89eb-136">서비스에서 사용하는 일반 매개 변수 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="c89eb-137">일반적으로 이 컬렉션에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="c89eb-138">서비스</span><span class="sxs-lookup"><span data-stu-id="c89eb-138">services</span></span>|<span data-ttu-id="c89eb-139"><xref:System.Workflow.Runtime.WorkflowRuntime> 엔진에 추가할 서비스 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="c89eb-140">요소는 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="c89eb-141">컬렉션에 지정된 서비스는 워크플로 런타임 엔진에 의해 초기화되며 해당 <xref:System.Workflow.Runtime.WorkflowRuntime> 생성자를 호출할 때 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="c89eb-142">따라서 컬렉션에 지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="c89eb-143">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c89eb-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c89eb-144">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c89eb-144">Parent Elements</span></span>  
  
|<span data-ttu-id="c89eb-145">요소</span><span class="sxs-lookup"><span data-stu-id="c89eb-145">Element</span></span>|<span data-ttu-id="c89eb-146">설명</span><span class="sxs-lookup"><span data-stu-id="c89eb-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c89eb-147">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="c89eb-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c89eb-148">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c89eb-149">설명</span><span class="sxs-lookup"><span data-stu-id="c89eb-149">Remarks</span></span>  
 <span data-ttu-id="c89eb-150">동작을 제어 하는 구성 파일을 사용 하 여 대 한 자세한 내용은 <xref:System.Workflow.Runtime.WorkflowRuntime> 개체는 Windows Workflow Foundation 호스트 응용 프로그램의 참조 [워크플로 구성 파일](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)합니다.</span><span class="sxs-lookup"><span data-stu-id="c89eb-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c89eb-151">예</span><span class="sxs-lookup"><span data-stu-id="c89eb-151">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <commonParameters>  
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
            <add name="EnableRetries" value="True" />  
         </commonParameters>  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c89eb-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c89eb-152">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="c89eb-153">워크플로 구성 파일</span><span class="sxs-lookup"><span data-stu-id="c89eb-153">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
