---
title: "WCF의 &lt;activityScheduledQueries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97726c7faa08477351d4496650b6c08b643cdb76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="36e7e-102">WCF의 &lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="36e7e-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="36e7e-103">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36e7e-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="36e7e-104">추적 참가자가 활동 예약 레코드를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="36e7e-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="36e7e-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="36e7e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="36e7e-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="36e7e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="36e7e-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="36e7e-107">\<tracking></span></span>  
<span data-ttu-id="36e7e-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="36e7e-108">\<trackingProfile></span></span>  
<span data-ttu-id="36e7e-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="36e7e-109">\<workflow></span></span>  
<span data-ttu-id="36e7e-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="36e7e-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36e7e-111">구문</span><span class="sxs-lookup"><span data-stu-id="36e7e-111">Syntax</span></span>  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36e7e-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="36e7e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="36e7e-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36e7e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36e7e-114">특성</span><span class="sxs-lookup"><span data-stu-id="36e7e-114">Attributes</span></span>  
 <span data-ttu-id="36e7e-115">없음</span><span class="sxs-lookup"><span data-stu-id="36e7e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="36e7e-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="36e7e-116">Child Elements</span></span>  
  
|<span data-ttu-id="36e7e-117">요소</span><span class="sxs-lookup"><span data-stu-id="36e7e-117">Element</span></span>|<span data-ttu-id="36e7e-118">설명</span><span class="sxs-lookup"><span data-stu-id="36e7e-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36e7e-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="36e7e-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="36e7e-120">부모 활동에 의해 실행이 예약된 활동을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="36e7e-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="36e7e-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="36e7e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="36e7e-122">요소</span><span class="sxs-lookup"><span data-stu-id="36e7e-122">Element</span></span>|<span data-ttu-id="36e7e-123">설명</span><span class="sxs-lookup"><span data-stu-id="36e7e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36e7e-124">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="36e7e-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="36e7e-125">`activityDefinitionId` 속성에 의해 식별되는 특정 워크플로에 대한 모든 쿼리를 포함하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="36e7e-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36e7e-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36e7e-126">See Also</span></span>  
 <span data-ttu-id="36e7e-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span><span class="sxs-lookup"><span data-stu-id="36e7e-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span></span>     
 <span data-ttu-id="36e7e-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="36e7e-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="36e7e-129">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="36e7e-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="36e7e-130">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="36e7e-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
