---
title: '&lt;customTrackingQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 7ddf19ed75d50f3cd5f20de8b0e2dfcdd5ea82b0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="d4508-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="d4508-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="d4508-103">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d4508-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="d4508-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d4508-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="d4508-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d4508-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d4508-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d4508-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d4508-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d4508-107">\<tracking></span></span>  
<span data-ttu-id="d4508-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d4508-108">\<trackingProfile></span></span>  
<span data-ttu-id="d4508-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d4508-109">\<workflow></span></span>  
<span data-ttu-id="d4508-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="d4508-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="d4508-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="d4508-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4508-112">구문</span><span class="sxs-lookup"><span data-stu-id="d4508-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d4508-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d4508-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d4508-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4508-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d4508-115">특성</span><span class="sxs-lookup"><span data-stu-id="d4508-115">Attributes</span></span>  
  
|<span data-ttu-id="d4508-116">특성</span><span class="sxs-lookup"><span data-stu-id="d4508-116">Attribute</span></span>|<span data-ttu-id="d4508-117">설명</span><span class="sxs-lookup"><span data-stu-id="d4508-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d4508-118">activityName</span><span class="sxs-lookup"><span data-stu-id="d4508-118">activityName</span></span>|<span data-ttu-id="d4508-119">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4508-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="d4508-120">name</span><span class="sxs-lookup"><span data-stu-id="d4508-120">name</span></span>|<span data-ttu-id="d4508-121">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4508-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d4508-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d4508-122">Child Elements</span></span>  
 <span data-ttu-id="d4508-123">없음</span><span class="sxs-lookup"><span data-stu-id="d4508-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d4508-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d4508-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d4508-125">요소</span><span class="sxs-lookup"><span data-stu-id="d4508-125">Element</span></span>|<span data-ttu-id="d4508-126">설명</span><span class="sxs-lookup"><span data-stu-id="d4508-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4508-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="d4508-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="d4508-128">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="d4508-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4508-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4508-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>         
 [<span data-ttu-id="d4508-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="d4508-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d4508-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="d4508-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
