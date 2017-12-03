---
title: "&lt;변수&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad2a4d3768c26755a9437826c70585a43f967d09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltvariablegt"></a><span data-ttu-id="3201f-102">&lt;변수&gt;</span><span class="sxs-lookup"><span data-stu-id="3201f-102">&lt;variable&gt;</span></span>
<span data-ttu-id="3201f-103">이 활동 쿼리와 연결된 변수의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3201f-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="3201f-104">추적 프로필 쿼리에 대 한 자세한 내용은 참조 하십시오. [추적 프로필](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3201f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3201f-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3201f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3201f-106">\<추적 ></span><span class="sxs-lookup"><span data-stu-id="3201f-106">\<tracking></span></span>  
<span data-ttu-id="3201f-107">\<프로 파일 ></span><span class="sxs-lookup"><span data-stu-id="3201f-107">\<profiles></span></span>  
<span data-ttu-id="3201f-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3201f-108">\<trackingProfile></span></span>  
<span data-ttu-id="3201f-109">\<워크플로 ></span><span class="sxs-lookup"><span data-stu-id="3201f-109">\<workflow></span></span>  
<span data-ttu-id="3201f-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="3201f-110">\<activityStateQueries></span></span>  
<span data-ttu-id="3201f-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="3201f-111">\<activityStateQuery></span></span>  
<span data-ttu-id="3201f-112">\<변수 ></span><span class="sxs-lookup"><span data-stu-id="3201f-112">\<variables></span></span>  
<span data-ttu-id="3201f-113">\<변수 ></span><span class="sxs-lookup"><span data-stu-id="3201f-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3201f-114">구문</span><span class="sxs-lookup"><span data-stu-id="3201f-114">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3201f-115">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3201f-115">Attributes and Elements</span></span>  
 <span data-ttu-id="3201f-116">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3201f-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3201f-117">특성</span><span class="sxs-lookup"><span data-stu-id="3201f-117">Attributes</span></span>  
  
|<span data-ttu-id="3201f-118">특성</span><span class="sxs-lookup"><span data-stu-id="3201f-118">Attribute</span></span>|<span data-ttu-id="3201f-119">설명</span><span class="sxs-lookup"><span data-stu-id="3201f-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3201f-120">name</span><span class="sxs-lookup"><span data-stu-id="3201f-120">name</span></span>|<span data-ttu-id="3201f-121">변수의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3201f-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3201f-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3201f-122">Child Elements</span></span>  
 <span data-ttu-id="3201f-123">없음</span><span class="sxs-lookup"><span data-stu-id="3201f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3201f-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3201f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="3201f-125">요소</span><span class="sxs-lookup"><span data-stu-id="3201f-125">Element</span></span>|<span data-ttu-id="3201f-126">설명</span><span class="sxs-lookup"><span data-stu-id="3201f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3201f-127">\<변수 ></span><span class="sxs-lookup"><span data-stu-id="3201f-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="3201f-128">활동 상태 쿼리와 연결되는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="3201f-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3201f-129">설명</span><span class="sxs-lookup"><span data-stu-id="3201f-129">Remarks</span></span>  
 <span data-ttu-id="3201f-130">ActivityStateQuery의 한 가지 고유한 특징은 워크플로 실행을 추적할 때 데이터를 추출하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="3201f-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="3201f-131">이 기능은 추적 레코드 사후 실행에 액세스할 때 추가 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3201f-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="3201f-132">사용할 수는 [ \<인수 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 및 [ \<상태 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) 임의의 변수 또는 인수를 추출 하는 요소 워크플로의 모든 활동입니다. 다음 예에서는 변수 및 인수를 추출 하는 활동 상태 쿼리 때 활동의 `Closed` 추적 레코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3201f-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="3201f-133">ActivityStateRecord 사용해 서만 추출할 수 있으므로 구독 하는 추적 내에서 변수 및 인수를 사용 하 여 프로 파일링 [ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3201f-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3201f-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3201f-134">See Also</span></span>  
 <span data-ttu-id="3201f-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3201f-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3201f-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3201f-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3201f-137">워크플로 추적</span><span class="sxs-lookup"><span data-stu-id="3201f-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3201f-138">추적 프로필</span><span class="sxs-lookup"><span data-stu-id="3201f-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
