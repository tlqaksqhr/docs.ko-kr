---
title: "&lt;scopes&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c720d99a5abee00eeb52f91586503e0a8a89027b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltscopesgt"></a><span data-ttu-id="34bbb-102">&lt;scopes&gt;의 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="34bbb-102">&lt;add&gt; of &lt;scopes&gt;</span></span>
<span data-ttu-id="34bbb-103">쿼리 중에 서비스 끝점을 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-103">Adds a custom scope Uri that can be used to filter service endpoints during query.</span></span>  
  
<span data-ttu-id="34bbb-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="34bbb-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="34bbb-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="34bbb-105">\<behaviors></span></span>  
<span data-ttu-id="34bbb-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="34bbb-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="34bbb-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="34bbb-107">\<behavior></span></span>  
<span data-ttu-id="34bbb-108">\<endpointDiscovery ></span><span class="sxs-lookup"><span data-stu-id="34bbb-108">\<endpointDiscovery></span></span>  
<span data-ttu-id="34bbb-109">\<범위 ></span><span class="sxs-lookup"><span data-stu-id="34bbb-109">\<scopes></span></span>  
<span data-ttu-id="34bbb-110">\<add></span><span class="sxs-lookup"><span data-stu-id="34bbb-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34bbb-111">구문</span><span class="sxs-lookup"><span data-stu-id="34bbb-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34bbb-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="34bbb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="34bbb-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34bbb-114">특성</span><span class="sxs-lookup"><span data-stu-id="34bbb-114">Attributes</span></span>  
  
|<span data-ttu-id="34bbb-115">특성</span><span class="sxs-lookup"><span data-stu-id="34bbb-115">Attribute</span></span>|<span data-ttu-id="34bbb-116">설명</span><span class="sxs-lookup"><span data-stu-id="34bbb-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34bbb-117">범위</span><span class="sxs-lookup"><span data-stu-id="34bbb-117">scope</span></span>|<span data-ttu-id="34bbb-118">서비스를 찾기 위한 일치 기준으로 사용할 수 있는 끝점의 범위 정보가 포함되는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-118">A URI that contains scope information for the endpoint that can be used in matching criteria for finding services.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34bbb-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="34bbb-119">Child Elements</span></span>  
 <span data-ttu-id="34bbb-120">없음</span><span class="sxs-lookup"><span data-stu-id="34bbb-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34bbb-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="34bbb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="34bbb-122">요소</span><span class="sxs-lookup"><span data-stu-id="34bbb-122">Element</span></span>|<span data-ttu-id="34bbb-123">설명</span><span class="sxs-lookup"><span data-stu-id="34bbb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34bbb-124">\<범위 ></span><span class="sxs-lookup"><span data-stu-id="34bbb-124">\<scopes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|<span data-ttu-id="34bbb-125">쿼리 중에 서비스 끝점을 필터링하기 위해 사용할 수 있는 사용자 지정 범위 URI를 지정하는 구성 요소의 컬렉션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-125">Contains a collection of configuration elements that specify custom scope Uris that can be used to filter service endpoints during query.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34bbb-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34bbb-126">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
