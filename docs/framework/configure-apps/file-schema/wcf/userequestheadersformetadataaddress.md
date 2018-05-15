---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 7e661570f8b94b979595a615b3f6819d41ed5e35
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="e5bbc-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="e5bbc-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="e5bbc-103">요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bbc-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="e5bbc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e5bbc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e5bbc-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="e5bbc-105">\<behaviors></span></span>  
<span data-ttu-id="e5bbc-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="e5bbc-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e5bbc-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="e5bbc-107">\<behavior></span></span>  
<span data-ttu-id="e5bbc-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="e5bbc-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5bbc-109">구문</span><span class="sxs-lookup"><span data-stu-id="e5bbc-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5bbc-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e5bbc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e5bbc-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bbc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5bbc-112">특성</span><span class="sxs-lookup"><span data-stu-id="e5bbc-112">Attributes</span></span>  
 <span data-ttu-id="e5bbc-113">없음</span><span class="sxs-lookup"><span data-stu-id="e5bbc-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5bbc-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e5bbc-114">Child Elements</span></span>  
  
|<span data-ttu-id="e5bbc-115">요소</span><span class="sxs-lookup"><span data-stu-id="e5bbc-115">Element</span></span>|<span data-ttu-id="e5bbc-116">설명</span><span class="sxs-lookup"><span data-stu-id="e5bbc-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5bbc-117">\<a d d ></span><span class="sxs-lookup"><span data-stu-id="e5bbc-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="e5bbc-118">클라이언트 응용 프로그램에서 수신하는 기본 통신 끝점을 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="e5bbc-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5bbc-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e5bbc-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e5bbc-120">요소</span><span class="sxs-lookup"><span data-stu-id="e5bbc-120">Element</span></span>|<span data-ttu-id="e5bbc-121">설명</span><span class="sxs-lookup"><span data-stu-id="e5bbc-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5bbc-122">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="e5bbc-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e5bbc-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5bbc-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5bbc-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5bbc-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
