---
title: "이벤트 처리 (Visual Basic) | Microsoft 문서"
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
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword, walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
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
ms.openlocfilehash: b4ad77b3b0236e762fc17b8aba9d34108c8d75b5
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-handling-events-visual-basic"></a><span data-ttu-id="8be22-102">연습: 이벤트 처리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8be22-102">Walkthrough: Handling Events (Visual Basic)</span></span>
<span data-ttu-id="8be22-103">이벤트와 함께 작업 하는 방법을 보여 주는 두 항목 중 두 번째 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-103">This is the second of two topics that demonstrate how to work with events.</span></span> <span data-ttu-id="8be22-104">첫 번째 항목 [연습: 이벤트 선언 및 발생](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)를 선언 하 고 이벤트를 발생 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-104">The first topic, [Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), shows how to declare and raise events.</span></span> <span data-ttu-id="8be22-105">이 섹션에서는 발생할 때 이벤트를 처리 하는 방법을 보여 주는 폼과 해당 연습에서 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-105">This section uses the form and class from that walkthrough to show how to handle events when they take place.</span></span>  
  
 <span data-ttu-id="8be22-106">`Widget` 클래스 예제에는 일반적인 이벤트 처리 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-106">The `Widget` class example uses traditional event-handling statements.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="8be22-107">이벤트를 사용 하기 위한 다른 기법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-107"> provides other techniques for working with events.</span></span> <span data-ttu-id="8be22-108">연습을 사용 하 여이 예제를 수정할 수는 `AddHandler` 및 `Handles` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-108">As an exercise, you can modify this example to use the `AddHandler` and `Handles` statements.</span></span>  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a><span data-ttu-id="8be22-109">위젯 클래스의 PercentDone 이벤트를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="8be22-109">To handle the PercentDone event of the Widget class</span></span>  
  
1.  <span data-ttu-id="8be22-110">에 다음 코드를 넣을 `Form1`:</span><span class="sxs-lookup"><span data-stu-id="8be22-110">Place the following code in `Form1`:</span></span>  
  
     <span data-ttu-id="8be22-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&4;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8be22-111">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]</span></span>  
  
     <span data-ttu-id="8be22-112">`WithEvents` 키워드를 지정 하는 변수 `mWidget` 개체의 이벤트를 처리 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-112">The `WithEvents` keyword specifies that the variable `mWidget` is used to handle an object's events.</span></span> <span data-ttu-id="8be22-113">개체가 생성 될 클래스의 이름을 제공 하 여 개체의 종류를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-113">You specify the kind of object by supplying the name of the class from which the object will be created.</span></span>  
  
     <span data-ttu-id="8be22-114">변수 `mWidget` 에 선언 된 `Form1` 때문에 `WithEvents` 변수는 클래스 수준 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-114">The variable `mWidget` is declared in `Form1` because `WithEvents` variables must be class-level.</span></span> <span data-ttu-id="8be22-115">에 배치 되는 클래스의 형식에 관계 없이 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-115">This is true regardless of the type of class you place them in.</span></span>  
  
     <span data-ttu-id="8be22-116">변수 `mblnCancel` 취소 하는 데 사용 되는 `LongTask` 메서드.</span><span class="sxs-lookup"><span data-stu-id="8be22-116">The variable `mblnCancel` is used to cancel the `LongTask` method.</span></span>  
  
## <a name="writing-code-to-handle-an-event"></a><span data-ttu-id="8be22-117">이벤트를 처리 하는 코드 작성</span><span class="sxs-lookup"><span data-stu-id="8be22-117">Writing Code to Handle an Event</span></span>  
 <span data-ttu-id="8be22-118">사용 하는 변수를 선언 하는 즉시 `WithEvents`, 클래스의 왼쪽된 드롭 다운 목록에서 변수 이름이 표시 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-118">As soon as you declare a variable using `WithEvents`, the variable name appears in the left drop-down list of the class's **Code Editor**.</span></span> <span data-ttu-id="8be22-119">선택 하면 `mWidget`, `Widget` 클래스의 이벤트 오른쪽 드롭다운 목록에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-119">When you select `mWidget`, the `Widget` class's events appear in the right drop-down list.</span></span> <span data-ttu-id="8be22-120">접두사와 해당 이벤트 프로시저에서 이벤트를 선택 하면 표시 `mWidget` 과 밑줄이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-120">Selecting an event displays the corresponding event procedure, with the prefix `mWidget` and an underscore.</span></span> <span data-ttu-id="8be22-121">와 연결 된 모든 이벤트 프로시저는 `WithEvents` 변수는 변수 이름 접두사로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-121">All the event procedures associated with a `WithEvents` variable are given the variable name as a prefix.</span></span>  
  
#### <a name="to-handle-an-event"></a><span data-ttu-id="8be22-122">이벤트를 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="8be22-122">To handle an event</span></span>  
  
1.  <span data-ttu-id="8be22-123">선택 `mWidget` 왼쪽 드롭 다운 목록에서 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-123">Select `mWidget` from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="8be22-124">선택 된 `PercentDone` 오른쪽 드롭다운 목록에서 이벤트 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-124">Select the `PercentDone` event from the right drop-down list.</span></span> <span data-ttu-id="8be22-125">**코드 편집기** 열립니다는 `mWidget_PercentDone` 이벤트 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-125">The **Code Editor** opens the `mWidget_PercentDone` event procedure.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8be22-126">**코드 편집기** 는 유용 하지만 새 이벤트 처리기를 삽입에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-126">The **Code Editor** is useful, but not required, for inserting new event handlers.</span></span> <span data-ttu-id="8be22-127">이 연습에서는 것이 이벤트 처리기 코드에 직접 복사 하는 보다 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-127">In this walkthrough, it is more direct to just copy the event handlers directly into your code.</span></span>  
  
3.  <span data-ttu-id="8be22-128">다음 코드를 `mWidget_PercentDone` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-128">Add the following code to the `mWidget_PercentDone` event handler:</span></span>  
  
     <span data-ttu-id="8be22-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&5;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8be22-129">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]</span></span>  
  
     <span data-ttu-id="8be22-130">때마다는 `PercentDone` 이벤트가 발생 하면 이벤트 프로시저에서 완료율을 표시 한 `Label` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-130">Whenever the `PercentDone` event is raised, the event procedure displays the percent complete in a `Label` control.</span></span> <span data-ttu-id="8be22-131">`DoEvents` 메서드를 사용 하면 자동으로 그려지도록, 레이블을 또한에 게 사용자를 클릭 하 고는 **취소** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-131">The `DoEvents` method allows the label to repaint, and also gives the user the opportunity to click the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="8be22-132">다음 코드에 대 한 추가 `Button2_Click` 이벤트 처리기:</span><span class="sxs-lookup"><span data-stu-id="8be22-132">Add the following code for the `Button2_Click` event handler:</span></span>  
  
     <span data-ttu-id="8be22-133">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&6;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8be22-133">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]</span></span>  
  
 <span data-ttu-id="8be22-134">클릭 하면는 **취소** 동안 단추 `LongTask` 실행 중인는 `Button2_Click` 이벤트가 실행 될 즉시는 `DoEvents` 문이 발생 하도록 이벤트 처리를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-134">If the user clicks the **Cancel** button while `LongTask` is running, the `Button2_Click` event is executed as soon as the `DoEvents` statement allows event processing to occur.</span></span> <span data-ttu-id="8be22-135">클래스 수준 변수 `mblnCancel` 로 설정 된 `True`, 및 `mWidget_PercentDone` 테스트 한 설정 하는 다음 이벤트는 `ByRef Cancel` 인수를 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-135">The class-level variable `mblnCancel` is set to `True`, and the `mWidget_PercentDone` event then tests it and sets the `ByRef Cancel` argument to `True`.</span></span>  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a><span data-ttu-id="8be22-136">WithEvents 변수가 개체에 연결</span><span class="sxs-lookup"><span data-stu-id="8be22-136">Connecting a WithEvents Variable to an Object</span></span>  
 <span data-ttu-id="8be22-137">`Form1`처리 하도록 설정 된 `Widget` 개체의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-137">`Form1` is now set up to handle a `Widget` object's events.</span></span> <span data-ttu-id="8be22-138">이제 남은 것을 찾으려고는 `Widget` 어딘가에 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-138">All that remains is to find a `Widget` somewhere.</span></span>  
  
 <span data-ttu-id="8be22-139">변수를 선언 하면 `WithEvents` 없는 개체는 연결 된 디자인 타임에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-139">When you declare a variable `WithEvents` at design time, no object is associated with it.</span></span> <span data-ttu-id="8be22-140">A `WithEvents` 변수는 다른 모든 개체 변수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-140">A `WithEvents` variable is just like any other object variable.</span></span> <span data-ttu-id="8be22-141">개체를 만들고 사용 하 여에 대 한 참조를 할당 해야는 `WithEvents` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-141">You have to create an object and assign a reference to it with the `WithEvents` variable.</span></span>  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a><span data-ttu-id="8be22-142">개체를 생성 하 고 그에 대 한 참조를 할당 하려면</span><span class="sxs-lookup"><span data-stu-id="8be22-142">To create an object and assign a reference to it</span></span>  
  
1.  <span data-ttu-id="8be22-143">선택 **(Form1 이벤트)** 왼쪽 드롭 다운 목록에서 **코드 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-143">Select **(Form1 Events)** from the left drop-down list in the **Code Editor**.</span></span>  
  
2.  <span data-ttu-id="8be22-144">선택 된 `Load` 오른쪽 드롭다운 목록에서 이벤트 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-144">Select the `Load` event from the right drop-down list.</span></span> <span data-ttu-id="8be22-145">**코드 편집기** 열립니다는 `Form1_Load` 이벤트 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-145">The **Code Editor** opens the `Form1_Load` event procedure.</span></span>  
  
3.  <span data-ttu-id="8be22-146">다음 코드에 대 한 추가 `Form1_Load` 이벤트 프로시저를 만드는 `Widget`:</span><span class="sxs-lookup"><span data-stu-id="8be22-146">Add the following code for the `Form1_Load` event procedure to create the `Widget`:</span></span>  
  
     <span data-ttu-id="8be22-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&7;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="8be22-147">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]</span></span>  
  
 <span data-ttu-id="8be22-148">이 코드가 실행 되 면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 만듭니다는 `Widget` 개체와 관련 된 이벤트 프로시저를 해당 이벤트를 연결 `mWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-148">When this code executes, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] creates a `Widget` object and connects its events to the event procedures associated with `mWidget`.</span></span> <span data-ttu-id="8be22-149">때부터, 때마다는 `Widget` 를 발생 시킵니다 해당 `PercentDone` 이벤트는 `mWidget_PercentDone` 이벤트 프로시저가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-149">From that point on, whenever the `Widget` raises its `PercentDone` event, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
#### <a name="to-call-the-longtask-method"></a><span data-ttu-id="8be22-150">LongTask 메서드를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="8be22-150">To call the LongTask method</span></span>  
  
-   <span data-ttu-id="8be22-151">다음 코드를 `Button1_Click` 이벤트 처리기에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-151">Add the following code to the `Button1_Click` event handler:</span></span>  
  
     <span data-ttu-id="8be22-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&8;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="8be22-152">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]</span></span>  
  
 <span data-ttu-id="8be22-153">전에 `LongTask` 완료율을 표시 해야 초기화 레이블과 클래스 수준의 메서드를 호출 `Boolean` 으로 설정 되어 있어야 해당 메서드를 취소에 대 한 플래그 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-153">Before the `LongTask` method is called, the label that displays the percent complete must be initialized, and the class-level `Boolean` flag for canceling the method must be set to `False`.</span></span>  
  
 <span data-ttu-id="8be22-154">`LongTask`12.2 초의 작업 기간으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-154">`LongTask` is called with a task duration of 12.2 seconds.</span></span> <span data-ttu-id="8be22-155">`PercentDone` 이벤트는 한 번 마다&1; /&3; 초입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-155">The `PercentDone` event is raised once every one-third of a second.</span></span> <span data-ttu-id="8be22-156">이벤트가 발생 될 때마다는 `mWidget_PercentDone` 이벤트 프로시저가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-156">Each time the event is raised, the `mWidget_PercentDone` event procedure is executed.</span></span>  
  
 <span data-ttu-id="8be22-157">때 `LongTask` 완료 되 면 `mblnCancel` 있는지 테스트 `LongTask` 정상적으로 종료 하기 때문에 가상 컴퓨터가 중지 또는 `mblnCancel` 로 설정 된 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-157">When `LongTask` is done, `mblnCancel` is tested to see if `LongTask` ended normally, or if it stopped because `mblnCancel` was set to `True`.</span></span> <span data-ttu-id="8be22-158">완료율 옵션을 선택한 경우에만 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-158">The percent complete is updated only in the former case.</span></span>  
  
#### <a name="to-run-the-program"></a><span data-ttu-id="8be22-159">프로그램을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8be22-159">To run the program</span></span>  
  
1.  <span data-ttu-id="8be22-160">F5 키를 눌러 실행된 모드에는 프로젝트를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-160">Press F5 to put the project in run mode.</span></span>  
  
2.  <span data-ttu-id="8be22-161">클릭 하 고 **작업 시작** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-161">Click the **Start Task** button.</span></span> <span data-ttu-id="8be22-162">때마다는 `PercentDone` 이벤트가 발생 하면 완료 된 작업의 백분율 레이블을 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-162">Each time the `PercentDone` event is raised, the label is updated with the percentage of the task that is complete.</span></span>  
  
3.  <span data-ttu-id="8be22-163">클릭 된 **취소** 작업을 중지 하려면 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-163">Click the **Cancel** button to stop the task.</span></span> <span data-ttu-id="8be22-164">모양의 **취소** 단추 클릭 하면 바로 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-164">Notice that the appearance of the **Cancel** button does not change immediately when you click it.</span></span> <span data-ttu-id="8be22-165">`Click` 이벤트가 발생할 수는 `My.Application.DoEvents` 문을 이벤트 처리를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-165">The `Click` event cannot happen until the `My.Application.DoEvents` statement allows event processing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8be22-166">`My.Application.DoEvents` 메서드 이벤트를 처리 하지 동일한 방식으로 폼 마찬가지로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-166">The `My.Application.DoEvents` method does not process events in exactly the same way as the form does.</span></span> <span data-ttu-id="8be22-167">예를 들어이 연습에서는 클릭 해야는 **취소** 단추를 두 번입니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-167">For example, in this walkthrough, you must click the **Cancel** button twice.</span></span> <span data-ttu-id="8be22-168">사용할 수를 직접 이벤트를 처리 하기 위해 다중 스레딩을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-168">To allow the form to handle the events directly, you can use multithreading.</span></span> <span data-ttu-id="8be22-169">자세한 내용은 참조 [스레딩](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-169">For more information, see [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).</span></span>  
  
 <span data-ttu-id="8be22-170">F11으로 프로그램을 실행 하 여 한 번에 한 줄을 코드를 단계별로 실행 하는 방법도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-170">You may find it instructive to run the program with F11 and step through the code a line at a time.</span></span> <span data-ttu-id="8be22-171">실행 중 시작 하는 방법을 볼 수 있듯이 `LongTask`, 간단 하 게 다시 진입할 `Form1` 때마다는 `PercentDone` 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-171">You can clearly see how execution enters `LongTask`, and then briefly re-enters `Form1` each time the `PercentDone` event is raised.</span></span>  
  
 <span data-ttu-id="8be22-172">어떤 일이 발생 하면 실행이의 코드에 다시 `Form1`, `LongTask` 메서드를 다시 호출?</span><span class="sxs-lookup"><span data-stu-id="8be22-172">What would happen if, while execution was back in the code of `Form1`, the `LongTask` method were called again?</span></span> <span data-ttu-id="8be22-173">최악의 경우에 스택 오버플로가 발생할 수 있습니다 `LongTask` 이벤트가 발생할 때마다가 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-173">At worst, a stack overflow might occur if `LongTask` were called every time the event was raised.</span></span>  
  
 <span data-ttu-id="8be22-174">변수를 할 수 있습니다 `mWidget` 다른 이벤트를 처리할 `Widget` 새에 대 한 참조를 할당 하 여 개체 `Widget` 를 `mWidget`합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-174">You can cause the variable `mWidget` to handle events for a different `Widget` object by assigning a reference to the new `Widget` to `mWidget`.</span></span> <span data-ttu-id="8be22-175">사실에 코드를 만들 수 있습니다 `Button1_Click` 단추를 클릭할 때마다이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-175">In fact, you can make the code in `Button1_Click` do this every time you click the button.</span></span>  
  
#### <a name="to-handle-events-for-a-different-widget"></a><span data-ttu-id="8be22-176">다른 장치에 대 한 이벤트를 처리 하기</span><span class="sxs-lookup"><span data-stu-id="8be22-176">To handle events for a different widget</span></span>  
  
-   <span data-ttu-id="8be22-177">다음 코드 줄을 추가 하는 `Button1_Click` 줄 바로 앞에 나오는 절차 `mWidget.LongTask(12.2, 0.33)`:</span><span class="sxs-lookup"><span data-stu-id="8be22-177">Add the following line of code to the `Button1_Click` procedure, immediately preceding the line that reads `mWidget.LongTask(12.2, 0.33)`:</span></span>  
  
     <span data-ttu-id="8be22-178">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&9;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="8be22-178">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]</span></span>  
  
 <span data-ttu-id="8be22-179">위의 코드에서는 새 `Widget` 될 때마다 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-179">The code above creates a new `Widget` each time the button is clicked.</span></span> <span data-ttu-id="8be22-180">즉시는 `LongTask` 메서드가 완료 되 면에 대 한 참조는 `Widget` 해제 되 고 `Widget` 소멸 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-180">As soon as the `LongTask` method completes, the reference to the `Widget` is released, and the `Widget` is destroyed.</span></span>  
  
 <span data-ttu-id="8be22-181">A `WithEvents` 변수 한 번에 하나의 개체만 참조를 포함할 수 없습니다 다른 할당 하는 경우 그렇게 `Widget` 개체를 `mWidget`, 이전 `Widget` 개체의 이벤트를 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-181">A `WithEvents` variable can contain only one object reference at a time, so if you assign a different `Widget` object to `mWidget`, the previous `Widget` object's events will no longer be handled.</span></span> <span data-ttu-id="8be22-182">경우 `mWidget` 는 이전에 대 한 참조를 포함 하는 유일한 개체 변수 `Widget`, 해당 개체가 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-182">If `mWidget` is the only object variable containing a reference to the old `Widget`, the object is destroyed.</span></span> <span data-ttu-id="8be22-183">여러 이벤트를 처리 하려는 경우 `Widget` 개체를 사용 하 여는 `AddHandler` 문을 개별적으로 각 개체의 이벤트를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-183">If you want to handle events from several `Widget` objects, use the `AddHandler` statement to process events from each object separately.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8be22-184">많은 선언할 수 있습니다 `WithEvents` 배열을 하지만 변수의 수 필요한 `WithEvents` 변수가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8be22-184">You can declare as many `WithEvents` variables as you need, but arrays of `WithEvents` variables are not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be22-185">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8be22-185">See Also</span></span>  
 <span data-ttu-id="8be22-186">[연습: 이벤트 선언 및 발생](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span><span class="sxs-lookup"><span data-stu-id="8be22-186">[Walkthrough: Declaring and Raising Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md) </span></span>  
<span data-ttu-id="8be22-187"> [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="8be22-187"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
