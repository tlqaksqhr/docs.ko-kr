---
title: "&lt;항목&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9b6d8d1c3797d60b26443e07cc527ea8b86f526e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltentriesgt"></a><span data-ttu-id="e8d94-102">&lt;항목&gt;</span><span class="sxs-lookup"><span data-stu-id="e8d94-102">&lt;entries&gt;</span></span>
<span data-ttu-id="e8d94-103">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함하는 라우팅 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e8d94-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="e8d94-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e8d94-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e8d94-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="e8d94-105">\<routing></span></span>  
<span data-ttu-id="e8d94-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="e8d94-106">\<routingTables></span></span>  
<span data-ttu-id="e8d94-107">\<테이블 ></span><span class="sxs-lookup"><span data-stu-id="e8d94-107">\<table></span></span>  
<span data-ttu-id="e8d94-108">\<항목 ></span><span class="sxs-lookup"><span data-stu-id="e8d94-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8d94-109">구문</span><span class="sxs-lookup"><span data-stu-id="e8d94-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e8d94-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e8d94-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e8d94-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d94-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8d94-112">특성</span><span class="sxs-lookup"><span data-stu-id="e8d94-112">Attributes</span></span>  
 <span data-ttu-id="e8d94-113">없음</span><span class="sxs-lookup"><span data-stu-id="e8d94-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e8d94-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e8d94-114">Child Elements</span></span>  
  
|<span data-ttu-id="e8d94-115">요소</span><span class="sxs-lookup"><span data-stu-id="e8d94-115">Element</span></span>|<span data-ttu-id="e8d94-116">설명</span><span class="sxs-lookup"><span data-stu-id="e8d94-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8d94-117">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="e8d94-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="e8d94-118">이전에 정의된 클라이언트 끝점에 필터를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="e8d94-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="e8d94-119">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8d94-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8d94-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e8d94-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e8d94-121">요소</span><span class="sxs-lookup"><span data-stu-id="e8d94-121">Element</span></span>|<span data-ttu-id="e8d94-122">설명</span><span class="sxs-lookup"><span data-stu-id="e8d94-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8d94-123">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="e8d94-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="e8d94-124">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="e8d94-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e8d94-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8d94-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
