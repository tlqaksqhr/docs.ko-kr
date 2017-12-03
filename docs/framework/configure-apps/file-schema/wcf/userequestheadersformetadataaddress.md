---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e7f69da871376f83422fb330f8babd56bb1fdcb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="d985f-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="d985f-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="d985f-103">요청 메시지 헤더에서 메타데이터 주소 정보를 검색할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d985f-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="d985f-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d985f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d985f-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d985f-105">\<behaviors></span></span>  
<span data-ttu-id="d985f-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d985f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="d985f-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d985f-107">\<behavior></span></span>  
<span data-ttu-id="d985f-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="d985f-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d985f-109">구문</span><span class="sxs-lookup"><span data-stu-id="d985f-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d985f-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d985f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d985f-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d985f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d985f-112">특성</span><span class="sxs-lookup"><span data-stu-id="d985f-112">Attributes</span></span>  
 <span data-ttu-id="d985f-113">없음</span><span class="sxs-lookup"><span data-stu-id="d985f-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d985f-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d985f-114">Child Elements</span></span>  
  
|<span data-ttu-id="d985f-115">요소</span><span class="sxs-lookup"><span data-stu-id="d985f-115">Element</span></span>|<span data-ttu-id="d985f-116">설명</span><span class="sxs-lookup"><span data-stu-id="d985f-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d985f-117">\<a d d ></span><span class="sxs-lookup"><span data-stu-id="d985f-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="d985f-118">클라이언트 응용 프로그램에서 수신하는 기본 통신 끝점을 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d985f-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d985f-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d985f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d985f-120">요소</span><span class="sxs-lookup"><span data-stu-id="d985f-120">Element</span></span>|<span data-ttu-id="d985f-121">설명</span><span class="sxs-lookup"><span data-stu-id="d985f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d985f-122">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="d985f-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="d985f-123">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d985f-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d985f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d985f-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
