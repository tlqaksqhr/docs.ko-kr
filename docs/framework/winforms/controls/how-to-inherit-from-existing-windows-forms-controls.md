---
title: "방법: 기존 Windows Forms 컨트롤에서 상속"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fb50e5b301095cce72e59dc2899d44a47215b536
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="b0a5c-102">방법: 기존 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="b0a5c-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="b0a5c-103">기존 컨트롤의 기능을 확장하려는 경우 상속을 통해 기존 컨트롤에서 파생된 컨트롤을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="b0a5c-104">기존 컨트롤에서 상속하는 경우 해당 컨트롤의 모든 기능 및 시각적 속성을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="b0a5c-105">상속 하는 컨트롤을 만들려는 경우 등 <xref:System.Windows.Forms.Button>, 새 컨트롤 모양 및 act 똑같이 표준 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="b0a5c-106">그런 다음 사용자 지정 메서드 및 속성의 구현을 통해 새 컨트롤의 기능을 확장하거나 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="b0a5c-107">일부 컨트롤에서 변경할 수 있습니다 또한 상속 된 컨트롤의 시각적 모양을 재정의 하 여 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0a5c-108">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b0a5c-109">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b0a5c-110">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-an-inherited-control"></a><span data-ttu-id="b0a5c-111">상속된 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="b0a5c-111">To create an inherited control</span></span>  
  
1.  <span data-ttu-id="b0a5c-112">새 **Windows Forms 응용 프로그램** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-112">Create a new **Windows Forms Application** project.</span></span>  
  
2.  <span data-ttu-id="b0a5c-113">**프로젝트** 메뉴에서 **새 항목 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-113">From the **Project** menu, choose **Add New Item**.</span></span>  
  
     <span data-ttu-id="b0a5c-114">**새 항목 추가** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-114">The **Add New Item** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="b0a5c-115">**새 항목 추가** 대화 상자에서 **사용자 지정 컨트롤**을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-115">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>  
  
     <span data-ttu-id="b0a5c-116">새 사용자 지정 컨트롤을 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="b0a5c-117">Visual Basic을 사용하면 **솔루션 탐색기**의 맨 위에서 **모든 파일 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-117">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="b0a5c-118">CustomControl1.vb를 확장한 다음 코드 편집기에서 CustomControl1.Designer.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-118">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>  
  
5.  <span data-ttu-id="b0a5c-119">C#을 사용하는 경우 코드 편집기에서 CustomControl1.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-119">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>  
  
6.  <span data-ttu-id="b0a5c-120">상속 하는 클래스 선언을 찾아 <xref:System.Windows.Forms.Control>합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-120">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>  
  
7.  <span data-ttu-id="b0a5c-121">기본 클래스를 상속하려는 컨트롤로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-121">Change the base class to the control that you want to inherit from.</span></span>  
  
     <span data-ttu-id="b0a5c-122">상속 하려는 경우 등 <xref:System.Windows.Forms.Button>, 다음과 같은 클래스 선언을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-122">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  <span data-ttu-id="b0a5c-123">Visual Basic을 사용하는 경우 저장하고 CustomControl1.Designer.vb를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-123">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="b0a5c-124">코드 편집기에서 CustomControl1.vb를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-124">Open CustomControl1.vb in the Code Editor.</span></span>  
  
9. <span data-ttu-id="b0a5c-125">컨트롤이 통합하는 사용자 지정 메서드 또는 속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-125">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
10. <span data-ttu-id="b0a5c-126">컨트롤의 그래픽 모양을 수정 하려는 경우 재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-126">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0a5c-127">재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 모든 컨트롤 모양을 수정할 수를 허용 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-127">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="b0a5c-128">모든 그리기가 Windows가 수행 되는 컨트롤 (예를 들어 <xref:System.Windows.Forms.TextBox>) 절대 호출 하지 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드, 따라서 사용 하지 것입니다는 사용자 지정 코드 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-128">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="b0a5c-129">있는지 수정할 특정 컨트롤에 대 한 도움말을 참고는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-129">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="b0a5c-130">모든 Windows Form 컨트롤의 목록은 [Windows Forms에서 사용할 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-130">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="b0a5c-131">컨트롤에 없는 경우 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드가 나열을 변경할 수 없습니다 모양을이 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-131">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="b0a5c-132">사용자 지정 그리기에 대한 자세한 내용은 [사용자 지정 컨트롤 그리기 및 렌더링](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-132">For more information about custom painting, see [Custom Control Painting and Rendering](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md).</span></span>  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. <span data-ttu-id="b0a5c-133">컨트롤을 저장하고 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="b0a5c-133">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0a5c-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0a5c-134">See Also</span></span>  
 [<span data-ttu-id="b0a5c-135">사용자 지정 컨트롤의 종류</span><span class="sxs-lookup"><span data-stu-id="b0a5c-135">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="b0a5c-136">방법: Control 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="b0a5c-136">How to: Inherit from the Control Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 [<span data-ttu-id="b0a5c-137">방법: UserControl 클래스에서 상속</span><span class="sxs-lookup"><span data-stu-id="b0a5c-137">How to: Inherit from the UserControl Class</span></span>](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 [<span data-ttu-id="b0a5c-138">방법: Windows Forms 컨트롤 작성</span><span class="sxs-lookup"><span data-stu-id="b0a5c-138">How to: Author Controls for Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 [<span data-ttu-id="b0a5c-139">Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b0a5c-139">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 [<span data-ttu-id="b0a5c-140">연습: Visual Basic을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="b0a5c-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 [<span data-ttu-id="b0a5c-141">연습: Visual C#을 사용하여 Windows Forms 컨트롤에서 상속</span><span class="sxs-lookup"><span data-stu-id="b0a5c-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
