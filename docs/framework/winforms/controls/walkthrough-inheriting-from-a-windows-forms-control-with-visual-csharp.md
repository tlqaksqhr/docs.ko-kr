---
title: '연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cdf472776fc293bc5dfa1db940d23c6a297767e7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-c"></a><span data-ttu-id="dfcb7-102">연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="dfcb7-102">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span> #
<span data-ttu-id="dfcb7-103">[!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)]에서는 *상속*을 통해 강력한 사용자 지정 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-103">With [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)], you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="dfcb7-104">상속을 통해 표준 Windows Forms 컨트롤의 모든 고유 기능을 유지하면서 사용자 지정 기능을 통합하는 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="dfcb7-105">이 연습에서는 `ValueButton`이라는 간단한 상속된 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="dfcb7-106">이 단추는 표준 Windows Forms에서 기능을 상속 <xref:System.Windows.Forms.Button> 컨트롤을 호출 하는 사용자 지정 속성을 노출 합니다 `ButtonValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfcb7-107">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="dfcb7-108">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="dfcb7-109">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="dfcb7-110">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="dfcb7-110">Creating the Project</span></span>  
 <span data-ttu-id="dfcb7-111">새 프로젝트를 만들 때는 루트 네임스페이스, 어셈블리 이름 및 프로젝트 이름을 설정하기 위해 이름을 지정하고 기본 구성 요소가 올바른 네임스페이스에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-111">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="dfcb7-112">ValueButtonLib 컨트롤 라이브러리 및 ValueButton 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="dfcb7-112">To create the ValueButtonLib control library and the ValueButton control</span></span>  
  
1.  <span data-ttu-id="dfcb7-113">**파일** 메뉴에서 **새로 만들기**를 가리키고 **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-113">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="dfcb7-114">선택 된 **Windows Forms 컨트롤 라이브러리** Visual C# 프로젝트, 및 형식 목록에서 프로젝트 템플릿을 `ValueButtonLib` 에 **이름** 상자.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-114">Select the **Windows Forms Control Library** project template from the list of Visual C# Projects, and type `ValueButtonLib` in the **Name** box.</span></span>  
  
     <span data-ttu-id="dfcb7-115">프로젝트 이름, `ValueButtonLib`는 기본적으로 루트 네임스페이스에도 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-115">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="dfcb7-116">루트 네임스페이스는 어셈블리에서 구성 요소의 이름을 정규화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-116">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="dfcb7-117">예를 들어 두 어셈블리에서 `ValueButton`이라는 구성 요소를 제공하면 `ValueButtonLib.ValueButton`을 사용하여 `ValueButton` 구성 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-117">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="dfcb7-118">자세한 내용은 [네임스페이스](../../../csharp/programming-guide/namespaces/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-118">For more information, see [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span></span>  
  
3.  <span data-ttu-id="dfcb7-119">**솔루션 탐색기**에서 **UserControl1.cs**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **이름 바꾸기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-119">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="dfcb7-120">파일 이름을 `ValueButton.cs`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-120">Change the file name to `ValueButton.cs`.</span></span> <span data-ttu-id="dfcb7-121">코드 요소 '`UserControl1`'에 대한 모든 참조 이름을 변경할지 묻는 메시지가 표시되면 **예** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-121">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>  
  
4.  <span data-ttu-id="dfcb7-122">**솔루션 탐색기**에서 **ValueButton.cs**를 마우스 오른쪽 단추로 클릭하고 **코드 보기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-122">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>  
  
5.  <span data-ttu-id="dfcb7-123">찾을 `class` 문의 줄 `public partial class ValueButton`,이 컨트롤에서 상속 된 형식을 변경 하 고 <xref:System.Windows.Forms.UserControl> 를 <xref:System.Windows.Forms.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-123">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="dfcb7-124">이렇게 하면 상속 된 컨트롤의 모든 기능을 상속는 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-124">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>  
  
6.  <span data-ttu-id="dfcb7-125">**솔루션 탐색기**에서 **ValueButton.cs** 노드를 열어 디자이너에서 생성한 코드 파일인 **ValueButton.Designer.cs**를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-125">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="dfcb7-126">**코드 편집기**에서 이 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-126">Open this file in the **Code Editor**.</span></span>  
  
7.  <span data-ttu-id="dfcb7-127">찾습니다는 `InitializeComponent` 메서드 및 remove 할당 하는 줄은 <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-127">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="dfcb7-128">이 속성에 존재 하지 않습니다는 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-128">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>  
  
8.  <span data-ttu-id="dfcb7-129">**파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-129">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfcb7-130">비주얼 디자이너는 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-130">A visual designer is no longer available.</span></span> <span data-ttu-id="dfcb7-131">때문에 <xref:System.Windows.Forms.Button> 디자이너에서 모양을 수정할 수 없는, 컨트롤은 자체 그리기를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-131">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="dfcb7-132">시각적 표시는 정확히 같을 수에서 상속 된 클래스의 (즉, <xref:System.Windows.Forms.Button>)는 코드에서 수정 하지 않는 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-132">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="dfcb7-133">UI 요소가 없는 구성 요소를 디자인 화면에 계속 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-133">You can still add components, which have no UI elements, to the design surface.</span></span>  
  
## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="dfcb7-134">상속된 컨트롤에 속성 추가</span><span class="sxs-lookup"><span data-stu-id="dfcb7-134">Adding a Property to Your Inherited Control</span></span>  
 <span data-ttu-id="dfcb7-135">상속된 Windows Forms 컨트롤의 한 가지 가능한 용도는 표준 Windows Forms 컨트롤과 모양 및 느낌이 동일하지만 사용자 지정 속성을 노출하는 컨트롤을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-135">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="dfcb7-136">이 섹션에서는 `ButtonValue`라는 속성을 컨트롤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-136">In this section, you will add a property called `ButtonValue` to your control.</span></span>  
  
#### <a name="to-add-the-value-property"></a><span data-ttu-id="dfcb7-137">Value 속성을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="dfcb7-137">To add the Value property</span></span>  
  
1.  <span data-ttu-id="dfcb7-138">**솔루션 탐색기**에서 **ValueButton.cs**를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-138">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="dfcb7-139">`class` 문을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-139">Locate the `class` statement.</span></span> <span data-ttu-id="dfcb7-140">`{` 바로 뒤에 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-140">Immediately after the `{`, type the following code:</span></span>  
  
    ```csharp  
    // Creates the private variable that will store the value of your   
    // property.  
    private int varValue;  
    // Declares the property.  
    public int ButtonValue  
    {  
       // Sets the method for retrieving the value of your property.  
       get  
       {  
          return varValue;  
       }  
       // Sets the method for setting the value of your property.  
       set  
       {  
          varValue = value;  
       }  
    }  
    ```  
  
     <span data-ttu-id="dfcb7-141">이 코드는 `ButtonValue` 속성을 저장 및 검색할 메서드를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-141">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="dfcb7-142">`get` 문은 반환된 값을 private 변수 `varValue`에 저장된 값으로 설정하고 `set` 문은 `value` 키워드를 사용하여 private 변수의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-142">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>  
  
3.  <span data-ttu-id="dfcb7-143">**파일** 메뉴에서 **모두 저장**을 선택하여 프로젝트를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-143">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
## <a name="testing-your-control"></a><span data-ttu-id="dfcb7-144">컨트롤 테스트</span><span class="sxs-lookup"><span data-stu-id="dfcb7-144">Testing Your Control</span></span>  
 <span data-ttu-id="dfcb7-145">컨트롤은 독립 실행형 프로젝트가 아니며 컨테이너에서 호스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-145">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="dfcb7-146">컨트롤을 테스트하려면 컨트롤을 실행할 테스트 프로젝트를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-146">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="dfcb7-147">또한 컨트롤을 빌드(컴파일)하여 컨트롤에서 테스트 프로젝트에 액세스할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-147">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="dfcb7-148">이 섹션에서는 컨트롤을 테스트하고 Windows Form에서 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-148">In this section, you will build your control and test it in a Windows Form.</span></span>  
  
#### <a name="to-build-your-control"></a><span data-ttu-id="dfcb7-149">컨트롤을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="dfcb7-149">To build your control</span></span>  
  
1.  <span data-ttu-id="dfcb7-150">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-150">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="dfcb7-151">컴파일러 오류 또는 경고 없이 빌드에 성공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-151">The build should be successful with no compiler errors or warnings.</span></span>  
  
#### <a name="to-create-a-test-project"></a><span data-ttu-id="dfcb7-152">테스트 프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="dfcb7-152">To create a test project</span></span>  
  
1.  <span data-ttu-id="dfcb7-153">**파일** 메뉴에서 **추가**를 가리킨 후 **새 프로젝트**를 클릭하여 **새 프로젝트 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-153">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="dfcb7-154">**Windows** 노드를 선택하고 **Visual C#** 노드 아래에서 **Windows Forms 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-154">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="dfcb7-155">**이름** 상자에 `Test`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-155">In the **Name** box, type `Test`.</span></span>  
  
4.  <span data-ttu-id="dfcb7-156">**솔루션 탐색기**에서 테스트 프로젝트에 대한 **참조** 노드를 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **참조 추가**를 선택하면 **참조 추가** 대화 상자가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-156">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>  
  
5.  <span data-ttu-id="dfcb7-157">**프로젝트**로 레이블이 지정된 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-157">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="dfcb7-158">`ValueButtonLib` 프로젝트가 **프로젝트 이름** 아래에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-158">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="dfcb7-159">프로젝트를 두 번 클릭하여 테스트 프로젝트에 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-159">Double-click the project to add the reference to the test project.</span></span>  
  
6.  <span data-ttu-id="dfcb7-160">**솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭한 후 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-160">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>  
  
#### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="dfcb7-161">폼에 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="dfcb7-161">To add your control to the form</span></span>  
  
1.  <span data-ttu-id="dfcb7-162">**솔루션 탐색기**에서 **Form1.cs**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **뷰 디자이너**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-162">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="dfcb7-163">**도구 상자**에서 **ValueButtonLib 구성 요소**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-163">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="dfcb7-164">**ValueButton**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-164">Double-click **ValueButton**.</span></span>  
  
     <span data-ttu-id="dfcb7-165">**ValueButton**이 폼에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-165">A **ValueButton** appears on the form.</span></span>  
  
3.  <span data-ttu-id="dfcb7-166">**ValueButton**을 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-166">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="dfcb7-167">**속성** 창에서 이 컨트롤의 속성을 점검합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-167">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="dfcb7-168">`ButtonValue`라는 추가 속성이 있는 것을 제외하고, 표준 단추에 노출된 속성과 동일한 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-168">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>  
  
5.  <span data-ttu-id="dfcb7-169">`ButtonValue` 속성을 `5`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-169">Set the `ButtonValue` property to `5`.</span></span>  
  
6.  <span data-ttu-id="dfcb7-170">에 **모든 Windows Forms** 탭은 **도구 상자**, 두 번 클릭 **레이블** 추가 하는 <xref:System.Windows.Forms.Label> 컨트롤을 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-170">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>  
  
7.  <span data-ttu-id="dfcb7-171">폼 가운데에 레이블을 다시 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-171">Relocate the label to the center of the form.</span></span>  
  
8.  <span data-ttu-id="dfcb7-172">`valueButton1`을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-172">Double-click `valueButton1`.</span></span>  
  
     <span data-ttu-id="dfcb7-173">**코드 편집기**에 `valueButton1_Click` 이벤트가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-173">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>  
  
9. <span data-ttu-id="dfcb7-174">다음 코드 행을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-174">Insert the following line of code.</span></span>  
  
    ```csharp  
    label1.Text = valueButton1.ButtonValue.ToString();  
    ```  
  
10. <span data-ttu-id="dfcb7-175">**솔루션 탐색기**에서 **Test**를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-175">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>  
  
11. <span data-ttu-id="dfcb7-176">**디버그** 메뉴에서 **디버깅 시작**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-176">From the **Debug** menu, select **Start Debugging**.</span></span>  
  
     <span data-ttu-id="dfcb7-177">`Form1`이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-177">`Form1` appears.</span></span>  
  
12. <span data-ttu-id="dfcb7-178">`valueButton1`을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-178">Click `valueButton1`.</span></span>  
  
     <span data-ttu-id="dfcb7-179">숫자 '5'가 `label1`에 표시되며 상속된 컨트롤의 `ButtonValue` 속성이 `valueButton1_Click` 메서드를 통해 `label1`에 전달되었음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-179">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="dfcb7-180">따라서 `ValueButton` 컨트롤은 표준 Windows Forms 단추의 모든 기능을 상속하지만 추가 사용자 지정 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcb7-180">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfcb7-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfcb7-181">See Also</span></span>  
 [<span data-ttu-id="dfcb7-182">구성 요소를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="dfcb7-182">Programming with Components</span></span>](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)  
 [<span data-ttu-id="dfcb7-183">구성 요소 제작 연습</span><span class="sxs-lookup"><span data-stu-id="dfcb7-183">Component Authoring Walkthroughs</span></span>](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 [<span data-ttu-id="dfcb7-184">방법: 도구 상자 항목 선택 대화 상자에 컨트롤 표시</span><span class="sxs-lookup"><span data-stu-id="dfcb7-184">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [<span data-ttu-id="dfcb7-185">연습: Visual C#에서 합성 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="dfcb7-185">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)
