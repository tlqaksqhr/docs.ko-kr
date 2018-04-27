---
title: '연습: COM 개체를 사용한 상속 구현(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10c6bdf46e351b23705107da3b693531718cfd37
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="a5c8f-102">연습: COM 개체를 사용한 상속 구현(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a5c8f-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="a5c8f-103">Visual Basic 클래스를 파생 시켜 `Public` 도 이전 버전의 Visual Basic에 생성 된 COM 개체의 클래스.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="a5c8f-104">속성 및 COM 개체에서 상속 된 클래스의 메서드를 재정의 하거나 속성와 마찬가지로 오버 로드 및 다른 기본 클래스의 메서드를 재정의 하거나 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="a5c8f-105">COM 개체에서 상속 다시 컴파일하지 않을 기존 클래스 라이브러리에 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="a5c8f-106">다음 절차에는 클래스를 포함 하는 COM 개체를 만들려면 Visual Basic 6.0을 사용 하 여 다음 기본 클래스로 사용 하 여 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="a5c8f-107">이 연습에 사용 되는 COM 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="a5c8f-107">To build the COM object that is used in this walkthrough</span></span>  
  
1.  <span data-ttu-id="a5c8f-108">Visual Basic 6.0에서 새로운 ActiveX DLL 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="a5c8f-109">라는 프로젝트가 `Project1` 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-109">A project named `Project1` is created.</span></span> <span data-ttu-id="a5c8f-110">여기에 라는 클래스가 `Class1`합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-110">It has a class named `Class1`.</span></span>  
  
2.  <span data-ttu-id="a5c8f-111">에 **프로젝트 탐색기**를 마우스 오른쪽 단추로 클릭 **Project1**, 클릭 하 고 **Project1 속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="a5c8f-112">**프로젝트 속성** 대화 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="a5c8f-113">에 **일반** 탭은 **프로젝트 속성** 대화 상자에서 프로젝트 이름을 입력 하 여 변경 `ComObject1` 에 **프로젝트 이름을** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4.  <span data-ttu-id="a5c8f-114">에 **프로젝트 탐색기**를 마우스 오른쪽 단추로 클릭 `Class1`, 클릭 하 고 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="a5c8f-115">**속성** 클래스 창에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-115">The **Properties** window for the class is displayed.</span></span>  
  
5.  <span data-ttu-id="a5c8f-116">변경 된 `Name` 속성을 `MathFunctions`합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6.  <span data-ttu-id="a5c8f-117">에 **프로젝트 탐색기**를 마우스 오른쪽 단추로 클릭 `MathFunctions`, 클릭 하 고 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="a5c8f-118">**코드 편집기** 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-118">The **Code Editor** is displayed.</span></span>  
  
7.  <span data-ttu-id="a5c8f-119">속성 값을 보유 하는 로컬 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  <span data-ttu-id="a5c8f-120">속성 추가 `Let` 속성과 `Get` 속성 프로시저:</span><span class="sxs-lookup"><span data-stu-id="a5c8f-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
    ```  
    Public Property Let Prop1(ByVal vData As Integer)  
       'Used when assigning a value to the property.  
       mvarProp1 = vData  
    End Property  
    Public Property Get Prop1() As Integer  
       'Used when retrieving a property's value.  
       Prop1 = mvarProp1  
    End Property  
    ```  
  
9. <span data-ttu-id="a5c8f-121">함수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="a5c8f-122">만들기 및 COM 개체를 클릭 하 여 등록 **확인 ComObject1.dll** 에 **파일** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a5c8f-123">클래스를 COM 개체로 Visual Basic을 사용 하 여 만든를 노출할 수도 있지만 실제 COM 개체 아니며이 연습에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="a5c8f-124">자세한 내용은 참조 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="a5c8f-125">Interop 어셈블리</span><span class="sxs-lookup"><span data-stu-id="a5c8f-125">Interop Assemblies</span></span>  
 <span data-ttu-id="a5c8f-126">다음 절차에서는 관리 되지 않는 코드 (예: COM 개체)와 관리 코드 간 브리지 역할을 하는 interop 어셈블리를 만들게 됩니다 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] uses.</span></span> <span data-ttu-id="a5c8f-127">Interop 어셈블리를 Visual Basic 만듭니다이 COM 개체와 같은 작업의 세부 사항을 처리 *interop 마샬링*, 프로세스 매개 변수 및 반환 값에 해당 하는 데이터를 이동 하는 동안 형식 및 COM 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="a5c8f-128">Visual Basic 응용 프로그램에 대 한 참조는 interop 어셈블리를 실제 COM 개체를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="a5c8f-129">Visual Basic 2005 및 이후 버전으로 COM 개체를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="a5c8f-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1.  <span data-ttu-id="a5c8f-130">새 Visual Basic Windows 응용 프로그램 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-130">Open a new Visual Basic Windows Application project.</span></span>  
  
2.  <span data-ttu-id="a5c8f-131">**프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="a5c8f-132">**참조 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="a5c8f-133">에 **COM** 탭을 두 번 클릭 `ComObject1` 에 **구성 요소 이름** 나열 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4.  <span data-ttu-id="a5c8f-134">**프로젝트** 메뉴에서 **새 항목 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="a5c8f-135">**새 항목 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5.  <span data-ttu-id="a5c8f-136">에 **템플릿** 창에서 클릭 **클래스**합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="a5c8f-137">기본 파일 이름은 `Class1.vb`에 표시는 **이름** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="a5c8f-138">이 필드를 MathClass.vb으로 클릭 변경 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="a5c8f-139">라는 클래스를 만들고이 `MathClass`, 해당 코드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6.  <span data-ttu-id="a5c8f-140">맨 위에 다음 코드를 추가 `MathClass` COM 클래스에서 상속 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  <span data-ttu-id="a5c8f-141">다음 코드를 추가 하 여 기본 클래스의 공용 메서드를 오버 로드 `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="a5c8f-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  <span data-ttu-id="a5c8f-142">다음 코드를 추가 하 여 상속 된 클래스를 확장 `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="a5c8f-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 <span data-ttu-id="a5c8f-143">새 클래스는 COM 개체에서 기본 클래스의 속성을 상속 하 고 메서드를 오버 로드와 클래스를 확장 하는 새 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="a5c8f-144">상속 된 클래스를 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="a5c8f-144">To test the inherited class</span></span>  
  
1.  <span data-ttu-id="a5c8f-145">시작 폼에 단추를 추가 하 고 해당 코드를 보려면 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-145">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2.  <span data-ttu-id="a5c8f-146">단추의 `Click` 이벤트 처리기 프로시저의 인스턴스를 만들려면 다음 코드를 추가 `MathClass` 오버 로드 된 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  <span data-ttu-id="a5c8f-147">F5 키를 눌러 프로젝트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-147">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="a5c8f-148">폼에 단추를 클릭할 때는 `AddNumbers` 메서드를 먼저 호출한 `Short` 데이터 번호를 입력 한 Visual Basic 기본 클래스에서 적절 한 방법을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="a5c8f-149">두 번째 호출으로 `AddNumbers` 에서 메서드를 오버 로드로 향하는 `MathClass`합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="a5c8f-150">세 번째 호출은 호출에서 `SubtractNumbers` 메서드를 클래스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="a5c8f-151">기본 클래스에서 속성을 설정 하 고 값이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-151">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a5c8f-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a5c8f-152">Next Steps</span></span>  
 <span data-ttu-id="a5c8f-153">알 수 있습니다 하는 오버 로드 된 `AddNumbers` 함수를 동일한 데이터 형식이 COM 개체의 기본 클래스에서 상속 하는 방법으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="a5c8f-154">인수 및 기본 클래스 메서드의 매개 변수는 Visual Basic 6.0에서 16 비트 정수로 정의 되지만 16 비트 정수 형식으로 노출 되어 때문에 이것이 `Short` 이후 버전의 Visual Basic에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="a5c8f-155">새 함수는 32 비트 정수를 사용 하며 기본 클래스 함수를 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="a5c8f-156">COM 개체를 사용할 때 크기 및 데이터 유형의 매개 변수를 확인 하는 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="a5c8f-157">예를 들어 Visual Basic 6.0 컬렉션 개체를 인수로 허용 하는 COM 개체를 사용 하는 경우에 이후 버전의 Visual Basic에서 컬렉션을 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="a5c8f-158">속성 및 COM 클래스에서 상속 된 메서드를 재정의할 수 있습니다는 로컬 속성 또는 속성을 대체 하는 메서드 또는 기본 COM 클래스에서 상속 된 메서드를 선언할 수를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="a5c8f-159">상속 된 COM 속성을 재정의 하기 위한 규칙은 다른 속성 및 메서드는 다음과 같은 예외가 재정의 대 한 규칙과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="a5c8f-160">속성이 나 COM 클래스에서 상속 된 메서드를 재정의 하는 경우 다른 상속 된 속성 및 메서드를 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="a5c8f-161">사용 하는 속성 `ByRef` 매개 변수를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5c8f-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5c8f-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5c8f-162">See Also</span></span>  
 [<span data-ttu-id="a5c8f-163">.NET Framework 응용 프로그램의 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="a5c8f-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="a5c8f-164">Inherits 문</span><span class="sxs-lookup"><span data-stu-id="a5c8f-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="a5c8f-165">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a5c8f-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
