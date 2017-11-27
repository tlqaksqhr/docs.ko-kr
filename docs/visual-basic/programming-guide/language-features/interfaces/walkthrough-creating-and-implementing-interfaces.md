---
title: "인터페이스 (Visual Basic) 만들기 및 구현"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Basic], walkthroughs
- interfaces [Visual Basic], testing
- interface implementation [Visual Basic], walkthrough
- interfaces [Visual Basic], creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 08bf6dc7344d4f83c8ab1908fdeb29eb4a53e142
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="c0352-102">연습: 인터페이스 만들기 및 구현(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0352-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="c0352-103">인터페이스 속성, 메서드 및 이벤트의 특성을 설명 하지만 구조체나 클래스 구현 세부 사항을 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="c0352-104">이 연습에는 선언 및 인터페이스를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0352-105">이 연습에서는 사용자 인터페이스를 만드는 방법에 대 한 정보를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="c0352-106">인터페이스를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="c0352-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="c0352-107">새 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows 응용 프로그램 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-107">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="c0352-108">새 모듈을 클릭 하 여 프로젝트에 추가할 **모듈 추가** 에 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="c0352-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="c0352-109">새 모듈의 이름을 `Module1.vb` 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="c0352-110">새 모듈에 대 한 코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="c0352-111">라는 인터페이스를 정의 `TestInterface` 내 `Module1` 입력 하 여 `Interface TestInterface` 사이 `Module` 및 `End Module` 문, 한 다음 ENTER 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="c0352-112">**코드 편집기** 들여쓰기는 `Interface` 키워드 추가 `End Interface` 코드 블록을 형성 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="c0352-113">사이 다음 코드를 배치 하 여 속성, 메서드 및 인터페이스에 대 한 이벤트 정의 `Interface` 및 `End Interface` 문:</span><span class="sxs-lookup"><span data-stu-id="c0352-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a><span data-ttu-id="c0352-114">구현</span><span class="sxs-lookup"><span data-stu-id="c0352-114">Implementation</span></span>  
 <span data-ttu-id="c0352-115">인터페이스 멤버를 선언 하는 데 사용 하는 구문을 클래스 멤버를 선언 하는 데 사용 되는 구문에서 다른 임을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-115">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="c0352-116">이러한 차이 인터페이스 구현 코드가 포함 될 수 없음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-116">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="c0352-117">인터페이스를 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="c0352-117">To implement the interface</span></span>  
  
1.  <span data-ttu-id="c0352-118">라는 클래스를 추가 `ImplementationClass` 다음 문을 추가 하 여 `Module1`이후에 `End Interface` 문의 하기 전에 `End Module` 문, 한 다음 ENTER 키:</span><span class="sxs-lookup"><span data-stu-id="c0352-118">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     [!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     <span data-ttu-id="c0352-119">통합된 개발 환경에서 작업 하는 경우는 **코드 편집기** 에서 짝 `End Class` ENTER 키를 누르면 문.</span><span class="sxs-lookup"><span data-stu-id="c0352-119">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="c0352-120">다음 추가 `Implements` 문을 `ImplementationClass`를 구현 하는 인터페이스 클래스의 이름을:</span><span class="sxs-lookup"><span data-stu-id="c0352-120">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     [!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     <span data-ttu-id="c0352-121">클래스 또는 구조의 맨 위에 있는 다른 항목과 별도로 나열 하는 경우는 `Implements` 문은 구조체 또는 클래스 인터페이스를 구현 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-121">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="c0352-122">통합된 개발 환경에서 작업 하는 경우는 **코드 편집기** 클래스 멤버에 필요한 구현 `TestInterface` 때 ENTER 키를 누릅니다 하 고 다음 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-122">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="c0352-123">인터페이스의 모든 멤버를 구현 해야 통합된 개발 환경 내에서 작동 하지 않는 경우 `MyInterface`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-123">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="c0352-124">다음 코드를 추가 `ImplementationClass` 구현 하려면 `Event1`, `Method1`, 및 `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="c0352-124">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     [!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     <span data-ttu-id="c0352-125">`Implements` 문은 인터페이스와 구현 되는 인터페이스 멤버를 명명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-125">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="c0352-126">정의 완료 `Prop1` 속성 값을 저장 하는 클래스에 전용 필드를 추가 하 여:</span><span class="sxs-lookup"><span data-stu-id="c0352-126">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     [!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     <span data-ttu-id="c0352-127">값을 반환 된 `pval` 속성에서 get 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-127">Return the value of the `pval` from the property get accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     <span data-ttu-id="c0352-128">값을 설정할 `pval` 속성에 set 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-128">Set the value of `pval` in the property set accessor.</span></span>  
  
     [!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  <span data-ttu-id="c0352-129">정의 완료 `Method1` 다음 코드를 추가 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-129">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     [!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="c0352-130">인터페이스의 구현을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="c0352-130">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="c0352-131">프로젝트에 대 한 시작 폼을 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기**를 클릭 하 고 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-131">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="c0352-132">편집기 시작 폼에 대 한 클래스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-132">The editor displays the class for your startup form.</span></span> <span data-ttu-id="c0352-133">기본적으로 시작 폼 이름은 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-133">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="c0352-134">다음 추가 `testInstance` 필드는 `Form1` 클래스:</span><span class="sxs-lookup"><span data-stu-id="c0352-134">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     [!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     <span data-ttu-id="c0352-135">선언 하 여 `testInstance` 으로 `WithEvents`, `Form1` 클래스에는 해당 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-135">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="c0352-136">다음 이벤트 처리기를 추가 `Form1` 에 의해 발생 하는 이벤트를 처리 하는 클래스 `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="c0352-136">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     [!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  <span data-ttu-id="c0352-137">라는 서브루틴 추가 `Test` 에 `Form1` 클래스 구현 클래스를 테스트 하려면:</span><span class="sxs-lookup"><span data-stu-id="c0352-137">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     [!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     <span data-ttu-id="c0352-138">`Test` 프로시저 구현 하는 클래스의 인스턴스를 만들고 `MyInterface`, 할당 하도록 해당 인스턴스는 `testInstance` 필드 속성을 설정 및 인터페이스를 통해 메서드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-138">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="c0352-139">호출 하는 코드를 추가 `Test` 에서 프로시저는 `Form1 Load` 시작 폼의 프로시저:</span><span class="sxs-lookup"><span data-stu-id="c0352-139">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     [!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  <span data-ttu-id="c0352-140">실행 된 `Test` f5 키를 눌러 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-140">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="c0352-141">메시지 "Prop1으로 설정 된 9" 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-141">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="c0352-142">"Method1에 대 한 X 매개 변수는 5입니다"가 표시 되는 메시지 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-142">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="c0352-143">확인을 클릭 하 고 "이벤트 처리기는 이벤트를 발생 하는 데 사용" 메시지 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0352-143">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0352-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0352-144">See Also</span></span>  
 [<span data-ttu-id="c0352-145">Implements 문</span><span class="sxs-lookup"><span data-stu-id="c0352-145">Implements Statement</span></span>](../../../../visual-basic/language-reference/statements/implements-statement.md)  
 [<span data-ttu-id="c0352-146">인터페이스</span><span class="sxs-lookup"><span data-stu-id="c0352-146">Interfaces</span></span>](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [<span data-ttu-id="c0352-147">Interface 문</span><span class="sxs-lookup"><span data-stu-id="c0352-147">Interface Statement</span></span>](../../../../visual-basic/language-reference/statements/interface-statement.md)  
 [<span data-ttu-id="c0352-148">Event 문</span><span class="sxs-lookup"><span data-stu-id="c0352-148">Event Statement</span></span>](../../../../visual-basic/language-reference/statements/event-statement.md)
