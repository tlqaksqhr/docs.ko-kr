---
title: '&lt;filterTables&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05c8d3f5ce5a01e5a88f37fce43f3b4f8d260812
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="dd2a5-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="dd2a5-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="dd2a5-103">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함하는 라우팅 테이블을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2a5-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="dd2a5-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="dd2a5-104">\<system.serviceModel></span></span>  
<span data-ttu-id="dd2a5-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="dd2a5-105">\<routing></span></span>  
<span data-ttu-id="dd2a5-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="dd2a5-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd2a5-107">구문</span><span class="sxs-lookup"><span data-stu-id="dd2a5-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="dd2a5-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dd2a5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dd2a5-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2a5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd2a5-110">특성</span><span class="sxs-lookup"><span data-stu-id="dd2a5-110">Attributes</span></span>  
 <span data-ttu-id="dd2a5-111">없음</span><span class="sxs-lookup"><span data-stu-id="dd2a5-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dd2a5-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dd2a5-112">Child Elements</span></span>  
  
|<span data-ttu-id="dd2a5-113">요소</span><span class="sxs-lookup"><span data-stu-id="dd2a5-113">Element</span></span>|<span data-ttu-id="dd2a5-114">설명</span><span class="sxs-lookup"><span data-stu-id="dd2a5-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd2a5-115">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="dd2a5-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="dd2a5-116">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함하는 라우팅 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2a5-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd2a5-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dd2a5-117">Parent Elements</span></span>  
  
|<span data-ttu-id="dd2a5-118">요소</span><span class="sxs-lookup"><span data-stu-id="dd2a5-118">Element</span></span>|<span data-ttu-id="dd2a5-119">설명</span><span class="sxs-lookup"><span data-stu-id="dd2a5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd2a5-120">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="dd2a5-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="dd2a5-121">라우팅 필터와 라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2a5-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd2a5-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd2a5-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
