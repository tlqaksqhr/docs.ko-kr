---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: b0ce29213f1f281e8581b90dda17aba1bdc29072
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756243"
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="36c93-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="36c93-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="36c93-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36c93-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="36c93-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="36c93-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="36c93-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="36c93-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="36c93-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="36c93-106">\<system.serviceModel></span></span>  
<span data-ttu-id="36c93-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="36c93-107">\<tracking></span></span>  
<span data-ttu-id="36c93-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="36c93-108">\<trackingProfile></span></span>  
<span data-ttu-id="36c93-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="36c93-109">\<workflow></span></span>  
<span data-ttu-id="36c93-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="36c93-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="36c93-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="36c93-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c93-112">구문</span><span class="sxs-lookup"><span data-stu-id="36c93-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36c93-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="36c93-113">Attributes and Elements</span></span>  
 <span data-ttu-id="36c93-114">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36c93-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36c93-115">특성</span><span class="sxs-lookup"><span data-stu-id="36c93-115">Attributes</span></span>  
 <span data-ttu-id="36c93-116">없음</span><span class="sxs-lookup"><span data-stu-id="36c93-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="36c93-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="36c93-117">Child Elements</span></span>  
  
|<span data-ttu-id="36c93-118">요소</span><span class="sxs-lookup"><span data-stu-id="36c93-118">Element</span></span>|<span data-ttu-id="36c93-119">설명</span><span class="sxs-lookup"><span data-stu-id="36c93-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36c93-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="36c93-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="36c93-121">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="36c93-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="36c93-122">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="36c93-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36c93-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="36c93-123">Parent Elements</span></span>  
  
|<span data-ttu-id="36c93-124">요소</span><span class="sxs-lookup"><span data-stu-id="36c93-124">Element</span></span>|<span data-ttu-id="36c93-125">설명</span><span class="sxs-lookup"><span data-stu-id="36c93-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36c93-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="36c93-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="36c93-127">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소는 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="36c93-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36c93-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36c93-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="36c93-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="36c93-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="36c93-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="36c93-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
