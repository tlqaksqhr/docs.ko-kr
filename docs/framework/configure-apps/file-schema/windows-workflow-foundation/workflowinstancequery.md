---
title: '&lt;workflowInstanceQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
ms.openlocfilehash: eb8b84f70025df3a8a8ac96f61dec6755eb3a364
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowinstancequerygt"></a><span data-ttu-id="a3da6-102">&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="a3da6-102">&lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="a3da6-103">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3da6-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="a3da6-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a3da6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a3da6-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a3da6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a3da6-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a3da6-106">\<tracking></span></span>  
<span data-ttu-id="a3da6-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a3da6-107">\<trackingProfile></span></span>  
<span data-ttu-id="a3da6-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a3da6-108">\<workflow></span></span>  
<span data-ttu-id="a3da6-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="a3da6-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="a3da6-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="a3da6-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3da6-111">구문</span><span class="sxs-lookup"><span data-stu-id="a3da6-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3da6-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a3da6-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a3da6-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3da6-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3da6-114">특성</span><span class="sxs-lookup"><span data-stu-id="a3da6-114">Attributes</span></span>  
 <span data-ttu-id="a3da6-115">없음</span><span class="sxs-lookup"><span data-stu-id="a3da6-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a3da6-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a3da6-116">Child Elements</span></span>  
  
|<span data-ttu-id="a3da6-117">요소</span><span class="sxs-lookup"><span data-stu-id="a3da6-117">Element</span></span>|<span data-ttu-id="a3da6-118">설명</span><span class="sxs-lookup"><span data-stu-id="a3da6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3da6-119">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="a3da6-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="a3da6-120">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="a3da6-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3da6-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a3da6-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a3da6-122">요소</span><span class="sxs-lookup"><span data-stu-id="a3da6-122">Element</span></span>|<span data-ttu-id="a3da6-123">설명</span><span class="sxs-lookup"><span data-stu-id="a3da6-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3da6-124">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="a3da6-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="a3da6-125">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a3da6-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3da6-126">설명</span><span class="sxs-lookup"><span data-stu-id="a3da6-126">Remarks</span></span>  
 <span data-ttu-id="a3da6-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a3da6-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="a3da6-128">예제</span><span class="sxs-lookup"><span data-stu-id="a3da6-128">Example</span></span>  
 <span data-ttu-id="a3da6-129">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="a3da6-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3da6-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a3da6-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="a3da6-131">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="a3da6-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a3da6-132">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="a3da6-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
