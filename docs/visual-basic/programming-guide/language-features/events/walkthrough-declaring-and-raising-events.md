---
title: (Visual Basic) 이벤트 선언 및 발생
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 67bbf7bc95a0fe1ee8e9c2a6cf07d850d30bb028
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652811"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="bb2fe-102">연습: 이벤트 선언 및 발생(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bb2fe-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="bb2fe-103">이 연습에서는 선언 하 고 라는 클래스에 이벤트를 발생 하는 방법을 보여 줍니다. `Widget`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="bb2fe-104">항목을 참고할 하려는 단계를 완료 한 후 [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), 이벤트를 사용 하는 방법을 보여 주는 `Widget` 응용 프로그램에서 상태 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="bb2fe-105">위젯 클래스</span><span class="sxs-lookup"><span data-stu-id="bb2fe-105">The Widget Class</span></span>  
 <span data-ttu-id="bb2fe-106">있는 것으로 가정는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="bb2fe-107">프로그램 `Widget` 클래스에는 실행 하는 데 시간이 오래 걸릴 수 있습니다 하는 메서드를 일종의 완료 표시기 나타내려고 되도록 응용 프로그램 및입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="bb2fe-108">만들 수는 물론,는 `Widget` 개체 완료율 대화 상자를 표시 한 다음 할 수 있지만 수 이후에를 사용 하는 모든 프로젝트에서이 대화 상자는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="bb2fe-109">사용자 인터페이스 개체 핸들을 사용 하는 응용 프로그램을 사용 하는 개체를 디자인 하는 좋은 원칙 것-경우에 개체의 전체 목적은 양식 또는 대화 상자를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="bb2fe-110">목적은 `Widget` 추가 하는 것 이므로, 다른 작업을 수행 하는 것을 `PercentDone` 이벤트 및 호출 하는 프로시저를 통해 `Widget`의 메서드는 처리할 업데이트 이벤트와 표시 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="bb2fe-111">`PercentDone` 이벤트 작업을 취소 하기 위한 메커니즘을 제공할 수도 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="bb2fe-112">이 항목에 대 한 코드 예제를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="bb2fe-113">새 Visual Basic Windows 응용 프로그램 프로젝트를 열고 라는 양식을 만드는 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-113">Open a new Visual Basic Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="bb2fe-114">두 개의 단추와 적절 한 레이블을 추가 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="bb2fe-115">다음 표에 나와 있는 것처럼 개체의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="bb2fe-116">개체</span><span class="sxs-lookup"><span data-stu-id="bb2fe-116">Object</span></span>|<span data-ttu-id="bb2fe-117">속성</span><span class="sxs-lookup"><span data-stu-id="bb2fe-117">Property</span></span>|<span data-ttu-id="bb2fe-118">설정</span><span class="sxs-lookup"><span data-stu-id="bb2fe-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="bb2fe-119">시작 태스크</span><span class="sxs-lookup"><span data-stu-id="bb2fe-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="bb2fe-120">취소</span><span class="sxs-lookup"><span data-stu-id="bb2fe-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="bb2fe-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="bb2fe-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="bb2fe-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="bb2fe-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="bb2fe-123">에 **프로젝트** 메뉴 선택 **클래스 추가** 라는 클래스를 추가 하려면 `Widget.vb` 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="bb2fe-124">위젯 클래스에 대 한 이벤트를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="bb2fe-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="bb2fe-125">사용 하 여는 `Event` 에서 이벤트를 선언 하는 키워드는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="bb2fe-126">이벤트를 가질 수 있는 참고 `ByVal` 및 `ByRef` 인수,으로 `Widget`의 `PercentDone` 이벤트:</span><span class="sxs-lookup"><span data-stu-id="bb2fe-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 <span data-ttu-id="bb2fe-127">호출 하는 개체를 받으면는 `PercentDone` 이벤트는 `Percent` 인수 완료 된 작업의 백분율을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-127">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="bb2fe-128">`Cancel` 인수로 설정할 수 있습니다 `True` 이벤트를 발생 시킨 메서드를 취소할 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-128">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb2fe-129">다음과 같은 예외가 프로시저 인수를 같은 방식으로 이벤트 인수를 선언할 수 있습니다: 이벤트 가질 수 없습니다 `Optional` 또는 `ParamArray` 이벤트 및 인수, 반환 값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-129">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="bb2fe-130">`PercentDone` 이벤트에 의해 발생 되는 `LongTask` 의 메서드는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-130">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="bb2fe-131">`LongTask` 두 개의 인수: 작업 및 하기 전에 최소 시간 간격에는 시간 메서드가 가로채어 `LongTask` 일시 중지를 발생 시키는 `PercentDone` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-131">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="bb2fe-132">PercentDone 이벤트 발생</span><span class="sxs-lookup"><span data-stu-id="bb2fe-132">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="bb2fe-133">에 대 한 액세스를 간소화 하기 위해는 `Timer` 이 클래스에서 사용 하는 속성에 추가 `Imports` 클래스 모듈의 선언 섹션의 맨 위에 문을 위에 `Class Widget` 문.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-133">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  <span data-ttu-id="bb2fe-134">`Widget` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-134">Add the following code to the `Widget` class:</span></span>  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 <span data-ttu-id="bb2fe-135">응용 프로그램 호출 하는 경우는 `LongTask` 메서드는 `Widget` 발생 시키는 클래스는 `PercentDone` 이벤트 모든 `MinimumInterval` 초입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-135">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="bb2fe-136">이 이벤트는 반환 될 때 `LongTask` 확인 하는 `Cancel` 인수를 설정한 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-136">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="bb2fe-137">몇 가지 사항을 고려해 야 여기 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-137">A few disclaimers are necessary here.</span></span> <span data-ttu-id="bb2fe-138">간단히 하기 위해는 `LongTask` 프로시저 미리 알고 있는 작업 소요 될 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-138">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="bb2fe-139">이 경우 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-139">This is almost never the case.</span></span> <span data-ttu-id="bb2fe-140">작업 짝수 크기의 청크로 나누는 것이 어려울 수 있습니다 및 종종 가장 중요 한 사용자에 게는 단순히 이유가 항목 표시 해지기 전에 경과 되는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-140">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="bb2fe-141">이 샘플의 다른 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-141">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="bb2fe-142">`Timer` 자정 바로 전에 시작 된 경우 응용 프로그램 중지 따라서; 속성 자정부터 경과한 시간 (초) 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-142">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="bb2fe-143">보다 신중 시간을 측정 하는 이러한 고려 경계 조건을 거 나 피하도록, 같은 속성을 사용 하 여 `Now`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-143">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="bb2fe-144">이제는 `Widget` 클래스에서 이벤트를 발생 수를 이동할 수 있습니다 다음 연습 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-144">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="bb2fe-145">[연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) 사용 하는 방법을 보여 줍니다. `WithEvents` 와 이벤트 처리기를 연결 하는 `PercentDone` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2fe-145">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb2fe-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb2fe-146">See Also</span></span>  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [<span data-ttu-id="bb2fe-147">연습: 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="bb2fe-147">Walkthrough: Handling Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [<span data-ttu-id="bb2fe-148">이벤트</span><span class="sxs-lookup"><span data-stu-id="bb2fe-148">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)
