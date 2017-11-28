---
title: '&lt;baseAddresses&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4bf698b64b528b0ea109223a2d94e6725c8ce6b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltbaseaddressesgt"></a><span data-ttu-id="e540f-102">&lt;baseAddresses&gt;</span><span class="sxs-lookup"><span data-stu-id="e540f-102">&lt;baseAddresses&gt;</span></span>
<span data-ttu-id="e540f-103">자체 호스팅 환경의 서비스 호스트에 대한 기준 주소인 `baseAddress` 요소의 컬렉션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e540f-103">Represents a collection of `baseAddress` elements, which are base addresses for a service host in a self-hosted environment.</span></span> <span data-ttu-id="e540f-104">기준 주소가 있는 경우 기준 주소에 대한 상대 주소로 끝점을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e540f-104">If a base address is present, endpoints can be configured with addresses relative to the base address.</span></span>  
  
 <span data-ttu-id="e540f-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e540f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e540f-106">\<클라이언트 ></span><span class="sxs-lookup"><span data-stu-id="e540f-106">\<client></span></span>  
<span data-ttu-id="e540f-107">\<끝점 ></span><span class="sxs-lookup"><span data-stu-id="e540f-107">\<endpoint></span></span>  
<span data-ttu-id="e540f-108">\<호스트 ></span><span class="sxs-lookup"><span data-stu-id="e540f-108">\<host></span></span>  
<span data-ttu-id="e540f-109">\<baseAddresses ></span><span class="sxs-lookup"><span data-stu-id="e540f-109">\<baseAddresses></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e540f-110">구문</span><span class="sxs-lookup"><span data-stu-id="e540f-110">Syntax</span></span>  
  
```xml  
<baseAddresses>  
   <add baseAddress="string" />  
</baseAddresses>  
```  
  
## <a name="type"></a><span data-ttu-id="e540f-111">형식</span><span class="sxs-lookup"><span data-stu-id="e540f-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e540f-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e540f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e540f-113">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e540f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e540f-114">특성</span><span class="sxs-lookup"><span data-stu-id="e540f-114">Attributes</span></span>  
 <span data-ttu-id="e540f-115">없음</span><span class="sxs-lookup"><span data-stu-id="e540f-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e540f-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e540f-116">Child Elements</span></span>  
  
|<span data-ttu-id="e540f-117">요소</span><span class="sxs-lookup"><span data-stu-id="e540f-117">Element</span></span>|<span data-ttu-id="e540f-118">설명</span><span class="sxs-lookup"><span data-stu-id="e540f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e540f-119">\<add></span><span class="sxs-lookup"><span data-stu-id="e540f-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|<span data-ttu-id="e540f-120">서비스 호스트에서 사용하는 기본 주소를 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e540f-120">A configuration element that specifies the base addresses used by the service host.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e540f-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e540f-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e540f-122">요소</span><span class="sxs-lookup"><span data-stu-id="e540f-122">Element</span></span>|<span data-ttu-id="e540f-123">설명</span><span class="sxs-lookup"><span data-stu-id="e540f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e540f-124">\<호스트 ></span><span class="sxs-lookup"><span data-stu-id="e540f-124">\<host></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|<span data-ttu-id="e540f-125">서비스 호스트의 설정을 지정하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e540f-125">A configuration element that specifies settings for a service host.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e540f-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e540f-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [<span data-ttu-id="e540f-127">호스팅</span><span class="sxs-lookup"><span data-stu-id="e540f-127">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
