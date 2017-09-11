---
title: "클래스 정의 (Visual Basic) | Microsoft 문서"
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
- execution, ending
- objects [Visual Basic], initializing
- Initialize event
- files, closing
- programs, quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event
- execution, stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
caps.latest.revision: 21
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
ms.openlocfilehash: 5b470b8ba9b60dfb1cd1bbb207e02217f5311c27
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="71c57-102">연습: 클래스 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71c57-102">Walkthrough: Defining Classes (Visual Basic)</span></span>
<span data-ttu-id="71c57-103">이 연습에서는 다음 개체를 만드는 데 사용할 수 있는 클래스를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="71c57-104">또한 새 클래스에 속성 및 메서드를 추가 하는 방법을 보여 주고 개체를 초기화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-a-class"></a><span data-ttu-id="71c57-105">클래스를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="71c57-105">To define a class</span></span>  
  
1.  <span data-ttu-id="71c57-106">클릭 하 여 프로젝트를 만드는 **새 프로젝트** 에 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="71c57-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="71c57-107">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-107">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="71c57-108">Windows 응용 프로그램의 목록에서 선택 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로젝트 새 프로젝트를 표시 하는 템플릿이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-108">Select Windows Application from the list of [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project templates to display the new project.</span></span>  
  
3.  <span data-ttu-id="71c57-109">새 클래스를 클릭 하 여 프로젝트에 추가 **클래스 추가** 에 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="71c57-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="71c57-110">**새 항목 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-110">The **Add New Item** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="71c57-111">선택 된 **클래스** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="71c57-111">Select the **Class** template.</span></span>  
  
5.  <span data-ttu-id="71c57-112">새 클래스 이름을 `UserNameInfo.vb`를 클릭 하 고 **추가** 새 클래스에 대 한 코드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     <span data-ttu-id="71c57-113">[!code-vb[VbVbalrOOP #&5;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="71c57-113">[!code-vb[VbVbalrOOP#5](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_1.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71c57-114">사용할 수는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **코드 편집기** 시작 폼에 입력 하 여 클래스를 추가 하는 `Class` 키워드 새 클래스의 이름이 차례로 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-114">You can use the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="71c57-115">**코드 편집기** 해당 제공 `End Class` 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-115">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6.  <span data-ttu-id="71c57-116">사이 다음 코드를 추가 하 여 클래스에 대 한 전용 필드 정의 `Class` 및 `End Class` 문:</span><span class="sxs-lookup"><span data-stu-id="71c57-116">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     <span data-ttu-id="71c57-117">[!code-vb[VbVbalrOOP #&7;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="71c57-117">[!code-vb[VbVbalrOOP#7](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_2.vb)]</span></span>  
  
     <span data-ttu-id="71c57-118">로 필드를 선언 `Private` 클래스 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-118">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="71c57-119">가능 필드는 클래스 외부에서 사용할 수와 같은 액세스 한정자를 사용 하 여 `Public` 동일한 액세스를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-119">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="71c57-120">자세한 내용은 참조 [Visual Basic의 액세스 수준을](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-120">For more information, see [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7.  <span data-ttu-id="71c57-121">다음 코드를 추가 하 여 클래스에 대 한 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-121">Define a property for the class by adding the following code:</span></span>  
  
     <span data-ttu-id="71c57-122">[!code-vb[VbVbalrOOP #&8;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="71c57-122">[!code-vb[VbVbalrOOP#8](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_3.vb)]</span></span>  
  
8.  <span data-ttu-id="71c57-123">다음 코드를 추가 하 여 클래스에 대 한 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-123">Define a method for the class by adding the following code:</span></span>  
  
     <span data-ttu-id="71c57-124">[!code-vb[VbVbalrOOP #&9;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="71c57-124">[!code-vb[VbVbalrOOP#9](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_4.vb)]</span></span>  
  
9. <span data-ttu-id="71c57-125">프로시저를 추가 하 여 새 클래스에 대 한 매개 변수가 있는 생성자를 정의 `Sub New`:</span><span class="sxs-lookup"><span data-stu-id="71c57-125">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     <span data-ttu-id="71c57-126">[!code-vb[VbVbalrOOP #&10;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="71c57-126">[!code-vb[VbVbalrOOP#10](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_5.vb)]</span></span>  
  
     <span data-ttu-id="71c57-127">`Sub New` 생성자는이 클래스를 기반으로 하는 개체를 만들 때 자동으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-127">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="71c57-128">이 생성자는 사용자 이름을 사용 하는 필드의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-128">This constructor sets the value of the field that holds the user name.</span></span>  
  
### <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="71c57-129">클래스를 테스트 하려면 단추를 만들려면</span><span class="sxs-lookup"><span data-stu-id="71c57-129">To create a button to test the class</span></span>  
  
1.  <span data-ttu-id="71c57-130">시작 폼에서 해당 이름을 마우스 오른쪽 단추로 클릭 하 여 디자인 모드로 변경 **솔루션 탐색기** 클릭 한 다음 **뷰 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-130">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="71c57-131">기본적으로 Windows 응용 프로그램 프로젝트에 대 한 시작 폼 Form1.vb 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-131">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="71c57-132">기본 폼이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-132">The main form will then appear.</span></span>  
  
2.  <span data-ttu-id="71c57-133">기본 폼에 단추를 추가 하 고 두 번 클릭 하 여 코드를 표시 하는 `Button1_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-133">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="71c57-134">테스트 프로시저를 호출 하려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-134">Add the following code to call the test procedure:</span></span>  
  
     <span data-ttu-id="71c57-135">[!code-vb[VbVbalrOOP #&12;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="71c57-135">[!code-vb[VbVbalrOOP#12](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-defining-classes_6.vb)]</span></span>  
  
### <a name="to-run-your-application"></a><span data-ttu-id="71c57-136">응용 프로그램을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="71c57-136">To run your application</span></span>  
  
1.  <span data-ttu-id="71c57-137">F5 키를 눌러 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-137">Run your application by pressing F5.</span></span> <span data-ttu-id="71c57-138">테스트 프로시저를 호출 하려면 폼의 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-138">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="71c57-139">원래 했다는 메시지가 표시 `UserName` 프로시저가 호출 되므로 "MOORE, BOBBY"는 `Capitalize` 개체의 메서드.</span><span class="sxs-lookup"><span data-stu-id="71c57-139">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2.  <span data-ttu-id="71c57-140">클릭 **확인** 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-140">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="71c57-141">`Button1 Click` 의 값을 변경 하는 절차는 `UserName` 속성의 새 값이 했다는 메시지가 표시 됩니다 `UserName` "Worden, Joe"는 합니다.</span><span class="sxs-lookup"><span data-stu-id="71c57-141">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71c57-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71c57-142">See Also</span></span>  
 <span data-ttu-id="71c57-143">[개체 지향 프로그래밍](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2) </span><span class="sxs-lookup"><span data-stu-id="71c57-143">[Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2) </span></span>  
<span data-ttu-id="71c57-144"> [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span><span class="sxs-lookup"><span data-stu-id="71c57-144"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)</span></span>

