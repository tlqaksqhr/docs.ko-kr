---
title: "WCF의 &lt;states&gt;, &lt;workflowInstanceQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 65573b72c91eab41bd3167552ff1f42552f40f6b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="4126a-102">WCF의 &lt;states&gt;, &lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="4126a-102">&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="4126a-103">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="4126a-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4126a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="4126a-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="4126a-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4126a-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="4126a-106">\<tracking></span></span>  
<span data-ttu-id="4126a-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="4126a-107">\<trackingProfile></span></span>  
<span data-ttu-id="4126a-108">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="4126a-108">\<workflow></span></span>  
<span data-ttu-id="4126a-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="4126a-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="4126a-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="4126a-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="4126a-111">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="4126a-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4126a-112">구문</span><span class="sxs-lookup"><span data-stu-id="4126a-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4126a-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4126a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="4126a-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4126a-115">특성</span><span class="sxs-lookup"><span data-stu-id="4126a-115">Attributes</span></span>  
 <span data-ttu-id="4126a-116">없음</span><span class="sxs-lookup"><span data-stu-id="4126a-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4126a-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4126a-117">Child Elements</span></span>  
  
|<span data-ttu-id="4126a-118">요소</span><span class="sxs-lookup"><span data-stu-id="4126a-118">Element</span></span>|<span data-ttu-id="4126a-119">설명</span><span class="sxs-lookup"><span data-stu-id="4126a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4126a-120">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="4126a-120">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="4126a-121">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4126a-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4126a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4126a-123">요소</span><span class="sxs-lookup"><span data-stu-id="4126a-123">Element</span></span>|<span data-ttu-id="4126a-124">설명</span><span class="sxs-lookup"><span data-stu-id="4126a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4126a-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="4126a-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="4126a-126">시작된 이벤트나 완료된 이벤트와 같이 워크플로 인스턴스 수명 주기의 변경 내용을 추적하는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4126a-127">설명</span><span class="sxs-lookup"><span data-stu-id="4126a-127">Remarks</span></span>  
 <span data-ttu-id="4126a-128">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="4126a-129">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="4126a-130">상태</span><span class="sxs-lookup"><span data-stu-id="4126a-130">State</span></span>|<span data-ttu-id="4126a-131">설명</span><span class="sxs-lookup"><span data-stu-id="4126a-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4126a-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="4126a-132">Aborted</span></span>|<span data-ttu-id="4126a-133">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="4126a-134">Completed</span><span class="sxs-lookup"><span data-stu-id="4126a-134">Completed</span></span>|<span data-ttu-id="4126a-135">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="4126a-136">삭제됨</span><span class="sxs-lookup"><span data-stu-id="4126a-136">Deleted</span></span>|<span data-ttu-id="4126a-137">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="4126a-138">Idle</span><span class="sxs-lookup"><span data-stu-id="4126a-138">Idle</span></span>|<span data-ttu-id="4126a-139">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="4126a-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="4126a-140">Persisted</span></span>|<span data-ttu-id="4126a-141">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="4126a-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="4126a-142">Resumed</span></span>|<span data-ttu-id="4126a-143">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="4126a-144">Started</span><span class="sxs-lookup"><span data-stu-id="4126a-144">Started</span></span>|<span data-ttu-id="4126a-145">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="4126a-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="4126a-146">UnhandledException</span></span>|<span data-ttu-id="4126a-147">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="4126a-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="4126a-148">Unloaded</span></span>|<span data-ttu-id="4126a-149">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="4126a-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="4126a-150">Canceled</span></span>|<span data-ttu-id="4126a-151">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="4126a-152">Suspended</span><span class="sxs-lookup"><span data-stu-id="4126a-152">Suspended</span></span>|<span data-ttu-id="4126a-153">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="4126a-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="4126a-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="4126a-154">Terminated</span></span>|<span data-ttu-id="4126a-155">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="4126a-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="4126a-156">Unsuspended</span></span>|<span data-ttu-id="4126a-157">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4126a-158">예제</span><span class="sxs-lookup"><span data-stu-id="4126a-158">Example</span></span>  
 <span data-ttu-id="4126a-159">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="4126a-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4126a-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4126a-160">See Also</span></span>  
 <span data-ttu-id="4126a-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4126a-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="4126a-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4126a-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="4126a-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4126a-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="4126a-164">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="4126a-164">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="4126a-165">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="4126a-165">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
