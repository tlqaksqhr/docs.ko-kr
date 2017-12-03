---
title: '&lt;serviceTimeouts&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ada536cf-97dc-4cd7-89ec-ed1466c1c557
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6d2940a4c4615a922efcc74802a82adbe10267c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicetimeoutsgt"></a><span data-ttu-id="a1c46-102">&lt;serviceTimeouts&gt;</span><span class="sxs-lookup"><span data-stu-id="a1c46-102">&lt;serviceTimeouts&gt;</span></span>
<span data-ttu-id="a1c46-103">서비스에 대한 제한 시간을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-103">Specifies the timeout for a service.</span></span>  
  
 <span data-ttu-id="a1c46-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a1c46-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a1c46-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="a1c46-105">\<behaviors></span></span>  
<span data-ttu-id="a1c46-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a1c46-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="a1c46-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="a1c46-107">\<behavior></span></span>  
<span data-ttu-id="a1c46-108">\<serviceTimeouts ></span><span class="sxs-lookup"><span data-stu-id="a1c46-108">\<serviceTimeouts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c46-109">구문</span><span class="sxs-lookup"><span data-stu-id="a1c46-109">Syntax</span></span>  
  
```xml  
<serviceTimeouts transactionTimeout="TimeSpan" />  
```  
  
## <a name="type"></a><span data-ttu-id="a1c46-110">형식</span><span class="sxs-lookup"><span data-stu-id="a1c46-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1c46-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a1c46-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a1c46-112">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1c46-113">특성</span><span class="sxs-lookup"><span data-stu-id="a1c46-113">Attributes</span></span>  
  
|<span data-ttu-id="a1c46-114">특성</span><span class="sxs-lookup"><span data-stu-id="a1c46-114">Attribute</span></span>|<span data-ttu-id="a1c46-115">설명</span><span class="sxs-lookup"><span data-stu-id="a1c46-115">Description</span></span>|  
|---------------|-----------------|  
|`transactionTimeout`|<span data-ttu-id="a1c46-116">클라이언트에서 서버로 트랜잭션을 전달해야 하는 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-116">A <xref:System.TimeSpan> value that specifies the interval of time a transaction must flow from client to server.</span></span> <span data-ttu-id="a1c46-117">기본값은 "00: 00:00"입니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-117">The default is "00:00:00".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1c46-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a1c46-118">Child Elements</span></span>  
 <span data-ttu-id="a1c46-119">없음</span><span class="sxs-lookup"><span data-stu-id="a1c46-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1c46-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a1c46-120">Parent Elements</span></span>  
  
|<span data-ttu-id="a1c46-121">요소</span><span class="sxs-lookup"><span data-stu-id="a1c46-121">Element</span></span>|<span data-ttu-id="a1c46-122">설명</span><span class="sxs-lookup"><span data-stu-id="a1c46-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1c46-123">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="a1c46-123">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="a1c46-124">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c46-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1c46-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1c46-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
