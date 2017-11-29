---
title: "WCF의 &lt;cancelRequestedQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab16fe138701d180f528b5ec07e106acd53023b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="eb3f3-102">WCF의 &lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="eb3f3-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="eb3f3-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f3-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="eb3f3-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f3-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="eb3f3-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하십시오. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f3-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="eb3f3-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="eb3f3-106">\<system.serviceModel></span></span>  
<span data-ttu-id="eb3f3-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="eb3f3-107">\<tracking></span></span>  
<span data-ttu-id="eb3f3-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="eb3f3-108">\<trackingProfile></span></span>  
<span data-ttu-id="eb3f3-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="eb3f3-109">\<workflow></span></span>  
<span data-ttu-id="eb3f3-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="eb3f3-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="eb3f3-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="eb3f3-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3f3-112">구문</span><span class="sxs-lookup"><span data-stu-id="eb3f3-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eb3f3-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eb3f3-113">Attributes and Elements</span></span>  
 <span data-ttu-id="eb3f3-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f3-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb3f3-115">특성</span><span class="sxs-lookup"><span data-stu-id="eb3f3-115">Attributes</span></span>  
  
|<span data-ttu-id="eb3f3-116">특성</span><span class="sxs-lookup"><span data-stu-id="eb3f3-116">Attribute</span></span>|<span data-ttu-id="eb3f3-117">설명</span><span class="sxs-lookup"><span data-stu-id="eb3f3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb3f3-118">activityName</span><span class="sxs-lookup"><span data-stu-id="eb3f3-118">activityName</span></span>|<span data-ttu-id="eb3f3-119">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f3-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="eb3f3-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="eb3f3-120">childActivityName</span></span>|<span data-ttu-id="eb3f3-121">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f3-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb3f3-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eb3f3-122">Child Elements</span></span>  
 <span data-ttu-id="eb3f3-123">없음</span><span class="sxs-lookup"><span data-stu-id="eb3f3-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb3f3-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eb3f3-124">Parent Elements</span></span>  
  
|<span data-ttu-id="eb3f3-125">요소</span><span class="sxs-lookup"><span data-stu-id="eb3f3-125">Element</span></span>|<span data-ttu-id="eb3f3-126">설명</span><span class="sxs-lookup"><span data-stu-id="eb3f3-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb3f3-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="eb3f3-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="eb3f3-128">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f3-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="eb3f3-129">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="eb3f3-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb3f3-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb3f3-130">See Also</span></span>  
 <span data-ttu-id="eb3f3-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="eb3f3-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="eb3f3-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="eb3f3-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>     
 [<span data-ttu-id="eb3f3-133">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="eb3f3-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="eb3f3-134">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="eb3f3-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
