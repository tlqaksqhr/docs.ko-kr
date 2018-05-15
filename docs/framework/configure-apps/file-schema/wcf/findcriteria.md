---
title: '&lt;findCriteria&gt;'
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: fc9cd3b87d0f47ae0f16b5c5bfcaa4a1167bae9f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltfindcriteriagt"></a><span data-ttu-id="8022a-102">&lt;findCriteria&gt;</span><span class="sxs-lookup"><span data-stu-id="8022a-102">&lt;findCriteria&gt;</span></span>
<span data-ttu-id="8022a-103">클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-103">A configuration element that supplies a set of criteria used by a client application to search for a discovery service.</span></span> <span data-ttu-id="8022a-104">기준을 검색 조건 (찾으려는 서비스 지정)으로 그룹화 할 수 및 찾기 종료 조건 (검색 지속 기간).</span><span class="sxs-lookup"><span data-stu-id="8022a-104">Criteria can be grouped into search criteria (specifying what services you’re looking for) and find termination criteria (how long the search should last).</span></span>  
  
 <span data-ttu-id="8022a-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8022a-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8022a-106">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="8022a-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8022a-107">구문</span><span class="sxs-lookup"><span data-stu-id="8022a-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8022a-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="8022a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8022a-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8022a-110">특성</span><span class="sxs-lookup"><span data-stu-id="8022a-110">Attributes</span></span>  
  
|<span data-ttu-id="8022a-111">특성</span><span class="sxs-lookup"><span data-stu-id="8022a-111">Attribute</span></span>|<span data-ttu-id="8022a-112">설명</span><span class="sxs-lookup"><span data-stu-id="8022a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8022a-113">duration</span><span class="sxs-lookup"><span data-stu-id="8022a-113">duration</span></span>|<span data-ttu-id="8022a-114">네트워크에서 서비스로부터 응답을 기다리는 최대 시간을 지정하는 Timespan 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-114">A Timespan value that specifies the maximum time to wait for replies from services on the network.</span></span> <span data-ttu-id="8022a-115">기본 시간은 20초입니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-115">The default duration is 20 seconds..</span></span>|  
|<span data-ttu-id="8022a-116">maxResults</span><span class="sxs-lookup"><span data-stu-id="8022a-116">maxResults</span></span>|<span data-ttu-id="8022a-117">네트워크 또는 인터넷에서 서비스로부터 기다리는 최대 응답 횟수를 지정하는 정수입니다</span><span class="sxs-lookup"><span data-stu-id="8022a-117">An integer that specifies the maximum number of replies to wait for, from services on a network or the Internet.</span></span> <span data-ttu-id="8022a-118">`duration` 특성에 지정된 시간이 경과되기 전에 최대 응답이 수신되는 경우 찾기 작업이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-118">If maximum replies are received before the value specified in the `duration` attribute has elapsed, the find operation ends.</span></span>|  
|<span data-ttu-id="8022a-119">scopeMatchBy</span><span class="sxs-lookup"><span data-stu-id="8022a-119">scopeMatchBy</span></span>|<span data-ttu-id="8022a-120">Probe 메시지의 범위와 끝점의 범위를 일치시키는 동안 사용할 일치 알고리즘을 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-120">A URI that specify the matching algorithm to use while matching the scopes in the Probe message with that of the endpoint.</span></span><br /><br /> <span data-ttu-id="8022a-121">다섯 가지의 범위 일치 규칙이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-121">There are five supported scope-matching rules.</span></span> <span data-ttu-id="8022a-122">범위 일치 규칙을 지정하지 않으면 `ScopeMatchByPrefix`가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-122">If you do not specify a scope-matching rule, `ScopeMatchByPrefix` is used.</span></span> <span data-ttu-id="8022a-123">이에 대한 자세한 내용은 <xref:System.ServiceModel.Discovery.FindCriteria>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8022a-123">For more information on this, see <xref:System.ServiceModel.Discovery.FindCriteria>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8022a-124">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8022a-124">Child Elements</span></span>  
  
|<span data-ttu-id="8022a-125">요소</span><span class="sxs-lookup"><span data-stu-id="8022a-125">Element</span></span>|<span data-ttu-id="8022a-126">설명</span><span class="sxs-lookup"><span data-stu-id="8022a-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8022a-127">\<contractTypeNames ></span><span class="sxs-lookup"><span data-stu-id="8022a-127">\<contractTypeNames></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|<span data-ttu-id="8022a-128">워크플로 서비스 계약 형식의 이름을 포함하는 구성 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-128">A collection of configuration elements that contain the names of workflow service contract types..</span></span>|  
|<span data-ttu-id="8022a-129">\<확장 >의 \<findCriteria ></span><span class="sxs-lookup"><span data-stu-id="8022a-129">\<extensions> of \<findCriteria></span></span>|<span data-ttu-id="8022a-130">확장명을 제공하는 XML 요소 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-130">A collection of XML element objects that provide extensions.</span></span>|  
|[<span data-ttu-id="8022a-131">\<범위 ></span><span class="sxs-lookup"><span data-stu-id="8022a-131">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="8022a-132">찾기 작업 중에 특정 서비스를 찾기 위해 사용하는 절대 URI를 포함하는 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-132">A collection of objects that contain absolute URIs that are used during a find operation to locate a specific service or services.</span></span><br /><br /> <span data-ttu-id="8022a-133">특정 서비스를 찾으면 서비스 URI와 범위 URI 간에 성공한 일치 항목이 생깁니다. 이때 경우에 따라 일치의 복잡한 문제를 처리하는 범위 규칙이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-133">If the specific service is found, a successful match has been made between the service URI and the Scope URI, sometimes with the help of scope rules that handle complications of matching.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8022a-134">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8022a-134">Parent Elements</span></span>  
  
|<span data-ttu-id="8022a-135">요소</span><span class="sxs-lookup"><span data-stu-id="8022a-135">Element</span></span>|<span data-ttu-id="8022a-136">설명</span><span class="sxs-lookup"><span data-stu-id="8022a-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8022a-137">\<d a r d ></span><span class="sxs-lookup"><span data-stu-id="8022a-137">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="8022a-138">응용 프로그램에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8022a-138">Contains the settings needed by an application to participate in the service discovery process as a client.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8022a-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8022a-139">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
