---
title: '&lt;workflowInstanceQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9096e812-626a-409a-9eda-c31a60b84c55
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e7ed855dc49c4e6639734dcc6a9bc1db7ae53d01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltworkflowinstancequerygt"></a><span data-ttu-id="491e1-102">&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="491e1-102">&lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="491e1-103">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="491e1-103">Represents a query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>  
  
 <span data-ttu-id="491e1-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="491e1-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="491e1-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="491e1-105">\<system.serviceModel></span></span>  
<span data-ttu-id="491e1-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="491e1-106">\<tracking></span></span>  
<span data-ttu-id="491e1-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="491e1-107">\<trackingProfile></span></span>  
<span data-ttu-id="491e1-108">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="491e1-108">\<workflow></span></span>  
<span data-ttu-id="491e1-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="491e1-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="491e1-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="491e1-110">\<workflowInstanceQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="491e1-111">구문</span><span class="sxs-lookup"><span data-stu-id="491e1-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="491e1-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="491e1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="491e1-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="491e1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="491e1-114">특성</span><span class="sxs-lookup"><span data-stu-id="491e1-114">Attributes</span></span>  
 <span data-ttu-id="491e1-115">없음</span><span class="sxs-lookup"><span data-stu-id="491e1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="491e1-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="491e1-116">Child Elements</span></span>  
  
|<span data-ttu-id="491e1-117">요소</span><span class="sxs-lookup"><span data-stu-id="491e1-117">Element</span></span>|<span data-ttu-id="491e1-118">설명</span><span class="sxs-lookup"><span data-stu-id="491e1-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="491e1-119">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="491e1-119">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="491e1-120">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="491e1-120">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="491e1-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="491e1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="491e1-122">요소</span><span class="sxs-lookup"><span data-stu-id="491e1-122">Element</span></span>|<span data-ttu-id="491e1-123">설명</span><span class="sxs-lookup"><span data-stu-id="491e1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="491e1-124">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="491e1-124">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="491e1-125">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 구성 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="491e1-125">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="491e1-126">설명</span><span class="sxs-lookup"><span data-stu-id="491e1-126">Remarks</span></span>  
 <span data-ttu-id="491e1-127"><xref:System.Activities.Tracking.WorkflowInstanceQuery>는 다음 <xref:System.Activities.Tracking.TrackingRecord> 개체를 구독하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="491e1-127">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
-   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
## <a name="example"></a><span data-ttu-id="491e1-128">예제</span><span class="sxs-lookup"><span data-stu-id="491e1-128">Example</span></span>  
 <span data-ttu-id="491e1-129">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="491e1-129">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="491e1-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="491e1-130">See Also</span></span>  
 <span data-ttu-id="491e1-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="491e1-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="491e1-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="491e1-132"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="491e1-133">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="491e1-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="491e1-134">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="491e1-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
