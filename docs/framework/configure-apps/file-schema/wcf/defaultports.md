---
title: '&lt;a d d&gt;'
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 2f7de066a1b91e9fa22fbe0213e221c6f4bbe617
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747176"
---
# <a name="ltdefaultportsgt"></a><span data-ttu-id="f04d2-102">&lt;a d d&gt;</span><span class="sxs-lookup"><span data-stu-id="f04d2-102">&lt;defaultPorts&gt;</span></span>
<span data-ttu-id="f04d2-103">클라이언트 응용 프로그램에서 수신하는 기본 통신 끝점을 나열하는 기본 포트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f04d2-103">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="f04d2-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f04d2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f04d2-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="f04d2-105">\<behaviors></span></span>  
<span data-ttu-id="f04d2-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f04d2-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f04d2-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="f04d2-107">\<behavior></span></span>  
<span data-ttu-id="f04d2-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="f04d2-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="f04d2-109">\<a d d ></span><span class="sxs-lookup"><span data-stu-id="f04d2-109">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f04d2-110">구문</span><span class="sxs-lookup"><span data-stu-id="f04d2-110">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http" port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f04d2-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f04d2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f04d2-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f04d2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f04d2-113">특성</span><span class="sxs-lookup"><span data-stu-id="f04d2-113">Attributes</span></span>  
 <span data-ttu-id="f04d2-114">없음</span><span class="sxs-lookup"><span data-stu-id="f04d2-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f04d2-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f04d2-115">Child Elements</span></span>  
  
|<span data-ttu-id="f04d2-116">요소</span><span class="sxs-lookup"><span data-stu-id="f04d2-116">Element</span></span>|<span data-ttu-id="f04d2-117">설명</span><span class="sxs-lookup"><span data-stu-id="f04d2-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f04d2-118">\<추가 >의 \<a d d ></span><span class="sxs-lookup"><span data-stu-id="f04d2-118">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="f04d2-119">클라이언트 응용 프로그램에서 수신하는 기본 통신 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="f04d2-119">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f04d2-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f04d2-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f04d2-121">요소</span><span class="sxs-lookup"><span data-stu-id="f04d2-121">Element</span></span>|<span data-ttu-id="f04d2-122">설명</span><span class="sxs-lookup"><span data-stu-id="f04d2-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f04d2-123">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="f04d2-123">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="f04d2-124">기본 포트의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f04d2-124">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f04d2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f04d2-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
