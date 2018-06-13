---
title: '&lt;state&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 327a5e98a9ecf6ba23eaf47c3d6d73bfb7852ee7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757491"
---
# <a name="ltstategt"></a><span data-ttu-id="caae4-102">&lt;state&gt;</span><span class="sxs-lookup"><span data-stu-id="caae4-102">&lt;state&gt;</span></span>
<span data-ttu-id="caae4-103">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="caae4-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="caae4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="caae4-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="caae4-105">\<system.serviceModel></span></span>  
<span data-ttu-id="caae4-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="caae4-106">\<tracking></span></span>  
<span data-ttu-id="caae4-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="caae4-107">\<trackingProfile></span></span>  
<span data-ttu-id="caae4-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="caae4-108">\<workflow></span></span>  
<span data-ttu-id="caae4-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="caae4-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="caae4-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="caae4-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="caae4-111">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="caae4-111">\<states></span></span>  
<span data-ttu-id="caae4-112">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="caae4-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caae4-113">구문</span><span class="sxs-lookup"><span data-stu-id="caae4-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="caae4-114">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="caae4-114">Attributes and Elements</span></span>  
 <span data-ttu-id="caae4-115">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="caae4-116">특성</span><span class="sxs-lookup"><span data-stu-id="caae4-116">Attributes</span></span>  
  
|<span data-ttu-id="caae4-117">특성</span><span class="sxs-lookup"><span data-stu-id="caae4-117">Attribute</span></span>|<span data-ttu-id="caae4-118">설명</span><span class="sxs-lookup"><span data-stu-id="caae4-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="caae4-119">name</span><span class="sxs-lookup"><span data-stu-id="caae4-119">name</span></span>|<span data-ttu-id="caae4-120">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="caae4-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="caae4-121">Child Elements</span></span>  
 <span data-ttu-id="caae4-122">없음</span><span class="sxs-lookup"><span data-stu-id="caae4-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="caae4-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="caae4-123">Parent Elements</span></span>  
  
|<span data-ttu-id="caae4-124">요소</span><span class="sxs-lookup"><span data-stu-id="caae4-124">Element</span></span>|<span data-ttu-id="caae4-125">설명</span><span class="sxs-lookup"><span data-stu-id="caae4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="caae4-126">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="caae4-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="caae4-127">추적 레코드가 만들어질 때 추적된 워크플로 인스턴스에서 구독된 상태의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caae4-128">설명</span><span class="sxs-lookup"><span data-stu-id="caae4-128">Remarks</span></span>  
 <span data-ttu-id="caae4-129">반환되는 레코드는 이 컬렉션의 상태를 기준으로 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="caae4-130">가능한 상태 값은 다음 표에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="caae4-131">상태</span><span class="sxs-lookup"><span data-stu-id="caae4-131">State</span></span>|<span data-ttu-id="caae4-132">설명</span><span class="sxs-lookup"><span data-stu-id="caae4-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="caae4-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="caae4-133">Aborted</span></span>|<span data-ttu-id="caae4-134">워크플로 인스턴스가 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="caae4-135">Completed</span><span class="sxs-lookup"><span data-stu-id="caae4-135">Completed</span></span>|<span data-ttu-id="caae4-136">워크플로 인스턴스가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="caae4-137">삭제됨</span><span class="sxs-lookup"><span data-stu-id="caae4-137">Deleted</span></span>|<span data-ttu-id="caae4-138">워크플로 인스턴스가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="caae4-139">Idle</span><span class="sxs-lookup"><span data-stu-id="caae4-139">Idle</span></span>|<span data-ttu-id="caae4-140">워크플로 인스턴스가 유휴 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="caae4-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="caae4-141">Persisted</span></span>|<span data-ttu-id="caae4-142">워크플로 인스턴스가 지속되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="caae4-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="caae4-143">Resumed</span></span>|<span data-ttu-id="caae4-144">워크플로 인스턴스가 다시 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="caae4-145">Started</span><span class="sxs-lookup"><span data-stu-id="caae4-145">Started</span></span>|<span data-ttu-id="caae4-146">워크플로 인스턴스가 시작되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="caae4-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="caae4-147">UnhandledException</span></span>|<span data-ttu-id="caae4-148">워크플로 인스턴스에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="caae4-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="caae4-149">Unloaded</span></span>|<span data-ttu-id="caae4-150">워크플로 인스턴스가 언로드되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="caae4-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="caae4-151">Canceled</span></span>|<span data-ttu-id="caae4-152">워크플로 인스턴스가 취소되었습니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="caae4-153">Suspended</span><span class="sxs-lookup"><span data-stu-id="caae4-153">Suspended</span></span>|<span data-ttu-id="caae4-154">워크플로 인스턴스가 일시 중단된 경우</span><span class="sxs-lookup"><span data-stu-id="caae4-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="caae4-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="caae4-155">Terminated</span></span>|<span data-ttu-id="caae4-156">워크플로 인스턴스가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="caae4-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="caae4-157">Unsuspended</span></span>|<span data-ttu-id="caae4-158">워크플로 인스턴스의 일시 중단이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="caae4-159">예제</span><span class="sxs-lookup"><span data-stu-id="caae4-159">Example</span></span>  
 <span data-ttu-id="caae4-160">다음 구성은 이 쿼리를 사용하여 `Started` 인스턴스 상태에 대한 워크플로 인스턴스 수준 추적 레코드를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="caae4-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="caae4-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="caae4-161">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>      
 [<span data-ttu-id="caae4-162">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="caae4-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="caae4-163">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="caae4-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
