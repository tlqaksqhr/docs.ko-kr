---
title: '&lt;cancelRequestedQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c9ad0f766256d6507775c2cca1b9d54b474abc7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="7e230-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="7e230-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="7e230-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e230-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7e230-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7e230-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="7e230-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하십시오. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e230-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7e230-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="7e230-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7e230-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="7e230-107">\<tracking></span></span>  
<span data-ttu-id="7e230-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="7e230-108">\<trackingProfile></span></span>  
<span data-ttu-id="7e230-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="7e230-109">\<workflow></span></span>  
<span data-ttu-id="7e230-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="7e230-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="7e230-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="7e230-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e230-112">구문</span><span class="sxs-lookup"><span data-stu-id="7e230-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e230-113">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7e230-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7e230-114">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e230-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e230-115">특성</span><span class="sxs-lookup"><span data-stu-id="7e230-115">Attributes</span></span>  
  
|<span data-ttu-id="7e230-116">특성</span><span class="sxs-lookup"><span data-stu-id="7e230-116">Attribute</span></span>|<span data-ttu-id="7e230-117">설명</span><span class="sxs-lookup"><span data-stu-id="7e230-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e230-118">activityName</span><span class="sxs-lookup"><span data-stu-id="7e230-118">activityName</span></span>|<span data-ttu-id="7e230-119">취소를 요청하는 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e230-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="7e230-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="7e230-120">childActivityName</span></span>|<span data-ttu-id="7e230-121">취소가 요청된 자식 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e230-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e230-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7e230-122">Child Elements</span></span>  
 <span data-ttu-id="7e230-123">없음</span><span class="sxs-lookup"><span data-stu-id="7e230-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e230-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7e230-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7e230-125">요소</span><span class="sxs-lookup"><span data-stu-id="7e230-125">Element</span></span>|<span data-ttu-id="7e230-126">설명</span><span class="sxs-lookup"><span data-stu-id="7e230-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e230-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="7e230-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="7e230-128">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 구성 요소의 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e230-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7e230-129">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7e230-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e230-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e230-130">See Also</span></span>  
 <span data-ttu-id="7e230-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7e230-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="7e230-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7e230-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="7e230-133">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="7e230-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="7e230-134">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="7e230-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
