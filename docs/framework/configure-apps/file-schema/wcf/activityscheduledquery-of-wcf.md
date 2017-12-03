---
title: "WCF의 &lt;activityScheduledQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 260b77789df6a03b640895ed158c94bfd1533f9b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="e0356-102">WCF의 &lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="e0356-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="e0356-103">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e0356-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="e0356-104">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e0356-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="e0356-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e0356-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="e0356-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e0356-106">\<system.serviceModel></span></span>  
<span data-ttu-id="e0356-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="e0356-107">\<tracking></span></span>  
<span data-ttu-id="e0356-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e0356-108">\<trackingProfile></span></span>  
<span data-ttu-id="e0356-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="e0356-109">\<workflow></span></span>  
<span data-ttu-id="e0356-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="e0356-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="e0356-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="e0356-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0356-112">구문</span><span class="sxs-lookup"><span data-stu-id="e0356-112">Syntax</span></span>  
  
```xml
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0356-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e0356-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e0356-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e0356-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0356-115">특성</span><span class="sxs-lookup"><span data-stu-id="e0356-115">Attributes</span></span>  
  
|<span data-ttu-id="e0356-116">특성</span><span class="sxs-lookup"><span data-stu-id="e0356-116">Attribute</span></span>|<span data-ttu-id="e0356-117">설명</span><span class="sxs-lookup"><span data-stu-id="e0356-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0356-118">activityName</span><span class="sxs-lookup"><span data-stu-id="e0356-118">activityName</span></span>|<span data-ttu-id="e0356-119">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e0356-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="e0356-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="e0356-120">childActivityName</span></span>|<span data-ttu-id="e0356-121">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e0356-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0356-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e0356-122">Child Elements</span></span>  
 <span data-ttu-id="e0356-123">없음</span><span class="sxs-lookup"><span data-stu-id="e0356-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0356-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e0356-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e0356-125">요소</span><span class="sxs-lookup"><span data-stu-id="e0356-125">Element</span></span>|<span data-ttu-id="e0356-126">설명</span><span class="sxs-lookup"><span data-stu-id="e0356-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0356-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="e0356-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="e0356-128">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="e0356-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0356-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e0356-129">See Also</span></span>  
 <span data-ttu-id="e0356-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span><span class="sxs-lookup"><span data-stu-id="e0356-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span></span>     
 <span data-ttu-id="e0356-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="e0356-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="e0356-132">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="e0356-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e0356-133">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="e0356-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
