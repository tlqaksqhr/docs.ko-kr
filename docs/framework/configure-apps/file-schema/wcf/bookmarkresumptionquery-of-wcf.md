---
title: "WCF의 &lt;bookmarkResumptionQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 124b05d8e1ce9831a1efb3c6e62cc5e9fd3058fc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="ee9a4-102">WCF의 &lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ee9a4-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="ee9a4-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="ee9a4-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="ee9a4-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ee9a4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="ee9a4-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ee9a4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ee9a4-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="ee9a4-107">\<tracking></span></span>  
<span data-ttu-id="ee9a4-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="ee9a4-108">\<trackingProfile></span></span>  
<span data-ttu-id="ee9a4-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="ee9a4-109">\<workflow></span></span>  
<span data-ttu-id="ee9a4-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="ee9a4-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="ee9a4-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="ee9a4-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee9a4-112">구문</span><span class="sxs-lookup"><span data-stu-id="ee9a4-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ee9a4-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="ee9a4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ee9a4-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee9a4-115">특성</span><span class="sxs-lookup"><span data-stu-id="ee9a4-115">Attributes</span></span>  
  
|<span data-ttu-id="ee9a4-116">특성</span><span class="sxs-lookup"><span data-stu-id="ee9a4-116">Attribute</span></span>|<span data-ttu-id="ee9a4-117">설명</span><span class="sxs-lookup"><span data-stu-id="ee9a4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee9a4-118">name</span><span class="sxs-lookup"><span data-stu-id="ee9a4-118">name</span></span>|<span data-ttu-id="ee9a4-119">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee9a4-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ee9a4-120">Child Elements</span></span>  
 <span data-ttu-id="ee9a4-121">없음</span><span class="sxs-lookup"><span data-stu-id="ee9a4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee9a4-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ee9a4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ee9a4-123">요소</span><span class="sxs-lookup"><span data-stu-id="ee9a4-123">Element</span></span>|<span data-ttu-id="ee9a4-124">설명</span><span class="sxs-lookup"><span data-stu-id="ee9a4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee9a4-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="ee9a4-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="ee9a4-126">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ee9a4-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee9a4-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee9a4-127">See Also</span></span>  
 <span data-ttu-id="ee9a4-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ee9a4-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="ee9a4-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="ee9a4-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="ee9a4-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="ee9a4-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="ee9a4-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="ee9a4-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
