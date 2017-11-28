---
title: '&lt;a d d&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0e127935977795181411dfa6b03d8b09fe88e0f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="0962e-102">&lt;a d d&gt;</span><span class="sxs-lookup"><span data-stu-id="0962e-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="0962e-103">클라이언트 응용 프로그램에서 수신하는 기본 통신 끝점을 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0962e-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="0962e-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="0962e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0962e-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0962e-105">\<behaviors></span></span>  
<span data-ttu-id="0962e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0962e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0962e-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="0962e-107">\<behavior></span></span>  
<span data-ttu-id="0962e-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="0962e-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="0962e-109">\<a d d ></span><span class="sxs-lookup"><span data-stu-id="0962e-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0962e-110">구문</span><span class="sxs-lookup"><span data-stu-id="0962e-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0962e-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0962e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0962e-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0962e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0962e-113">특성</span><span class="sxs-lookup"><span data-stu-id="0962e-113">Attributes</span></span>  
 <span data-ttu-id="0962e-114">없음</span><span class="sxs-lookup"><span data-stu-id="0962e-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0962e-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0962e-115">Child Elements</span></span>  
  
|<span data-ttu-id="0962e-116">요소</span><span class="sxs-lookup"><span data-stu-id="0962e-116">Element</span></span>|<span data-ttu-id="0962e-117">설명</span><span class="sxs-lookup"><span data-stu-id="0962e-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0962e-118">\<추가 >의 \<a d d ></span><span class="sxs-lookup"><span data-stu-id="0962e-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="0962e-119">클라이언트 응용 프로그램에서 수신하는 기본 통신 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="0962e-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0962e-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0962e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="0962e-121">요소</span><span class="sxs-lookup"><span data-stu-id="0962e-121">Element</span></span>|<span data-ttu-id="0962e-122">설명</span><span class="sxs-lookup"><span data-stu-id="0962e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0962e-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="0962e-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="0962e-124">기본 포트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="0962e-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0962e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0962e-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
