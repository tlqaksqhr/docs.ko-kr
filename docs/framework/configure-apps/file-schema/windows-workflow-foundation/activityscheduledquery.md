---
title: '&lt;activityScheduledQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51db0762c10459d67929867a0fe44908dc7ec750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="331cc-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="331cc-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="331cc-103">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="331cc-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="331cc-104">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="331cc-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="331cc-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="331cc-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="331cc-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="331cc-106">\<system.serviceModel></span></span>  
<span data-ttu-id="331cc-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="331cc-107">\<tracking></span></span>  
<span data-ttu-id="331cc-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="331cc-108">\<trackingProfile></span></span>  
<span data-ttu-id="331cc-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="331cc-109">\<workflow></span></span>  
<span data-ttu-id="331cc-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="331cc-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="331cc-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="331cc-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="331cc-112">구문</span><span class="sxs-lookup"><span data-stu-id="331cc-112">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="331cc-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="331cc-113">Attributes and Elements</span></span>  
 <span data-ttu-id="331cc-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="331cc-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="331cc-115">특성</span><span class="sxs-lookup"><span data-stu-id="331cc-115">Attributes</span></span>  
  
|<span data-ttu-id="331cc-116">특성</span><span class="sxs-lookup"><span data-stu-id="331cc-116">Attribute</span></span>|<span data-ttu-id="331cc-117">설명</span><span class="sxs-lookup"><span data-stu-id="331cc-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="331cc-118">activityName</span><span class="sxs-lookup"><span data-stu-id="331cc-118">activityName</span></span>|<span data-ttu-id="331cc-119">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="331cc-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="331cc-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="331cc-120">childActivityName</span></span>|<span data-ttu-id="331cc-121">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="331cc-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="331cc-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="331cc-122">Child Elements</span></span>  
 <span data-ttu-id="331cc-123">없음</span><span class="sxs-lookup"><span data-stu-id="331cc-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="331cc-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="331cc-124">Parent Elements</span></span>  
  
|<span data-ttu-id="331cc-125">요소</span><span class="sxs-lookup"><span data-stu-id="331cc-125">Element</span></span>|<span data-ttu-id="331cc-126">설명</span><span class="sxs-lookup"><span data-stu-id="331cc-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="331cc-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="331cc-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="331cc-128">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="331cc-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="331cc-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="331cc-129">See Also</span></span>  
 <span data-ttu-id="331cc-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="331cc-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="331cc-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="331cc-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="331cc-132">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="331cc-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="331cc-133">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="331cc-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
