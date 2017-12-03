---
title: '&lt;customTrackingQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 908c340167d50d4d16e0eeff7cc2e01290b55e7a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="14a45-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="14a45-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="14a45-103">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="14a45-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="14a45-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14a45-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="14a45-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="14a45-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="14a45-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="14a45-106">\<system.serviceModel></span></span>  
<span data-ttu-id="14a45-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="14a45-107">\<tracking></span></span>  
<span data-ttu-id="14a45-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="14a45-108">\<trackingProfile></span></span>  
<span data-ttu-id="14a45-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="14a45-109">\<workflow></span></span>  
<span data-ttu-id="14a45-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="14a45-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="14a45-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="14a45-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14a45-112">구문</span><span class="sxs-lookup"><span data-stu-id="14a45-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14a45-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="14a45-113">Attributes and Elements</span></span>  
 <span data-ttu-id="14a45-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a45-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14a45-115">특성</span><span class="sxs-lookup"><span data-stu-id="14a45-115">Attributes</span></span>  
  
|<span data-ttu-id="14a45-116">특성</span><span class="sxs-lookup"><span data-stu-id="14a45-116">Attribute</span></span>|<span data-ttu-id="14a45-117">설명</span><span class="sxs-lookup"><span data-stu-id="14a45-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14a45-118">activityName</span><span class="sxs-lookup"><span data-stu-id="14a45-118">activityName</span></span>|<span data-ttu-id="14a45-119">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="14a45-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="14a45-120">name</span><span class="sxs-lookup"><span data-stu-id="14a45-120">name</span></span>|<span data-ttu-id="14a45-121">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="14a45-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14a45-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="14a45-122">Child Elements</span></span>  
 <span data-ttu-id="14a45-123">없음</span><span class="sxs-lookup"><span data-stu-id="14a45-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14a45-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="14a45-124">Parent Elements</span></span>  
  
|<span data-ttu-id="14a45-125">요소</span><span class="sxs-lookup"><span data-stu-id="14a45-125">Element</span></span>|<span data-ttu-id="14a45-126">설명</span><span class="sxs-lookup"><span data-stu-id="14a45-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14a45-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="14a45-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="14a45-128">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="14a45-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14a45-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14a45-129">See Also</span></span>  
 <span data-ttu-id="14a45-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14a45-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="14a45-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="14a45-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>         
 [<span data-ttu-id="14a45-132">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="14a45-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="14a45-133">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="14a45-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
