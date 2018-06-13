---
title: '&lt;activityScheduledQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 6192fea9a520a3f453593e5efac964a5d32a492f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756295"
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="2285f-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="2285f-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="2285f-103">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2285f-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="2285f-104">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2285f-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="2285f-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2285f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2285f-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2285f-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2285f-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2285f-107">\<tracking></span></span>  
<span data-ttu-id="2285f-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2285f-108">\<trackingProfile></span></span>  
<span data-ttu-id="2285f-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2285f-109">\<workflow></span></span>  
<span data-ttu-id="2285f-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="2285f-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2285f-111">구문</span><span class="sxs-lookup"><span data-stu-id="2285f-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2285f-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2285f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2285f-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2285f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2285f-114">특성</span><span class="sxs-lookup"><span data-stu-id="2285f-114">Attributes</span></span>  
 <span data-ttu-id="2285f-115">없음</span><span class="sxs-lookup"><span data-stu-id="2285f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2285f-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2285f-116">Child Elements</span></span>  
  
|<span data-ttu-id="2285f-117">요소</span><span class="sxs-lookup"><span data-stu-id="2285f-117">Element</span></span>|<span data-ttu-id="2285f-118">설명</span><span class="sxs-lookup"><span data-stu-id="2285f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2285f-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="2285f-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="2285f-120">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="2285f-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2285f-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2285f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2285f-122">요소</span><span class="sxs-lookup"><span data-stu-id="2285f-122">Element</span></span>|<span data-ttu-id="2285f-123">설명</span><span class="sxs-lookup"><span data-stu-id="2285f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2285f-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2285f-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="2285f-125">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소는 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="2285f-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2285f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2285f-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="2285f-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="2285f-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="2285f-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="2285f-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
