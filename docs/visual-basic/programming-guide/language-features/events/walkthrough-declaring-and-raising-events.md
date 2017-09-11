---
title: "(Visual Basic) 이벤트 선언 및 발생 | Microsoft 문서"
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
- declarations, events
- events [Visual Basic], walkthroughs
- declaring events, walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events, walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
caps.latest.revision: 16
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
ms.openlocfilehash: eca112aca39bd998697d379a1705845e8f607367
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a><span data-ttu-id="b07cd-102">연습: 이벤트 선언 및 발생(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b07cd-102">Walkthrough: Declaring and Raising Events (Visual Basic)</span></span>
<span data-ttu-id="b07cd-103">이 연습에서는 선언 하 고 라는 클래스에 대 한 이벤트를 발생 하는 방법을 보여 줍니다. `Widget`합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-103">This walkthrough demonstrates how to declare and raise events for a class named `Widget`.</span></span> <span data-ttu-id="b07cd-104">관련 항목은 읽을 하려는 단계를 완료 한 후 [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), 이벤트를 사용 하는 방법을 보여 주는 `Widget` 응용 프로그램에서 상태 정보를 제공 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-104">After you complete the steps, you might want to read the companion topic, [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), which shows how to use events from `Widget` objects to provide status information in an application.</span></span>  
  
## <a name="the-widget-class"></a><span data-ttu-id="b07cd-105">Widget 클래스</span><span class="sxs-lookup"><span data-stu-id="b07cd-105">The Widget Class</span></span>  
 <span data-ttu-id="b07cd-106">해야 하는 순간에 대 한 가정는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-106">Assume for the moment that you have a `Widget` class.</span></span> <span data-ttu-id="b07cd-107">프로그램 `Widget` 일종의 완료 표시기 할애할 수 있으려면 응용 프로그램 및 클래스에 메서드를 실행 하는 데 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-107">Your `Widget` class has a method that can take a long time to execute, and you want your application to be able to put up some kind of completion indicator.</span></span>  
  
 <span data-ttu-id="b07cd-108">만들 수는 물론,는 `Widget` 개체 완료율 대화 상자를 표시 한 다음 할 수 있지만 수 이후에를 사용 하는 모든 프로젝트에서이 대화 상자는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-108">Of course, you could make the `Widget` object show a percent-complete dialog box, but then you would be stuck with that dialog box in every project in which you used the `Widget` class.</span></span> <span data-ttu-id="b07cd-109">사용자 인터페이스 개체 핸들을 사용 하는 응용 프로그램을 사용 하는 개체를 디자인 하는 좋은 원칙-경우에 개체의 전체 목적은 양식 또는 대화 상자를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-109">A good principle of object design is to let the application that uses an object handle the user interface—unless the whole purpose of the object is to manage a form or dialog box.</span></span>  
  
 <span data-ttu-id="b07cd-110">목적은 `Widget` 추가 하는 것 이므로, 다른 작업을 수행 하는 것을 `PercentDone` 이벤트 및 호출 하는 프로시저를 통해 `Widget`의 메서드는 처리할 업데이트 이벤트와 표시 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-110">The purpose of `Widget` is to perform other tasks, so it is better to add a `PercentDone` event and let the procedure that calls `Widget`'s methods handle that event and display status updates.</span></span> <span data-ttu-id="b07cd-111">`PercentDone` 이벤트 작업을 취소 하기 위한 메커니즘을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-111">The `PercentDone` event can also provide a mechanism for canceling the task.</span></span>  
  
#### <a name="to-build-the-code-example-for-this-topic"></a><span data-ttu-id="b07cd-112">이 항목에 대 한 코드 예제를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-112">To build the code example for this topic</span></span>  
  
1.  <span data-ttu-id="b07cd-113">새 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows 응용 프로그램 이라는 폼을 만들고 프로젝트 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-113">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project and create a form named `Form1`.</span></span>  
  
2.  <span data-ttu-id="b07cd-114">두 개의 단추와 적절 한 레이블을 추가 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-114">Add two buttons and a label to `Form1`.</span></span>  
  
3.  <span data-ttu-id="b07cd-115">다음 표에 나와 있는 것 처럼 개체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-115">Name the objects as shown in the following table.</span></span>  
  
    |<span data-ttu-id="b07cd-116">개체</span><span class="sxs-lookup"><span data-stu-id="b07cd-116">Object</span></span>|<span data-ttu-id="b07cd-117">속성</span><span class="sxs-lookup"><span data-stu-id="b07cd-117">Property</span></span>|<span data-ttu-id="b07cd-118">설정</span><span class="sxs-lookup"><span data-stu-id="b07cd-118">Setting</span></span>|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|<span data-ttu-id="b07cd-119">시작 태스크</span><span class="sxs-lookup"><span data-stu-id="b07cd-119">Start Task</span></span>|  
    |`Button2`|`Text`|<span data-ttu-id="b07cd-120">취소</span><span class="sxs-lookup"><span data-stu-id="b07cd-120">Cancel</span></span>|  
    |`Label`|<span data-ttu-id="b07cd-121">`(Name)`, `Text`</span><span class="sxs-lookup"><span data-stu-id="b07cd-121">`(Name)`, `Text`</span></span>|<span data-ttu-id="b07cd-122">lblPercentDone, 0</span><span class="sxs-lookup"><span data-stu-id="b07cd-122">lblPercentDone, 0</span></span>|  
  
4.  <span data-ttu-id="b07cd-123">에 **프로젝트** 메뉴 선택 **클래스 추가** 라는 클래스를 추가 하려면 `Widget.vb` 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-123">On the **Project** menu, choose **Add Class** to add a class named `Widget.vb` to the project.</span></span>  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a><span data-ttu-id="b07cd-124">Widget 클래스에 대 한 이벤트를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="b07cd-124">To declare an event for the Widget class</span></span>  
  
-   <span data-ttu-id="b07cd-125">사용 된 `Event` 에서 이벤트를 선언 하는 키워드는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-125">Use the `Event` keyword to declare an event in the `Widget` class.</span></span> <span data-ttu-id="b07cd-126">이벤트를 가질 수 있는 참고 `ByVal` 및 `ByRef` 인수도 `Widget`의 `PercentDone` 이벤트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-126">Note that an event can have `ByVal` and `ByRef` arguments, as `Widget`'s `PercentDone` event demonstrates:</span></span>  
  
     <span data-ttu-id="b07cd-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&1;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b07cd-127">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]</span></span>  
  
 <span data-ttu-id="b07cd-128">호출 하는 개체를 받으면는 `PercentDone` 이벤트는 `Percent` 인수 완료 된 작업의 백분율이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-128">When the calling object receives a `PercentDone` event, the `Percent` argument contains the percentage of the task that is complete.</span></span> <span data-ttu-id="b07cd-129">`Cancel` 인수 설정할 수 있습니다 `True` 이벤트를 발생 시킨 메서드를 취소할 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-129">The `Cancel` argument can be set to `True` to cancel the method that raised the event.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b07cd-130">인수는 다음과 같은 예외가 프로시저의 경우와 마찬가지로 이벤트 인수를 선언할 수 있습니다: 이벤트 여야 `Optional` 또는 `ParamArray` 인수 및 이벤트 값을 갖지 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-130">You can declare event arguments just as you do arguments of procedures, with the following exceptions: Events cannot have `Optional` or `ParamArray` arguments, and events do not have return values.</span></span>  
  
 <span data-ttu-id="b07cd-131">`PercentDone` 이벤트에 의해 발생 되는 `LongTask` 의 메서드는 `Widget` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-131">The `PercentDone` event is raised by the `LongTask` method of the `Widget` class.</span></span> <span data-ttu-id="b07cd-132">`LongTask`두 개의 인수: 하기 전에 최소 시간 간격 및 작업, 작업을 수행 하는 시간 메서드 가로채어 `LongTask` 일시 중지 시키려면는 `PercentDone` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-132">`LongTask` takes two arguments: the length of time the method pretends to be doing work, and the minimum time interval before `LongTask` pauses to raise the `PercentDone` event.</span></span>  
  
#### <a name="to-raise-the-percentdone-event"></a><span data-ttu-id="b07cd-133">PercentDone 이벤트 발생</span><span class="sxs-lookup"><span data-stu-id="b07cd-133">To raise the PercentDone event</span></span>  
  
1.  <span data-ttu-id="b07cd-134">에 대 한 액세스를 간소화 하는 `Timer` 이 클래스에서 사용 하는 속성 추가 `Imports` 클래스 모듈의 선언 섹션의 맨 위에 문을 위에 `Class Widget` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-134">To simplify access to the `Timer` property used by this class, add an `Imports` statement to the top of the declarations section of your class module, above the `Class Widget` statement.</span></span>  
  
     <span data-ttu-id="b07cd-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&2;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b07cd-135">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]</span></span>  
  
2.  <span data-ttu-id="b07cd-136">`Widget` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-136">Add the following code to the `Widget` class:</span></span>  
  
     <span data-ttu-id="b07cd-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents #&3;](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b07cd-137">[!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]</span></span>  
  
 <span data-ttu-id="b07cd-138">응용 프로그램 호출 하는 경우는 `LongTask` 메서드를는 `Widget` 발생 시키는 클래스는 `PercentDone` 이벤트 마다 `MinimumInterval` 초입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-138">When your application calls the `LongTask` method, the `Widget` class raises the `PercentDone` event every `MinimumInterval` seconds.</span></span> <span data-ttu-id="b07cd-139">이 이벤트는 반환 될 때 `LongTask` 확인 하는 `Cancel` 인수로 설정 된 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-139">When the event returns, `LongTask` checks to see if the `Cancel` argument was set to `True`.</span></span>  
  
 <span data-ttu-id="b07cd-140">몇 가지 사항을 고려해 야 여기 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-140">A few disclaimers are necessary here.</span></span> <span data-ttu-id="b07cd-141">간단히 하기 위해는 `LongTask` 프로시저를 미리 파악해 두면 작업 소요 될 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-141">For simplicity, the `LongTask` procedure assumes you know in advance how long the task will take.</span></span> <span data-ttu-id="b07cd-142">이러한 경우가 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-142">This is almost never the case.</span></span> <span data-ttu-id="b07cd-143">작업 짝수 크기의 청크로 나누는 것이 어려울 수 있으며 단순히 기간 전에 무언가 작업이 진행을 나타내는 값을 전달 하는 경우가 가장 중요 한 사용자에 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-143">Dividing tasks into chunks of even size can be difficult, and often what matters most to users is simply the amount of time that passes before they get an indication that something is happening.</span></span>  
  
 <span data-ttu-id="b07cd-144">이 샘플에서 다른 문제가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-144">You may have spotted another flaw in this sample.</span></span> <span data-ttu-id="b07cd-145">`Timer` 자정 바로 전에 시작 된 경우 응용 프로그램 중지 따라서; 속성 자정부터 경과한 시간 (초) 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-145">The `Timer` property returns the number of seconds that have passed since midnight; therefore, the application gets stuck if it is started just before midnight.</span></span> <span data-ttu-id="b07cd-146">시간을 측정 하는 더 신중한 접근 방법을 것을 고려해 야 할 이와 같은 경계 조건 걸리거나 피하도록와 같은 속성을 사용 하 여 `Now`합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-146">A more careful approach to measuring time would take boundary conditions such as this into consideration, or avoid them altogether, using properties such as `Now`.</span></span>  
  
 <span data-ttu-id="b07cd-147">이제는 `Widget` 클래스에서 이벤트를 발생 수를 이동할 수 있습니다 다음 연습 합니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-147">Now that the `Widget` class can raise events, you can move to the next walkthrough.</span></span> <span data-ttu-id="b07cd-148">[연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) 사용 하는 방법을 보여 줍니다. `WithEvents` 이벤트 처리기를 연결 하는 `PercentDone` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="b07cd-148">[Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) demonstrates how to use `WithEvents` to associate an event handler with the `PercentDone` event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b07cd-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b07cd-149">See Also</span></span>  
 <span data-ttu-id="b07cd-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span><span class="sxs-lookup"><span data-stu-id="b07cd-150"><xref:Microsoft.VisualBasic.DateAndTime.Timer%2A></span></span>   
 <span data-ttu-id="b07cd-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="b07cd-151"><xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span></span>   
<span data-ttu-id="b07cd-152"> [연습: 이벤트 처리](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span><span class="sxs-lookup"><span data-stu-id="b07cd-152"> [Walkthrough: Handling Events](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) </span></span>  
<span data-ttu-id="b07cd-153"> [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="b07cd-153"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md)</span></span>
