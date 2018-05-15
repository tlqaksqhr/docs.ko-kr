---
title: '&lt;discoveryClient&gt;'
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 8c69104b9eb1097ef5dc94c9aae7352d4949668f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltdiscoveryclientgt"></a><span data-ttu-id="3b98b-102">&lt;discoveryClient&gt;</span><span class="sxs-lookup"><span data-stu-id="3b98b-102">&lt;discoveryClient&gt;</span></span>
<span data-ttu-id="3b98b-103">클라이언트 응용 프로그램에서 런타임에 검색 가능 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 사용자 지정 바인딩을 만들기 위한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b98b-103">A configuration element for creating a custom binding that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>  
  
<span data-ttu-id="3b98b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3b98b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3b98b-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3b98b-105">\<bindings></span></span>  
<span data-ttu-id="3b98b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="3b98b-106">\<customBinding></span></span>  
<span data-ttu-id="3b98b-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="3b98b-107">\<binding></span></span>  
<span data-ttu-id="3b98b-108">\<discoveryClient ></span><span class="sxs-lookup"><span data-stu-id="3b98b-108">\<discoveryClient></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b98b-109">구문</span><span class="sxs-lookup"><span data-stu-id="3b98b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b98b-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3b98b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3b98b-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3b98b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b98b-112">특성</span><span class="sxs-lookup"><span data-stu-id="3b98b-112">Attributes</span></span>  
  
|<span data-ttu-id="3b98b-113">특성</span><span class="sxs-lookup"><span data-stu-id="3b98b-113">Attribute</span></span>|<span data-ttu-id="3b98b-114">설명</span><span class="sxs-lookup"><span data-stu-id="3b98b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b98b-115">discoveryEndpoint</span><span class="sxs-lookup"><span data-stu-id="3b98b-115">discoveryEndpoint</span></span>|<span data-ttu-id="3b98b-116">클라이언트 응용 프로그램에서 런타임에 검색 가능한 서비스를 자동으로 검색하고 해당 주소를 찾을 수 있도록 하는 검색 끝점의 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3b98b-116">A string that contains the name of the Discovery Endpoint that enables a client application to automatically search for a discoverable service and find its address at runtime.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b98b-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3b98b-117">Child Elements</span></span>  
  
|<span data-ttu-id="3b98b-118">요소</span><span class="sxs-lookup"><span data-stu-id="3b98b-118">Element</span></span>|<span data-ttu-id="3b98b-119">설명</span><span class="sxs-lookup"><span data-stu-id="3b98b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b98b-120">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="3b98b-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="3b98b-121">클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b98b-121">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="3b98b-122">기준을 검색 조건 (찾으려는 서비스 지정)으로 그룹화 할 수 및 찾기 종료 조건 (검색 지속 기간).</span><span class="sxs-lookup"><span data-stu-id="3b98b-122">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3b98b-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3b98b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3b98b-124">요소</span><span class="sxs-lookup"><span data-stu-id="3b98b-124">Element</span></span>|<span data-ttu-id="3b98b-125">설명</span><span class="sxs-lookup"><span data-stu-id="3b98b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b98b-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="3b98b-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="3b98b-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3b98b-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3b98b-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b98b-128">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
