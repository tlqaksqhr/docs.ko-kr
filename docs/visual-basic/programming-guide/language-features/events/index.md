---
title: "이벤트(Visual Basic)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- events [Visual Basic], about events
- events [Visual Basic]
ms.assetid: 8fb0353a-e41b-4e23-b78f-da65db832f70
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 84f8385e1b2f16c4bcfa53ef2c77e1f0cf61e5e3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="events-visual-basic"></a><span data-ttu-id="46a89-102">이벤트(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="46a89-102">Events (Visual Basic)</span></span>
<span data-ttu-id="46a89-103">[!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 프로젝트를 시퀀스로 실행되는 프로시저 시리즈로 시각화할 수 있지만 실제로 대부분의 프로그램은 이벤트 구동 방식을 따릅니다. 즉, 실행 흐름은 *이벤트*라는 외부 발생 요인에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-103">While you might visualize a [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] project as a series of procedures that execute in a sequence, in reality, most programs are event driven—meaning the flow of execution is determined by external occurrences called *events*.</span></span>  
  
 <span data-ttu-id="46a89-104">이벤트는 중요한 문제가 발생했음을 응용 프로그램에 알리는 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-104">An event is a signal that informs an application that something important has occurred.</span></span> <span data-ttu-id="46a89-105">예를 들어 사용자가 폼의 컨트롤을 클릭하면 폼이 `Click` 이벤트를 발생시키고 이벤트를 처리하는 프로시저를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-105">For example, when a user clicks a control on a form, the form can raise a `Click` event and call a procedure that handles the event.</span></span> <span data-ttu-id="46a89-106">또한 이벤트는 개별 작업이 통신할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-106">Events also allow separate tasks to communicate.</span></span> <span data-ttu-id="46a89-107">예를 들어 응용 프로그램이 주 응용 프로그램과는 별도로 정렬 작업을 수행한다고 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-107">Say, for example, that your application performs a sort task separately from the main application.</span></span> <span data-ttu-id="46a89-108">사용자가 정렬을 취소하면 응용 프로그램은 정렬 프로세스를 중지하도록 지시하는 취소 이벤트를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-108">If a user cancels the sort, your application can send a cancel event instructing the sort process to stop.</span></span>  
  
## <a name="event-terms-and-concepts"></a><span data-ttu-id="46a89-109">이벤트 용어 및 개념</span><span class="sxs-lookup"><span data-stu-id="46a89-109">Event Terms and Concepts</span></span>  
 <span data-ttu-id="46a89-110">이 섹션에서는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]의 이벤트에서 사용되는 용어 및 개념에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-110">This section describes the terms and concepts used with events in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="declaring-events"></a><span data-ttu-id="46a89-111">이벤트 선언</span><span class="sxs-lookup"><span data-stu-id="46a89-111">Declaring Events</span></span>  
 <span data-ttu-id="46a89-112">다음 예제와 같이 `Event` 키워드를 사용하여 클래스, 구조체, 모듈 및 인터페이스를 사용하여 이벤트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-112">You declare events within classes, structures, modules, and interfaces using the `Event` keyword, as in the following example:</span></span>  
  
 <span data-ttu-id="46a89-113">[!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="46a89-113">[!code-vb[VbVbalrEvents#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_1.vb)]</span></span>  
  
### <a name="raising-events"></a><span data-ttu-id="46a89-114">이벤트 발생</span><span class="sxs-lookup"><span data-stu-id="46a89-114">Raising Events</span></span>  
 <span data-ttu-id="46a89-115">이벤트는 중요한 문제가 발생했음을 알리는 메시지와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-115">An event is like a message announcing that something important has occurred.</span></span> <span data-ttu-id="46a89-116">메시지를 브로드캐스트하는 동작을 이벤트 *발생*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-116">The act of broadcasting the message is called *raising* the event.</span></span> <span data-ttu-id="46a89-117">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서는 다음 예제와 같이 `RaiseEvent` 문으로 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-117">In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], you raise events with the `RaiseEvent` statement, as in the following example:</span></span>  
  
 <span data-ttu-id="46a89-118">[!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="46a89-118">[!code-vb[VbVbalrEvents#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_2.vb)]</span></span>  
  
 <span data-ttu-id="46a89-119">선언된 클래스, 모듈 또는 구조체의 범위 내에서 이벤트가 발생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-119">Events must be raised within the scope of the class, module, or structure where they are declared.</span></span> <span data-ttu-id="46a89-120">예를 들어 파생 클래스는 기본 클래스에서 상속된 이벤트를 발생시킬 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-120">For example, a derived class cannot raise events inherited from a base class.</span></span>  
  
### <a name="event-senders"></a><span data-ttu-id="46a89-121">이벤트 전송자</span><span class="sxs-lookup"><span data-stu-id="46a89-121">Event Senders</span></span>  
 <span data-ttu-id="46a89-122">이벤트를 발생시킬 수 있는 개체는 *이벤트 소스*라고도 하는 *이벤트 전송자*입니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-122">Any object capable of raising an event is an *event sender*, also known as an *event source*.</span></span> <span data-ttu-id="46a89-123">폼, 컨트롤 및 사용자 정의 개체는 이벤트 전송자에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-123">Forms, controls, and user-defined objects are examples of event senders.</span></span>  
  
### <a name="event-handlers"></a><span data-ttu-id="46a89-124">이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="46a89-124">Event Handlers</span></span>  
 <span data-ttu-id="46a89-125">*이벤트 처리기*는 해당 이벤트가 발생할 때 호출되는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-125">*Event handlers* are procedures that are called when a corresponding event occurs.</span></span> <span data-ttu-id="46a89-126">서명이 일치하는 모든 유효한 서브루틴을 이벤트 처리기로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-126">You can use any valid subroutine with a matching signature as an event handler.</span></span> <span data-ttu-id="46a89-127">그러나 함수는 이벤트 처리기로 사용할 수 없습니다. 이벤트 소스에 값을 반환할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-127">You cannot use a function as an event handler, however, because it cannot return a value to the event source.</span></span>  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="46a89-128">에서는 이벤트 처리기에 대해 이벤트 전송자의 이름, 밑줄 및 이벤트의 이름을 조합하는 표준 명명 규칙을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-128"> uses a standard naming convention for event handlers that combines the name of the event sender, an underscore, and the name of the event.</span></span> <span data-ttu-id="46a89-129">예를 들어 `button1`이라는 단추의 `Click` 이벤트의 이름은 `Sub button1_Click`으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-129">For example, the `Click` event of a button named `button1` would be named `Sub button1_Click`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46a89-130">사용자 고유의 이벤트에 대해 이벤트 처리기를 정의하는 경우 이러한 명명 규칙을 사용하는 것이 좋지만 필수는 아닙니다. 유효한 어떤 서브루틴 이름도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-130">We recommend that you use this naming convention when defining event handlers for your own events, but it is not required; you can use any valid subroutine name.</span></span>  
  
## <a name="associating-events-with-event-handlers"></a><span data-ttu-id="46a89-131">이벤트를 이벤트 처리기에 연결</span><span class="sxs-lookup"><span data-stu-id="46a89-131">Associating Events with Event Handlers</span></span>  
 <span data-ttu-id="46a89-132">이벤트 처리기를 사용하려면 먼저 `Handles` 또는 `AddHandler` 문을 사용하여 이벤트 처리기를 이벤트에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-132">Before an event handler becomes usable, you must first associate it with an event by using either the `Handles` or `AddHandler` statement.</span></span>  
  
### <a name="withevents-and-the-handles-clause"></a><span data-ttu-id="46a89-133">WithEvents 및 Handles 절</span><span class="sxs-lookup"><span data-stu-id="46a89-133">WithEvents and the Handles Clause</span></span>  
 <span data-ttu-id="46a89-134">`WithEvents` 문 및 `Handles` 절은 이벤트 처리기를 지정하는 선언적 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-134">The `WithEvents` statement and `Handles` clause provide a declarative way of specifying event handlers.</span></span> <span data-ttu-id="46a89-135">`WithEvents` 키워드로 선언된 개체에 의해 발생된 이벤트는 다음 그림과 같이 해당 이벤트에 대한 `Handles` 문을 사용하는 모든 프로시저에 의해 처리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-135">An event raised by an object declared with the `WithEvents` keyword can be handled by any procedure with a `Handles` statement for that event, as shown in the following example:</span></span>  
  
 <span data-ttu-id="46a89-136">[!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="46a89-136">[!code-vb[VbVbalrEvents#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_3.vb)]</span></span>  
  
 <span data-ttu-id="46a89-137">`WithEvents` 문 및 `Handles` 절은 선언적 구문을 사용하여 이벤트 처리를 보다 쉽게 코딩하고 읽고 디버그할 수 있도록 하므로 이벤트 처리기에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-137">The `WithEvents` statement and the `Handles` clause are often the best choice for event handlers because the declarative syntax they use makes event handling easier to code, read and debug.</span></span> <span data-ttu-id="46a89-138">그러나 `WithEvents` 변수를 사용할 때는 다음과 같은 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-138">However, be aware of the following limitations on the use of `WithEvents` variables:</span></span>  
  
-   <span data-ttu-id="46a89-139">`WithEvents` 변수를 개체 변수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-139">You cannot use a `WithEvents` variable as an object variable.</span></span> <span data-ttu-id="46a89-140">즉, `Object`로 선언할 수 없습니다. 따라서 변수를 선언할 때는 클래스 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-140">That is, you cannot declare it as `Object`—you must specify the class name when you declare the variable.</span></span>  
  
-   <span data-ttu-id="46a89-141">공유 이벤트는 클래스 인스턴스에 연결되어 있지 않으므로 `WithEvents`를 사용하여 공유 이벤트를 선언적으로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-141">Because shared eventsare not tied to class instances, you cannot use `WithEvents` to declaratively handle shared events.</span></span> <span data-ttu-id="46a89-142">마찬가지로 `WithEvents` 또는 `Handles`를 사용하여 `Structure`의 이벤트를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-142">Similarly, you cannot use `WithEvents` or `Handles` to handle events from a `Structure`.</span></span> <span data-ttu-id="46a89-143">두 경우 모두 `AddHandler` 문을 사용해서 해당 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-143">In both cases, you can use the `AddHandler` statement to handle those events.</span></span>  
  
-   <span data-ttu-id="46a89-144">`WithEvents` 변수 배열을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-144">You cannot create arrays of `WithEvents` variables.</span></span>  
  
 <span data-ttu-id="46a89-145">`WithEvents` 변수는 단일 이벤트 처리기로 하나 이상의 이벤트 종류를 처리하거나, 하나 이상의 이벤트 처리기로 동일한 종류의 이벤트를 처리하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-145">`WithEvents` variables allow a single event handler to handle one or more kind of event, or one or more event handlers to handle the same kind of event.</span></span>  
  
 <span data-ttu-id="46a89-146">`Handles` 절은 이벤트를 이벤트 처리기와 연결하는 표준 방법이지만 컴파일 타임에 이벤트를 이벤트 처리기와 연결하도록 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-146">Although the `Handles` clause is the standard way of associating an event with an event handler, it is limited to associating events with event handlers at compile time.</span></span>  
  
 <span data-ttu-id="46a89-147">폼이나 컨트롤에 이벤트가 연결된 것과 같은 일부 경우에서 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]는 빈 이벤트 처리기를 자동으로 스텁하고 이벤트와 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-147">In some cases, such as with events associated with forms or controls, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] automatically stubs out an empty event handler and associates it with an event.</span></span> <span data-ttu-id="46a89-148">예를 들어 디자인 모드에서 폼의 명령 단추를 두 번 클릭하면 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서는 다음 코드와 같이 명령 버튼에 대해 빈 이벤트 처리기와 `WithEvents` 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-148">For example, when you double-click a command button on a form in design mode, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] creates an empty event handler and a `WithEvents` variable for the command button, as in the following code:</span></span>  
  
 <span data-ttu-id="46a89-149">[!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="46a89-149">[!code-vb[VbVbalrEvents#26](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_4.vb)]</span></span>  
  
### <a name="addhandler-and-removehandler"></a><span data-ttu-id="46a89-150">AddHandler 및 RemoveHandler</span><span class="sxs-lookup"><span data-stu-id="46a89-150">AddHandler and RemoveHandler</span></span>  
 <span data-ttu-id="46a89-151">`AddHandler` 문은 둘 다 이벤트 처리기를 지정할 수 있다는 측면에서 `Handles` 절과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-151">The `AddHandler` statement is similar to the `Handles` clause in that both allow you to specify an event handler.</span></span> <span data-ttu-id="46a89-152">그러나 `AddHandler`를 `RemoveHandler`와 함께 사용하면 `Handles` 절보다 유연성이 높아져서 이벤트와 연결된 이벤트 처리기를 동적으로 추가, 제거 및 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-152">However, `AddHandler`, used with `RemoveHandler`, provides greater flexibility than the `Handles` clause, allowing you to dynamically add, remove, and change the event handler associated with an event.</span></span> <span data-ttu-id="46a89-153">공유 이벤트 또는 구조체의 이벤트를 처리하려는 경우 `AddHandler`를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-153">If you want to handle shared events or events from a structure, you must use `AddHandler`.</span></span>  
  
 <span data-ttu-id="46a89-154">`AddHandler`는 두 개의 인수, 즉 컨트롤과 같은 이벤트 전송자의 이벤트 이름과 대리자로 평가되는 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-154">`AddHandler` takes two arguments: the name of an event from an event sender such as a control, and an expression that evaluates to a delegate.</span></span> <span data-ttu-id="46a89-155">`AddressOf` 문은 항상 대리자에 대한 참조를 반환하므로 `AddHandler`를 사용할 경우 대리자 클래스를 명시적으로 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-155">You do not need to explicitly specify the delegate class when using `AddHandler`, since the `AddressOf` statement always returns a reference to the delegate.</span></span> <span data-ttu-id="46a89-156">다음 예제에서는 개체에 의해 발생하는 이벤트와 이벤트 처리기를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-156">The following example associates an event handler with an event raised by an object:</span></span>  
  
 <span data-ttu-id="46a89-157">[!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="46a89-157">[!code-vb[VbVbalrEvents#28](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_5.vb)]</span></span>  
  
 <span data-ttu-id="46a89-158">이벤트 처리기에서 이벤트의 연결을 끊는 `RemoveHandler`는 `AddHandler`와 동일한 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-158">`RemoveHandler`, which disconnects an event from an event handler, uses the same syntax as `AddHandler`.</span></span> <span data-ttu-id="46a89-159">예:</span><span class="sxs-lookup"><span data-stu-id="46a89-159">For example:</span></span>  
  
 <span data-ttu-id="46a89-160">[!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="46a89-160">[!code-vb[VbVbalrEvents#29](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_6.vb)]</span></span>  
  
 <span data-ttu-id="46a89-161">다음 예제에서 이벤트 처리기는 이벤트와 연결되고 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-161">In the following example, an event handler is associated with an event, and the event is raised.</span></span> <span data-ttu-id="46a89-162">이벤트 처리기는 이벤트를 catch하고 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-162">The event handler catches the event and displays a message.</span></span>  
  
 <span data-ttu-id="46a89-163">그런 다음 첫 번째 이벤트 처리기가 제거되고 다른 이벤트 처리기가 이벤트와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-163">Then the first event handler is removed and a different event handler is associated with the event.</span></span> <span data-ttu-id="46a89-164">이벤트가 다시 발생하면 다른 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-164">When the event is raised again, a different message is displayed.</span></span>  
  
 <span data-ttu-id="46a89-165">마지막으로 두 번째 이벤트 처리기가 제거되고 세 번째로 해당 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-165">Finally, the second event handler is removed and the event is raised for a third time.</span></span> <span data-ttu-id="46a89-166">해당 이벤트와 연결된 이벤트 처리기가 더 이상 없으므로 아무 작업도 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-166">Because there is no longer an event handler associated with the event, no action is taken.</span></span>  
  
 <span data-ttu-id="46a89-167">[!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="46a89-167">[!code-vb[VbVbalrEvents#38](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_7.vb)]</span></span>  
  
## <a name="handling-events-inherited-from-a-base-class"></a><span data-ttu-id="46a89-168">기본 클래스에서 상속된 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="46a89-168">Handling Events Inherited from a Base Class</span></span>  
 <span data-ttu-id="46a89-169">기본 클래스에서 특성을 상속하는 클래스인 *파생 클래스*는 `Handles``MyBase` 문을 사용하여 기본 클래스에 의해 발생된 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-169">*Derived classes*—classes that inherit characteristics from a base class—can handle events raised by their base class using the `Handles``MyBase` statement.</span></span>  
  
#### <a name="to-handle-events-from-a-base-class"></a><span data-ttu-id="46a89-170">기본 클래스의 이벤트를 처리하려면</span><span class="sxs-lookup"><span data-stu-id="46a89-170">To handle events from a base class</span></span>  
  
-   <span data-ttu-id="46a89-171">이벤트 처리기 프로시저의 선언 줄에 `Handles MyBase.`*eventname* 문을 추가하여 파생 클래스에서 이벤트 처리기를 선언합니다. 여기서 *eventname*은 처리하는 기본 클래스의 이벤트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-171">Declare an event handler in the derived class by adding a `Handles MyBase.`*eventname* statement to the declaration line of your event-handler procedure, where *eventname* is the name of the event in the base class you are handling.</span></span> <span data-ttu-id="46a89-172">예:</span><span class="sxs-lookup"><span data-stu-id="46a89-172">For example:</span></span>  
  
     <span data-ttu-id="46a89-173">[!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="46a89-173">[!code-vb[VbVbalrEvents#12](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/events_8.vb)]</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="46a89-174">관련 단원</span><span class="sxs-lookup"><span data-stu-id="46a89-174">Related Sections</span></span>  
  
|<span data-ttu-id="46a89-175">제목</span><span class="sxs-lookup"><span data-stu-id="46a89-175">Title</span></span>|<span data-ttu-id="46a89-176">설명</span><span class="sxs-lookup"><span data-stu-id="46a89-176">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="46a89-177">연습: 이벤트 선언 및 발생</span><span class="sxs-lookup"><span data-stu-id="46a89-177">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)|<span data-ttu-id="46a89-178">클래스의 이벤트를 선언하고 발생시키는 방법에 대한 단계별 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-178">Provides a step-by-step description of how to declare and raise events for a class.</span></span>|  
|[<span data-ttu-id="46a89-179">연습: 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="46a89-179">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)|<span data-ttu-id="46a89-180">이벤트 처리기 프로시저를 작성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-180">Demonstrates how to write an event-handler procedure.</span></span>|  
|[<span data-ttu-id="46a89-181">방법: 차단을 방지하는 사용자 지정 이벤트 선언</span><span class="sxs-lookup"><span data-stu-id="46a89-181">How to: Declare Custom Events To Avoid Blocking</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)|<span data-ttu-id="46a89-182">이벤트 처리기를 비동기적으로 호출할 수 있는 사용자 지정 이벤트를 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-182">Demonstrates how to define a custom event that allows its event handlers to be called asynchronously.</span></span>|  
|[<span data-ttu-id="46a89-183">방법: 메모리를 절약하는 사용자 지정 이벤트 선언</span><span class="sxs-lookup"><span data-stu-id="46a89-183">How to: Declare Custom Events To Conserve Memory</span></span>](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)|<span data-ttu-id="46a89-184">이벤트가 처리될 때만 메모리를 사용하는 사용자 지정 이벤트를 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-184">Demonstrates how to define a custom event that uses memory only when the event is handled.</span></span>|  
|[<span data-ttu-id="46a89-185">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="46a89-185">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)|<span data-ttu-id="46a89-186">상속된 구성 요소의 이벤트 처리기에서 발생하는 일반적인 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-186">Lists common issues that arise with event handlers in inherited components.</span></span>|  
|[<span data-ttu-id="46a89-187">이벤트</span><span class="sxs-lookup"><span data-stu-id="46a89-187">Events</span></span>](../../../../standard/events/index.md)|<span data-ttu-id="46a89-188">[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]의 이벤트 모델 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-188">Provides an overview of the event model in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>|  
|[<span data-ttu-id="46a89-189">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="46a89-189">Creating Event Handlers in Windows Forms</span></span>](https://msdn.microsoft.com/library/dacysss4.aspx)|<span data-ttu-id="46a89-190">Windows Forms 개체와 관련된 이벤트로 작업하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-190">Describes how to work with events associated with Windows Forms objects.</span></span>|  
|[<span data-ttu-id="46a89-191">대리자</span><span class="sxs-lookup"><span data-stu-id="46a89-191">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)|<span data-ttu-id="46a89-192">Visual Basic의 대리자에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="46a89-192">Provides an overview of delegates in Visual Basic.</span></span>|

