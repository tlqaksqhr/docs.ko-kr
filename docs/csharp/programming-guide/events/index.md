---
title: 이벤트(C# 프로그래밍 가이드)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
caps.latest.revision: 43
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c4ac62a38698f0e43c2868e86fa8776e913b715d
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="events-c-programming-guide"></a><span data-ttu-id="f0d6c-102">이벤트(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f0d6c-102">Events (C# Programming Guide)</span></span>
<span data-ttu-id="f0d6c-103">[클래스](../../../csharp/language-reference/keywords/class.md) 나 개체에서는 특정 상황이 발생할 때 이벤트를 통해 다른 클래스나 개체에 이를 알려줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-103">Events enable a [class](../../../csharp/language-reference/keywords/class.md) or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="f0d6c-104">이벤트를 보내거나 *발생시키는*클래스를 *게시자* 라고 하며 이벤트를 받거나 *처리하는*클래스를 *구독자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-104">The class that sends (or *raises*) the event is called the *publisher* and the classes that receive (or *handle*) the event are called *subscribers*.</span></span>  
  
 <span data-ttu-id="f0d6c-105">일반적인 C# Windows Forms 또는 웹 응용 프로그램, 단추 및 목록 상자 같은 컨트롤에 의해 발생하는 이벤트를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-105">In a typical C# Windows Forms or Web application, you subscribe to events raised by controls such as buttons and list boxes.</span></span> <span data-ttu-id="f0d6c-106">컨트롤이 게시하는 이벤트를 찾아보고 처리할 이벤트를 선택하려면 Visual C# IDE(통합 개발 환경)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-106">You can use the Visual C# integrated development environment (IDE) to browse the events that a control publishes and select the ones that you want to handle.</span></span> <span data-ttu-id="f0d6c-107">IDE는 빈 이벤트 처리기 메서드 및 이벤트를 구독하기 위한 코드를 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-107">The IDE automatically adds an empty event handler method and the code to subscribe to the event.</span></span> <span data-ttu-id="f0d6c-108">자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-108">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="events-overview"></a><span data-ttu-id="f0d6c-109">이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="f0d6c-109">Events Overview</span></span>  
 <span data-ttu-id="f0d6c-110">이벤트에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-110">Events have the following properties:</span></span>  
  
-   <span data-ttu-id="f0d6c-111">게시자는 이벤트 발생 시기를 결정합니다. 구독자는 이벤트에 대한 응답으로 수행할 작업을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-111">The publisher determines when an event is raised; the subscribers determine what action is taken in response to the event.</span></span>  
  
-   <span data-ttu-id="f0d6c-112">한 이벤트에는 여러 구독자가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-112">An event can have multiple subscribers.</span></span> <span data-ttu-id="f0d6c-113">구독자는 여러 게시자의 여러 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-113">A subscriber can handle multiple events from multiple publishers.</span></span>  
  
-   <span data-ttu-id="f0d6c-114">구독자가 없는 이벤트는 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-114">Events that have no subscribers are never raised.</span></span>  
  
-   <span data-ttu-id="f0d6c-115">이벤트는 일반적으로 그래픽 사용자 인터페이스에서 단추 클릭이나 메뉴 선택 같은 사용자 작업을 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-115">Events are typically used to signal user actions such as button clicks or menu selections in graphical user interfaces.</span></span>  
  
-   <span data-ttu-id="f0d6c-116">이벤트에 여러 구독자가 있는 경우 이벤트 처리기는 이벤트가 발생할 때 동기적으로 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-116">When an event has multiple subscribers, the event handlers are invoked synchronously when an event is raised.</span></span> <span data-ttu-id="f0d6c-117">이벤트를 비동기적으로 호출하려면 [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-117">To invoke events asynchronously, see [Calling Synchronous Methods Asynchronously](../../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).</span></span>  
  
-   <span data-ttu-id="f0d6c-118">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스 라이브러리에서 이벤트는 <xref:System.EventHandler> 대리자 및 <xref:System.EventArgs> 기본 클래스를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-118">In the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library, events are based on the <xref:System.EventHandler> delegate and the <xref:System.EventArgs> base class.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f0d6c-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f0d6c-119">Related Sections</span></span>  
 <span data-ttu-id="f0d6c-120">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0d6c-120">For more information, see:</span></span>  
  
-   [<span data-ttu-id="f0d6c-121">방법: 이벤트 구독 및 구독 취소</span><span class="sxs-lookup"><span data-stu-id="f0d6c-121">How to: Subscribe to and Unsubscribe from Events</span></span>](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)  
  
-   [<span data-ttu-id="f0d6c-122">방법: .NET Framework 지침을 따르는 이벤트 게시</span><span class="sxs-lookup"><span data-stu-id="f0d6c-122">How to: Publish Events that Conform to .NET Framework Guidelines</span></span>](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)  
  
-   [<span data-ttu-id="f0d6c-123">방법: 파생 클래스에서 기본 클래스 이벤트 발생</span><span class="sxs-lookup"><span data-stu-id="f0d6c-123">How to: Raise Base Class Events in Derived Classes</span></span>](../../../csharp/programming-guide/events/how-to-raise-base-class-events-in-derived-classes.md)  
  
-   [<span data-ttu-id="f0d6c-124">방법: 인터페이스 이벤트 구현</span><span class="sxs-lookup"><span data-stu-id="f0d6c-124">How to:  Implement Interface Events</span></span>](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)  
  
-   [<span data-ttu-id="f0d6c-125">스레드 동기화</span><span class="sxs-lookup"><span data-stu-id="f0d6c-125">Thread Synchronization</span></span>](../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
  
-   [<span data-ttu-id="f0d6c-126">방법: 사전을 사용하여 이벤트 인스턴스 저장</span><span class="sxs-lookup"><span data-stu-id="f0d6c-126">How to: Use a Dictionary to Store Event Instances</span></span>](../../../csharp/programming-guide/events/how-to-use-a-dictionary-to-store-event-instances.md)  
  
-   [<span data-ttu-id="f0d6c-127">방법: 사용자 지정 이벤트 접근자 구현</span><span class="sxs-lookup"><span data-stu-id="f0d6c-127">How to: Implement Custom Event Accessors</span></span>](../../../csharp/programming-guide/events/how-to-implement-custom-event-accessors.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f0d6c-128">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f0d6c-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="featured-book-chapters"></a><span data-ttu-id="f0d6c-129">중요 설명서 장</span><span class="sxs-lookup"><span data-stu-id="f0d6c-129">Featured Book Chapters</span></span>  
 <span data-ttu-id="f0d6c-130">[C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) 의 [Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span><span class="sxs-lookup"><span data-stu-id="f0d6c-130">[Delegates, Events, and Lambda Expressions](https://msdn.microsoft.com/library/orm-9780596516109-03-09.aspx) in [C# 3.0 Cookbook, Third Edition: More than 250 solutions for C# 3.0 programmers](https://msdn.microsoft.com/library/orm-9780596516109-03.aspx)</span></span>  
  
 <span data-ttu-id="f0d6c-131">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span><span class="sxs-lookup"><span data-stu-id="f0d6c-131">[Delegates and Events](https://msdn.microsoft.com/library/orm-9780596521066-01-17.aspx) in [Learning C# 3.0: Master the fundamentals of C# 3.0](https://msdn.microsoft.com/library/orm-9780596521066-01.aspx)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0d6c-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0d6c-132">See Also</span></span>  
 <xref:System.EventHandler>  
 [<span data-ttu-id="f0d6c-133">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f0d6c-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f0d6c-134">대리자</span><span class="sxs-lookup"><span data-stu-id="f0d6c-134">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="f0d6c-135">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="f0d6c-135">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="f0d6c-136">이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f0d6c-136">Multithreaded Programming with the Event-based Asynchronous Pattern</span></span>](../../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)
