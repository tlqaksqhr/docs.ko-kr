---
title: '&lt;state&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca170740fbe55547c9897054f9c4782c2d25afdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltstategt"></a><span data-ttu-id="857d6-102">&lt;state&gt;</span><span class="sxs-lookup"><span data-stu-id="857d6-102">&lt;state&gt;</span></span>
<span data-ttu-id="857d6-103">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="857d6-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="857d6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="857d6-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="857d6-105">\<system.serviceModel></span></span>  
<span data-ttu-id="857d6-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="857d6-106">\<tracking></span></span>  
<span data-ttu-id="857d6-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="857d6-107">\<trackingProfile></span></span>  
<span data-ttu-id="857d6-108">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="857d6-108">\<workflow></span></span>  
<span data-ttu-id="857d6-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="857d6-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="857d6-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="857d6-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="857d6-111">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="857d6-111">\<states></span></span>  
<span data-ttu-id="857d6-112">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="857d6-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="857d6-113">구문</span><span class="sxs-lookup"><span data-stu-id="857d6-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="857d6-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="857d6-114">Attributes and Elements</span></span>  
 <span data-ttu-id="857d6-115">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="857d6-116">특성</span><span class="sxs-lookup"><span data-stu-id="857d6-116">Attributes</span></span>  
  
|<span data-ttu-id="857d6-117">특성</span><span class="sxs-lookup"><span data-stu-id="857d6-117">Attribute</span></span>|<span data-ttu-id="857d6-118">설명</span><span class="sxs-lookup"><span data-stu-id="857d6-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="857d6-119">name</span><span class="sxs-lookup"><span data-stu-id="857d6-119">name</span></span>|<span data-ttu-id="857d6-120">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="857d6-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="857d6-121">Child Elements</span></span>  
 <span data-ttu-id="857d6-122">없음</span><span class="sxs-lookup"><span data-stu-id="857d6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="857d6-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="857d6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="857d6-124">요소</span><span class="sxs-lookup"><span data-stu-id="857d6-124">Element</span></span>|<span data-ttu-id="857d6-125">설명</span><span class="sxs-lookup"><span data-stu-id="857d6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="857d6-126">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="857d6-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="857d6-127">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="857d6-128">설명</span><span class="sxs-lookup"><span data-stu-id="857d6-128">Remarks</span></span>  
 <span data-ttu-id="857d6-129">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="857d6-130">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="857d6-131">상태</span><span class="sxs-lookup"><span data-stu-id="857d6-131">State</span></span>|<span data-ttu-id="857d6-132">설명</span><span class="sxs-lookup"><span data-stu-id="857d6-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="857d6-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="857d6-133">Aborted</span></span>|<span data-ttu-id="857d6-134">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="857d6-135">Completed</span><span class="sxs-lookup"><span data-stu-id="857d6-135">Completed</span></span>|<span data-ttu-id="857d6-136">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="857d6-137">삭제됨</span><span class="sxs-lookup"><span data-stu-id="857d6-137">Deleted</span></span>|<span data-ttu-id="857d6-138">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="857d6-139">Idle</span><span class="sxs-lookup"><span data-stu-id="857d6-139">Idle</span></span>|<span data-ttu-id="857d6-140">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="857d6-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="857d6-141">Persisted</span></span>|<span data-ttu-id="857d6-142">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="857d6-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="857d6-143">Resumed</span></span>|<span data-ttu-id="857d6-144">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="857d6-145">Started</span><span class="sxs-lookup"><span data-stu-id="857d6-145">Started</span></span>|<span data-ttu-id="857d6-146">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="857d6-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="857d6-147">UnhandledException</span></span>|<span data-ttu-id="857d6-148">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="857d6-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="857d6-149">Unloaded</span></span>|<span data-ttu-id="857d6-150">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="857d6-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="857d6-151">Canceled</span></span>|<span data-ttu-id="857d6-152">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="857d6-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="857d6-153">Suspended</span></span>|<span data-ttu-id="857d6-154">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="857d6-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="857d6-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="857d6-155">Terminated</span></span>|<span data-ttu-id="857d6-156">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="857d6-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="857d6-157">Unsuspended</span></span>|<span data-ttu-id="857d6-158">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="857d6-159">예제</span><span class="sxs-lookup"><span data-stu-id="857d6-159">Example</span></span>  
 <span data-ttu-id="857d6-160">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="857d6-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="857d6-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="857d6-161">See Also</span></span>  
 <span data-ttu-id="857d6-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="857d6-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="857d6-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="857d6-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="857d6-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="857d6-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>      
 [<span data-ttu-id="857d6-165">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="857d6-165">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="857d6-166">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="857d6-166">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
