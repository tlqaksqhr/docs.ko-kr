---
title: "&lt;serviceBehavior&gt;의 &lt;routing&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8f9c844-4629-4a45-9599-856dc8f01794
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4e5c27b2b276e6659680dabfd9460c6d072bad3a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltroutinggt-of-ltservicebehaviorgt"></a><span data-ttu-id="bfa4d-102">&lt;serviceBehavior&gt;의 &lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="bfa4d-102">&lt;routing&gt; of &lt;serviceBehavior&gt;</span></span>
<span data-ttu-id="bfa4d-103">라우팅 서비스에 대한 런타임 액세스를 제공하여 라우팅 구성의 동적 수정을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-103">Provides run-time access to the routing service to allow dynamic modification of the routing configuration.</span></span>  
  
 <span data-ttu-id="bfa4d-104">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="bfa4d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bfa4d-105">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="bfa4d-105">\<behaviors></span></span>  
<span data-ttu-id="bfa4d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="bfa4d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bfa4d-107">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="bfa4d-107">\<behavior></span></span>  
<span data-ttu-id="bfa4d-108">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="bfa4d-108">\<routing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa4d-109">구문</span><span class="sxs-lookup"><span data-stu-id="bfa4d-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <routing filterTable="String" 
               routeOnHeadersOnly="Boolean" 
               SoapProcessingEnabled="Boolean" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfa4d-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bfa4d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bfa4d-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfa4d-112">특성</span><span class="sxs-lookup"><span data-stu-id="bfa4d-112">Attributes</span></span>  
  
|<span data-ttu-id="bfa4d-113">특성</span><span class="sxs-lookup"><span data-stu-id="bfa4d-113">Attribute</span></span>|<span data-ttu-id="bfa4d-114">설명</span><span class="sxs-lookup"><span data-stu-id="bfa4d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bfa4d-115">filterTable</span><span class="sxs-lookup"><span data-stu-id="bfa4d-115">filterTable</span></span>|<span data-ttu-id="bfa4d-116">라우팅 서비스에서 평가할 필터를 포함하는 라우팅 테이블의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-116">A string that specifies the name of the routing table that contains filters to be evaluated by the routing service.</span></span> <span data-ttu-id="bfa4d-117">이 값과 일치 해야는 `name` 특성에는 [ \<filterTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) 요소에는 [ \<filterTables >](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) 섹션.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-117">This value must match the `name` attribute of a [\<filterTable>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertable.md) element in the [\<filterTables>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) section.</span></span>|  
|<span data-ttu-id="bfa4d-118">routeOnHeaderOnly</span><span class="sxs-lookup"><span data-stu-id="bfa4d-118">routeOnHeaderOnly</span></span>|<span data-ttu-id="bfa4d-119">필터를 사용하여 메시지 본문과 헤더를 모두 검사할지 또는 헤더만 검사할지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-119">A Boolean value that specifies whether the filter will examine both the message body and the header, or the header only.</span></span> <span data-ttu-id="bfa4d-120">기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-120">The default is `true`.</span></span>|  
|<span data-ttu-id="bfa4d-121">soapProcessingEnabled</span><span class="sxs-lookup"><span data-stu-id="bfa4d-121">soapProcessingEnabled</span></span>|<span data-ttu-id="bfa4d-122">SOAP 처리가 발생해야 하는지 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-122">A Boolean value that specifies whether SOAP processing should occur.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfa4d-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bfa4d-123">Child Elements</span></span>  
 <span data-ttu-id="bfa4d-124">없음</span><span class="sxs-lookup"><span data-stu-id="bfa4d-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bfa4d-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bfa4d-125">Parent Elements</span></span>  
  
|<span data-ttu-id="bfa4d-126">요소</span><span class="sxs-lookup"><span data-stu-id="bfa4d-126">Element</span></span>|<span data-ttu-id="bfa4d-127">설명</span><span class="sxs-lookup"><span data-stu-id="bfa4d-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bfa4d-128">\<동작 ></span><span class="sxs-lookup"><span data-stu-id="bfa4d-128">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="bfa4d-129">동작 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-129">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfa4d-130">설명</span><span class="sxs-lookup"><span data-stu-id="bfa4d-130">Remarks</span></span>  
 <span data-ttu-id="bfa4d-131">이 구성 요소가 서비스 동작 구성에 추가되면 서비스에 대한 라우팅을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-131">When added to the service’s behavior configuration, this configuration element enables routing for the service.</span></span> <span data-ttu-id="bfa4d-132">서비스에서 실제로 사용할 라우팅 테이블을 이 요소에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-132">You can specify the actual routing table to be used by the service in this element.</span></span>  
  
 <span data-ttu-id="bfa4d-133">이 구성 섹션을 사용하여 배포 패턴이 변경되는 경우 즉시 라우팅 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-133">Using this configuration section, you can change your routing settings on the fly when your deployment pattern changes.</span></span> <span data-ttu-id="bfa4d-134">런타임에 새로운 라우팅 설정을 사용하여 직접 작성한 라우팅 확장을 등록할 수 있습니다. 이렇게 하면 진행 중인 메시지/세션은 시작 시 적용되었던 규칙을 사용하여 그대로 유지하면서 새로운 메시지 및 세션에 업데이트된 구성 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-134">At runtime, you can register your own routing extension with new routing settings and the routing service will begin using the updated configuration information for new messages and sessions, while leaving in-flight messages/sessions using whatever rules were in place when they started.</span></span>  <span data-ttu-id="bfa4d-135">따라서 런타임 동안 라우팅 서비스를 세션에 관계없이 재활용을 줄이면서 재구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfa4d-135">This gives you the ability to do session-safe, recycle-less reconfiguration of the Routing Service during runtime.</span></span>  
  
