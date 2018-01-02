---
title: '&lt;discoveryClient&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c9cbdb61152a5315aaf919e3a3c58d9329449e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="80ab7-102">&lt;discoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="80ab7-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="80ab7-103">클라이언트 응용 프로그램에서 런타임에 검색 가능 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 사용자 지정 바인딩을 만들기 위한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="80ab7-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="80ab7-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="80ab7-104">\<system.serviceModel></span></span>  
<span data-ttu-id="80ab7-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="80ab7-105">\<bindings></span></span>  
<span data-ttu-id="80ab7-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="80ab7-106">\<customBinding></span></span>  
<span data-ttu-id="80ab7-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="80ab7-107">\<binding></span></span>  
<span data-ttu-id="80ab7-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="80ab7-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ab7-109">구문</span><span class="sxs-lookup"><span data-stu-id="80ab7-109">Syntax</span></span>  
  
```xml  
<discoveryClient discoveryEndpoint="String" >
  <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String" namespace="String" />
    <contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80ab7-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="80ab7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="80ab7-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80ab7-112">특성</span><span class="sxs-lookup"><span data-stu-id="80ab7-112">Attributes</span></span>  
  
|<span data-ttu-id="80ab7-113">특성</span><span class="sxs-lookup"><span data-stu-id="80ab7-113">Attribute</span></span>|<span data-ttu-id="80ab7-114">설명</span><span class="sxs-lookup"><span data-stu-id="80ab7-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80ab7-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="80ab7-115">discoveryEndpoint</span></span>|<span data-ttu-id="80ab7-116">클라이언트 응용 프로그램에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 끝점의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="80ab7-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80ab7-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="80ab7-117">Child Elements</span></span>  
  
|<span data-ttu-id="80ab7-118">요소</span><span class="sxs-lookup"><span data-stu-id="80ab7-118">Element</span></span>|<span data-ttu-id="80ab7-119">설명</span><span class="sxs-lookup"><span data-stu-id="80ab7-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80ab7-120">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="80ab7-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="80ab7-121">클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="80ab7-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="80ab7-122">기준을 검색 조건 (찾으려는 서비스 지정)으로 그룹화 할 수 및 찾기 종료 조건 (검색 지속 기간).</span><span class="sxs-lookup"><span data-stu-id="80ab7-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80ab7-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="80ab7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="80ab7-124">요소</span><span class="sxs-lookup"><span data-stu-id="80ab7-124">Element</span></span>|<span data-ttu-id="80ab7-125">설명</span><span class="sxs-lookup"><span data-stu-id="80ab7-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80ab7-126">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="80ab7-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="80ab7-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="80ab7-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80ab7-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80ab7-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
