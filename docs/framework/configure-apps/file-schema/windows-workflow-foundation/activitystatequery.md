---
title: '&lt;activityStateQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcd46509a76432cf695966a641a509f3db4c991d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivitystatequerygt"></a><span data-ttu-id="3441b-102">&lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="3441b-102">&lt;activityStateQuery&gt;</span></span>
<span data-ttu-id="3441b-103">워크플로 인스턴스를 구성하는 활동의 수명 주기 변경 내용을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="3441b-104">예를 들어 다음 워크플로 인스턴스 내에서 "전자 메일 보내기" 활동이 완료 될 때마다 추적 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="3441b-105">추적 참가자가 활동 상태 레코드 개체를 구독하려면 이 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="3441b-106">구독하기 위해 사용 가능한 상태는 ActivityStates에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="3441b-107">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하십시오. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3441b-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3441b-108">\<system.serviceModel></span></span>  
<span data-ttu-id="3441b-109">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="3441b-109">\<tracking></span></span>  
<span data-ttu-id="3441b-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3441b-110">\<trackingProfile></span></span>  
<span data-ttu-id="3441b-111">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="3441b-111">\<workflow></span></span>  
<span data-ttu-id="3441b-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="3441b-112">\<activityStateQueries></span></span>  
<span data-ttu-id="3441b-113">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="3441b-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3441b-114">구문</span><span class="sxs-lookup"><span data-stu-id="3441b-114">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3441b-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3441b-115">Attributes and Elements</span></span>  
 <span data-ttu-id="3441b-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3441b-117">특성</span><span class="sxs-lookup"><span data-stu-id="3441b-117">Attributes</span></span>  
  
|<span data-ttu-id="3441b-118">특성</span><span class="sxs-lookup"><span data-stu-id="3441b-118">Attribute</span></span>|<span data-ttu-id="3441b-119">설명</span><span class="sxs-lookup"><span data-stu-id="3441b-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3441b-120">activityName</span><span class="sxs-lookup"><span data-stu-id="3441b-120">activityName</span></span>|<span data-ttu-id="3441b-121"><xref:System.Activities.Tracking.ActivityStateRecord> 인스턴스를 필터링할 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3441b-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3441b-122">Child Elements</span></span>  
  
|<span data-ttu-id="3441b-123">요소</span><span class="sxs-lookup"><span data-stu-id="3441b-123">Element</span></span>|<span data-ttu-id="3441b-124">설명</span><span class="sxs-lookup"><span data-stu-id="3441b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3441b-125">\<인수 ></span><span class="sxs-lookup"><span data-stu-id="3441b-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="3441b-126">이 활동 쿼리와 연결되는 인수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="3441b-127">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="3441b-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="3441b-128">추적 레코드를 내보내야 할 구독된 활동의 상태를 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="3441b-129">\<상태 ></span><span class="sxs-lookup"><span data-stu-id="3441b-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="3441b-130">이 활동 쿼리와 연결되는 변수의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3441b-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3441b-131">Parent Elements</span></span>  
  
|<span data-ttu-id="3441b-132">요소</span><span class="sxs-lookup"><span data-stu-id="3441b-132">Element</span></span>|<span data-ttu-id="3441b-133">설명</span><span class="sxs-lookup"><span data-stu-id="3441b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3441b-134">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="3441b-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="3441b-135">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3441b-136">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3441b-137">설명</span><span class="sxs-lookup"><span data-stu-id="3441b-137">Remarks</span></span>  
 <span data-ttu-id="3441b-138">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="3441b-139">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="3441b-140">사용할 수는 [ \<인수 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 및 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 임의의 변수 또는 인수를 추출 하는 요소 워크플로의 모든 활동입니다. 다음 예에서는 변수 및 인수를 추출 하는 활동 상태 쿼리 때 활동의 `Closed` 추적 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="3441b-141">ActivityStateRecord 사용해 서만 추출할 수 있으므로 구독 하는 추적 내에서 변수 및 인수를 사용 하 여 프로 파일링 [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3441b-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3441b-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3441b-142">See Also</span></span>  
 <span data-ttu-id="3441b-143"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3441b-143"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3441b-144"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3441b-144"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3441b-145">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="3441b-145">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3441b-146">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="3441b-146">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
