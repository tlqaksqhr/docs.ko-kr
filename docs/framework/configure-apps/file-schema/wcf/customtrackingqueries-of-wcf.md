---
title: "WCF의 &lt;customTrackingQueries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d1d87a5b95d7679018c7e50af3c8e1c0265a3d4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="dbfa2-102">WCF의 &lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="dbfa2-102">&lt;customTrackingQueries&gt; of WCF</span></span>
<span data-ttu-id="dbfa2-103">코드 활동에서 정의하는 이벤트를 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dbfa2-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="dbfa2-104">추적 참가자가 사용자 지정 추적 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dbfa2-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="dbfa2-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="dbfa2-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="dbfa2-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="dbfa2-106">\<system.serviceModel></span></span>  
<span data-ttu-id="dbfa2-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="dbfa2-107">\<tracking></span></span>  
<span data-ttu-id="dbfa2-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="dbfa2-108">\<trackingProfile></span></span>  
<span data-ttu-id="dbfa2-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="dbfa2-109">\<workflow></span></span>  
<span data-ttu-id="dbfa2-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="dbfa2-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbfa2-111">구문</span><span class="sxs-lookup"><span data-stu-id="dbfa2-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbfa2-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dbfa2-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dbfa2-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbfa2-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbfa2-114">특성</span><span class="sxs-lookup"><span data-stu-id="dbfa2-114">Attributes</span></span>  
 <span data-ttu-id="dbfa2-115">없음</span><span class="sxs-lookup"><span data-stu-id="dbfa2-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dbfa2-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dbfa2-116">Child Elements</span></span>  
  
|<span data-ttu-id="dbfa2-117">요소</span><span class="sxs-lookup"><span data-stu-id="dbfa2-117">Element</span></span>|<span data-ttu-id="dbfa2-118">설명</span><span class="sxs-lookup"><span data-stu-id="dbfa2-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbfa2-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="dbfa2-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="dbfa2-120">코드 활동에서 정의하는 이벤트를 추적하기 위해 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="dbfa2-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dbfa2-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dbfa2-121">Parent Elements</span></span>  
  
|<span data-ttu-id="dbfa2-122">요소</span><span class="sxs-lookup"><span data-stu-id="dbfa2-122">Element</span></span>|<span data-ttu-id="dbfa2-123">설명</span><span class="sxs-lookup"><span data-stu-id="dbfa2-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dbfa2-124">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="dbfa2-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="dbfa2-125">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dbfa2-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dbfa2-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dbfa2-126">See Also</span></span>  
 <span data-ttu-id="dbfa2-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dbfa2-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="dbfa2-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="dbfa2-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="dbfa2-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="dbfa2-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="dbfa2-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="dbfa2-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
