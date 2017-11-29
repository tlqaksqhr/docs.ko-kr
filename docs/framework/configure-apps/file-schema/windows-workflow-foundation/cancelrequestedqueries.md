---
title: '&lt;cancelRequestedQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b3699985095fca59d5817a31c52b29fe7609a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="5d298-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="5d298-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="5d298-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d298-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="5d298-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5d298-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="5d298-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5d298-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5d298-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="5d298-106">\<system.serviceModel></span></span>  
<span data-ttu-id="5d298-107">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="5d298-107">\<tracking></span></span>  
<span data-ttu-id="5d298-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="5d298-108">\<trackingProfile></span></span>  
<span data-ttu-id="5d298-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="5d298-109">\<workflow></span></span>  
<span data-ttu-id="5d298-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="5d298-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d298-111">구문</span><span class="sxs-lookup"><span data-stu-id="5d298-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d298-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5d298-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5d298-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d298-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d298-114">특성</span><span class="sxs-lookup"><span data-stu-id="5d298-114">Attributes</span></span>  
 <span data-ttu-id="5d298-115">없음</span><span class="sxs-lookup"><span data-stu-id="5d298-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5d298-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5d298-116">Child Elements</span></span>  
  
|<span data-ttu-id="5d298-117">요소</span><span class="sxs-lookup"><span data-stu-id="5d298-117">Element</span></span>|<span data-ttu-id="5d298-118">설명</span><span class="sxs-lookup"><span data-stu-id="5d298-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d298-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="5d298-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="5d298-120">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="5d298-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d298-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5d298-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5d298-122">요소</span><span class="sxs-lookup"><span data-stu-id="5d298-122">Element</span></span>|<span data-ttu-id="5d298-123">설명</span><span class="sxs-lookup"><span data-stu-id="5d298-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d298-124">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="5d298-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5d298-125">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소는 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5d298-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d298-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d298-126">See Also</span></span>  
 [<span data-ttu-id="5d298-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="5d298-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="5d298-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="5d298-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
