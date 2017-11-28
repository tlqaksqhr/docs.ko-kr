---
title: "&lt;동작&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b38b27a7b196026e2ff873c7748ed46b96ba9b2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltbehaviorsgt"></a><span data-ttu-id="7034d-102">&lt;동작&gt;</span><span class="sxs-lookup"><span data-stu-id="7034d-102">&lt;behaviors&gt;</span></span>
<span data-ttu-id="7034d-103">이 요소는 이름이 `endpointBehaviors` 및 `serviceBehaviors`인 두 개의 자식 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-103">This element defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="7034d-104">각 컬렉션은 끝점 및 서비스가 사용하는 동작 요소를 각각 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-104">Each collection defines behavior elements consumed by endpoints and services respectively.</span></span> <span data-ttu-id="7034d-105">각 동작 요소는 고유한 `name` 특성으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-105">Each behavior element is identified by its unique `name` attribute.</span></span> <span data-ttu-id="7034d-106">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="7034d-107">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
 <span data-ttu-id="7034d-108">\<시스템입니다. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7034d-108">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7034d-109">구문</span><span class="sxs-lookup"><span data-stu-id="7034d-109">Syntax</span></span>  
  
```xml  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7034d-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7034d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7034d-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7034d-112">특성</span><span class="sxs-lookup"><span data-stu-id="7034d-112">Attributes</span></span>  
 <span data-ttu-id="7034d-113">없음</span><span class="sxs-lookup"><span data-stu-id="7034d-113">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7034d-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7034d-114">Child Elements</span></span>  
  
|<span data-ttu-id="7034d-115">요소</span><span class="sxs-lookup"><span data-stu-id="7034d-115">Element</span></span>|<span data-ttu-id="7034d-116">설명</span><span class="sxs-lookup"><span data-stu-id="7034d-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7034d-117">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7034d-117">\<endpointBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|<span data-ttu-id="7034d-118">이 구성 섹션은 특정 끝점에 정의된 모든 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-118">This configuration section represents all the behaviors defined for a specific endpoint.</span></span>|  
|[<span data-ttu-id="7034d-119">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="7034d-119">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|<span data-ttu-id="7034d-120">이 구성 섹션은 특정 서비스에 정의된 모든 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-120">This configuration section represents all the behaviors defined for a specific service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7034d-121">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7034d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="7034d-122">요소</span><span class="sxs-lookup"><span data-stu-id="7034d-122">Element</span></span>|<span data-ttu-id="7034d-123">설명</span><span class="sxs-lookup"><span data-stu-id="7034d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7034d-124">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7034d-124">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="7034d-125">모든 WCF(Windows Communication Foundation) 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-125">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7034d-126">설명</span><span class="sxs-lookup"><span data-stu-id="7034d-126">Remarks</span></span>  
 <span data-ttu-id="7034d-127">`<remove>` 요소를 사용하여 컬렉션에서 특정 동작을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-127">You can use the `<remove>` element to remove a particular behavior from the collection.</span></span> <span data-ttu-id="7034d-128">이렇게 하려면 제거할 동작의 이름을 `name` 요소의 `<remove>` 특성에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-128">To do so, simply supply the name of the behavior to remove in the `name` attribute of the `<remove>` element.</span></span>  <span data-ttu-id="7034d-129">`<clear>` 요소를 사용하여 컬렉션의 모든 내용을 지워 동작 컬렉션이 비어 있는 상태로 시작되도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7034d-129">You can also use the `<clear>` element to insure that a behavior collection starts empty by clearing out all the content of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7034d-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7034d-130">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>  
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>  
 [<span data-ttu-id="7034d-131">구성 하 고 런타임 동작을 확장</span><span class="sxs-lookup"><span data-stu-id="7034d-131">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 [<span data-ttu-id="7034d-132">클라이언트 동작 구성</span><span class="sxs-lookup"><span data-stu-id="7034d-132">Configuring Client Behaviors</span></span>](../../../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [<span data-ttu-id="7034d-133">클라이언트 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="7034d-133">Specifying Client Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)  
 [<span data-ttu-id="7034d-134">서비스 런타임 동작 지정</span><span class="sxs-lookup"><span data-stu-id="7034d-134">Specifying Service Run-Time Behavior</span></span>](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)  
 [<span data-ttu-id="7034d-135">보안 동작</span><span class="sxs-lookup"><span data-stu-id="7034d-135">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
