---
title: "방법: 합성 컨트롤 제작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 72c68568f0178956d6154f0b3a070e69b6ff0502
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-author-composite-controls"></a><span data-ttu-id="69e19-102">방법: 합성 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="69e19-102">How to: Author Composite Controls</span></span>
<span data-ttu-id="69e19-103">여러 가지 방법으로 복합 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-103">Composite controls can be employed in many ways.</span></span> <span data-ttu-id="69e19-104">Windows 데스크톱 응용 프로그램 프로젝트의 일부로 작성하고 프로젝트의 양식에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-104">You can author them as part of a Windows desktop application project, and use them only on forms in the project.</span></span> <span data-ttu-id="69e19-105">또는 Windows 컨트롤 라이브러리 프로젝트에서 작성하고 프로젝트를 어셈블리로 컴파일하고 다른 프로젝트에서 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-105">Or you can author them in a Windows Control Library project, compile the project into an assembly, and use the controls in other projects.</span></span> <span data-ttu-id="69e19-106">상속하고 시각적 상속을 사용하여 특별한 목적을 위해 신속하게 사용자 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-106">You can even inherit from them, and use visual inheritance to customize them quickly for special purposes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69e19-107">Web Forms에서 사용할 복합 컨트롤을 작성하려는 경우 [사용자 지정 ASP.NET 서버 컨트롤 개발](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69e19-107">If you want to author a composite control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
>   
>  <span data-ttu-id="69e19-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="69e19-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="69e19-110">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69e19-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-author-a-composite-control"></a><span data-ttu-id="69e19-111">복합 컨트롤을 작성하려면</span><span class="sxs-lookup"><span data-stu-id="69e19-111">To author a composite control</span></span>  
  
1.  <span data-ttu-id="69e19-112">`DemoControlHost`이라는 새 **Windows 응용 프로그램** 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-112">Open a new **Windows Application** project called `DemoControlHost`.</span></span>  
  
2.  <span data-ttu-id="69e19-113">**프로젝트** 메뉴에서 **사용자 정의 컨트롤 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-113">On the **Project**menu, click **Add User Control**.</span></span>  
  
3.  <span data-ttu-id="69e19-114">**새 항목 추가** 대화 상자에서 클래스 파일(.cs 또는 .vb 파일)에 복합 컨트롤이 원하는 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-114">In the **Add New Item** dialog box, give the class file (.vb or .cs file) the name you want the composite control to have.</span></span>  
  
4.  <span data-ttu-id="69e19-115">**추가** 단추를 클릭하여 복합 컨트롤의 클래스 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-115">Click the **Add** button to create the class file for the composite control.</span></span>  
  
5.  <span data-ttu-id="69e19-116">**도구 상자**에서 복합 컨트롤 화면에 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-116">Add controls from the **Toolbox** to the composite control surface.</span></span>  
  
6.  <span data-ttu-id="69e19-117">이벤트 프로시저에 복합 컨트롤 또는 구성원 컨트롤에 의해 발생한 이벤트를 처리하는 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-117">Place code in event procedures, to handle events raised by the composite control or by its constituent controls.</span></span>  
  
7.  <span data-ttu-id="69e19-118">복합 컨트롤의 디자이너를 닫고 메시지가 나타나면 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-118">Close the designer for the composite control, and save the file when you are prompted.</span></span>  
  
8.  <span data-ttu-id="69e19-119">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-119">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="69e19-120">사용자 지정 컨트롤을 **도구 상자**에 표시하기 위해 프로젝트를 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-120">The project must be built in order for custom controls to appear in the **Toolbox**.</span></span>  
  
9. <span data-ttu-id="69e19-121">**도구 상자**의 **DemoControlHost** 탭을 사용하여 컨트롤의 인스턴스를 `Form1`에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-121">Use the **DemoControlHost** tab of the **Toolbox** to add instances of your control to `Form1`.</span></span>  
  
### <a name="to-author-a-control-class-library"></a><span data-ttu-id="69e19-122">컨트롤 클래스 라이브러리를 작성하려면</span><span class="sxs-lookup"><span data-stu-id="69e19-122">To author a control class library</span></span>  
  
1.  <span data-ttu-id="69e19-123">새 **Windows 컨트롤 라이브러리** 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-123">Open a new **Windows Control Library** project.</span></span>  
  
     <span data-ttu-id="69e19-124">기본적으로 프로젝트는 복합 컨트롤을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-124">By default, the project contains a composite control.</span></span>  
  
2.  <span data-ttu-id="69e19-125">위의 절차에서 설명한 대로 컨트롤 및 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-125">Add controls and code as described in the procedure above.</span></span>  
  
3.  <span data-ttu-id="69e19-126">변경할 클래스를 상속하려는 컨트롤을 선택하고 이 컨트롤의 **한정자** 속성을 **개인**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-126">Choose a control you do not want inheriting classes to change, and set the **Modifiers** property of this control to **Private**.</span></span>  
  
4.  <span data-ttu-id="69e19-127">DLL을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-127">Build the DLL.</span></span>  
  
### <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a><span data-ttu-id="69e19-128">컨트롤 클래스 라이브러리의 복합 컨트롤에서 상속하려면</span><span class="sxs-lookup"><span data-stu-id="69e19-128">To inherit from a composite control in a control class library</span></span>  
  
1.  <span data-ttu-id="69e19-129">**파일** 메뉴에서 **추가**를 가리키고 **새 프로젝트**를 선택하여 새 **Windows 응용 프로그램** 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-129">On the **File** menu, point to **Add** and select **New Project** to add a new **Windows Application** project to the solution.</span></span>  
  
2.  <span data-ttu-id="69e19-130">**솔루션 탐색기**에서 새 프로젝트의 **References** 폴더를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택하여 **참조 추가** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-130">In **Solution Explorer**, right-click the **References** folder for the new project and choose **Add Reference** to open the **Add Reference** dialog box.</span></span>  
  
3.  <span data-ttu-id="69e19-131">**프로젝트** 탭을 선택하고 컨트롤 라이브러리 프로젝트를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-131">Select the **Projects** tab and double-click your control library project.</span></span>  
  
4.  <span data-ttu-id="69e19-132">**빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-132">On the **Build** menu, click **Build Solution**.</span></span>  
  
5.  <span data-ttu-id="69e19-133">**솔루션 탐색기**에서 컨트롤 라이브러리 프로젝트를 마우스 오른쪽 단추로 클릭하고 바로 가기 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-133">In **Solution Explorer**, right-click your control library project and select **Add New Item** from the shortcut menu.</span></span>  
  
6.  <span data-ttu-id="69e19-134">**새 항목 추가** 대화 상자에서 **상속된 사용자 정의 컨트롤** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-134">Select the **Inherited User Control** template from the **Add New Item** dialog box.</span></span>  
  
7.  <span data-ttu-id="69e19-135">**상속 선택** 대화 상자에서 상속하려는 컨트롤을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-135">In the **Inheritance Picker** dialog box, double-click the control you want to inherit from.</span></span>  
  
     <span data-ttu-id="69e19-136">새 컨트롤을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-136">A new control is added to your project.</span></span>  
  
8.  <span data-ttu-id="69e19-137">새 컨트롤에 대한 시각적 디자이너를 열고 추가 구성 요소 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-137">Open the visual designer for the new control and add additional constituent controls.</span></span>  
  
     <span data-ttu-id="69e19-138">DLL의 복합 컨트롤에서 상속된 구성 요소 컨트롤을 볼 수 있으며 **한정자** 속성이 **공용**인 컨트롤의 속성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-138">You can see the constituent controls that were inherited from the composite control in your DLL, and you can alter the properties of controls whose **Modifiers** property is **Public**.</span></span> <span data-ttu-id="69e19-139">**한정자** 속성이 **개인**인 컨트롤의 속성을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69e19-139">You cannot change the properties of the control whose **Modifiers** property is **Private**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69e19-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69e19-140">See Also</span></span>  
 [<span data-ttu-id="69e19-141">연습: Visual Basic에서 합성 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="69e19-141">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="69e19-142">연습: Visual C#에서 합성 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="69e19-142">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [<span data-ttu-id="69e19-143">연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="69e19-143">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="69e19-144">연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="69e19-144">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 [<span data-ttu-id="69e19-145">컨트롤 형식 권장 사항</span><span class="sxs-lookup"><span data-stu-id="69e19-145">Control Type Recommendations</span></span>](../../../../docs/framework/winforms/controls/control-type-recommendations.md)  
 [<span data-ttu-id="69e19-146">방법: Windows Forms 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="69e19-146">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="69e19-147">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="69e19-147">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
