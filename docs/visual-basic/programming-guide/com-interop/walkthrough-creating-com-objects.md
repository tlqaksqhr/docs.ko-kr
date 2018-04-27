---
title: '연습: Visual Basic을 사용하여 COM 개체 만들기'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e660d672fc32455cee349dc44ad20c3244c087b4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="0f49a-102">연습: Visual Basic을 사용하여 COM 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="0f49a-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="0f49a-103">새 응용 프로그램 또는 구성 요소를 만들 때.NET Framework 어셈블리를 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="0f49a-104">그러나 Visual Basic을 사용 하면 com.NET Framework 구성 요소를 노출 하기가</span><span class="sxs-lookup"><span data-stu-id="0f49a-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="0f49a-105">이 COM 구성 요소를 필요로 하는 이전 응용 프로그램 제품군에 대 한 새 구성 요소를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="0f49a-106">이 연습에서는 Visual Basic을 사용 하 여 노출 하도록 하는 방법을 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 와 COM 클래스 템플릿을 사용 하지 않고 COM 개체로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-106">This walkthrough demonstrates how to use Visual Basic to expose [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="0f49a-107">COM 클래스 템플릿을 사용 하 여 COM 개체를 노출 하는 가장 쉬운 방법은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="0f49a-108">COM 클래스 템플릿을 새 클래스를 만들고 COM 개체로 클래스 및 상호 운용성 계층을 생성 하 고 운영 체제에 등록 하려면 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f49a-109">Visual Basic에서 사용 하 여 비관리 코드를 COM 개체로 만든 클래스를 노출할 수도 있지만 true COM 개체가 아니라 및 Visual Basic에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="0f49a-110">자세한 내용은 참조 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="0f49a-111">COM 클래스 템플릿을 사용 하 여 COM 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="0f49a-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="0f49a-112">새 Windows 응용 프로그램 프로젝트를 열고는 **파일** 메뉴를 클릭 하 여 **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="0f49a-113">에 **새 프로젝트** 대화 상자는 **프로젝트 형식** 필드에서 Windows가 선택 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="0f49a-114">선택 **클래스 라이브러리** 에서 **템플릿** 목록으로 이동한 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="0f49a-115">새 프로젝트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="0f49a-116">선택 **새 항목 추가** 에서 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="0f49a-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="0f49a-117">**새 항목 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="0f49a-118">선택 **COM 클래스** 에서 **템플릿** 목록으로 이동한 다음 클릭 **추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="0f49a-119">Visual Basic 새 클래스를 추가 하 고 COM interop에 대 한 새 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="0f49a-120">COM 클래스에 속성, 메서드 및 이벤트 등의 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="0f49a-121">선택 **빌드 ClassLibrary1** 에서 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="0f49a-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="0f49a-122">Visual Basic 어셈블리를 빌드하고 운영 체제와 COM 개체를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="0f49a-123">COM 클래스 템플릿 사용 하지 않고 COM 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="0f49a-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="0f49a-124">COM 클래스 템플릿을 사용 하지 않고 수동으로 COM 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="0f49a-125">이 절차는 명령줄에서 작업할 때 또는 COM 개체를 정의 하는 방법을 보다 더 많은 제어 하려는 경우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="0f49a-126">COM 개체를 생성 하 여 프로젝트를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0f49a-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="0f49a-127">새 Windows 응용 프로그램 프로젝트를 열고는 **파일** 메뉴를 클릭 하 여 **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="0f49a-128">에 **새 프로젝트** 대화 상자는 **프로젝트 형식** 필드에서 Windows가 선택 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="0f49a-129">선택 **클래스 라이브러리** 에서 **템플릿** 목록으로 이동한 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="0f49a-130">새 프로젝트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="0f49a-131">**솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="0f49a-132">**프로젝트 디자이너** 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="0f49a-133">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="0f49a-134">선택 된 **COM Interop 등록** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="0f49a-135">COM 개체를 만들려면 클래스에 코드를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="0f49a-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="0f49a-136">**솔루션 탐색기**를 두 번 클릭 **Class1.vb** 해당 코드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="0f49a-137">클래스 이름을 `ComClass1`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="0f49a-138">다음 상수를 추가 `ComClass1`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="0f49a-139">전역적으로 고유 식별자 (GUID) 상수 COM 개체가 있어야 하는 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  <span data-ttu-id="0f49a-140">**도구** 메뉴에서 **GUID 만들기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="0f49a-141">**GUID 만들기** 대화 상자에서 **레지스트리 형식**과 **복사**를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="0f49a-142">**끝내기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-142">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="0f49a-143">빈 문자열을 바꾸기는 `ClassId` GUID를 가진 제거 하는 선행 및 후행 중괄호 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="0f49a-144">예를 들어 Guidgen에 의해 제공 된 GUID는 `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` 코드는 다음과 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  <span data-ttu-id="0f49a-145">에 대해 위의 단계를 반복 하는 `InterfaceId` 및 `EventsId` 다음 예제와 같이 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="0f49a-146">Guid는 새롭고 고유한; 되는지 확인 그렇지 않으면 COM 구성 요소는 다른 COM 구성 요소와 충돌할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="0f49a-147">추가 `ComClass` 특성을 `ComClass1`, 다음 예제와 같이 클래스 ID, 인터페이스 ID 및 이벤트 ID에 대 한 Guid를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  <span data-ttu-id="0f49a-148">COM 클래스에는 매개 변수가 없는 있어야 `Public Sub New()` 생성자 또는 클래스 올바르게 등록 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="0f49a-149">클래스에 매개 변수가 없는 생성자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. <span data-ttu-id="0f49a-150">속성, 메서드 및 이벤트에 추가 클래스를 사용 하 여 종료는 `End Class` 문.</span><span class="sxs-lookup"><span data-stu-id="0f49a-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="0f49a-151">선택 **솔루션 빌드** 에서 **빌드** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="0f49a-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="0f49a-152">Visual Basic 어셈블리를 빌드하고 운영 체제와 COM 개체를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f49a-153">True 이면 COM 개체 되지 않기 때문에 다른 Visual Basic 응용 프로그램에서 Visual Basic을 사용한 생성 COM 개체를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="0f49a-154">이러한 COM 개체에 대 한 참조를 추가 하려는 시도 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="0f49a-155">자세한 내용은 참조 [.NET Framework 응용 프로그램의 COM 상호 운용성](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0f49a-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f49a-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f49a-156">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [<span data-ttu-id="0f49a-157">COM Interop</span><span class="sxs-lookup"><span data-stu-id="0f49a-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="0f49a-158">연습: COM 개체를 사용한 상속 구현</span><span class="sxs-lookup"><span data-stu-id="0f49a-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="0f49a-159">#Region 지시문</span><span class="sxs-lookup"><span data-stu-id="0f49a-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="0f49a-160">.NET Framework 응용 프로그램의 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="0f49a-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="0f49a-161">상호 운용성 문제 해결</span><span class="sxs-lookup"><span data-stu-id="0f49a-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
