---
title: 정의 하는 클래스가 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- execution [Visual Basic], ending
- objects [Visual Basic], initializing
- Initialize event [Visual Basic]
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- objects [Visual Basic], creating
- program termination
- classes [Visual Basic], walkthroughs
- class modules, walkthroughs
- Terminate event [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 07018828-2d49-4cf5-a44b-19fb15d9efea
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9fc173ad853755c4b02a13abc0a80229bebffe64
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-defining-classes-visual-basic"></a><span data-ttu-id="5ebea-102">연습: 클래스 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ebea-102">Walkthrough: Defining Classes (Visual Basic)</span></span>

<span data-ttu-id="5ebea-103">이 연습에서는 다음 개체를 만드는 데 사용할 수 있는 클래스를 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-103">This walkthrough demonstrates how to define classes, which you can then use to create objects.</span></span> <span data-ttu-id="5ebea-104">또한 새 클래스에 속성 및 메서드를 추가 하는 방법을 보여 주고 개체를 초기화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-104">It also shows you how to add properties and methods to the new class, and demonstrates how to initialize an object.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="to-define-a-class"></a><span data-ttu-id="5ebea-105">클래스를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="5ebea-105">To define a class</span></span>
  
1.  <span data-ttu-id="5ebea-106">클릭 하 여 프로젝트를 만들 **새 프로젝트** 에 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="5ebea-106">Create a project by clicking **New Project** on the **File** menu.</span></span> <span data-ttu-id="5ebea-107">**새 프로젝트** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-107">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="5ebea-108">새 프로젝트를 표시 하는 Visual Basic 프로젝트 템플릿 목록에서 Windows 응용 프로그램을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-108">Select Windows Application from the list of Visual Basic project templates to display the new project.</span></span>  
  
3.  <span data-ttu-id="5ebea-109">새 클래스를 클릭 하 여 프로젝트에 추가 **클래스 추가** 에 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="5ebea-109">Add a new class to the project by clicking **Add Class** on the **Project** menu.</span></span> <span data-ttu-id="5ebea-110">**새 항목 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-110">The **Add New Item** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="5ebea-111">선택 된 **클래스** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="5ebea-111">Select the **Class** template.</span></span>  
  
5.  <span data-ttu-id="5ebea-112">클래스의 새 이름을 `UserNameInfo.vb`, 클릭 하 고 **추가** 새 클래스에 대 한 코드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-112">Name the new class `UserNameInfo.vb`, and then click **Add** to display the code for the new class.</span></span>  
  
     [!code-vb[VbVbalrOOP#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#5)]
  
    > [!NOTE]
    >  <span data-ttu-id="5ebea-113">Visual Basic을 사용할 수 있습니다 **코드 편집기** 시작 폼에 입력 하 여 클래스를 추가 하는 `Class` 키워드 다음 새 클래스의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-113">You can use the Visual Basic **Code Editor** to add a class to your startup form by typing the `Class` keyword followed by the name of the new class.</span></span> <span data-ttu-id="5ebea-114">**코드 편집기** 해당 제공 `End Class` 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-114">The **Code Editor** provides a corresponding `End Class` statement for you.</span></span>  
  
6.  <span data-ttu-id="5ebea-115">사이 다음 코드를 추가 하 여 클래스에 대 한 전용 필드를 정의 고 `Class` 및 `End Class` 문:</span><span class="sxs-lookup"><span data-stu-id="5ebea-115">Define a private field for the class by adding the following code between the `Class` and `End Class` statements:</span></span>  
  
     [!code-vb[VbVbalrOOP#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#7)]
  
     <span data-ttu-id="5ebea-116">로 필드를 선언 `Private` 의미는 클래스 내 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-116">Declaring the field as `Private` means it can be used only within the class.</span></span> <span data-ttu-id="5ebea-117">있습니다 수 필드에서 사용할 수 있도록 클래스 외부와 같은 액세스 한정자를 사용 하 여 `Public` 많은 액세스 권한을 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-117">You can make fields available from outside a class by using access modifiers such as `Public` that provide more access.</span></span> <span data-ttu-id="5ebea-118">자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-118">For more information, see [Access levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
7.  <span data-ttu-id="5ebea-119">다음 코드를 추가 하 여 클래스에 대 한 속성을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-119">Define a property for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#8)]
  
8.  <span data-ttu-id="5ebea-120">다음 코드를 추가 하 여 클래스에 대 한 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-120">Define a method for the class by adding the following code:</span></span>  
  
     [!code-vb[VbVbalrOOP#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#9)]
  
9. <span data-ttu-id="5ebea-121">프로시저를 추가 하 여 새 클래스에 대 한 매개 변수가 있는 생성자를 정의 `Sub New`:</span><span class="sxs-lookup"><span data-stu-id="5ebea-121">Define a parameterized constructor for the new class by adding a procedure named `Sub New`:</span></span>  
  
     [!code-vb[VbVbalrOOP#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#10)]
  
     <span data-ttu-id="5ebea-122">`Sub New` 생성자는이 클래스에 기반 하는 개체를 만들 때 자동으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-122">The `Sub New` constructor is called automatically when an object based on this class is created.</span></span> <span data-ttu-id="5ebea-123">이 생성자는 사용자 이름을 사용 하는 필드의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-123">This constructor sets the value of the field that holds the user name.</span></span>  
  
## <a name="to-create-a-button-to-test-the-class"></a><span data-ttu-id="5ebea-124">클래스를 테스트 하려면 단추를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5ebea-124">To create a button to test the class</span></span>
  
1.  <span data-ttu-id="5ebea-125">시작 폼에서 해당 이름을 마우스 오른쪽 단추로 클릭 하 여 디자인 모드로 변경 **솔루션 탐색기** 클릭 한 다음 **뷰 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-125">Change the startup form to design mode by right-clicking its name in **Solution Explorer** and then clicking **View Designer**.</span></span> <span data-ttu-id="5ebea-126">기본적으로 Windows 응용 프로그램 프로젝트에 대 한 시작 폼 Form1.vb 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-126">By default, the startup form for Windows Application projects is named Form1.vb.</span></span> <span data-ttu-id="5ebea-127">기본 폼이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-127">The main form will then appear.</span></span>  
  
2.  <span data-ttu-id="5ebea-128">기본 폼에 단추를 추가 하 고 두 번 클릭에 대 한 코드를 표시는 `Button1_Click` 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-128">Add a button to the main form and double-click it to display the code for the `Button1_Click` event handler.</span></span> <span data-ttu-id="5ebea-129">테스트 프로시저를 호출 하려면 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-129">Add the following code to call the test procedure:</span></span>  
  
     [!code-vb[VbVbalrOOP#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#12)]
  
## <a name="to-run-your-application"></a><span data-ttu-id="5ebea-130">응용 프로그램을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="5ebea-130">To run your application</span></span>
  
1.  <span data-ttu-id="5ebea-131">F5 키를 눌러 응용 프로그램을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-131">Run your application by pressing F5.</span></span> <span data-ttu-id="5ebea-132">테스트 프로시저를 호출 하려면 폼에서 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-132">Click the button on the form to call the test procedure.</span></span> <span data-ttu-id="5ebea-133">원래 했다는 메시지가 표시 `UserName` "MOORE, BOBBY" 이므로 프로시저 호출의 `Capitalize` 개체의 메서드.</span><span class="sxs-lookup"><span data-stu-id="5ebea-133">It displays a message stating that the original `UserName` is "MOORE, BOBBY", because the procedure called the `Capitalize` method of the object.</span></span>  
  
2.  <span data-ttu-id="5ebea-134">클릭 **확인** 메시지 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-134">Click **OK** to dismiss the message box.</span></span> <span data-ttu-id="5ebea-135">`Button1 Click` 의 값을 변경 하는 프로시저는 `UserName` 속성 내용을 입력 하는 메시지의 새 값을 표시 하 고 `UserName` "Worden Joe"는 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ebea-135">The `Button1 Click` procedure changes the value of the `UserName` property and displays a message stating that the new value of `UserName` is "Worden, Joe".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ebea-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="5ebea-136">See also</span></span>

[<span data-ttu-id="5ebea-137">개체 지향 프로그래밍(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ebea-137">Object-Oriented Programming (Visual Basic)</span></span>](../../concepts/object-oriented-programming.md)  
[<span data-ttu-id="5ebea-138">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="5ebea-138">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)