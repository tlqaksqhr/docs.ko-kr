---
title: "RaiseEvent 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
dev_langs:
- VB
helpviewer_keywords:
- raising events, RaiseEvent statement
- RaiseEvent statement
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6a0cf1c5635335f22fddd57c7dd2baaeca6ddd23
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="raiseevent-statement"></a><span data-ttu-id="53235-102">RaiseEvent 문</span><span class="sxs-lookup"><span data-stu-id="53235-102">RaiseEvent Statement</span></span>
<span data-ttu-id="53235-103">트리거는 이벤트 클래스, 폼 또는 문서 내에서 모듈 수준에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-103">Triggers an event declared at module level within a class, form, or document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53235-104">구문</span><span class="sxs-lookup"><span data-stu-id="53235-104">Syntax</span></span>  
  
```  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a><span data-ttu-id="53235-105">요소</span><span class="sxs-lookup"><span data-stu-id="53235-105">Parts</span></span>  
 `eventname`  
 <span data-ttu-id="53235-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="53235-106">Required.</span></span> <span data-ttu-id="53235-107">트리거할 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="53235-107">Name of the event to trigger.</span></span>  
  
 `argumentlist`  
 <span data-ttu-id="53235-108">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="53235-108">Optional.</span></span> <span data-ttu-id="53235-109">변수, 배열, 또는 식의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="53235-109">Comma-delimited list of variables, arrays, or expressions.</span></span> <span data-ttu-id="53235-110">`argumentlist` 인수를 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-110">The `argumentlist` argument must be enclosed by parentheses.</span></span> <span data-ttu-id="53235-111">인수가 있을 경우 괄호를 생략 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-111">If there are no arguments, the parentheses must be omitted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53235-112">주의</span><span class="sxs-lookup"><span data-stu-id="53235-112">Remarks</span></span>  
 <span data-ttu-id="53235-113">필수 `eventname` 모듈 내에서 선언 하는 이벤트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="53235-113">The required `eventname` is the name of an event declared within the module.</span></span> <span data-ttu-id="53235-114">Visual Basic의 변수 명명 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="53235-114">It follows Visual Basic variable naming conventions.</span></span>  
  
 <span data-ttu-id="53235-115">이 이벤트는 발생 한 모듈 내에서 선언 되지 않은, 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-115">If the event has not been declared within the module in which it is raised, an error occurs.</span></span> <span data-ttu-id="53235-116">다음 코드에서는 이벤트 선언 및 이벤트가 발생 하는 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="53235-116">The following code fragment illustrates an event declaration and a procedure in which the event is raised.</span></span>  
  
 <span data-ttu-id="53235-117">[!code-vb[VbVbalrEvents #&37;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="53235-117">[!code-vb[VbVbalrEvents#37](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="53235-118">사용할 수 없습니다 `RaiseEvent` 모듈에 명시적으로 선언 되지 않은 이벤트를 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-118">You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module.</span></span> <span data-ttu-id="53235-119">예를 들어 모든 폼 상속을 <xref:System.Windows.Forms.Control.Click>에서 이벤트 <xref:System.Windows.Forms.Form?displayProperty=fullName>를 사용 하 여 높일 수 없습니다 `RaiseEvent` 파생된 된 폼에서.</xref:System.Windows.Forms.Form?displayProperty=fullName> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="53235-119">For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=fullName>, it cannot be raised using `RaiseEvent` in a derived form.</span></span> <span data-ttu-id="53235-120">선언 하는 경우는 `Click` 이벤트 폼 자체의 폼 모듈에 숨겨집니다 <xref:System.Windows.Forms.Control.Click>이벤트.</xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="53235-120">If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="53235-121">폼의를 여전히 호출할 수 있습니다 <xref:System.Windows.Forms.Control.Click>를 호출 하 여 이벤트는 <xref:System.Windows.Forms.Control.OnClick%2A>메서드.</xref:System.Windows.Forms.Control.OnClick%2A> </xref:System.Windows.Forms.Control.Click></span><span class="sxs-lookup"><span data-stu-id="53235-121">You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="53235-122">기본적으로 Visual Basic에서 정의 된 이벤트의 이벤트 처리기는 연결이 설정 된 순서 대로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-122">By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established.</span></span> <span data-ttu-id="53235-123">이벤트를 가질 수 있으므로 `ByRef` 매개 변수를 나중에 연결 하는 프로세스는 이전 이벤트 처리기에 의해 변경 된 매개 변수를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53235-123">Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler.</span></span> <span data-ttu-id="53235-124">이벤트 처리기가 실행 된 후 컨트롤 이벤트를 발생 시킨 서브루틴으로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="53235-124">After the event handlers execute, control is returned to the subroutine that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53235-125">공유 되지 않는 이벤트 선언 된 클래스의 생성자 내에서 발생 하지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-125">Non-shared events should not be raised within the constructor of the class in which they are declared.</span></span> <span data-ttu-id="53235-126">이러한 이벤트를 런타임 오류 발생 지는 않지만 연결 된 이벤트 처리기에서 포착 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53235-126">Although such events do not cause run-time errors, they may fail to be caught by associated event handlers.</span></span> <span data-ttu-id="53235-127">사용 된 `Shared` 한정자를 생성자에서 이벤트를 발생 하는 경우 공유 이벤트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="53235-127">Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53235-128">사용자 지정 이벤트를 정의 하 여 이벤트의 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53235-128">You can change the default behavior of events by defining a custom event.</span></span> <span data-ttu-id="53235-129">사용자 지정 이벤트는 `RaiseEvent` 문은 이벤트의 호출 `RaiseEvent` 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="53235-129">For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor.</span></span> <span data-ttu-id="53235-130">사용자 지정 이벤트에 대 한 자세한 내용은 참조 하십시오. [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-130">For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="53235-131">예제</span><span class="sxs-lookup"><span data-stu-id="53235-131">Example</span></span>  
 <span data-ttu-id="53235-132">다음 예제에서는 이벤트를 사용하여 10초부터 0초까지 카운트 다운합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-132">The following example uses events to count down seconds from 10 to 0.</span></span> <span data-ttu-id="53235-133">코드에 나와 있는 이벤트 관련 메서드, 속성 및 포함 하 여 문 중 일부는 `RaiseEvent` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="53235-133">The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.</span></span>  
  
 <span data-ttu-id="53235-134">이벤트를 발생시키는 클래스는 이벤트 소스이고 이벤트를 처리하는 메서드는 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="53235-134">The class that raises an event is the event source, and the methods that process the event are the event handlers.</span></span> <span data-ttu-id="53235-135">이벤트 소스는 생성되는 이벤트에 대해 여러 개의 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53235-135">An event source can have multiple handlers for the events it generates.</span></span> <span data-ttu-id="53235-136">클래스에서 이벤트를 발생시키면 해당 이벤트는 개체의 해당 인스턴스에 대해 이벤트를 처리하도록 선택한 모든 클래스에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="53235-136">When the class raises the event, that event is raised on every class that has elected to handle events for that instance of the object.</span></span>  
  
 <span data-ttu-id="53235-137">또한 이 예제에서는 단추(`Button1`)와 텍스트 상자(`TextBox1`)가 있는 폼(`Form1`)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-137">The example also uses a form (`Form1`) with a button (`Button1`) and a text box (`TextBox1`).</span></span> <span data-ttu-id="53235-138">단추를 클릭하면 첫 번째 텍스트 상자에 10초부터 0초까지의 카운트 다운이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="53235-138">When you click the button, the first text box displays a countdown from 10 to 0 seconds.</span></span> <span data-ttu-id="53235-139">전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="53235-139">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
 <span data-ttu-id="53235-140">`Form1`에 대한 코드는 폼의 초기 상태 및 최종 상태를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-140">The code for `Form1` specifies the initial and terminal states of the form.</span></span> <span data-ttu-id="53235-141">또한 이벤트가 발생될 때 실행될 코드도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="53235-141">It also contains the code executed when events are raised.</span></span>  
  
 <span data-ttu-id="53235-142">이 예제를 사용 하려면 새 Windows 응용 프로그램 프로젝트를 열고 라는 단추를 추가 `Button1` 및 라는 텍스트 상자가 `TextBox1` 라는 기본 폼에 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-142">To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`.</span></span> <span data-ttu-id="53235-143">그런 다음 폼을 마우스 오른쪽 단추로 클릭 하 고 클릭 **코드 보기** 코드 편집기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="53235-143">Then right-click the form and click **View Code** to open the Code Editor.</span></span>  
  
 <span data-ttu-id="53235-144">추가 `WithEvents` 의 선언 섹션에는 변수는 `Form1` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="53235-144">Add a `WithEvents` variable to the declarations section of the `Form1` class.</span></span>  
  
 <span data-ttu-id="53235-145">[!code-vb[VbVbalrEvents #&14;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="53235-145">[!code-vb[VbVbalrEvents#14](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="53235-146">예제</span><span class="sxs-lookup"><span data-stu-id="53235-146">Example</span></span>  
 <span data-ttu-id="53235-147">`Form1`에 대한 코드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-147">Add the following code to the code for `Form1`.</span></span> <span data-ttu-id="53235-148">교체와 같은 존재할 수 있는 모든 중복 프로시저 `Form_Load`, 또는 `Button_Click`합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-148">Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.</span></span>  
  
 <span data-ttu-id="53235-149">[!code-vb[VbVbalrEvents #&15;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="53235-149">[!code-vb[VbVbalrEvents#15](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/raiseevent-statement_3.vb)]</span></span>  
  
 <span data-ttu-id="53235-150">앞의 예제를 실행 하 고 저장 단추를 클릭 하는 F5 키를 눌러 **시작**합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-150">Press F5 to run the preceding example, and click the button labeled **Start**.</span></span> <span data-ttu-id="53235-151">첫 번째 텍스트 상자에서 초를 카운트 다운하기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-151">The first text box starts to count down the seconds.</span></span> <span data-ttu-id="53235-152">전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="53235-152">When the full time (10 seconds) has elapsed, the first text box displays "Done".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53235-153">`My.Application.DoEvents` 메서드 이벤트를 처리 하지 동일한 방식으로 폼 마찬가지로 합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-153">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="53235-154">사용할 수를 직접 이벤트를 처리 하기 위해 다중 스레딩을 합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-154">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="53235-155">자세한 내용은 참조 [스레딩](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)합니다.</span><span class="sxs-lookup"><span data-stu-id="53235-155">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53235-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="53235-156">See Also</span></span>  
 <span data-ttu-id="53235-157">[이벤트](../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="53235-157">[Events](../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="53235-158"> [Event 문](../../../visual-basic/language-reference/statements/event-statement.md) </span><span class="sxs-lookup"><span data-stu-id="53235-158"> [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md) </span></span>  
<span data-ttu-id="53235-159"> [AddHandler 문](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="53235-159"> [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md) </span></span>  
<span data-ttu-id="53235-160"> [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span><span class="sxs-lookup"><span data-stu-id="53235-160"> [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md) </span></span>  
<span data-ttu-id="53235-161"> [핸들](../../../visual-basic/language-reference/statements/handles-clause.md)</span><span class="sxs-lookup"><span data-stu-id="53235-161"> [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)</span></span>
