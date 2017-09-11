---
title: "인터페이스 (Visual Basic) 만들기 및 구현 | Microsoft 문서"
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
- interfaces, walkthroughs
- interfaces, testing
- interface implementation, walkthrough
- interfaces, creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
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
ms.openlocfilehash: ef1ec16005bf0a7967d396054ae23c1023143c2a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a><span data-ttu-id="a35b7-102">연습: 인터페이스 만들기 및 구현(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a35b7-102">Walkthrough: Creating and Implementing Interfaces (Visual Basic)</span></span>
<span data-ttu-id="a35b7-103">인터페이스는 속성, 메서드 및 이벤트의 특징을 설명 하지만 구조체나 클래스는 구현 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-103">Interfaces describe the characteristics of properties, methods, and events, but leave the implementation details up to structures or classes.</span></span>  
  
 <span data-ttu-id="a35b7-104">이 연습에는 선언 및 인터페이스를 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-104">This walkthrough demonstrates how to declare and implement an interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a35b7-105">이 연습에서는 사용자 인터페이스를 만드는 방법에 대 한 정보를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-105">This walkthrough doesn't provide information about how to create a user interface.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-an-interface"></a><span data-ttu-id="a35b7-106">인터페이스를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="a35b7-106">To define an interface</span></span>  
  
1.  <span data-ttu-id="a35b7-107">새 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows 응용 프로그램 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-107">Open a new [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="a35b7-108">새 모듈을 클릭 하 여 프로젝트에 추가 **모듈 추가** 에 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="a35b7-108">Add a new module to the project by clicking **Add Module** on the **Project** menu.</span></span>  
  
3.  <span data-ttu-id="a35b7-109">새 모듈의 이름을 `Module1.vb` 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-109">Name the new module `Module1.vb` and click **Add**.</span></span> <span data-ttu-id="a35b7-110">새 모듈에 대 한 코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-110">The code for the new module is displayed.</span></span>  
  
4.  <span data-ttu-id="a35b7-111">라는 인터페이스를 정의 `TestInterface` 내 `Module1` 입력 하 여 `Interface TestInterface` 간에 `Module` 및 `End Module` 문의 한 다음 ENTER 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-111">Define an interface named `TestInterface` within `Module1` by typing `Interface TestInterface` between the `Module` and `End Module` statements, and then pressing ENTER.</span></span> <span data-ttu-id="a35b7-112">**코드 편집기** 들여쓰기는 `Interface` 키워드를 추가 하 고는 `End Interface` 코드 블록을 형성 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-112">The **Code Editor** indents the `Interface` keyword and adds an `End Interface` statement to form a code block.</span></span>  
  
5.  <span data-ttu-id="a35b7-113">속성, 메서드 및 인터페이스에 대 한 이벤트 사이 다음 코드를 배치 하 여 정의 된 `Interface` 및 `End Interface` 문:</span><span class="sxs-lookup"><span data-stu-id="a35b7-113">Define a property, method, and event for the interface by placing the following code between the `Interface` and `End Interface` statements:</span></span>  
  
     <span data-ttu-id="a35b7-114">[!code-vb[VbVbalrOOP #&98;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-114">[!code-vb[VbVbalrOOP#98](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]</span></span>  
  
## <a name="implementation"></a><span data-ttu-id="a35b7-115">구현</span><span class="sxs-lookup"><span data-stu-id="a35b7-115">Implementation</span></span>  
 <span data-ttu-id="a35b7-116">인터페이스 멤버를 선언 하는 데 구문은 다른 클래스 멤버를 선언 하는 데 사용 되는 구문에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-116">You may notice that the syntax used to declare interface members is different from the syntax used to declare class members.</span></span> <span data-ttu-id="a35b7-117">이러한 차이 반영 인터페이스 구현 코드를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-117">This difference reflects the fact that interfaces cannot contain implementation code.</span></span>  
  
#### <a name="to-implement-the-interface"></a><span data-ttu-id="a35b7-118">인터페이스를 구현 하려면</span><span class="sxs-lookup"><span data-stu-id="a35b7-118">To implement the interface</span></span>  
  
1.  <span data-ttu-id="a35b7-119">라는 클래스를 추가 `ImplementationClass` 다음 문을 추가 하 여 `Module1`뒤의 `End Interface` 문의 하기 전에 `End Module` 문의 한 다음 ENTER 키:</span><span class="sxs-lookup"><span data-stu-id="a35b7-119">Add a class named `ImplementationClass` by adding the following statement to `Module1`, after the `End Interface` statement but before the `End Module` statement, and then pressing ENTER:</span></span>  
  
     <span data-ttu-id="a35b7-120">[!code-vb[VbVbalrOOP #&99;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-120">[!code-vb[VbVbalrOOP#99](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]</span></span>  
  
     <span data-ttu-id="a35b7-121">통합된 개발 환경 내에서 작업 하는 경우는 **코드 편집기** 에서 짝 `End Class` ENTER 키를 누르면 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-121">If you are working within the integrated development environment, the **Code Editor** supplies a matching `End Class` statement when you press ENTER.</span></span>  
  
2.  <span data-ttu-id="a35b7-122">다음 코드를 추가 `Implements` 문을 `ImplementationClass`를 구현 하는 인터페이스는 클래스의 이름을:</span><span class="sxs-lookup"><span data-stu-id="a35b7-122">Add the following `Implements` statement to `ImplementationClass`, which names the interface the class implements:</span></span>  
  
     <span data-ttu-id="a35b7-123">[!code-vb[VbVbalrOOP #&100;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-123">[!code-vb[VbVbalrOOP#100](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]</span></span>  
  
     <span data-ttu-id="a35b7-124">클래스 또는 구조를 맨 위에 있는 다른 항목과 별도로 나열 하는 경우는 `Implements` 클래스 또는 구조체는 인터페이스를 구현 하는 문은 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-124">When listed separately from other items at the top of a class or structure, the `Implements` statement indicates that the class or structure implements an interface.</span></span>  
  
     <span data-ttu-id="a35b7-125">통합된 개발 환경 내에서 작업 하는 경우는 **코드 편집기** 구현에 필요한 클래스 멤버 `TestInterface` 때 ENTER 키를 누릅니다 하 고 다음 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-125">If you are working within the integrated development environment, the **Code Editor** implements the class members required by `TestInterface` when you press ENTER, and you can skip the next step.</span></span>  
  
3.  <span data-ttu-id="a35b7-126">인터페이스의 모든 멤버를 구현 해야 통합된 개발 환경 내에서 작동 하지 않는 경우 `MyInterface`합니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-126">If you are not working within the integrated development environment, you must implement all the members of the interface `MyInterface`.</span></span> <span data-ttu-id="a35b7-127">다음 코드를 추가 `ImplementationClass` 구현 하려면 `Event1`, `Method1`, 및 `Prop1`:</span><span class="sxs-lookup"><span data-stu-id="a35b7-127">Add the following code to `ImplementationClass` to implement `Event1`, `Method1`, and `Prop1`:</span></span>  
  
     <span data-ttu-id="a35b7-128">[!code-vb[VbVbalrOOP #&101;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-128">[!code-vb[VbVbalrOOP#101](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]</span></span>  
  
     <span data-ttu-id="a35b7-129">`Implements` 문을 인터페이스 및 인터페이스 멤버 구현 되는 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-129">The `Implements` statement names the interface and interface member being implemented.</span></span>  
  
4.  <span data-ttu-id="a35b7-130">정의 완료 `Prop1` 속성 값을 저장 하는 클래스에는 개인 필드를 추가 하 여:</span><span class="sxs-lookup"><span data-stu-id="a35b7-130">Complete the definition of `Prop1` by adding a private field to the class that stored the property value:</span></span>  
  
     <span data-ttu-id="a35b7-131">[!code-vb[VbVbalrOOP #&102;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-131">[!code-vb[VbVbalrOOP#102](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]</span></span>  
  
     <span data-ttu-id="a35b7-132">값을 반환 된 `pval` 속성에서 get 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-132">Return the value of the `pval` from the property get accessor.</span></span>  
  
     <span data-ttu-id="a35b7-133">[!code-vb[VbVbalrOOP #&103;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-133">[!code-vb[VbVbalrOOP#103](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]</span></span>  
  
     <span data-ttu-id="a35b7-134">값을 설정할 `pval` 속성 집합 접근자입니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-134">Set the value of `pval` in the property set accessor.</span></span>  
  
     <span data-ttu-id="a35b7-135">[!code-vb[VbVbalrOOP #&104;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-135">[!code-vb[VbVbalrOOP#104](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]</span></span>  
  
5.  <span data-ttu-id="a35b7-136">정의 완료 `Method1` 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-136">Complete the definition of `Method1` by adding the following code.</span></span>  
  
     <span data-ttu-id="a35b7-137">[!code-vb[VbVbalrOOP #&105;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-137">[!code-vb[VbVbalrOOP#105](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]</span></span>  
  
#### <a name="to-test-the-implementation-of-the-interface"></a><span data-ttu-id="a35b7-138">인터페이스의 구현을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="a35b7-138">To test the implementation of the interface</span></span>  
  
1.  <span data-ttu-id="a35b7-139">프로젝트의 시작 폼을 마우스 오른쪽 단추로 클릭는 **솔루션 탐색기**를 클릭 하 고 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-139">Right-click the startup form for your project in the **Solution Explorer**, and click **View Code**.</span></span> <span data-ttu-id="a35b7-140">편집기 시작 폼에 대 한 클래스를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-140">The editor displays the class for your startup form.</span></span> <span data-ttu-id="a35b7-141">기본적으로 시작 폼 이라고 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-141">By default, the startup form is called `Form1`.</span></span>  
  
2.  <span data-ttu-id="a35b7-142">다음 코드를 추가 `testInstance` 필드는 `Form1` 클래스:</span><span class="sxs-lookup"><span data-stu-id="a35b7-142">Add the following `testInstance` field to the `Form1` class:</span></span>  
  
     <span data-ttu-id="a35b7-143">[!code-vb[VbVbalrOOP #&120;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-143">[!code-vb[VbVbalrOOP#120](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]</span></span>  
  
     <span data-ttu-id="a35b7-144">선언 하 여 `testInstance` 으로 `WithEvents`, `Form1` 클래스는 해당 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-144">By declaring `testInstance` as `WithEvents`, the `Form1` class can handle its events.</span></span>  
  
3.  <span data-ttu-id="a35b7-145">다음 이벤트 처리기를 추가 `Form1` 에 의해 발생 하는 이벤트를 처리 하는 클래스 `testInstance`:</span><span class="sxs-lookup"><span data-stu-id="a35b7-145">Add the following event handler to the `Form1` class to handle events raised by `testInstance`:</span></span>  
  
     <span data-ttu-id="a35b7-146">[!code-vb[VbVbalrOOP #&106;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-146">[!code-vb[VbVbalrOOP#106](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]</span></span>  
  
4.  <span data-ttu-id="a35b7-147">라는 서브루틴 추가 `Test` 에 `Form1` 클래스 구현 클래스를 테스트 하려면:</span><span class="sxs-lookup"><span data-stu-id="a35b7-147">Add a subroutine named `Test` to the `Form1` class to test the implementation class:</span></span>  
  
     <span data-ttu-id="a35b7-148">[!code-vb[VbVbalrOOP #&107;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-148">[!code-vb[VbVbalrOOP#107](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]</span></span>  
  
     <span data-ttu-id="a35b7-149">`Test` 프로시저 구현 하는 클래스의 인스턴스를 만들고 `MyInterface`, 해당 인스턴스를 할당는 `testInstance` 필드, 속성을 설정 하 고 인터페이스를 통해 메서드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-149">The `Test` procedure creates an instance of the class that implements `MyInterface`, assigns that instance to the `testInstance` field, sets a property, and runs a method through the interface.</span></span>  
  
5.  <span data-ttu-id="a35b7-150">호출 하는 코드를 추가 `Test` 에서 프로시저는 `Form1 Load` 시작 폼의 프로시저:</span><span class="sxs-lookup"><span data-stu-id="a35b7-150">Add code to call the `Test` procedure from the `Form1 Load` procedure of your startup form:</span></span>  
  
     <span data-ttu-id="a35b7-151">[!code-vb[VbVbalrOOP #&108;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="a35b7-151">[!code-vb[VbVbalrOOP#108](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]</span></span>  
  
6.  <span data-ttu-id="a35b7-152">실행 된 `Test` f5 키를 눌러 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-152">Run the `Test` procedure by pressing F5.</span></span> <span data-ttu-id="a35b7-153">메시지 "Prop1으로 설정 된 9" 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-153">The message "Prop1 was set to 9" is displayed.</span></span> <span data-ttu-id="a35b7-154">"Method1에 대 한 X 매개 변수는 5입니다"가 표시 되는 메시지 확인을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-154">After you click OK, the message "The X parameter for Method1 is 5" is displayed.</span></span> <span data-ttu-id="a35b7-155">확인을 클릭 하 고 "이벤트 처리기는 이벤트를 발생 하는 데 사용" 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a35b7-155">Click OK, and the message "The event handler caught the event" is displayed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a35b7-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a35b7-156">See Also</span></span>  
 <span data-ttu-id="a35b7-157">[Implements 문](../../../../visual-basic/language-reference/statements/implements-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a35b7-157">[Implements Statement](../../../../visual-basic/language-reference/statements/implements-statement.md) </span></span>  
<span data-ttu-id="a35b7-158"> [인터페이스](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="a35b7-158"> [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md) </span></span>  
<span data-ttu-id="a35b7-159"> [Interface 문](../../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a35b7-159"> [Interface Statement](../../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="a35b7-160"> [Event 문](../../../../visual-basic/language-reference/statements/event-statement.md)</span><span class="sxs-lookup"><span data-stu-id="a35b7-160"> [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md)</span></span>

