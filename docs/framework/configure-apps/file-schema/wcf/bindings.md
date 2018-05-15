---
title: '&lt;바인딩&gt;'
ms.date: 03/30/2017
ms.assetid: b62cd369-5409-4030-8490-9759a462dd3a
ms.openlocfilehash: 76ebd7c317bf5f0aa1ec02d4014235df232314f0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltbindingsgt"></a><span data-ttu-id="38753-102">&lt;바인딩&gt;</span><span class="sxs-lookup"><span data-stu-id="38753-102">&lt;bindings&gt;</span></span>
<span data-ttu-id="38753-103">이 섹션에는 표준 및 사용자 지정 바인딩 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="38753-103">This section holds a collection of standard and custom bindings.</span></span> <span data-ttu-id="38753-104">각 항목은 고유한 `binding`으로 식별될 수 있는 `name` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="38753-104">Each entry is a `binding` element that can be identified by its unique `name`.</span></span> <span data-ttu-id="38753-105">서비스에서는 `name`을 통해 바인딩을 연결하여 바인딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-105">Services use bindings by linking them using the `name`.</span></span> <span data-ttu-id="38753-106">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38753-106">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="38753-107">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-107">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="38753-108">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="38753-108">System-Provided Binding</span></span>  
 <span data-ttu-id="38753-109">시스템 제공 바인딩은 WCF 메시지 스택의 복잡성을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="38753-109">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="38753-110">시스템 제공 바인딩을 사용하는 응용 프로그램은 스택을 완전히 제어할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38753-110">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="38753-111">각 시스템 제공 바인딩에는 바인딩이 처리하는 사용 시나리오에 가장 적합한 특성이 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="38753-111">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="38753-112">각 시스템 제공 바인딩의 구성 섹션은 바인딩 구성에 사용되는 일부 구성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38753-112">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="38753-113">각 구성은 고유한 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="38753-113">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="38753-114">시스템 제공 바인딩에는 요소나 특성을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38753-114">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="38753-115">이렇게 하려면 이 항목의 "사용자 지정 바인딩" 섹션에 설명된 것처럼 사용자 지정 바인딩을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-115">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="38753-116">시스템 제공 바인딩과 완전히 같으며 사용자 응용 프로그램이 제어하려는 몇 가지 설정을 추가로 제공하는 사용자 지정 바인딩을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38753-116">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
 <span data-ttu-id="38753-117">시스템 제공 바인딩 목록, 참조 [시스템 제공 바인딩](../../../../../docs/framework/wcf/system-provided-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-117">For a list of system-provided bindings, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="38753-118">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="38753-118">Custom Binding</span></span>  
 <span data-ttu-id="38753-119">사용자 지정 바인딩은 WCF 메시징 스택에 대한 모든 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-119">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="38753-120">개별 바인딩에서는 스택에 나타나는 순서대로 스택 요소의 구성 요소를 지정함으로써 메시지 스택을 정의하며,</span><span class="sxs-lookup"><span data-stu-id="38753-120">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="38753-121">각 요소는 스택의 한 요소를 정의하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-121">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="38753-122">각 사용자 지정 바인딩에는 `transport` 요소가 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-122">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="38753-123">이 요소가 없으면 메시징 스택이 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38753-123">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="38753-124">스택에서 요소가 나타나는 순서는 작업이 메시지에 적용되는 순서이므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-124">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="38753-125">다음과 같은 스택 요소 순서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-125">The required order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="38753-126">Transactions(선택적)</span><span class="sxs-lookup"><span data-stu-id="38753-126">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="38753-127">Reliable Messaging(선택적)</span><span class="sxs-lookup"><span data-stu-id="38753-127">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="38753-128">Security(선택적)</span><span class="sxs-lookup"><span data-stu-id="38753-128">Security (optional)</span></span>  
  
4.  <span data-ttu-id="38753-129">인코더</span><span class="sxs-lookup"><span data-stu-id="38753-129">Encoder</span></span>  
  
5.  <span data-ttu-id="38753-130">전송</span><span class="sxs-lookup"><span data-stu-id="38753-130">Transport</span></span>  
  
 <span data-ttu-id="38753-131">사용자 지정 바인딩은 `name` 특성으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="38753-131">Custom bindings are identified by their `name` attribute.</span></span> <span data-ttu-id="38753-132">사용자 지정 바인딩에 대 한 자세한 내용은 참조 하십시오. [사용자 지정 바인딩을](../../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="38753-132">For more information on custom bindings, see [Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38753-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38753-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [<span data-ttu-id="38753-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="38753-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="38753-135">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="38753-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="38753-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="38753-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="38753-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="38753-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
