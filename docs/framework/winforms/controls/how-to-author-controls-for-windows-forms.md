---
title: "방법: Windows Forms 컨트롤 제작"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], creating
- UserControl class [Windows Forms], Windows Forms
- custom controls [Windows Forms], creating
ms.assetid: 7570e982-545b-4c3a-a7c7-55581d313400
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f42ee49a4690c23a563740993e721207d5dedea0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-author-controls-for-windows-forms"></a><span data-ttu-id="69838-102">방법: Windows Forms 컨트롤 제작</span><span class="sxs-lookup"><span data-stu-id="69838-102">How to: Author Controls for Windows Forms</span></span>
<span data-ttu-id="69838-103">컨트롤은 사용자와 프로그램 간의 그래픽 링크를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69838-103">A control represents a graphical link between the user and the program.</span></span> <span data-ttu-id="69838-104">컨트롤은 데이터를 제공하거나 처리하고, 사용자 입력을 허용하고, 사용자 및 응용 프로그램을 연결하는 다른 함수의 구성원을 합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-104">A control can provide or process data, accept user input, respond to events, or perform any number of other functions that connect the user and the application.</span></span> <span data-ttu-id="69838-105">컨트롤이 기본적으로 그래픽 인터페이스를 사용하는 구성 요소이기 때문에 사용자 상호 작용을 제공할 뿐만 아니라 구성 요소가 수행하는 모든 함수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69838-105">Because a control is essentially a component with a graphical interface, it can serve any function that a component does, as well as provide user interaction.</span></span> <span data-ttu-id="69838-106">컨트롤은 특정 목적을 수행하기 위해 만들어지며 컨트롤 작성은 다른 프로그래밍 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="69838-106">Controls are created to serve specific purposes, and authoring controls is just another programming task.</span></span> <span data-ttu-id="69838-107">이 점을 염두하면서 다음 단계는 컨트롤 작성 프로세스의 개요를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="69838-107">With that in mind, the following steps represent an overview of the control authoring process.</span></span> <span data-ttu-id="69838-108">링크는 각 단계에 대한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-108">Links provide additional information on the individual steps.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69838-109">Web Forms에서 사용할 사용자 지정 컨트롤을 작성하려는 경우 [사용자 지정 ASP.NET 서버 컨트롤 개발](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69838-109">If you want to author a custom control to use on Web Forms, see [Developing Custom ASP.NET Server Controls](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).</span></span>  
>   
>  <span data-ttu-id="69838-110">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69838-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="69838-111">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="69838-112">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69838-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-author-a-control"></a><span data-ttu-id="69838-113">컨트롤을 작성하려면</span><span class="sxs-lookup"><span data-stu-id="69838-113">To author a control</span></span>  
  
1.  <span data-ttu-id="69838-114">컨트롤이 수행하려는 항목 또는 응용 프로그램에서 컨트롤이 맡은 역할을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-114">Determine what you want your control to accomplish, or what part it will play in your application.</span></span> <span data-ttu-id="69838-115">고려해야 하는 요인은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69838-115">Factors to consider are:</span></span>  
  
    -   <span data-ttu-id="69838-116">어떤 종류의 그래픽 인터페이스가 필요한가요?</span><span class="sxs-lookup"><span data-stu-id="69838-116">What kind of graphical interface do you need?</span></span>  
  
    -   <span data-ttu-id="69838-117">이 컨트롤이 다룰 특정 사용자 인터페이스는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="69838-117">What specific user interactions will this control handle?</span></span>  
  
    -   <span data-ttu-id="69838-118">기존 컨트롤에서 필요한 기능을 제공하나요?</span><span class="sxs-lookup"><span data-stu-id="69838-118">Is the functionality you need provided by any existing controls?</span></span>  
  
    -   <span data-ttu-id="69838-119">여러 Windows Forms 컨트롤을 결합하여 필요한 기능을 얻을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="69838-119">Can you get the functionality you need by combining several Windows Forms controls?</span></span>  
  
2.  <span data-ttu-id="69838-120">컨트롤에 대한 개체 모델이 필요한 경우 개체 모델 전체에 기능을 분산할 방법을 결정하고 컨트롤과 하위 개체 간의 기능을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-120">If you need an object model for your control, determine how functionality will be distributed throughout the object model, and divide up functionality between the control and any subobjects.</span></span> <span data-ttu-id="69838-121">개체 모델은 복잡한 컨트롤 계획하거나 여러 기능을 통합하려는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69838-121">An object model may be useful if you are planning a complex control, or want to incorporate several functionalities.</span></span>  
  
3.  <span data-ttu-id="69838-122">필요한 컨트롤의 형식을 확인합니다(예: 사용자 정의 컨트롤, 사용자 지정 컨트롤, 상속된 Windows Forms 컨트롤).</span><span class="sxs-lookup"><span data-stu-id="69838-122">Determine the type of control (for example, user control, custom control, inherited Windows Forms control) you need.</span></span> <span data-ttu-id="69838-123">자세한 내용은 [컨트롤 형식 권장 사항](../../../../docs/framework/winforms/controls/control-type-recommendations.md) 및 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69838-123">For details, see [Control Type Recommendations](../../../../docs/framework/winforms/controls/control-type-recommendations.md) and [Varieties of Custom Controls](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md).</span></span>  
  
4.  <span data-ttu-id="69838-124">기능을 컨트롤의 속성, 메서드 및 이벤트 및 해당 하위 개체 또는 보조 구조로 나타내고 적절한 액세스 수준(예: 공용, 보호 등)을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-124">Express functionality as properties, methods, and events of the control and its subobjects or subsidiary structures, and assign appropriate access levels (for example, public, protected, and so on).</span></span>  
  
5.  <span data-ttu-id="69838-125">컨트롤에 사용자 지정 그리기가 필요한 경우 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-125">If you need custom painting for your control, add code for it.</span></span> <span data-ttu-id="69838-126">자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-126">For details, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
6.  <span data-ttu-id="69838-127">컨트롤에서 상속 하는 경우 <xref:System.Windows.Forms.UserControl>, 컨트롤 프로젝트를 빌드하고에서 실행 하 여 해당 런타임 동작을 테스트할 수는 **UserControl Test Container**합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-127">If your control inherits from <xref:System.Windows.Forms.UserControl>, you can test its runtime behavior by building the control project and running it in the **UserControl Test Container**.</span></span> <span data-ttu-id="69838-128">자세한 내용은 [방법: UserControl의 런타임 동작 테스트](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69838-128">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
7.  <span data-ttu-id="69838-129">또한 Windows 응용 프로그램과 같이 새 프로젝트를 만들고 컨테이너에 배치하여 컨트롤을 테스트하고 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69838-129">You can also test and debug your control by creating a new project, such as a Windows Application, and placing it into a container.</span></span> <span data-ttu-id="69838-130">이 프로세스는 [연습: Visual Basic에서 복합 컨트롤 작성](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)의 일부로 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="69838-130">This process is demonstrated as part of [Walkthrough: Authoring a Composite Control with Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md).</span></span>  
  
8.  <span data-ttu-id="69838-131">각 기능을 추가하면 기능을 테스트 프로젝트에 추가하여 새 기능을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-131">As you add each feature, add features to your test project to exercise the new functionality.</span></span>  
  
9. <span data-ttu-id="69838-132">반복하여 디자인을 구체화합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-132">Repeat, refining the design.</span></span>  
  
10. <span data-ttu-id="69838-133">컨트롤을 패키지하고 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="69838-133">Package and deploy your control.</span></span> <span data-ttu-id="69838-134">자세한 내용은 [응용 프로그램, 서비스 및 구성 요소 배포](https://msdn.microsoft.com/library/wtzawcsz)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69838-134">For details, see [Deploying Applications, Services, and Components](https://msdn.microsoft.com/library/wtzawcsz).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69838-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69838-135">See Also</span></span>  
 [<span data-ttu-id="69838-136">연습: Visual Basic에서 합성 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="69838-136">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="69838-137">연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="69838-137">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="69838-138">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="69838-138">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="69838-139">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="69838-139">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="69838-140">방법: 기존 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="69838-140">How to: Inherit from Existing Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 [<span data-ttu-id="69838-141">방법: UserControl의 런타임 동작 테스트</span><span class="sxs-lookup"><span data-stu-id="69838-141">How to: Test the Run-Time Behavior of a UserControl</span></span>](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 [<span data-ttu-id="69838-142">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="69838-142">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
