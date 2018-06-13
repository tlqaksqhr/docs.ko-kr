---
title: WCF의 &lt;trackingProfile&gt;
ms.date: 03/30/2017
ms.assetid: 09b651c2-c0d2-4850-a101-b0e009a1dc3a
ms.openlocfilehash: b832cf4744c9cbdd9f671e0e5f674a52c60a1a20
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750832"
---
# <a name="lttrackingprofilegt-of-wcf"></a><span data-ttu-id="42ecb-102">WCF의 &lt;trackingProfile&gt;</span><span class="sxs-lookup"><span data-stu-id="42ecb-102">&lt;trackingProfile&gt; of WCF</span></span>
<span data-ttu-id="42ecb-103">워크플로 추적 레코드는 추적 참가자에 대 한 구독을 만들기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="42ecb-104">추적 프로필에는 추적 참가자가 런타임에 워크플로 인스턴스 상태가 변경될 때 발생하는 워크플로 이벤트를 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="42ecb-105">추적 프로필 섹션 내에서 정의되는 쿼리는 구독에서 반환되는 이벤트의 종류를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="42ecb-106">워크플로 추적 및 해당 구성에 대 한 자세한 내용은 참조 하십시오. [워크플로 추적 및 트레이싱](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) 및 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="42ecb-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="42ecb-107">\<system.serviceModel></span></span>  
<span data-ttu-id="42ecb-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="42ecb-108">\<tracking></span></span>  
<span data-ttu-id="42ecb-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="42ecb-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42ecb-110">구문</span><span class="sxs-lookup"><span data-stu-id="42ecb-110">Syntax</span></span>  
  
```xml
   <system.serviceModel>  <tracking>      <trackingProfile name="String">      <workflow activityDefinitionId="String">          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>         <workflowInstanceQueries>            <workflowInstanceQuery>              <states>                 <state name="String"/>              </states>          </workflowInstanceQuery>        </workflowInstanceQueries>      </workflow>    </trackingProfile>           </profiles>  </tracking></system.serviceModel>    
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42ecb-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="42ecb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="42ecb-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42ecb-113">특성</span><span class="sxs-lookup"><span data-stu-id="42ecb-113">Attributes</span></span>  
  
|<span data-ttu-id="42ecb-114">특성</span><span class="sxs-lookup"><span data-stu-id="42ecb-114">Attribute</span></span>|<span data-ttu-id="42ecb-115">설명</span><span class="sxs-lookup"><span data-stu-id="42ecb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42ecb-116">name</span><span class="sxs-lookup"><span data-stu-id="42ecb-116">name</span></span>|<span data-ttu-id="42ecb-117">추적 프로필의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42ecb-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="42ecb-118">Child Elements</span></span>  
  
|<span data-ttu-id="42ecb-119">요소</span><span class="sxs-lookup"><span data-stu-id="42ecb-119">Element</span></span>|<span data-ttu-id="42ecb-120">설명</span><span class="sxs-lookup"><span data-stu-id="42ecb-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42ecb-121">\<participants></span><span class="sxs-lookup"><span data-stu-id="42ecb-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="42ecb-122">`a HYPERLINK "http://msdn.microsoft.com/library/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-122">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/library/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="42ecb-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="42ecb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="42ecb-124">요소</span><span class="sxs-lookup"><span data-stu-id="42ecb-124">Element</span></span>|<span data-ttu-id="42ecb-125">설명</span><span class="sxs-lookup"><span data-stu-id="42ecb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42ecb-126">\<tracking></span><span class="sxs-lookup"><span data-stu-id="42ecb-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="42ecb-127">워크플로 서비스에 대한 추적 설정을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42ecb-128">설명</span><span class="sxs-lookup"><span data-stu-id="42ecb-128">Remarks</span></span>  
 <span data-ttu-id="42ecb-129">추적 프로필에는 추적 참가자가 런타임에 워크플로 인스턴스 상태가 변경될 때 발생하는 워크플로 이벤트를 구독할 수 있도록 허용하는 추적 쿼리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="42ecb-130">모니터링 요구 사항에 따라 워크플로에서 상위 수준의 상태 변경 내용 중 작은 부분만 구독하는 매우 개괄적인 프로필을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="42ecb-131">이와 반대로 이후에 세부 실행 흐름을 다시 작성할 수 있을 정도로 상세한 결과 이벤트를 포함하는 매우 구체적인 프로필을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="42ecb-132">추적 프로필은 특정 추적 레코드에 대한 워크플로 런타임을 쿼리할 수 있는 추적 레코드에 대한 선언적 구독으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="42ecb-133">하이퍼링크의 다양 한 클래스를 구독할 수 있는 쿼리 형식이 소수의 "http://msdn.microsoft.com/library/library/system.activities.tracking.trackingrecord(VS.100).aspx" TrackingRecord 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-133">There are a handful of query types that allow you subscribe to different classes of  HYPERLINK "http://msdn.microsoft.com/library/library/system.activities.tracking.trackingrecord(VS.100).aspx" TrackingRecord objects.</span></span> <span data-ttu-id="42ecb-134">쿼리 목록은 전체 참조 [ \<참가자 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) 및 [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="42ecb-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="42ecb-135">다음 예제에서는 추적 참가자가 구독할 수 있는 구성 파일에 추적 프로필을 보여 줍니다.는 `Started` 및 `Completed` 워크플로 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="42ecb-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42ecb-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42ecb-136">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="42ecb-137">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="42ecb-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="42ecb-138">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="42ecb-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
