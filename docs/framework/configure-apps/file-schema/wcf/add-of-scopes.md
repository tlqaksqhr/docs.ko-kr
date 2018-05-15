---
title: '&lt;scopes&gt;의 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: a889100da4723a1f5e8f84ca88ea426ccaa2e77f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="52234-102">&lt;scopes&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="52234-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="52234-103">쿼리 중에 서비스 끝점을 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="52234-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="52234-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="52234-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="52234-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="52234-105">\<behaviors></span></span>  
<span data-ttu-id="52234-106">\<endpointBehaviors></span><span class="sxs-lookup"><span data-stu-id="52234-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="52234-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="52234-107">\<behavior></span></span>  
<span data-ttu-id="52234-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="52234-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="52234-109">\<범위 ></span><span class="sxs-lookup"><span data-stu-id="52234-109">\<scopes></span></span>  
<span data-ttu-id="52234-110">\<add></span><span class="sxs-lookup"><span data-stu-id="52234-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52234-111">구문</span><span class="sxs-lookup"><span data-stu-id="52234-111">Syntax</span></span>  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52234-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="52234-112">Attributes and Elements</span></span>  
 <span data-ttu-id="52234-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="52234-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52234-114">특성</span><span class="sxs-lookup"><span data-stu-id="52234-114">Attributes</span></span>  
  
|<span data-ttu-id="52234-115">특성</span><span class="sxs-lookup"><span data-stu-id="52234-115">Attribute</span></span>|<span data-ttu-id="52234-116">설명</span><span class="sxs-lookup"><span data-stu-id="52234-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52234-117">범위</span><span class="sxs-lookup"><span data-stu-id="52234-117">scope</span></span>|<span data-ttu-id="52234-118">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 끝점의 범위 정보가 포함되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="52234-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="52234-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="52234-119">Child Elements</span></span>  
 <span data-ttu-id="52234-120">없음</span><span class="sxs-lookup"><span data-stu-id="52234-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="52234-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="52234-121">Parent Elements</span></span>  
  
|<span data-ttu-id="52234-122">요소</span><span class="sxs-lookup"><span data-stu-id="52234-122">Element</span></span>|<span data-ttu-id="52234-123">설명</span><span class="sxs-lookup"><span data-stu-id="52234-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52234-124">\<범위 ></span><span class="sxs-lookup"><span data-stu-id="52234-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="52234-125">쿼리 중에 서비스 끝점을 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="52234-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52234-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="52234-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
