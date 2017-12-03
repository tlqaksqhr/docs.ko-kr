---
title: "WCF의 &lt;bookmarkResumptionQueries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aa46d62262b91d5b88564b50f97fccf7aefefa6d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="39130-102">WCF의 &lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="39130-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="39130-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="39130-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="39130-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="39130-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="39130-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="39130-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="39130-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="39130-106">\<system.serviceModel></span></span>  
<span data-ttu-id="39130-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="39130-107">\<tracking></span></span>  
<span data-ttu-id="39130-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="39130-108">\<trackingProfile></span></span>  
<span data-ttu-id="39130-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="39130-109">\<workflow></span></span>  
<span data-ttu-id="39130-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="39130-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="39130-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="39130-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39130-112">구문</span><span class="sxs-lookup"><span data-stu-id="39130-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="39130-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="39130-113">Attributes and Elements</span></span>  
 <span data-ttu-id="39130-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="39130-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39130-115">특성</span><span class="sxs-lookup"><span data-stu-id="39130-115">Attributes</span></span>  
 <span data-ttu-id="39130-116">없음</span><span class="sxs-lookup"><span data-stu-id="39130-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39130-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="39130-117">Child Elements</span></span>  
  
|<span data-ttu-id="39130-118">요소</span><span class="sxs-lookup"><span data-stu-id="39130-118">Element</span></span>|<span data-ttu-id="39130-119">설명</span><span class="sxs-lookup"><span data-stu-id="39130-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39130-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="39130-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="39130-121">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="39130-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="39130-122">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="39130-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39130-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="39130-123">Parent Elements</span></span>  
  
|<span data-ttu-id="39130-124">요소</span><span class="sxs-lookup"><span data-stu-id="39130-124">Element</span></span>|<span data-ttu-id="39130-125">설명</span><span class="sxs-lookup"><span data-stu-id="39130-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39130-126">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="39130-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="39130-127">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="39130-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39130-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39130-128">See Also</span></span>  
 <span data-ttu-id="39130-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="39130-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="39130-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="39130-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="39130-131">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="39130-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="39130-132">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="39130-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
