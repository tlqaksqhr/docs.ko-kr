---
title: "&lt;entries&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d62236c604cd91c2dfe4b92cfaac4004fc18d439
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltentriesgt"></a><span data-ttu-id="dc728-102">&lt;entries&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="dc728-102">&lt;add&gt; of &lt;entries&gt;</span></span>
<span data-ttu-id="dc728-103">이전에 정의된 클라이언트 끝점에 필터를 매핑하는 라우팅 항목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-103">Represents a routing entry that maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="dc728-104">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-104">Messages matching this filter will be sent to this destination.</span></span>  
  
 <span data-ttu-id="dc728-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="dc728-105">\<system.serviceModel></span></span>  
<span data-ttu-id="dc728-106">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="dc728-106">\<routing></span></span>  
<span data-ttu-id="dc728-107">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="dc728-107">\<routingTables></span></span>  
<span data-ttu-id="dc728-108">\<테이블 ></span><span class="sxs-lookup"><span data-stu-id="dc728-108">\<table></span></span>  
<span data-ttu-id="dc728-109">\<항목 ></span><span class="sxs-lookup"><span data-stu-id="dc728-109">\<entries></span></span>  
<span data-ttu-id="dc728-110">\<add></span><span class="sxs-lookup"><span data-stu-id="dc728-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc728-111">구문</span><span class="sxs-lookup"><span data-stu-id="dc728-111">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc728-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dc728-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dc728-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc728-114">특성</span><span class="sxs-lookup"><span data-stu-id="dc728-114">Attributes</span></span>  
  
|<span data-ttu-id="dc728-115">특성</span><span class="sxs-lookup"><span data-stu-id="dc728-115">Attribute</span></span>|<span data-ttu-id="dc728-116">설명</span><span class="sxs-lookup"><span data-stu-id="dc728-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc728-117">backupList</span><span class="sxs-lookup"><span data-stu-id="dc728-117">backupList</span></span>|<span data-ttu-id="dc728-118">끝점의 백업 목록에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-118">A string that specifies a reference to a backup list of endpoints.</span></span>|  
|<span data-ttu-id="dc728-119">끝점(endpoint)</span><span class="sxs-lookup"><span data-stu-id="dc728-119">endpoint</span></span>|<span data-ttu-id="dc728-120">`filterName` 특성에 의해 지정된 필터와 일치하는 메시지를 수신할 클라이언트 끝점에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-120">A string that specifies a reference to a client endpoint that will receive messages that match the filter specified by the `filterName` attribute.</span></span>|  
|<span data-ttu-id="dc728-121">filterName</span><span class="sxs-lookup"><span data-stu-id="dc728-121">filterName</span></span>|<span data-ttu-id="dc728-122">필터 요소에 대한 참조를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-122">A string that specifies a reference to a filter element.</span></span>|  
|<span data-ttu-id="dc728-123">priority</span><span class="sxs-lookup"><span data-stu-id="dc728-123">priority</span></span>|<span data-ttu-id="dc728-124">이 항목의 우선 순위를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-124">An integer that specifies the priority of this entry.</span></span><br /><br /> <span data-ttu-id="dc728-125">라우팅 테이블의 항목은 우선 순위를 기준으로 평가되며 0이 가장 낮은 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-125">Entries in the routing table will be evaluated based on priority, with 0 being the lowest priority.</span></span> <span data-ttu-id="dc728-126">특정 우선 순위를 갖는 모든 항목은 동시에 평가되며 현재 우선 순위에 대해 일치하는 항목이 없는 경우 다음 우선 순위가 평가됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-126">All entries for a specific priority are evaluated simultaneously, if no matching entry is found for the current priority, the next priority level will be evaluated.</span></span><br /><br /> <span data-ttu-id="dc728-127">이 값은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-127">This value is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc728-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dc728-128">Child Elements</span></span>  
 <span data-ttu-id="dc728-129">없음</span><span class="sxs-lookup"><span data-stu-id="dc728-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc728-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dc728-130">Parent Elements</span></span>  
  
|<span data-ttu-id="dc728-131">요소</span><span class="sxs-lookup"><span data-stu-id="dc728-131">Element</span></span>|<span data-ttu-id="dc728-132">설명</span><span class="sxs-lookup"><span data-stu-id="dc728-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc728-133">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="dc728-133">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="dc728-134">라우팅 매핑 항목을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="dc728-134">A configuration section that contains routing mapping entries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc728-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc728-135">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType> 
