---
title: "&lt;바인딩&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 666183d6-4d1f-45c7-ac64-bdf93ee8f36f
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 874a3766a64a9abb7c35efd5ac0a0f698707281e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltbindinggt"></a><span data-ttu-id="17feb-102">&lt;바인딩&gt;</span><span class="sxs-lookup"><span data-stu-id="17feb-102">&lt;binding&gt;</span></span>
<span data-ttu-id="17feb-103">`binding` 요소를 사용하여 WCF(Windows Communication Foundation)에서 제공하는 미리 정의된 다양한 바인딩 형식을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-103">You can use the `binding` element to configure different types of predefined bindings provided by Windows Communication Foundation (WCF).</span></span>  
  
## <a name="system-provided-binding"></a><span data-ttu-id="17feb-104">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="17feb-104">System-Provided Binding</span></span>  
 <span data-ttu-id="17feb-105">시스템 제공 바인딩은 WCF 메시지 스택의 복잡성을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-105">System-provided bindings hide the complexity of the WCF messaging stack.</span></span> <span data-ttu-id="17feb-106">시스템 제공 바인딩을 사용하는 응용 프로그램은 스택을 완전히 제어할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-106">Applications using system-provided bindings do not require full control over the stack.</span></span> <span data-ttu-id="17feb-107">각 시스템 제공 바인딩에는 바인딩이 처리하는 사용 시나리오에 가장 적합한 특성이 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-107">The attributes exposed on each system-provided binding are the ones most appropriate for the usage scenario the binding addresses.</span></span>  
  
 <span data-ttu-id="17feb-108">각 시스템 제공 바인딩의 구성 섹션은 바인딩 구성에 사용되는 일부 구성을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-108">The configuration section for each system-provided binding can define several configurations used to configure the binding.</span></span> <span data-ttu-id="17feb-109">각 구성은 고유한 이름으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-109">Each configuration is identified by a unique name.</span></span>  
  
 <span data-ttu-id="17feb-110">시스템 제공 바인딩에는 요소나 특성을 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-110">It is not possible to add elements or attributes to a system-provided binding.</span></span> <span data-ttu-id="17feb-111">이렇게 하려면 이 항목의 "사용자 지정 바인딩" 섹션에 설명된 것처럼 사용자 지정 바인딩을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-111">To do so, you should implement a custom binding as described in the "Custom Binding" section of this topic.</span></span> <span data-ttu-id="17feb-112">시스템 제공 바인딩과 완전히 같으며 사용자 응용 프로그램이 제어하려는 몇 가지 설정을 추가로 제공하는 사용자 지정 바인딩을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-112">It is possible to define a custom binding that mimics a system-provided binding perfectly and adds a few settings the user application wants to have control over.</span></span>  
  
## <a name="custom-binding"></a><span data-ttu-id="17feb-113">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="17feb-113">Custom Binding</span></span>  
 <span data-ttu-id="17feb-114">사용자 지정 바인딩은 WCF 메시징 스택에 대한 모든 권한을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-114">Custom bindings provide full control over the WCF messaging stack.</span></span> <span data-ttu-id="17feb-115">개별 바인딩에서는 스택에 나타나는 순서대로 스택 요소의 구성 요소를 지정함으로써 메시지 스택을 정의하며,</span><span class="sxs-lookup"><span data-stu-id="17feb-115">An individual binding defines the message stack by specifying the configuration elements for the stack elements in the order they appear on the stack.</span></span> <span data-ttu-id="17feb-116">각 요소는 스택의 한 요소를 정의하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-116">Each element defines and configures the one element of the stack.</span></span> <span data-ttu-id="17feb-117">각 사용자 지정 바인딩에는 `transport` 요소가 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-117">There must be one and only one `transport` element in each custom binding.</span></span> <span data-ttu-id="17feb-118">이 요소가 없으면 메시징 스택이 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-118">Without this element, the messaging stack is incomplete.</span></span>  
  
 <span data-ttu-id="17feb-119">스택에서 요소가 나타나는 순서는 작업이 메시지에 적용되는 순서이므로 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-119">The order in which elements appear in the stack matters, because it is the order in which operations are applied to the message.</span></span> <span data-ttu-id="17feb-120">다음과 같은 스택 요소 순서를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-120">The recommended order of stack elements is the following:</span></span>  
  
1.  <span data-ttu-id="17feb-121">Transactions(선택적)</span><span class="sxs-lookup"><span data-stu-id="17feb-121">Transactions (optional)</span></span>  
  
2.  <span data-ttu-id="17feb-122">Reliable Messaging(선택적)</span><span class="sxs-lookup"><span data-stu-id="17feb-122">Reliable Messaging (optional)</span></span>  
  
3.  <span data-ttu-id="17feb-123">Security(선택적)</span><span class="sxs-lookup"><span data-stu-id="17feb-123">Security (optional)</span></span>  
  
4.  <span data-ttu-id="17feb-124">인코더</span><span class="sxs-lookup"><span data-stu-id="17feb-124">Encoder</span></span>  
  
5.  <span data-ttu-id="17feb-125">전송</span><span class="sxs-lookup"><span data-stu-id="17feb-125">Transport</span></span>  
  
 <span data-ttu-id="17feb-126">사용자 지정 바인딩은 `name` 특성으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="17feb-126">Custom bindings are identified by their `name` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17feb-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17feb-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BindingsSection>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 [<span data-ttu-id="17feb-128">바인딩</span><span class="sxs-lookup"><span data-stu-id="17feb-128">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="17feb-129">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="17feb-129">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="17feb-130">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="17feb-130">\<customBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
