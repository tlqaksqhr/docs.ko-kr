---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 2abb2dc05bfec4419ca49d1517084ebc208e81e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757023"
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="b1485-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="b1485-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="b1485-103">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1485-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b1485-104">추적 참가자가 취소 요청 레코드 개체를 구독하려면 쿼리가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b1485-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="b1485-105">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하세요. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b1485-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b1485-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b1485-106">\<system.serviceModel></span></span>  
<span data-ttu-id="b1485-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b1485-107">\<tracking></span></span>  
<span data-ttu-id="b1485-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b1485-108">\<trackingProfile></span></span>  
<span data-ttu-id="b1485-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b1485-109">\<workflow></span></span>  
<span data-ttu-id="b1485-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="b1485-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1485-111">구문</span><span class="sxs-lookup"><span data-stu-id="b1485-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1485-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b1485-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b1485-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b1485-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1485-114">특성</span><span class="sxs-lookup"><span data-stu-id="b1485-114">Attributes</span></span>  
 <span data-ttu-id="b1485-115">없음</span><span class="sxs-lookup"><span data-stu-id="b1485-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b1485-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b1485-116">Child Elements</span></span>  
  
|<span data-ttu-id="b1485-117">요소</span><span class="sxs-lookup"><span data-stu-id="b1485-117">Element</span></span>|<span data-ttu-id="b1485-118">설명</span><span class="sxs-lookup"><span data-stu-id="b1485-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1485-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="b1485-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="b1485-120">부모 활동에 의한 자식 활동 취소 요청을 추적하는 데 사용되는 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="b1485-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1485-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b1485-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b1485-122">요소</span><span class="sxs-lookup"><span data-stu-id="b1485-122">Element</span></span>|<span data-ttu-id="b1485-123">설명</span><span class="sxs-lookup"><span data-stu-id="b1485-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1485-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b1485-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="b1485-125">로 식별 되는 특정 워크플로에 대 한 모든 쿼리를 포함 하는 구성 요소는 **activityDefinitionId** 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b1485-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1485-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1485-126">See Also</span></span>  
 [<span data-ttu-id="b1485-127">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="b1485-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b1485-128">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="b1485-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
