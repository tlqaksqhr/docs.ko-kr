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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7cdc85c23202154728610ab4721bf830004928c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltclientviagt"></a><span data-ttu-id="f5897-102">&lt;clientVia&gt;</span><span class="sxs-lookup"><span data-stu-id="f5897-102">&lt;clientVia&gt;</span></span>
<span data-ttu-id="f5897-103">전송 채널을 만들어야 하는 URI를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5897-103">Specifies the URI for which the transport channel should be created.</span></span> <span data-ttu-id="f5897-104">자세한 내용은 <xref:System.ServiceModel.Description.ClientViaBehavior>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5897-104">For more information, see <xref:System.ServiceModel.Description.ClientViaBehavior>.</span></span>  
  
 <span data-ttu-id="f5897-105">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f5897-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="f5897-106">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="f5897-106">\<behaviors></span></span>  
<span data-ttu-id="f5897-107">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f5897-107">\<endpointBehaviors></span></span>  
<span data-ttu-id="f5897-108">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="f5897-108">\<behavior></span></span>  
<span data-ttu-id="f5897-109">\<clientVia ></span><span class="sxs-lookup"><span data-stu-id="f5897-109">\<clientVia></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5897-110">구문</span><span class="sxs-lookup"><span data-stu-id="f5897-110">Syntax</span></span>  
  
```xml  
<clientVia viaUri="String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5897-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f5897-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f5897-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5897-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5897-113">특성</span><span class="sxs-lookup"><span data-stu-id="f5897-113">Attributes</span></span>  
  
|<span data-ttu-id="f5897-114">특성</span><span class="sxs-lookup"><span data-stu-id="f5897-114">Attribute</span></span>|<span data-ttu-id="f5897-115">설명</span><span class="sxs-lookup"><span data-stu-id="f5897-115">Description</span></span>|  
|---------------|-----------------|  
|`viaUri`|<span data-ttu-id="f5897-116">메시지가 이동할 경로를 나타내는 URI를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f5897-116">A string that specifies a URI that indicates the route a message should take.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5897-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f5897-117">Child Elements</span></span>  
 <span data-ttu-id="f5897-118">없음</span><span class="sxs-lookup"><span data-stu-id="f5897-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5897-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f5897-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f5897-120">요소</span><span class="sxs-lookup"><span data-stu-id="f5897-120">Element</span></span>|<span data-ttu-id="f5897-121">설명</span><span class="sxs-lookup"><span data-stu-id="f5897-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5897-122">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="f5897-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="f5897-123">끝점 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5897-123">Specifies an endpoint behavior.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5897-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5897-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
