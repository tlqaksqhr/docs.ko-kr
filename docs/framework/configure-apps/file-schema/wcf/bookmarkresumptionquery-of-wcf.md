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
ms.workload: dotnet
ms.openlocfilehash: 3240fcf026869aee7540c0e792ccd81e2592e620
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="64f4d-102">WCF의 &lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="64f4d-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>
<span data-ttu-id="64f4d-103">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64f4d-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="64f4d-104">추적 참가자가 책갈피 다시 시작 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="64f4d-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="64f4d-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="64f4d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="64f4d-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="64f4d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="64f4d-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="64f4d-107">\<tracking></span></span>  
<span data-ttu-id="64f4d-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="64f4d-108">\<trackingProfile></span></span>  
<span data-ttu-id="64f4d-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="64f4d-109">\<workflow></span></span>  
<span data-ttu-id="64f4d-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="64f4d-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="64f4d-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="64f4d-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64f4d-112">구문</span><span class="sxs-lookup"><span data-stu-id="64f4d-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="64f4d-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="64f4d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="64f4d-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="64f4d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64f4d-115">특성</span><span class="sxs-lookup"><span data-stu-id="64f4d-115">Attributes</span></span>  
  
|<span data-ttu-id="64f4d-116">특성</span><span class="sxs-lookup"><span data-stu-id="64f4d-116">Attribute</span></span>|<span data-ttu-id="64f4d-117">설명</span><span class="sxs-lookup"><span data-stu-id="64f4d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="64f4d-118">name</span><span class="sxs-lookup"><span data-stu-id="64f4d-118">name</span></span>|<span data-ttu-id="64f4d-119">구독할 책갈피 레코드의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="64f4d-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="64f4d-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="64f4d-120">Child Elements</span></span>  
 <span data-ttu-id="64f4d-121">없음</span><span class="sxs-lookup"><span data-stu-id="64f4d-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="64f4d-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="64f4d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="64f4d-123">요소</span><span class="sxs-lookup"><span data-stu-id="64f4d-123">Element</span></span>|<span data-ttu-id="64f4d-124">설명</span><span class="sxs-lookup"><span data-stu-id="64f4d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64f4d-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="64f4d-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="64f4d-126">워크플로 인스턴스 내의 책갈피 다시 시작을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64f4d-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64f4d-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64f4d-127">See Also</span></span>  
 <span data-ttu-id="64f4d-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="64f4d-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="64f4d-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="64f4d-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="64f4d-130">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="64f4d-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="64f4d-131">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="64f4d-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
