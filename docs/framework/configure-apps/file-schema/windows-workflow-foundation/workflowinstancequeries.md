---
title: '&lt;workflowInstanceQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fe7ce85-cf9a-4dbf-a8f7-bc9b1fc2fe35
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 182a4082de6f1c67b7a0bc26662e2491623b2bba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancequeriesgt"></a><span data-ttu-id="07763-102">&lt;workflowInstanceQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="07763-102">&lt;workflowInstanceQueries&gt;</span></span>
<span data-ttu-id="07763-103">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="07763-103">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="07763-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="07763-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="07763-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="07763-105">\<system.serviceModel></span></span>  
<span data-ttu-id="07763-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="07763-106">\<tracking></span></span>  
<span data-ttu-id="07763-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="07763-107">\<trackingProfile></span></span>  
<span data-ttu-id="07763-108">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="07763-108">\<workflow></span></span>  
<span data-ttu-id="07763-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="07763-109">\<workflowInstanceQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07763-110">구문</span><span class="sxs-lookup"><span data-stu-id="07763-110">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07763-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="07763-111">Attributes and Elements</span></span>  
 <span data-ttu-id="07763-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="07763-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07763-113">특성</span><span class="sxs-lookup"><span data-stu-id="07763-113">Attributes</span></span>  
 <span data-ttu-id="07763-114">없음</span><span class="sxs-lookup"><span data-stu-id="07763-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07763-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="07763-115">Child Elements</span></span>  
  
|<span data-ttu-id="07763-116">요소</span><span class="sxs-lookup"><span data-stu-id="07763-116">Element</span></span>|<span data-ttu-id="07763-117">설명</span><span class="sxs-lookup"><span data-stu-id="07763-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07763-118">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="07763-118">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="07763-119">워크플로 인스턴스 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="07763-119">A query that is used to track workflow instance life cycle changes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07763-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="07763-120">Parent Elements</span></span>  
  
|<span data-ttu-id="07763-121">요소</span><span class="sxs-lookup"><span data-stu-id="07763-121">Element</span></span>|<span data-ttu-id="07763-122">설명</span><span class="sxs-lookup"><span data-stu-id="07763-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07763-123">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="07763-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="07763-124">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소는 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="07763-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07763-125">설명</span><span class="sxs-lookup"><span data-stu-id="07763-125">Remarks</span></span>  
 <span data-ttu-id="07763-126"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07763-126">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="07763-127">예제</span><span class="sxs-lookup"><span data-stu-id="07763-127">Example</span></span>  
 <span data-ttu-id="07763-128">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="07763-128">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="07763-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07763-129">See Also</span></span>  
 <span data-ttu-id="07763-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="07763-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="07763-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="07763-131"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="07763-132">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="07763-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="07763-133">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="07763-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
