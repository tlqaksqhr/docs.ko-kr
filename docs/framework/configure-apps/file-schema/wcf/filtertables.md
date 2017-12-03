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
ms.openlocfilehash: 028681acffcd93633807bdb1c6fa78aab98011c4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltertablesgt"></a><span data-ttu-id="e6b28-102">&lt;filterTables&gt;</span><span class="sxs-lookup"><span data-stu-id="e6b28-102">&lt;filterTables&gt;</span></span>
<span data-ttu-id="e6b28-103">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함하는 라우팅 테이블을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6b28-103">Represents a configuration section for defining routing tables that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>  
  
 <span data-ttu-id="e6b28-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e6b28-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e6b28-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="e6b28-105">\<routing></span></span>  
<span data-ttu-id="e6b28-106">\<routingTables ></span><span class="sxs-lookup"><span data-stu-id="e6b28-106">\<routingTables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b28-107">구문</span><span class="sxs-lookup"><span data-stu-id="e6b28-107">Syntax</span></span>  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e6b28-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e6b28-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e6b28-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e6b28-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6b28-110">특성</span><span class="sxs-lookup"><span data-stu-id="e6b28-110">Attributes</span></span>  
 <span data-ttu-id="e6b28-111">없음</span><span class="sxs-lookup"><span data-stu-id="e6b28-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e6b28-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e6b28-112">Child Elements</span></span>  
  
|<span data-ttu-id="e6b28-113">요소</span><span class="sxs-lookup"><span data-stu-id="e6b28-113">Element</span></span>|<span data-ttu-id="e6b28-114">설명</span><span class="sxs-lookup"><span data-stu-id="e6b28-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6b28-115">\<필터 ></span><span class="sxs-lookup"><span data-stu-id="e6b28-115">\<filters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|<span data-ttu-id="e6b28-116">필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함하는 라우팅 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e6b28-116">A routing table that contain mappings between the routing filters and the target endpoints to send messages to when the filter matches.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e6b28-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e6b28-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e6b28-118">요소</span><span class="sxs-lookup"><span data-stu-id="e6b28-118">Element</span></span>|<span data-ttu-id="e6b28-119">설명</span><span class="sxs-lookup"><span data-stu-id="e6b28-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e6b28-120">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="e6b28-120">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="e6b28-121">라우팅 필터와 라우팅 테이블을 포함하는 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="e6b28-121">A configuration section that contains routing filters and routing tables.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e6b28-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6b28-122">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
