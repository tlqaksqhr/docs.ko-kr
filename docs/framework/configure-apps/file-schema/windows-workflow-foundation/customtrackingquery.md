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
ms.workload: dotnet
ms.openlocfilehash: 7d4427ad1b45ceade29b8859d30eba746a70a27d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="dc8a8-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="dc8a8-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="dc8a8-103">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc8a8-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="dc8a8-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8a8-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="dc8a8-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="dc8a8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="dc8a8-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="dc8a8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="dc8a8-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="dc8a8-107">\<tracking></span></span>  
<span data-ttu-id="dc8a8-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dc8a8-108">\<trackingProfile></span></span>  
<span data-ttu-id="dc8a8-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="dc8a8-109">\<workflow></span></span>  
<span data-ttu-id="dc8a8-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="dc8a8-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="dc8a8-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="dc8a8-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc8a8-112">구문</span><span class="sxs-lookup"><span data-stu-id="dc8a8-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc8a8-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dc8a8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="dc8a8-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc8a8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc8a8-115">특성</span><span class="sxs-lookup"><span data-stu-id="dc8a8-115">Attributes</span></span>  
  
|<span data-ttu-id="dc8a8-116">특성</span><span class="sxs-lookup"><span data-stu-id="dc8a8-116">Attribute</span></span>|<span data-ttu-id="dc8a8-117">설명</span><span class="sxs-lookup"><span data-stu-id="dc8a8-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc8a8-118">activityName</span><span class="sxs-lookup"><span data-stu-id="dc8a8-118">activityName</span></span>|<span data-ttu-id="dc8a8-119">추적 레코드를 생성하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc8a8-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="dc8a8-120">name</span><span class="sxs-lookup"><span data-stu-id="dc8a8-120">name</span></span>|<span data-ttu-id="dc8a8-121">내보내는 사용자 지정 추적 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc8a8-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc8a8-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dc8a8-122">Child Elements</span></span>  
 <span data-ttu-id="dc8a8-123">없음</span><span class="sxs-lookup"><span data-stu-id="dc8a8-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc8a8-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dc8a8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="dc8a8-125">요소</span><span class="sxs-lookup"><span data-stu-id="dc8a8-125">Element</span></span>|<span data-ttu-id="dc8a8-126">설명</span><span class="sxs-lookup"><span data-stu-id="dc8a8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc8a8-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="dc8a8-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="dc8a8-128">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="dc8a8-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc8a8-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc8a8-129">See Also</span></span>  
 <span data-ttu-id="dc8a8-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dc8a8-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="dc8a8-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dc8a8-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>         
 [<span data-ttu-id="dc8a8-132">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="dc8a8-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dc8a8-133">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="dc8a8-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
