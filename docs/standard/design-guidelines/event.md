---
title: "이벤트 디자인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pre-events
- events [.NET Framework], design guidelines
- member design guidelines, events
- event handlers [.NET Framework], event design guidelines
- post-events
- signatures, event handling
ms.assetid: 67b3c6e2-6a8f-480d-a78f-ebeeaca1b95a
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a07392ba805b5f2a3913b01a15dd0e1668f0ccf7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="event-design"></a><span data-ttu-id="ae0dc-102">이벤트 디자인</span><span class="sxs-lookup"><span data-stu-id="ae0dc-102">Event Design</span></span>
<span data-ttu-id="ae0dc-103">이벤트는 자주 사용 하는 형식의 콜백 (사용자 코드를 호출 하기 위해 프레임 워크를 사용할 수 있는 구문).</span><span class="sxs-lookup"><span data-stu-id="ae0dc-103">Events are the most commonly used form of callbacks (constructs that allow the framework to call into user code).</span></span> <span data-ttu-id="ae0dc-104">다른 콜백 메커니즘 대리자, 가상 멤버 및 플러그 인 인터페이스 기반 라인으로 전환 하는 구성원을 포함 합니다. 유용성 연구에서 데이터는 대부분의 개발자가 이벤트를 사용 하 여 다른 콜백 메커니즘을 사용 하는 것 보다 더 친숙 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-104">Other callback mechanisms include members taking delegates, virtual members, and interface-based plug-ins. Data from usability studies indicate that the majority of developers are more comfortable using events than they are using the other callback mechanisms.</span></span> <span data-ttu-id="ae0dc-105">이벤트는 Visual Studio 및 많은 언어와 원활 하 게 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-105">Events are nicely integrated with Visual Studio and many languages.</span></span>  
  
 <span data-ttu-id="ae0dc-106">두 그룹의 이벤트는 해야: 사전 이벤트 및 상태가 변경 된 후 발생 한 이벤트를 호출 하는 시스템 변경 내용 상태의 하기 전에 발생 하는 이벤트 후 이벤트를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-106">It is important to note that there are two groups of events: events raised before a state of the system changes, called pre-events, and events raised after a state changes, called post-events.</span></span> <span data-ttu-id="ae0dc-107">사전 이벤트의 예로 들 수 `Form.Closing`, 폼이 닫히기 전에 발생 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-107">An example of a pre-event would be `Form.Closing`, which is raised before a form is closed.</span></span> <span data-ttu-id="ae0dc-108">이후 이벤트의 예로 들 수 `Form.Closed`는 폼이 닫힌 후 발생 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-108">An example of a post-event would be `Form.Closed`, which is raised after a form is closed.</span></span>  
  
 <span data-ttu-id="ae0dc-109">**✓ 않습니다** "발생" 이라는 용어를 사용 하 여 이벤트 보다는 "발생" 시키는"또는"트리거"입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-109">**✓ DO** use the term "raise" for events rather than "fire" or "trigger."</span></span>  
  
 <span data-ttu-id="ae0dc-110">**✓ 않습니다** 사용 <xref:System.EventHandler%601?displayProperty=nameWithType> 수동으로 이벤트 처리기로 사용할 새 대리자를 만드는 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-110">**✓ DO** use <xref:System.EventHandler%601?displayProperty=nameWithType> instead of manually creating new delegates to be used as event handlers.</span></span>  
  
 <span data-ttu-id="ae0dc-111">**✓ 고려** 의 서브 클래스를 사용 하 여 <xref:System.EventArgs> 이벤트 인수로 제외 이벤트 데이터를 이벤트 처리 메서드를 필요가 없습니다 확실히 경우에서 사용할 수 있습니다는 `EventArgs` 직접 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-111">**✓ CONSIDER** using a subclass of <xref:System.EventArgs> as the event argument, unless you are absolutely sure the event will never need to carry any data to the event handling method, in which case you can use the `EventArgs` type directly.</span></span>  
  
 <span data-ttu-id="ae0dc-112">사용 하 여 API를 제공 하는 경우 `EventArgs` 를 직접 하면 안 됩니다 이벤트와 호환성을 중단 하지 않고 실행 될 모든 데이터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-112">If you ship an API using `EventArgs` directly, you will never be able to add any data to be carried with the event without breaking compatibility.</span></span> <span data-ttu-id="ae0dc-113">하위 클래스를 사용 하는 경우에 하는 경우 처음 완전히 비어 있는 됩니다 필요할 때 하위 클래스에 속성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-113">If you use a subclass, even if initially completely empty, you will be able to add properties to the subclass when needed.</span></span>  
  
 <span data-ttu-id="ae0dc-114">**✓ 않습니다** 보호 된 가상 메서드를 사용 하 여 각 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-114">**✓ DO** use a protected virtual method to raise each event.</span></span> <span data-ttu-id="ae0dc-115">만 비정적 이벤트 봉인 되지 않은 클래스, 구조체, 봉인 된 클래스 또는 정적 이벤트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-115">This is only applicable to nonstatic events on unsealed classes, not to structs, sealed classes, or static events.</span></span>  
  
 <span data-ttu-id="ae0dc-116">메서드의 목적은 재정의 사용 하 여 이벤트를 처리 하려면 파생된 클래스에 대 한 방법을 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-116">The purpose of the method is to provide a way for a derived class to handle the event using an override.</span></span> <span data-ttu-id="ae0dc-117">파생된 클래스에서 기본 클래스 이벤트를 처리 하는 보다 유연한 빠르고 더 자연 스러운 방법을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-117">Overriding is a more flexible, faster, and more natural way to handle base class events in derived classes.</span></span> <span data-ttu-id="ae0dc-118">규칙에 따라 메서드의 이름을 "On"로 시작 해야 하 고 이벤트의 이름으로 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-118">By convention, the name of the method should start with "On" and be followed with the name of the event.</span></span>  
  
 <span data-ttu-id="ae0dc-119">파생된 클래스의 재정의 메서드의 기본 구현을 호출 하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-119">The derived class can choose not to call the base implementation of the method in its override.</span></span> <span data-ttu-id="ae0dc-120">가 제대로 작동 하려면 기본 클래스에 대 한 필요 하는 방법에 처리를 포함 하 여이를 준비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-120">Be prepared for this by not including any processing in the method that is required for the base class to work correctly.</span></span>  
  
 <span data-ttu-id="ae0dc-121">**✓ 않습니다** 하나의 매개 변수는 이벤트를 발생 시키는 보호 된 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-121">**✓ DO** take one parameter to the protected method that raises an event.</span></span>  
  
 <span data-ttu-id="ae0dc-122">매개 변수 이름은 `e` 및 이벤트 인수 클래스로 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-122">The parameter should be named `e` and should be typed as the event argument class.</span></span>  
  
 <span data-ttu-id="ae0dc-123">**X 하지 않으면** 비정적 이벤트를 발생 시킬 때 보낸 사람으로 null을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-123">**X DO NOT** pass null as the sender when raising a nonstatic event.</span></span>  
  
 <span data-ttu-id="ae0dc-124">**✓ 않습니다** 정적 이벤트를 발생 시킬 때 보낸 사람으로 null을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-124">**✓ DO** pass null as the sender when raising a static event.</span></span>  
  
 <span data-ttu-id="ae0dc-125">**X 하지 않으면** 이벤트를 발생 시키는 경우 이벤트 데이터 매개 변수와 null을 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-125">**X DO NOT** pass null as the event data parameter when raising an event.</span></span>  
  
 <span data-ttu-id="ae0dc-126">전달 해야 `EventArgs.Empty` 모든 데이터 이벤트 처리 메서드를 전달 하지 않을 경우.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-126">You should pass `EventArgs.Empty` if you don’t want to pass any data to the event handling method.</span></span> <span data-ttu-id="ae0dc-127">개발자는이 매개 변수를 null이 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-127">Developers expect this parameter not to be null.</span></span>  
  
 <span data-ttu-id="ae0dc-128">**✓ 고려** 최종 사용자가 취소할 수 있는 이벤트를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-128">**✓ CONSIDER** raising events that the end user can cancel.</span></span> <span data-ttu-id="ae0dc-129">사전 이벤트에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-129">This only applies to pre-events.</span></span>  
  
 <span data-ttu-id="ae0dc-130">사용 하 여 <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> 또는 최종 사용자 이벤트를 취소할 수 있도록 이벤트 인수로 해당 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-130">Use <xref:System.ComponentModel.CancelEventArgs?displayProperty=nameWithType> or its subclass as the event argument to allow the end user to cancel events.</span></span>  
  
### <a name="custom-event-handler-design"></a><span data-ttu-id="ae0dc-131">사용자 지정 이벤트 처리기 디자인</span><span class="sxs-lookup"><span data-stu-id="ae0dc-131">Custom Event Handler Design</span></span>  
 <span data-ttu-id="ae0dc-132">경우에는 `EventHandler<T>` 같은 프레임 워크를 제네릭을 지원 하지 않는 CLR의 이전 버전을 사용 해야 하는 경우 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-132">There are cases in which `EventHandler<T>` cannot be used, such as when the framework needs to work with earlier versions of the CLR, which did not support Generics.</span></span> <span data-ttu-id="ae0dc-133">이러한 경우를 디자인 하 고 사용자 지정 이벤트 처리기 대리자를 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-133">In such cases, you might need to design and develop a custom event handler delegate.</span></span>  
  
 <span data-ttu-id="ae0dc-134">**✓ 않습니다** 이벤트 처리기에 대 한 void의 반환 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-134">**✓ DO** use a return type of void for event handlers.</span></span>  
  
 <span data-ttu-id="ae0dc-135">이벤트 처리기에 여러 이벤트 처리 여러 개체에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-135">An event handler can invoke multiple event handling methods, possibly on multiple objects.</span></span> <span data-ttu-id="ae0dc-136">이벤트 처리 메서드는 값을 반환 하도록 허용 된, 각 이벤트 호출에 대해 여러 개의 반환 값 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-136">If event handling methods were allowed to return a value, there would be multiple return values for each event invocation.</span></span>  
  
 <span data-ttu-id="ae0dc-137">**✓ 않습니다** 사용 `object` 이벤트 처리기의 첫 번째 매개 변수 형식으로 버전을 호출 `sender`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-137">**✓ DO** use `object` as the type of the first parameter of the event handler, and call it `sender`.</span></span>  
  
 <span data-ttu-id="ae0dc-138">**✓ 않습니다** 사용 <xref:System.EventArgs?displayProperty=nameWithType> 또는 해당 하위 클래스의 이벤트 처리기의 두 번째 매개 변수 형식으로 버전을 호출 `e`합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-138">**✓ DO** use <xref:System.EventArgs?displayProperty=nameWithType> or its subclass as the type of the second parameter of the event handler, and call it `e`.</span></span>  
  
 <span data-ttu-id="ae0dc-139">**X 하지 않으면** 이벤트 처리기에 두 개 이상의 매개 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae0dc-139">**X DO NOT** have more than two parameters on event handlers.</span></span>  
  
 <span data-ttu-id="ae0dc-140">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="ae0dc-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ae0dc-141">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="ae0dc-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae0dc-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae0dc-142">See Also</span></span>  
 [<span data-ttu-id="ae0dc-143">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ae0dc-143">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="ae0dc-144">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ae0dc-144">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
