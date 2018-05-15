---
title: '&lt;항목&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: b9cc7f7736ffefaca68a0f197bd064a99c4dca9a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltentriesgt"></a><span data-ttu-id="70e35-102">&lt;항목&gt;</span><span class="sxs-lookup"><span data-stu-id="70e35-102">&lt;entries&gt;</span></span>
<span data-ttu-id="70e35-103">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함하는 라우팅 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="70e35-103">A routing entry that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="70e35-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="70e35-104">\<system.serviceModel></span></span>  
<span data-ttu-id="70e35-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="70e35-105">\<routing></span></span>  
<span data-ttu-id="70e35-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="70e35-106">\<routingTables></span></span>  
<span data-ttu-id="70e35-107">\<테이블 ></span><span class="sxs-lookup"><span data-stu-id="70e35-107">\<table></span></span>  
<span data-ttu-id="70e35-108">\<항목 ></span><span class="sxs-lookup"><span data-stu-id="70e35-108">\<entries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70e35-109">구문</span><span class="sxs-lookup"><span data-stu-id="70e35-109">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="70e35-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="70e35-110">Attributes and Elements</span></span>  
 <span data-ttu-id="70e35-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="70e35-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="70e35-112">특성</span><span class="sxs-lookup"><span data-stu-id="70e35-112">Attributes</span></span>  
 <span data-ttu-id="70e35-113">없음</span><span class="sxs-lookup"><span data-stu-id="70e35-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="70e35-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="70e35-114">Child Elements</span></span>  
  
|<span data-ttu-id="70e35-115">요소</span><span class="sxs-lookup"><span data-stu-id="70e35-115">Element</span></span>|<span data-ttu-id="70e35-116">설명</span><span class="sxs-lookup"><span data-stu-id="70e35-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70e35-117">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="70e35-117">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="70e35-118">이전에 정의된 클라이언트 끝점에 필터를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="70e35-118">Maps a filter to a client endpoint that was previously defined.</span></span> <span data-ttu-id="70e35-119">이 필터와 일치하는 메시지가 해당 대상으로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="70e35-119">Messages matching this filter will be sent to this destination.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="70e35-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="70e35-120">Parent Elements</span></span>  
  
|<span data-ttu-id="70e35-121">요소</span><span class="sxs-lookup"><span data-stu-id="70e35-121">Element</span></span>|<span data-ttu-id="70e35-122">설명</span><span class="sxs-lookup"><span data-stu-id="70e35-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="70e35-123">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="70e35-123">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="70e35-124">라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="70e35-124">A configuration section that contains a routing table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70e35-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70e35-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>    
