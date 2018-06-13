---
title: WCF의 &lt;bookmarkResumptionQueries&gt;
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 8a83f521e444838b6495221c00211710dd99ab6b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753042"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="91d14-102">WCF의 &lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="91d14-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="91d14-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91d14-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="91d14-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="91d14-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="91d14-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="91d14-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="91d14-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="91d14-106">\<system.serviceModel></span></span>  
<span data-ttu-id="91d14-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="91d14-107">\<tracking></span></span>  
<span data-ttu-id="91d14-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="91d14-108">\<trackingProfile></span></span>  
<span data-ttu-id="91d14-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="91d14-109">\<workflow></span></span>  
<span data-ttu-id="91d14-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="91d14-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="91d14-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="91d14-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91d14-112">구문</span><span class="sxs-lookup"><span data-stu-id="91d14-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="91d14-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91d14-113">Attributes and Elements</span></span>  
 <span data-ttu-id="91d14-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91d14-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91d14-115">특성</span><span class="sxs-lookup"><span data-stu-id="91d14-115">Attributes</span></span>  
 <span data-ttu-id="91d14-116">없음</span><span class="sxs-lookup"><span data-stu-id="91d14-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91d14-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91d14-117">Child Elements</span></span>  
  
|<span data-ttu-id="91d14-118">요소</span><span class="sxs-lookup"><span data-stu-id="91d14-118">Element</span></span>|<span data-ttu-id="91d14-119">설명</span><span class="sxs-lookup"><span data-stu-id="91d14-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91d14-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="91d14-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="91d14-121">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="91d14-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="91d14-122">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="91d14-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91d14-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91d14-123">Parent Elements</span></span>  
  
|<span data-ttu-id="91d14-124">요소</span><span class="sxs-lookup"><span data-stu-id="91d14-124">Element</span></span>|<span data-ttu-id="91d14-125">설명</span><span class="sxs-lookup"><span data-stu-id="91d14-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91d14-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="91d14-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="91d14-127">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="91d14-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91d14-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91d14-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="91d14-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="91d14-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="91d14-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="91d14-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
