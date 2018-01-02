---
title: '&lt;clientVia&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7a1870a8c331aae16ab14da62c64d6fb15ecd3bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltclientviagt"></a><span data-ttu-id="6c921-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="6c921-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="6c921-103">전송 채널을 만들어야 하는 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c921-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="6c921-104">자세한 내용은 <xref:System.ServiceModel.Description.ClientViaBehavior>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c921-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="6c921-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6c921-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="6c921-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="6c921-106">\<behaviors></span></span>  
<span data-ttu-id="6c921-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6c921-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="6c921-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="6c921-108">\<behavior></span></span>  
<span data-ttu-id="6c921-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="6c921-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c921-110">구문</span><span class="sxs-lookup"><span data-stu-id="6c921-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c921-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6c921-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6c921-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6c921-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c921-113">특성</span><span class="sxs-lookup"><span data-stu-id="6c921-113">Attributes</span></span>  
  
|<span data-ttu-id="6c921-114">특성</span><span class="sxs-lookup"><span data-stu-id="6c921-114">Attribute</span></span>|<span data-ttu-id="6c921-115">설명</span><span class="sxs-lookup"><span data-stu-id="6c921-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="6c921-116">메시지가 이동할 경로를 나타내는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6c921-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6c921-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6c921-117">Child Elements</span></span>  
 <span data-ttu-id="6c921-118">없음</span><span class="sxs-lookup"><span data-stu-id="6c921-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6c921-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6c921-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6c921-120">요소</span><span class="sxs-lookup"><span data-stu-id="6c921-120">Element</span></span>|<span data-ttu-id="6c921-121">설명</span><span class="sxs-lookup"><span data-stu-id="6c921-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c921-122">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="6c921-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6c921-123">끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c921-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c921-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c921-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
