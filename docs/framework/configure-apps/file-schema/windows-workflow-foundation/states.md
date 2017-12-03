---
title: "&lt;상태&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e5e9050a01cf58c3c103fdbe4e8b22e173efaf5c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltstatesgt"></a><span data-ttu-id="cddb6-102">&lt;상태&gt;</span><span class="sxs-lookup"><span data-stu-id="cddb6-102">&lt;states&gt;</span></span>
<span data-ttu-id="cddb6-103">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="cddb6-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cddb6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="cddb6-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="cddb6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="cddb6-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="cddb6-106">\<tracking></span></span>  
<span data-ttu-id="cddb6-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="cddb6-107">\<trackingProfile></span></span>  
<span data-ttu-id="cddb6-108">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="cddb6-108">\<workflow></span></span>  
<span data-ttu-id="cddb6-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="cddb6-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="cddb6-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="cddb6-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="cddb6-111">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="cddb6-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cddb6-112">구문</span><span class="sxs-lookup"><span data-stu-id="cddb6-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cddb6-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cddb6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cddb6-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cddb6-115">특성</span><span class="sxs-lookup"><span data-stu-id="cddb6-115">Attributes</span></span>  
 <span data-ttu-id="cddb6-116">없음</span><span class="sxs-lookup"><span data-stu-id="cddb6-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cddb6-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cddb6-117">Child Elements</span></span>  
  
|<span data-ttu-id="cddb6-118">요소</span><span class="sxs-lookup"><span data-stu-id="cddb6-118">Element</span></span>|<span data-ttu-id="cddb6-119">설명</span><span class="sxs-lookup"><span data-stu-id="cddb6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cddb6-120">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="cddb6-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="cddb6-121">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cddb6-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cddb6-122">Parent Elements</span></span>  
  
|<span data-ttu-id="cddb6-123">요소</span><span class="sxs-lookup"><span data-stu-id="cddb6-123">Element</span></span>|<span data-ttu-id="cddb6-124">설명</span><span class="sxs-lookup"><span data-stu-id="cddb6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cddb6-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="cddb6-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="cddb6-126">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cddb6-127">설명</span><span class="sxs-lookup"><span data-stu-id="cddb6-127">Remarks</span></span>  
 <span data-ttu-id="cddb6-128">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="cddb6-129">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="cddb6-130">상태</span><span class="sxs-lookup"><span data-stu-id="cddb6-130">State</span></span>|<span data-ttu-id="cddb6-131">설명</span><span class="sxs-lookup"><span data-stu-id="cddb6-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="cddb6-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="cddb6-132">Aborted</span></span>|<span data-ttu-id="cddb6-133">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="cddb6-134">Completed</span><span class="sxs-lookup"><span data-stu-id="cddb6-134">Completed</span></span>|<span data-ttu-id="cddb6-135">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="cddb6-136">삭제됨</span><span class="sxs-lookup"><span data-stu-id="cddb6-136">Deleted</span></span>|<span data-ttu-id="cddb6-137">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="cddb6-138">Idle</span><span class="sxs-lookup"><span data-stu-id="cddb6-138">Idle</span></span>|<span data-ttu-id="cddb6-139">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="cddb6-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="cddb6-140">Persisted</span></span>|<span data-ttu-id="cddb6-141">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="cddb6-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="cddb6-142">Resumed</span></span>|<span data-ttu-id="cddb6-143">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="cddb6-144">Started</span><span class="sxs-lookup"><span data-stu-id="cddb6-144">Started</span></span>|<span data-ttu-id="cddb6-145">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="cddb6-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="cddb6-146">UnhandledException</span></span>|<span data-ttu-id="cddb6-147">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="cddb6-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="cddb6-148">Unloaded</span></span>|<span data-ttu-id="cddb6-149">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="cddb6-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="cddb6-150">Canceled</span></span>|<span data-ttu-id="cddb6-151">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="cddb6-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="cddb6-152">Suspended</span></span>|<span data-ttu-id="cddb6-153">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="cddb6-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="cddb6-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="cddb6-154">Terminated</span></span>|<span data-ttu-id="cddb6-155">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="cddb6-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="cddb6-156">Unsuspended</span></span>|<span data-ttu-id="cddb6-157">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cddb6-158">예제</span><span class="sxs-lookup"><span data-stu-id="cddb6-158">Example</span></span>  
 <span data-ttu-id="cddb6-159">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="cddb6-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cddb6-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cddb6-160">See Also</span></span>  
 <span data-ttu-id="cddb6-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cddb6-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="cddb6-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cddb6-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="cddb6-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cddb6-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="cddb6-164">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="cddb6-164">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="cddb6-165">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="cddb6-165">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
