---
title: '&lt;faultPropagationQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 50dc2c4c5d4c1517d6ac3409dc4d932f67cbeb8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltfaultpropagationquerygt"></a><span data-ttu-id="0c545-102">&lt;faultPropagationQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="0c545-102">&lt;faultPropagationQuery&gt;</span></span>
<span data-ttu-id="0c545-103">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 쿼리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0c545-104">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="0c545-105">활동 내에서 발생하는 오류 처리를 추적하려면 이러한 쿼리를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="0c545-106">추적 참가자가 오류 전파 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="0c545-107">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하십시오. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="0c545-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0c545-108">\<system.serviceModel></span></span>  
<span data-ttu-id="0c545-109">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="0c545-109">\<tracking></span></span>  
<span data-ttu-id="0c545-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0c545-110">\<trackingProfile></span></span>  
<span data-ttu-id="0c545-111">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="0c545-111">\<workflow></span></span>  
<span data-ttu-id="0c545-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="0c545-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="0c545-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="0c545-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c545-114">구문</span><span class="sxs-lookup"><span data-stu-id="0c545-114">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c545-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0c545-115">Attributes and Elements</span></span>  
 <span data-ttu-id="0c545-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c545-117">특성</span><span class="sxs-lookup"><span data-stu-id="0c545-117">Attributes</span></span>  
  
|<span data-ttu-id="0c545-118">특성</span><span class="sxs-lookup"><span data-stu-id="0c545-118">Attribute</span></span>|<span data-ttu-id="0c545-119">설명</span><span class="sxs-lookup"><span data-stu-id="0c545-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c545-120">activityName</span><span class="sxs-lookup"><span data-stu-id="0c545-120">activityName</span></span>|<span data-ttu-id="0c545-121">오류를 전파하는 오류 처리 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="0c545-122">기본값은 *이며, 이는 모든 활동에 대해 오류 전파 레코드가 반환된다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-122">The default is *, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="0c545-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="0c545-123">faultHandlerActivityName</span></span>|<span data-ttu-id="0c545-124">오류의 출처인 활동의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c545-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0c545-125">Child Elements</span></span>  
 <span data-ttu-id="0c545-126">없음</span><span class="sxs-lookup"><span data-stu-id="0c545-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c545-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0c545-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0c545-128">요소</span><span class="sxs-lookup"><span data-stu-id="0c545-128">Element</span></span>|<span data-ttu-id="0c545-129">설명</span><span class="sxs-lookup"><span data-stu-id="0c545-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c545-130">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="0c545-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="0c545-131">활동 내에서 발생하는 오류의 처리를 추적하는 데 사용되는 구성 요소 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="0c545-132">이 이벤트는 FaultHandler가 오류를 처리할 때마다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0c545-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0c545-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c545-133">See Also</span></span>  
 <span data-ttu-id="0c545-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0c545-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="0c545-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="0c545-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="0c545-136">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="0c545-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0c545-137">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="0c545-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
