---
title: "&lt;services&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a859676adf48fda05040633fb8909d161e9ce8e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="b323a-102">&lt;services&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="b323a-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="b323a-103">워크플로 기반 <xref:System.Workflow.Runtime.WorkflowRuntime> 서비스를 호스트하기 위해 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]의 인스턴스에 대한 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span> <span data-ttu-id="b323a-104">이 요소는 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="b323a-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="b323a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="b323a-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="b323a-106">\<behaviors></span></span>  
<span data-ttu-id="b323a-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b323a-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="b323a-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="b323a-108">\<behavior></span></span>  
<span data-ttu-id="b323a-109">\<서비스 ></span><span class="sxs-lookup"><span data-stu-id="b323a-109">\<services></span></span>  
<span data-ttu-id="b323a-110">\<add></span><span class="sxs-lookup"><span data-stu-id="b323a-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b323a-111">구문</span><span class="sxs-lookup"><span data-stu-id="b323a-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b323a-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b323a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b323a-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b323a-114">특성</span><span class="sxs-lookup"><span data-stu-id="b323a-114">Attributes</span></span>  
  
|<span data-ttu-id="b323a-115">특성</span><span class="sxs-lookup"><span data-stu-id="b323a-115">Attribute</span></span>|<span data-ttu-id="b323a-116">설명</span><span class="sxs-lookup"><span data-stu-id="b323a-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b323a-117">형식</span><span class="sxs-lookup"><span data-stu-id="b323a-117">type</span></span>|<span data-ttu-id="b323a-118">초기화할 서비스의 정규화된 어셈블리 형식 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="b323a-119">지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="b323a-120">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b323a-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b323a-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b323a-121">Child Elements</span></span>  
 <span data-ttu-id="b323a-122">없음</span><span class="sxs-lookup"><span data-stu-id="b323a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b323a-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b323a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b323a-124">요소</span><span class="sxs-lookup"><span data-stu-id="b323a-124">Element</span></span>|<span data-ttu-id="b323a-125">설명</span><span class="sxs-lookup"><span data-stu-id="b323a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b323a-126">\<서비스 ></span><span class="sxs-lookup"><span data-stu-id="b323a-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="b323a-127"><xref:System.Workflow.Runtime.WorkflowRuntime> 엔진에 추가할 서비스 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="b323a-128">요소는 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="b323a-129">컬렉션에 지정된 서비스는 워크플로 런타임 엔진에 의해 초기화되며 해당 <xref:System.Workflow.Runtime.WorkflowRuntime> 생성자를 호출할 때 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="b323a-130">따라서 컬렉션에 지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="b323a-131">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b323a-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b323a-132">설명</span><span class="sxs-lookup"><span data-stu-id="b323a-132">Remarks</span></span>  
 <span data-ttu-id="b323a-133">이 요소에 지정된 서비스는 워크플로 런타임 엔진에 의해 초기화되며 해당 <xref:System.Workflow.Runtime.WorkflowRuntime> 생성자를 호출할 때 서비스에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="b323a-134">따라서 지정된 서비스는 생성자의 시그니처에 대한 특정 규칙을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b323a-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="b323a-135">자세한 내용은 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b323a-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b323a-136">예</span><span class="sxs-lookup"><span data-stu-id="b323a-136">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b323a-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b323a-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="b323a-138">워크플로 구성 파일</span><span class="sxs-lookup"><span data-stu-id="b323a-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
