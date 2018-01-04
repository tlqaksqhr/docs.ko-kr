---
title: "약한 이벤트 패턴"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21a36797f945f37a641e7002bbb9937a664650fd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="weak-event-patterns"></a><span data-ttu-id="4f2d2-102">약한 이벤트 패턴</span><span class="sxs-lookup"><span data-stu-id="4f2d2-102">Weak Event Patterns</span></span>
<span data-ttu-id="4f2d2-103">응용 프로그램에서 있기 이벤트 소스에 연결 된 처리기를 조정 하 여 처리기는 소스에 연결 하는 수신기 개체 소멸 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-103">In applications, it is possible that handlers that are attached to event sources will not be destroyed in coordination with the listener object that attached the handler to the source.</span></span> <span data-ttu-id="4f2d2-104">이 경우 메모리 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-104">This situation can lead to memory leaks.</span></span> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="4f2d2-105">특정 이벤트에 대 한 전용된 관리자 클래스를 제공 하 고 해당 이벤트에 대 한 수신기에 인터페이스를 구현 하 여이 문제를 해결 하는 데 사용할 수 있는 디자인 패턴을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-105"> introduces a design pattern that can be used to address this issue, by providing a dedicated manager class for particular events and implementing an interface on listeners for that event.</span></span> <span data-ttu-id="4f2d2-106">이 디자인 패턴 이라고는 *취약 한 이벤트 패턴*합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-106">This design pattern is known as the *weak event pattern*.</span></span>  
  
## <a name="why-implement-the-weak-event-pattern"></a><span data-ttu-id="4f2d2-107">취약 한 이벤트 패턴을 구현 하는 이유</span><span class="sxs-lookup"><span data-stu-id="4f2d2-107">Why Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="4f2d2-108">이벤트를 수신 대기 메모리 누수 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-108">Listening for events can lead to memory leaks.</span></span> <span data-ttu-id="4f2d2-109">이벤트를 수신 하는 일반적인 방법 처리기 이벤트 소스에 연결 하는 언어 관련 구문을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-109">The typical technique for listening to an event is to use the language-specific syntax that attaches a handler to an event on a source.</span></span> <span data-ttu-id="4f2d2-110">예를 들어 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], 구문이 않은: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-110">For example, in [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], that syntax is: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`.</span></span>  
  
 <span data-ttu-id="4f2d2-111">이 기술은 이벤트 소스에서 이벤트 수신기에 강력한 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-111">This technique creates a strong reference from the event source to the event listener.</span></span> <span data-ttu-id="4f2d2-112">일반적으로 수신기에 대 한 이벤트 처리기를 연결 하면 해당 수신기는 영향을 원본 개체 수명 (이벤트 처리기가 명시적으로 제거) 하는 개체 수명이 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-112">Ordinarily, attaching an event handler for a listener causes the listener to have an object lifetime that is influenced by the object lifetime of the source (unless the event handler is explicitly removed).</span></span> <span data-ttu-id="4f2d2-113">하지만 속해 있는지 여부 현재 소스의 수명이 아니라에 응용 프로그램의 시각적 트리 같은 개체 수명에 대 한 다른 요인에 의해 제어 수신기의 하려는 특정 상황에서는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-113">But in certain circumstances, you might want the object lifetime of the listener to be controlled by other factors, such as whether it currently belongs to the visual tree of the application, and not by the lifetime of the source.</span></span> <span data-ttu-id="4f2d2-114">메모리 누수 일반 이벤트 패턴으로 인해 소스 개체 수명 수신기의 개체 수명을 넘어가는, 때마다: 수신기 예정 보다 더 이상 활성 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-114">Whenever the source object lifetime extends beyond the object lifetime of the listener, the normal event pattern leads to a memory leak: the listener is kept alive longer than intended.</span></span>  
  
 <span data-ttu-id="4f2d2-115">취약 한 이벤트 패턴이 메모리 누수 문제를 해결 하기 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-115">The weak event pattern is designed to solve this memory leak problem.</span></span> <span data-ttu-id="4f2d2-116">수신기는 이벤트에 대 한 등록 해야 하지만 수신기 명시적으로 알지 못하는 등록을 취소 하는 경우 때마다 취약 한 이벤트 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-116">The weak event pattern can be used whenever a listener needs to register for an event, but the listener does not explicitly know when to unregister.</span></span> <span data-ttu-id="4f2d2-117">소스 개체 수명 수신기의 적절 한 개체 수명 초과할 때마다 취약 한 이벤트 패턴을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-117">The weak event pattern can also be used whenever the object lifetime of the source exceeds the useful object lifetime of the listener.</span></span> <span data-ttu-id="4f2d2-118">(이 경우 *유용한* 사용자에 의해 결정 됩니다.) 취약 한 이벤트 패턴에는 수신기를 대 한 등록 한 어떤 방식으로든에서 수신기의 개체 수명 특성을 영향을 주지 않고 이벤트를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-118">(In this case, *useful* is determined by you.) The weak event pattern allows the listener to register for and receive the event without affecting the object lifetime characteristics of the listener in any way.</span></span> <span data-ttu-id="4f2d2-119">실제로, 소스에서 대 한 암시적된 참조가 수신기가 가비지 수집을 수행할 수 있는지을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-119">In effect, the implied reference from the source does not determine whether the listener is eligible for garbage collection.</span></span> <span data-ttu-id="4f2d2-120">참조는 따라서 이름은 취약 한 이벤트 패턴 및 관련 된 약한 참조를 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-120">The reference is a weak reference, thus the naming of the weak event pattern and the related [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)].</span></span> <span data-ttu-id="4f2d2-121">수신기는 가비지 수집 하거나 그렇지 않으면 제거 될 수 있습니다 및 소스 삭제 된 개체에 대 한 존재할 처리기 참조를 보존 하지 않고 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-121">The listener can be garbage collected or otherwise destroyed, and the source can continue without retaining noncollectible handler references to a now destroyed object.</span></span>  
  
## <a name="who-should-implement-the-weak-event-pattern"></a><span data-ttu-id="4f2d2-122">취약 한 이벤트 패턴을 구현 해야가?</span><span class="sxs-lookup"><span data-stu-id="4f2d2-122">Who Should Implement the Weak Event Pattern?</span></span>  
 <span data-ttu-id="4f2d2-123">취약 한 이벤트 패턴을 구현할 컨트롤 작성자에 주로 흥미로운 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-123">Implementing the weak event pattern is interesting primarily for control authors.</span></span> <span data-ttu-id="4f2d2-124">컨트롤 작성자는 동작과 컨트롤 및 삽입 되는 응용 프로그램에 아무런 영향 제약 주로 담당 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-124">As a control author, you are largely responsible for the behavior and containment of your control and the impact it has on applications in which it is inserted.</span></span> <span data-ttu-id="4f2d2-125">여기에 컨트롤 개체 수명 동작 특히 설명한 메모리 누수 문제를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-125">This includes the control object lifetime behavior, in particular the handling of the described memory leak problem.</span></span>  
  
 <span data-ttu-id="4f2d2-126">특정 시나리오를 기본적으로 취약 한 이벤트 패턴의 응용 프로그램에 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-126">Certain scenarios inherently lend themselves to the application of the weak event pattern.</span></span> <span data-ttu-id="4f2d2-127">이러한 시나리오 중 하나에 데이터 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-127">One such scenario is data binding.</span></span> <span data-ttu-id="4f2d2-128">이 데이터 바인딩에서 바인딩 대상 수신기 개체에 완전히 독립적인 소스 개체에 대 한 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-128">In data binding, it is common for the source object to be completely independent of the listener object, which is a target of a binding.</span></span> <span data-ttu-id="4f2d2-129">많은 부분이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 취약 한 이벤트 패턴의 이벤트 구현 방식에 적용 한 데이터 바인딩이 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-129">Many aspects of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] data binding already have the weak event pattern applied in how the events are implemented.</span></span>  
  
## <a name="how-to-implement-the-weak-event-pattern"></a><span data-ttu-id="4f2d2-130">취약 한 이벤트 패턴을 구현 하는 방법</span><span class="sxs-lookup"><span data-stu-id="4f2d2-130">How to Implement the Weak Event Pattern</span></span>  
 <span data-ttu-id="4f2d2-131">취약 한 이벤트 패턴을 구현 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-131">There are three ways to implement weak event pattern.</span></span> <span data-ttu-id="4f2d2-132">다음 표에서 세 가지 방법을 고 각 사용 시기에 대 한 몇 가지 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-132">The following table lists the three approaches and provides some guidance for when you should use each.</span></span>  
  
|<span data-ttu-id="4f2d2-133">방법</span><span class="sxs-lookup"><span data-stu-id="4f2d2-133">Approach</span></span>|<span data-ttu-id="4f2d2-134">구현 시기</span><span class="sxs-lookup"><span data-stu-id="4f2d2-134">When to Implement</span></span>|  
|--------------|-----------------------|  
|<span data-ttu-id="4f2d2-135">기존 취약 한 이벤트 관리자 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="4f2d2-135">Use an existing weak event manager class</span></span>|<span data-ttu-id="4f2d2-136">구독 하려는 이벤트에 해당 하는 경우 <xref:System.Windows.WeakEventManager>, 기존 취약 한 이벤트 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-136">If the event you want to subscribe to has a corresponding <xref:System.Windows.WeakEventManager>, use the existing weak event manager.</span></span> <span data-ttu-id="4f2d2-137">WPF와 함께 제공 되는 취약 한 이벤트 관리자의 목록에 대 한 참조의 상속 계층 구조는 <xref:System.Windows.WeakEventManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-137">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span> <span data-ttu-id="4f2d2-138">그러나 Note, 되므로 다른 인증 방법 중 하나를 선택 해야 것 WPF와 함께 제공 되는 비교적 취약 한 이벤트 관리자가 없음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-138">Note, however, that there are relatively few weak event managers that are included with WPF, so you will probably need to choose one of the other approaches.</span></span>|  
|<span data-ttu-id="4f2d2-139">일반 약한 이벤트 관리자 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="4f2d2-139">Use a generic weak event manager class</span></span>|<span data-ttu-id="4f2d2-140">일반을 사용 하 여 <xref:System.Windows.WeakEventManager%602> 기존 <xref:System.Windows.WeakEventManager> 을 사용할 수 없는 쉽게를 구현 하는 방법을 원하고 없는 우려 효율성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-140">Use a generic <xref:System.Windows.WeakEventManager%602> when an existing <xref:System.Windows.WeakEventManager> is not available, you want an easy way to implement, and you are not concerned about efficiency.</span></span> <span data-ttu-id="4f2d2-141">제네릭 <xref:System.Windows.WeakEventManager%602> 에서 기존 또는 사용자 지정 취약 한 이벤트 관리자 보다 덜 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-141">The generic <xref:System.Windows.WeakEventManager%602> is less efficient than an existing or custom weak event manager.</span></span> <span data-ttu-id="4f2d2-142">예를 들어 제네릭 클래스는 이벤트의 이름이 지정 된 이벤트를 검색 하기 위해 더 많은 리플렉션을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-142">For example, the generic class does more reflection to discover the event given the event's name.</span></span> <span data-ttu-id="4f2d2-143">또한 제네릭을 사용 하 여 이벤트를 등록 하려면 코드 <xref:System.Windows.WeakEventManager%602> 더 기존를 사용 하 여 보다 자세한 정보 또는 사용자 지정은 <xref:System.Windows.WeakEventManager>합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-143">Also, the code to register the event by using the generic <xref:System.Windows.WeakEventManager%602> is more verbose than using an existing or custom <xref:System.Windows.WeakEventManager>.</span></span>|  
|<span data-ttu-id="4f2d2-144">취약 한 사용자 지정 이벤트 관리자 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="4f2d2-144">Create a custom weak event manager class</span></span>|<span data-ttu-id="4f2d2-145">사용자 지정 만들기 <xref:System.Windows.WeakEventManager> 기존 <xref:System.Windows.WeakEventManager> 사용할 수 없으면 효율성을 극대화 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-145">Create a custom <xref:System.Windows.WeakEventManager> when an existing <xref:System.Windows.WeakEventManager> is not available and you want the best efficiency.</span></span> <span data-ttu-id="4f2d2-146">사용자 지정을 사용 하 여 <xref:System.Windows.WeakEventManager> 구독할 이벤트는 더 효율적 이지만 시작 부분에 더 많은 코드 작성의 비용 발생 시 키 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-146">Using a custom <xref:System.Windows.WeakEventManager> to subscribe to an event will be more efficient, but you do incur the cost of writing more code at the beginning.</span></span>|  
  
 <span data-ttu-id="4f2d2-147">다음 섹션에는 취약 한 이벤트 패턴을 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-147">The following sections describe how to implement the weak event pattern.</span></span>  <span data-ttu-id="4f2d2-148">이 논의의 목적에 대 한 이벤트를 구독할 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-148">For purposes of this discussion, the event to subscribe to has the following characteristics.</span></span>  
  
-   <span data-ttu-id="4f2d2-149">이벤트 이름이 잘못 된 `SomeEvent`합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-149">The event name is `SomeEvent`.</span></span>  
  
-   <span data-ttu-id="4f2d2-150">이벤트에 의해 발생 되는 `EventSource` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-150">The event is raised by the `EventSource` class.</span></span>  
  
-   <span data-ttu-id="4f2d2-151">이벤트 처리기에 형식이: `SomeEventEventHandler` (또는 `EventHandler<SomeEventEventArgs>`).</span><span class="sxs-lookup"><span data-stu-id="4f2d2-151">The event handler has type: `SomeEventEventHandler` (or `EventHandler<SomeEventEventArgs>`).</span></span>  
  
-   <span data-ttu-id="4f2d2-152">이 이벤트는 형식의 매개 변수 전달 `SomeEventEventArgs` 이벤트 처리기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-152">The event passes a parameter of type `SomeEventEventArgs` to the event handlers.</span></span>  
  
### <a name="using-an-existing-weak-event-manager-class"></a><span data-ttu-id="4f2d2-153">기존 약한 이벤트 관리자 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="4f2d2-153">Using an Existing Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="4f2d2-154">관리자를 기존 약한 이벤트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-154">Find an existing weak event manager.</span></span>  
  
     <span data-ttu-id="4f2d2-155">WPF와 함께 제공 되는 취약 한 이벤트 관리자의 목록에 대 한 참조의 상속 계층 구조는 <xref:System.Windows.WeakEventManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-155">For a list of weak event managers that are included with WPF, see the inheritance hierarchy in the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
2.  <span data-ttu-id="4f2d2-156">일반 이벤트 후크 하는 대신 새로운 취약 한 이벤트 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-156">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="4f2d2-157">예를 들어, 코드 패턴을 사용 하 여 이벤트를 구독할 경우:</span><span class="sxs-lookup"><span data-stu-id="4f2d2-157">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="4f2d2-158">다음 패턴으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-158">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="4f2d2-159">마찬가지로, 사용자 코드는 다음 패턴을 사용 하 여 이벤트를 등록 취소 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="4f2d2-159">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="4f2d2-160">다음 패턴으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-160">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a><span data-ttu-id="4f2d2-161">제네릭 약한 이벤트 관리자 클래스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="4f2d2-161">Using the Generic Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="4f2d2-162">제네릭을 사용 하 여 <xref:System.Windows.WeakEventManager%602> 일반 이벤트 후크 대신 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-162">Use the generic <xref:System.Windows.WeakEventManager%602> class instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="4f2d2-163">사용 하는 경우 <xref:System.Windows.WeakEventManager%602> 이벤트 원본이 이벤트 수신기를 등록 하려면 제공 및 <xref:System.EventArgs> 형식이 형식 매개 변수는 클래스와 호출 <xref:System.Windows.WeakEventManager%602.AddHandler%2A> 다음 코드에 나와 있는 것 처럼:</span><span class="sxs-lookup"><span data-stu-id="4f2d2-163">When you use <xref:System.Windows.WeakEventManager%602> to register event listeners, you supply the event source and <xref:System.EventArgs> type as the type parameters to the class and call <xref:System.Windows.WeakEventManager%602.AddHandler%2A> as shown in the following code:</span></span>  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a><span data-ttu-id="4f2d2-164">사용자 지정 약한 이벤트 관리자 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="4f2d2-164">Creating a Custom Weak Event Manager Class</span></span>  
  
1.  <span data-ttu-id="4f2d2-165">다음 클래스 템플릿을 프로젝트에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-165">Copy the following class template to your project.</span></span>  
  
     <span data-ttu-id="4f2d2-166">이 클래스에서 상속 된 <xref:System.Windows.WeakEventManager> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-166">This class inherits from the <xref:System.Windows.WeakEventManager> class.</span></span>  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  <span data-ttu-id="4f2d2-167">대체는 `SomeEventWeakEventManager` 사용자 이름으로 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-167">Replace the `SomeEventWeakEventManager` name with your own name.</span></span>  
  
3.  <span data-ttu-id="4f2d2-168">이벤트에는 해당 이름의 앞에서 설명한 세 가지 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-168">Replace the three names described previously with the corresponding names for your event.</span></span> <span data-ttu-id="4f2d2-169">(`SomeEvent`, `EventSource`, 및 `SomeEventEventArgs`)</span><span class="sxs-lookup"><span data-stu-id="4f2d2-169">(`SomeEvent`, `EventSource`, and `SomeEventEventArgs`)</span></span>  
  
4.  <span data-ttu-id="4f2d2-170">관리 하는 이벤트로 동일한 표시 취약 한 이벤트 관리자 클래스의 표시 유형 (public / private, 내부)를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-170">Set the visibility (public / internal / private) of the weak event manager class to the same visibility as event it manages.</span></span>  
  
5.  <span data-ttu-id="4f2d2-171">일반 이벤트 후크 하는 대신 새로운 취약 한 이벤트 관리자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-171">Use the new weak event manager instead of the normal event hookup.</span></span>  
  
     <span data-ttu-id="4f2d2-172">예를 들어, 코드 패턴을 사용 하 여 이벤트를 구독할 경우:</span><span class="sxs-lookup"><span data-stu-id="4f2d2-172">For example, if your code uses the following pattern to subscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     <span data-ttu-id="4f2d2-173">다음 패턴으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-173">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     <span data-ttu-id="4f2d2-174">마찬가지로, 사용자 코드는 다음 패턴을 사용 하 여 이벤트를 등록 취소 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="4f2d2-174">Similarly, if your code uses the following pattern to unsubscribe to an event:</span></span>  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     <span data-ttu-id="4f2d2-175">다음 패턴으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2d2-175">Change it to the following pattern:</span></span>  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4f2d2-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f2d2-176">See Also</span></span>  
 <xref:System.Windows.WeakEventManager>  
 <xref:System.Windows.IWeakEventListener>  
 [<span data-ttu-id="4f2d2-177">라우트된 이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="4f2d2-177">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="4f2d2-178">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="4f2d2-178">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
