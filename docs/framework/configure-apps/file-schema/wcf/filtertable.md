---
title: '&lt;filterTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04780d51cfd1d1d0049fc608cf7bd304be382b9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltertablegt"></a><span data-ttu-id="18947-102">&lt;filterTable&gt;</span><span class="sxs-lookup"><span data-stu-id="18947-102">&lt;filterTable&gt;</span></span>
<span data-ttu-id="18947-103">필터 식이 true로 평가 대해 메시지 및 메시지를 라우팅할 클라이언트 끝점을 평가 하는 필터의 목록을 포함 하는 라우팅 테이블을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="18947-103">Represents a routing table that contains a list of filters to evaluate messages against and the client endpoint to route messages to if the filter evaluates to true.</span></span>  
  
 <span data-ttu-id="18947-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="18947-104">\<system.serviceModel></span></span>  
<span data-ttu-id="18947-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="18947-105">\<routing></span></span>  
<span data-ttu-id="18947-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="18947-106">\<routingTables></span></span>  
<span data-ttu-id="18947-107">\<테이블 ></span><span class="sxs-lookup"><span data-stu-id="18947-107">\<table></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18947-108">구문</span><span class="sxs-lookup"><span data-stu-id="18947-108">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="18947-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="18947-109">Attributes and Elements</span></span>  
 <span data-ttu-id="18947-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="18947-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18947-111">특성</span><span class="sxs-lookup"><span data-stu-id="18947-111">Attributes</span></span>  
  
|<span data-ttu-id="18947-112">요소</span><span class="sxs-lookup"><span data-stu-id="18947-112">Element</span></span>|<span data-ttu-id="18947-113">설명</span><span class="sxs-lookup"><span data-stu-id="18947-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="18947-114">name</span><span class="sxs-lookup"><span data-stu-id="18947-114">name</span></span>|<span data-ttu-id="18947-115">이 구성 요소의 고유 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="18947-115">A string that contains the unique name of this configuration element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18947-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="18947-116">Child Elements</span></span>  
  
|<span data-ttu-id="18947-117">요소</span><span class="sxs-lookup"><span data-stu-id="18947-117">Element</span></span>|<span data-ttu-id="18947-118">설명</span><span class="sxs-lookup"><span data-stu-id="18947-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18947-119">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="18947-119">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="18947-120">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="18947-120">Mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18947-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="18947-121">Parent Elements</span></span>  
  
|<span data-ttu-id="18947-122">요소</span><span class="sxs-lookup"><span data-stu-id="18947-122">Element</span></span>|<span data-ttu-id="18947-123">설명</span><span class="sxs-lookup"><span data-stu-id="18947-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18947-124">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="18947-124">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="18947-125">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="18947-125">A configuration section that contains routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18947-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18947-126">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
