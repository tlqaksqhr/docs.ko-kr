---
title: 이벤트 처리 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1743e5f5d9dcdf83ab646407cd1fcdc77ff71cd
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="fe985-102">연습: 이벤트 처리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe985-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="fe985-103">이벤트로 작업 하는 방법을 보여 주는 두 항목 중 두 번째 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="fe985-104">첫 번째 항목 [연습: 이벤트 선언 및 발생](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)를 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="fe985-105">이 섹션에서는 발생할 때 이벤트를 처리 하는 방법을 보여 주는 폼과 다음 연습에서 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="fe985-106">`Widget` 클래스 예제에는 일반적인 이벤트 처리 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-106">The `Widget` class example uses traditional event-handling statements.</span></span> <span data-ttu-id="fe985-107">Visual Basic에서 이벤트를 사용한 작업에 대 한 명시 된 기타 기술을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-107">Visual Basic provides other techniques for working with events.</span></span> <span data-ttu-id="fe985-108">연습으로 사용 하도록이 예제를 수정할 수 있습니다는 `AddHandler` 및 `Handles` 문.</span><span class="sxs-lookup"><span data-stu-id="fe985-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="fe985-109">위젯 클래스의 PercentDone 이벤트를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="fe985-109">To handle the PercentDone event of the Widget class</span></span>  
  
1.  <span data-ttu-id="fe985-110">에 다음 코드를 넣을 `Form1`:</span><span class="sxs-lookup"><span data-stu-id="fe985-110">Place the following code in `Form1`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     <span data-ttu-id="fe985-111">`WithEvents` 키워드를 지정 하는 변수 `mWidget` 개체의 이벤트를 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-111">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="fe985-112">개체가 만들어집니다 클래스의 이름을 제공 하 여 개체의 종류를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-112">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="fe985-113">변수 `mWidget` 에 선언 된 `Form1` 때문에 `WithEvents` 변수 클래스 수준 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-113">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="fe985-114">에 배치 되는 클래스의 유형에 관계 없이 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-114">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="fe985-115">변수 `mblnCancel` 취소 하는 데 사용 되는 `LongTask` 메서드.</span><span class="sxs-lookup"><span data-stu-id="fe985-115">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="fe985-116">이벤트를 처리 하는 코드 작성</span><span class="sxs-lookup"><span data-stu-id="fe985-116">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="fe985-117">사용 하는 변수를 선언 하는 즉시 `WithEvents`, 클래스의 왼쪽된 드롭다운 목록에서 변수 이름이 나타납니다 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-117">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="fe985-118">선택 하는 경우 `mWidget`, `Widget` 클래스의 이벤트 오른쪽 드롭다운 목록에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-118">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="fe985-119">이벤트를 선택 하면 해당 이벤트 프로시저가 접두사와 함께 표시 됩니다. `mWidget` 과 밑줄이 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-119">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="fe985-120">와 연결 된 모든 이벤트 프로시저는 `WithEvents` 변수에는 접두사로 변수 이름이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-120">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="fe985-121">이벤트를 처리 하도록</span><span class="sxs-lookup"><span data-stu-id="fe985-121">To handle an event</span></span>  
  
1.  <span data-ttu-id="fe985-122">선택 `mWidget` 왼쪽 드롭다운 목록에서 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-122">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="fe985-123">선택 된 `PercentDone` 오른쪽 드롭다운 목록에서 이벤트 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-123">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="fe985-124">**코드 편집기** 열립니다는 `mWidget_PercentDone` 이벤트 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-124">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe985-125">**코드 편집기** 는 유용 하지만 새 이벤트 처리기를 삽입 하는 데 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-125">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="fe985-126">이 연습에서는 것이 이벤트 처리기 코드에 직접 복사 하는 보다 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-126">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3.  <span data-ttu-id="fe985-127">다음 코드를 `mWidget_PercentDone` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-127">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     <span data-ttu-id="fe985-128">때마다는 `PercentDone` 이벤트가 발생 하면 이벤트 프로시저 표시에서 완료율은 `Label` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-128">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="fe985-129">`DoEvents` 메서드를 사용 하면 다시 그릴 수 레이블을 또한에 게 사용자를 클릭 하 고는 **취소** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-129">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="fe985-130">다음 코드에 대 한 추가 `Button2_Click` 이벤트 처리기.</span><span class="sxs-lookup"><span data-stu-id="fe985-130">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 <span data-ttu-id="fe985-131">클릭 하면는 **취소** 동안 단추 `LongTask` 실행 되는 `Button2_Click` 이벤트가 실행 될으로 `DoEvents` 문을 적용 되려면 이벤트 처리를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-131">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="fe985-132">클래스 수준 변수 `mblnCancel` 로 설정 된 `True`, 및 `mWidget_PercentDone` 테스트 한 설정 하는 다음 이벤트는 `ByRef Cancel` 인수 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-132">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="fe985-133">WithEvents 변수 개체에 연결</span><span class="sxs-lookup"><span data-stu-id="fe985-133">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="fe985-134">`Form1` 처리 하도록 설정 된 `Widget` 개체의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-134">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="fe985-135">이제 남은 것 찾으려고는 `Widget` 어딘가에 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-135">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="fe985-136">변수를 선언 하는 경우 `WithEvents` 디자인 타임에 없는 개체는 이와 연관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-136">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="fe985-137">A `WithEvents` 변수는 다른 개체 변수 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-137">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="fe985-138">개체를 만들고 사용 하 여에 대 한 참조를 할당 해야는 `WithEvents` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-138">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="fe985-139">개체를 생성 하 고 참조를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="fe985-139">To create an object and assign a reference to it</span></span>  
  
1.  <span data-ttu-id="fe985-140">선택 **(Form1 이벤트)** 왼쪽 드롭다운 목록에서 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-140">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="fe985-141">선택 된 `Load` 오른쪽 드롭다운 목록에서 이벤트 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-141">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="fe985-142">**코드 편집기** 열립니다는 `Form1_Load` 이벤트 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-142">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3.  <span data-ttu-id="fe985-143">다음 코드에 대 한 추가 `Form1_Load` 이벤트 프로시저를 만드는 `Widget`:</span><span class="sxs-lookup"><span data-stu-id="fe985-143">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 <span data-ttu-id="fe985-144">Visual Basic 만듭니다이 코드가 실행 되는 `Widget` 개체 및 해당 이벤트와 연결 된 이벤트 프로시저에 연결 `mWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-144">When this code executes, Visual Basic creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="fe985-145">때부터, 때마다는 `Widget` 발생 해당 `PercentDone` 이벤트는 `mWidget_PercentDone` 이벤트 프로시저를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-145">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="fe985-146">LongTask 메서드를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="fe985-146">To call the LongTask method</span></span>  
  
-   <span data-ttu-id="fe985-147">다음 코드를 `Button1_Click` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-147">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 <span data-ttu-id="fe985-148">전에 `LongTask` 메서드를 호출 완료율을 표시 해야 초기화 레이블과 클래스 수준 `Boolean` 으로 설정 되어 있어야 해당 메서드를 취소에 대 한 플래그 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-148">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="fe985-149">`LongTask` 작업 기간 12.2 시간 (초)으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-149">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="fe985-150">`PercentDone` 이벤트가 발생 한 번 마다 1 / 3 초입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-150">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="fe985-151">이벤트가 발생할 때마다는 `mWidget_PercentDone` 이벤트 프로시저를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-151">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="fe985-152">때 `LongTask` 완료 되 면 `mblnCancel` 있는지 테스트 `LongTask` 정상적으로 종료 하기 때문에 중지 된 경우 또는 `mblnCancel` 로 설정 된 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-152">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="fe985-153">완료율 전자의 경우에만 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-153">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="fe985-154">프로그램을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="fe985-154">To run the program</span></span>  
  
1.  <span data-ttu-id="fe985-155">F5 키를 눌러 실행된 모드에서 프로젝트를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-155">Press F5 to put the project in run mode.</span></span>  
  
2.  <span data-ttu-id="fe985-156">클릭는 **작업 시작** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-156">Click the **Start Task** button.</span></span> <span data-ttu-id="fe985-157">될 때마다는 `PercentDone` 이벤트가 발생 하면 완료 된 작업의 백분율 레이블을 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-157">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3.  <span data-ttu-id="fe985-158">클릭는 **취소** 단추 태스크를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-158">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="fe985-159">모양의 **취소** 단추에는 클릭할 때 즉시 변경 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-159">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="fe985-160">`Click` 이벤트가 발생할 수는 `My.Application.DoEvents` 문을 이벤트 처리를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-160">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe985-161">`My.Application.DoEvents` 메서드 이벤트를 처리 하지 동일한 방식으로 폼 마찬가지로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-161">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="fe985-162">예를 들어이 연습에서는 클릭 해야는 **취소** 단추를 두 번입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-162">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="fe985-163">이벤트를 직접 처리 하기를 사용할 수 있습니다 다중 스레딩을 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-163">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="fe985-164">자세한 내용은 참조 [스레딩](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-164">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="fe985-165">F11으로 프로그램을 실행 하 여 한 번에 한 줄을 코드를 단계별로 실행 하는 방법도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-165">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="fe985-166">실행 중 시작 하는 방법을 볼 수 있듯이 `LongTask`, 간단 하 게 다시 진입할 `Form1` 될 때마다는 `PercentDone` 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-166">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="fe985-167">수행 된 작업의 코드에 다시 실행 되는 동안 if, `Form1`, `LongTask` 메서드를 다시 호출?</span><span class="sxs-lookup"><span data-stu-id="fe985-167">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="fe985-168">최악의 경우 스택 오버플로가 발생할 수 있습니다 `LongTask` 이벤트가 발생할 때마다가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-168">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="fe985-169">변수를 발생 시킬 수 있습니다 `mWidget` 다른 이벤트를 처리할 `Widget` 새에 대 한 참조를 할당 하 여 개체 `Widget` 를 `mWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-169">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="fe985-170">코드를 만들 수는 실제로 `Button1_Click` 단추를 클릭할 때마다이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-170">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="fe985-171">다른 장치에 대 한 이벤트를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="fe985-171">To handle events for a different widget</span></span>  
  
-   <span data-ttu-id="fe985-172">다음 줄의 코드를 추가 `Button1_Click` 절차 바로 앞에 행을 기록해둡니다 `mWidget.LongTask(12.2, 0.33)`:</span><span class="sxs-lookup"><span data-stu-id="fe985-172">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 <span data-ttu-id="fe985-173">위의 코드에서는 새 `Widget` 단추를 클릭할 때마다 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-173">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="fe985-174">즉시는 `LongTask` 메서드가 완료 되 면에 대 한 참조는 `Widget` 출시 되 면 및 `Widget` 소멸 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-174">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="fe985-175">A `WithEvents` 변수가 한 번에 하나의 개체 참조를 포함할 수 있으므로 다른 할당 하는 경우 `Widget` 개체를 `mWidget`, 이전 `Widget` 개체의 이벤트를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-175">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="fe985-176">경우 `mWidget` 이전에 대 한 참조를 포함 하는 유일한 개체 변수가 `Widget`, 해당 개체가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-176">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="fe985-177">여러 이벤트를 처리 하려는 경우 `Widget` 개체를 사용 하 여는 `AddHandler` 각 개체의 이벤트를 개별적으로 처리 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-177">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe985-178">많은 선언할 수 있습니다 `WithEvents` 배열을 하지만 변수의 수, 필요한 `WithEvents` 변수는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fe985-178">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe985-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe985-179">See Also</span></span>  
 [<span data-ttu-id="fe985-180">연습: 이벤트 선언 및 발생</span><span class="sxs-lookup"><span data-stu-id="fe985-180">Walkthrough: Declaring and Raising Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 [<span data-ttu-id="fe985-181">이벤트</span><span class="sxs-lookup"><span data-stu-id="fe985-181">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
