---
title: "연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기"
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
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- MDI [Windows Forms], creating forms
- multiple document interface forms
- MDI forms
- ToolStrip control [Windows Forms]
- MDI forms [Windows Forms], creating
- MDI forms [Windows Forms], walkthroughs
ms.assetid: fbab4221-74af-42d0-bbf4-3c97f7b2e544
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3e0538151c19eb47f8a51330b7f2c06818d1e73f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a><span data-ttu-id="1b37b-102">연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용하여 MDI 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="1b37b-102">Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls</span></span>
<span data-ttu-id="1b37b-103"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 MDI(다중 문서 인터페이스) 응용 프로그램을 지원하고 <xref:System.Windows.Forms.MenuStrip> 컨트롤은 메뉴 병합을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-103">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace supports multiple document interface (MDI) applications, and the <xref:System.Windows.Forms.MenuStrip> control supports menu merging.</span></span> <span data-ttu-id="1b37b-104">MDI 폼은 <xref:System.Windows.Forms.ToolStrip> 컨트롤일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-104">MDI forms can also <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="1b37b-105">이 연습에서는 사용 하는 방법을 보여 줍니다. <xref:System.Windows.Forms.ToolStripPanel> MDI 폼을 사용 하 여 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-105">This walkthrough demonstrates how to use <xref:System.Windows.Forms.ToolStripPanel> controls with an MDI form.</span></span> <span data-ttu-id="1b37b-106">폼은 자식 메뉴와 메뉴 병합도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-106">The form also supports menu merging with child menus.</span></span> <span data-ttu-id="1b37b-107">같은 작업을이 연습에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-107">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="1b37b-108">Windows Forms 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-108">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="1b37b-109">폼에 대 한 주 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="1b37b-109">Creating the main menu for your form.</span></span> <span data-ttu-id="1b37b-110">메뉴의 실제 이름 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-110">The actual name of the menu will vary.</span></span>  
  
-   <span data-ttu-id="1b37b-111">추가 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-111">Adding the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox**.</span></span>  
  
-   <span data-ttu-id="1b37b-112">자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="1b37b-112">Creating a child form.</span></span>  
  
-   <span data-ttu-id="1b37b-113">정렬 <xref:System.Windows.Forms.ToolStripPanel> z 순서를 기준으로 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-113">Arranging <xref:System.Windows.Forms.ToolStripPanel> controls by z-order.</span></span>  
  
 <span data-ttu-id="1b37b-114">작업을 완료 하는 경우 메뉴 병합 및 이동할 수 있는 지 원하는 MDI 폼 것 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-114">When you are finished, you will have an MDI form that supports menu merging and movable <xref:System.Windows.Forms.ToolStrip> controls.</span></span>  
  
 <span data-ttu-id="1b37b-115">단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 메뉴 병합 및 ToolStrip 컨트롤 MDI 폼 만들기](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-115">To copy the code in this topic as a single listing, see [How to: Create an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b37b-116">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="1b37b-117">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="1b37b-118">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b37b-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1b37b-119">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="1b37b-119">Prerequisites</span></span>  
 <span data-ttu-id="1b37b-120">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-120">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="1b37b-121">만들고 컴퓨터에 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있는 충분 한 권한이 있는 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 가 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-121">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="1b37b-122">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="1b37b-122">Creating the Project</span></span>  
 <span data-ttu-id="1b37b-123">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-123">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="1b37b-124">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1b37b-124">To create the project</span></span>  
  
1.  <span data-ttu-id="1b37b-125">호출 하는 Windows 응용 프로그램 프로젝트 만들기 **MdiForm**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-125">Create a Windows Application project called **MdiForm**.</span></span>  
  
     <span data-ttu-id="1b37b-126">자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b37b-126">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="1b37b-127">Windows Forms 디자이너에서 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-127">In the Windows Forms Designer, select the form.</span></span>  
  
3.  <span data-ttu-id="1b37b-128">속성 창에서 설정의 값은 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 를 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-128">In the Properties window, set the value of the <xref:System.Windows.Forms.Form.IsMdiContainer%2A> to `true`.</span></span>  
  
## <a name="creating-the-main-menu"></a><span data-ttu-id="1b37b-129">주 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="1b37b-129">Creating the Main Menu</span></span>  
 <span data-ttu-id="1b37b-130">MDI 부모 폼의 주 메뉴를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-130">The parent MDI form contains the main menu.</span></span> <span data-ttu-id="1b37b-131">주 메뉴에는 하나의 이라는 메뉴 항목이 **창**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-131">The main menu has one menu item named **Window**.</span></span> <span data-ttu-id="1b37b-132">와 **창** 메뉴 항목을 자식 폼을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-132">With the **Window** menu item, you can create child forms.</span></span> <span data-ttu-id="1b37b-133">주 메뉴에 자식 폼의 메뉴 항목 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-133">Menu items from child forms are merged into the main menu.</span></span>  
  
#### <a name="to-create-the-main-menu"></a><span data-ttu-id="1b37b-134">주 메뉴를 만들려면</span><span class="sxs-lookup"><span data-stu-id="1b37b-134">To create the Main menu</span></span>  
  
1.  <span data-ttu-id="1b37b-135">**도구 상자**를 끌어 한 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-135">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the form.</span></span>  
  
2.  <span data-ttu-id="1b37b-136">추가 <xref:System.Windows.Forms.ToolStripMenuItem> 에 <xref:System.Windows.Forms.MenuStrip> 제어 하 고 이름을 **창**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-136">Add a <xref:System.Windows.Forms.ToolStripMenuItem> to the <xref:System.Windows.Forms.MenuStrip> control and name it **Window**.</span></span>  
  
3.  <span data-ttu-id="1b37b-137"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-137">Select the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
4.  <span data-ttu-id="1b37b-138">속성 창에서 설정의 값은 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 `ToolStripMenuItem1`합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-138">In the Properties window, set the value of the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to `ToolStripMenuItem1`.</span></span>  
  
5.  <span data-ttu-id="1b37b-139">하위 항목을 추가 **창** 메뉴 항목을 선택한 후 이름을 하위 항목 **새로**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-139">Add a subitem to the **Window** menu item, and then name the subitem **New**.</span></span>  
  
6.  <span data-ttu-id="1b37b-140">속성 창에서 클릭 **이벤트**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-140">In the Properties window, click **Events**.</span></span>  
  
7.  <span data-ttu-id="1b37b-141">두 번 클릭 하 여 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-141">Double-click the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
     <span data-ttu-id="1b37b-142">Windows Forms 디자이너에 대 한 이벤트 처리기가 생성 된 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-142">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event.</span></span>  
  
8.  <span data-ttu-id="1b37b-143">이벤트 처리기에 다음 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-143">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#2)]  
  
## <a name="adding-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="1b37b-144">ToolStripPanel 컨트롤을 도구 상자에 추가</span><span class="sxs-lookup"><span data-stu-id="1b37b-144">Adding the ToolStripPanel Control to the Toolbox</span></span>  
 <span data-ttu-id="1b37b-145">사용 하는 경우 <xref:System.Windows.Forms.MenuStrip> 있어야 MDI 폼을 사용 하 여 컨트롤의 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-145">When you use <xref:System.Windows.Forms.MenuStrip> controls with an MDI form you must have the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="1b37b-146">추가 해야 합니다는 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 **도구 상자** Windows Forms 디자이너에서 MDI 폼을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-146">You must add the <xref:System.Windows.Forms.ToolStripPanel> control to the **Toolbox** to build your MDI form in the Windows Forms Designer.</span></span>  
  
#### <a name="to-add-the-toolstrippanel-control-to-the-toolbox"></a><span data-ttu-id="1b37b-147">ToolStripPanel 컨트롤을 도구 상자에 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="1b37b-147">To add the ToolStripPanel control to the Toolbox</span></span>  
  
1.  <span data-ttu-id="1b37b-148">열기는 **도구 상자**, 클릭 하 고는 **모든 Windows Forms** 탭을 사용할 수 있는 Windows Forms 컨트롤을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-148">Open the **Toolbox**, and then click the **All Windows Forms** tab to show the available Windows Forms controls.</span></span>  
  
2.  <span data-ttu-id="1b37b-149">바로 가기 메뉴를 열려면 마우스 오른쪽 단추로 클릭 하 고 선택 **항목 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-149">Right-click to open the shortcut menu, and select **Choose Items**.</span></span>  
  
3.  <span data-ttu-id="1b37b-150">에 **도구 상자 항목 선택** 대화 상자에서 아래쪽으로 스크롤하여는 **이름** 열을 찾을 때까지 **ToolStripPanel**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-150">In the **Choose Toolbox Items** dialog box, scroll down the **Name** column until you find **ToolStripPanel**.</span></span>  
  
4.  <span data-ttu-id="1b37b-151">확인란을 선택 **ToolStripPanel**, 클릭 하 고 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-151">Select the check box by **ToolStripPanel**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="1b37b-152"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤이에 표시 되는 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-152">The <xref:System.Windows.Forms.ToolStripPanel> control appears in the **Toolbox**.</span></span>  
  
## <a name="creating-a-child-form"></a><span data-ttu-id="1b37b-153">자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="1b37b-153">Creating a Child Form</span></span>  
 <span data-ttu-id="1b37b-154">이 절차에서는 별도 자식 폼 클래스에는 자체를 정의 합니다 <xref:System.Windows.Forms.MenuStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-154">In this procedure, you will define a separate child form class that has its own <xref:System.Windows.Forms.MenuStrip> control.</span></span> <span data-ttu-id="1b37b-155">이 폼에 대 한 메뉴 항목 부모 폼의 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-155">The menu items for this form are merged with those of the parent form.</span></span>  
  
#### <a name="to-define-a-child-form"></a><span data-ttu-id="1b37b-156">자식 폼을 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="1b37b-156">To define a child form</span></span>  
  
1.  <span data-ttu-id="1b37b-157">라는 새 폼을 추가 `ChildForm` 프로젝트에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-157">Add a new form named `ChildForm` to the project.</span></span>  
  
     <span data-ttu-id="1b37b-158">자세한 내용은 참조 [하는 방법: Windows Forms 프로젝트에 추가](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-158">For more information, see [How to: Add Windows Forms to a Project](http://msdn.microsoft.com/library/3d7bb25f-fd90-47cf-9378-fa0d764686c1).</span></span>  
  
2.  <span data-ttu-id="1b37b-159">**도구 상자**를 끌어 한 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 자식 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-159">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto the child form.</span></span>  
  
3.  <span data-ttu-id="1b37b-160">클릭는 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))를 선택한 후 **항목 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-160">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")), and then select **Edit Items**.</span></span>  
  
4.  <span data-ttu-id="1b37b-161">에 **항목 컬렉션 편집기** 대화 상자에서 새 추가 <xref:System.Windows.Forms.ToolStripMenuItem> 라는 **ChildMenuItem** 하위 메뉴에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-161">In the **Items Collection Editor** dialog box, add a new <xref:System.Windows.Forms.ToolStripMenuItem> named **ChildMenuItem** to the child menu.</span></span>  
  
     <span data-ttu-id="1b37b-162">자세한 내용은 참조 [ToolStrip 항목 컬렉션 편집기](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-162">For more information, see [ToolStrip Items Collection Editor](http://msdn.microsoft.com/library/e681f3ab-94ba-4b2b-ac64-1dfad46caa25).</span></span>  
  
## <a name="testing-the-form"></a><span data-ttu-id="1b37b-163">테스트 폼</span><span class="sxs-lookup"><span data-stu-id="1b37b-163">Testing the Form</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="1b37b-164">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="1b37b-164">To test your form</span></span>  
  
1.  <span data-ttu-id="1b37b-165">F5 키를 눌러를 컴파일 및 폼을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-165">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="1b37b-166">클릭는 **창** 메뉴 항목을 클릭 하 고 메뉴를 연 **새로**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-166">Click the **Window** menu item to open the menu, and then click **New**.</span></span>  
  
     <span data-ttu-id="1b37b-167">새 자식 폼을 폼의 MDI 클라이언트 영역에서 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-167">A new child form is created in the form's MDI client area.</span></span> <span data-ttu-id="1b37b-168">자식 폼의 메뉴가 주 메뉴와 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-168">The child form's menu is merged with the main menu.</span></span>  
  
3.  <span data-ttu-id="1b37b-169">자식 폼을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-169">Close the child form.</span></span>  
  
     <span data-ttu-id="1b37b-170">자식 폼의 메뉴가 주 메뉴에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-170">The child form's menu is removed from the main menu.</span></span>  
  
4.  <span data-ttu-id="1b37b-171">클릭 **새로** 여러 번입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-171">Click **New** several times.</span></span>  
  
     <span data-ttu-id="1b37b-172">자식 폼 W가 자동으로 나열**창** 때문에 메뉴 항목의 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-172">The child forms are automatically listed under the W**indow** menu item because the <xref:System.Windows.Forms.MenuStrip> control's <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property is assigned.</span></span>  
  
## <a name="adding-toolstrip-support"></a><span data-ttu-id="1b37b-173">ToolStrip 지원 추가</span><span class="sxs-lookup"><span data-stu-id="1b37b-173">Adding ToolStrip Support</span></span>  
 <span data-ttu-id="1b37b-174">이 절차에서 추가한 4 <xref:System.Windows.Forms.ToolStrip> MDI 부모 폼에 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-174">In this procedure, you will add four <xref:System.Windows.Forms.ToolStrip> controls to the MDI parent form.</span></span> <span data-ttu-id="1b37b-175">각 <xref:System.Windows.Forms.ToolStrip> 내부 컨트롤에 추가 됩니다 한 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 가장자리에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-175">Each <xref:System.Windows.Forms.ToolStrip> control is added inside a <xref:System.Windows.Forms.ToolStripPanel> control, which is docked to the edge of the form.</span></span>  
  
#### <a name="to-add-toolstrip-controls-to-the-mdi-parent-form"></a><span data-ttu-id="1b37b-176">ToolStrip 컨트롤 MDI 부모 폼을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="1b37b-176">To add ToolStrip controls to the MDI parent form</span></span>  
  
1.  <span data-ttu-id="1b37b-177">**도구 상자**를 끌어 한 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-177">From the **Toolbox**, drag a <xref:System.Windows.Forms.ToolStripPanel> control onto the form.</span></span>  
  
2.  <span data-ttu-id="1b37b-178">와 <xref:System.Windows.Forms.ToolStripPanel> 선택 컨트롤을 두 번 클릭은 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-178">With the <xref:System.Windows.Forms.ToolStripPanel> control selected, double-click the <xref:System.Windows.Forms.ToolStrip> control in the **Toolbox**.</span></span>  
  
     <span data-ttu-id="1b37b-179">A <xref:System.Windows.Forms.ToolStrip> 컨트롤에서 만드는 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-179">A <xref:System.Windows.Forms.ToolStrip> control is created in the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
3.  <span data-ttu-id="1b37b-180"><xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-180">Select the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
4.  <span data-ttu-id="1b37b-181">속성 창에서 컨트롤의 값을 변경 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Left>합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-181">In the Properties window, change the value of the control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Left>.</span></span>  
  
     <span data-ttu-id="1b37b-182"><xref:System.Windows.Forms.ToolStripPanel> 주 메뉴 아래 폼의 왼쪽에 도킹을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-182">The <xref:System.Windows.Forms.ToolStripPanel> control docks to the left side of the form, underneath the main menu.</span></span> <span data-ttu-id="1b37b-183">MDI 클라이언트 영역에 맞게 조정 된 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-183">The MDI client area resizes to fit the <xref:System.Windows.Forms.ToolStripPanel> control.</span></span>  
  
5.  <span data-ttu-id="1b37b-184">1-4 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-184">Repeat steps 1 through 4.</span></span>  
  
     <span data-ttu-id="1b37b-185">새 도킹 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 맨 위로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-185">Dock the new <xref:System.Windows.Forms.ToolStripPanel> control to the top of the form.</span></span>  
  
     <span data-ttu-id="1b37b-186"><xref:System.Windows.Forms.ToolStripPanel> 주 메뉴 아래 하지만 첫 번째의 오른쪽에 컨트롤 도킹 <xref:System.Windows.Forms.ToolStripPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-186">The <xref:System.Windows.Forms.ToolStripPanel> control is docked underneath the main menu, but to the right of the first <xref:System.Windows.Forms.ToolStripPanel> control.</span></span> <span data-ttu-id="1b37b-187">이 단계 올바른 배치에 z 순서의 중요성을 보여 줍니다. <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-187">This step illustrates the importance of z-order in correctly positioning <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
6.  <span data-ttu-id="1b37b-188">두 개 이상의 대해 1-4 단계를 반복 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-188">Repeat steps 1 through 4 for two more <xref:System.Windows.Forms.ToolStripPanel> controls.</span></span>  
  
     <span data-ttu-id="1b37b-189">새 도킹 <xref:System.Windows.Forms.ToolStripPanel> 컨트롤을 폼의 아래쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-189">Dock the new <xref:System.Windows.Forms.ToolStripPanel> controls to the right and bottom of the form.</span></span>  
  
## <a name="arranging-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="1b37b-190">ToolStripPanel 컨트롤 Z 순서 정렬</span><span class="sxs-lookup"><span data-stu-id="1b37b-190">Arranging ToolStripPanel Controls by Z-order</span></span>  
 <span data-ttu-id="1b37b-191">도킹 된 위치 <xref:System.Windows.Forms.ToolStripPanel> MDI 폼의 컨트롤을 z-순서에서 컨트롤의 위치에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-191">The position of a docked <xref:System.Windows.Forms.ToolStripPanel> control on your MDI form is determined by the control's position in the z-order.</span></span> <span data-ttu-id="1b37b-192">문서 개요 창에서 컨트롤의 z 순서를 쉽게 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-192">You can easily arrange the z-order of your controls in the Document Outline window.</span></span>  
  
#### <a name="to-arrange-toolstrippanel-controls-by-z-order"></a><span data-ttu-id="1b37b-193">Z 순서 ToolStripPanel 컨트롤을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="1b37b-193">To arrange ToolStripPanel controls by Z-order</span></span>  
  
1.  <span data-ttu-id="1b37b-194">에 **보기** 메뉴를 클릭 **다른 창**, 클릭 하 고 **문서 개요**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-194">In the **View** menu, click **Other Windows**, and then click **Document Outline**.</span></span>  
  
     <span data-ttu-id="1b37b-195">배열을 프로그램 <xref:System.Windows.Forms.ToolStripPanel> 이전 절차에서 컨트롤은 표준이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-195">The arrangement of your <xref:System.Windows.Forms.ToolStripPanel> controls from the previous procedure is nonstandard.</span></span> <span data-ttu-id="1b37b-196">즉, z-순서 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-196">This is because the z-order is not correct.</span></span> <span data-ttu-id="1b37b-197">컨트롤의 z 순서를 변경 하려면 문서 개요 창을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-197">Use the Document Outline window to change the z-order of the controls.</span></span>  
  
2.  <span data-ttu-id="1b37b-198">문서 개요 창에서 선택한 **ToolStripPanel4**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-198">In the Document Outline window, select **ToolStripPanel4**.</span></span>  
  
3.  <span data-ttu-id="1b37b-199">아래쪽 화살표 단추를 클릭 때까지 반복 해 서 **ToolStripPanel4** 목록의 아래쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-199">Click the down-arrow button repeatedly, until **ToolStripPanel4** is at the bottom of the list.</span></span>  
  
     <span data-ttu-id="1b37b-200">**ToolStripPanel4** 컨트롤이 다른 컨트롤 아래 폼의 아래쪽에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-200">The **ToolStripPanel4** control is docked to the bottom of the form, underneath the other controls.</span></span>  
  
4.  <span data-ttu-id="1b37b-201">선택 **ToolStripPanel2**합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-201">Select **ToolStripPanel2**.</span></span>  
  
5.  <span data-ttu-id="1b37b-202">목록에서 세 번째 컨트롤을 이동 하려면 아래쪽 화살표 단추 한 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-202">Click the down-arrow button one time to position the control third in the list.</span></span>  
  
     <span data-ttu-id="1b37b-203">**ToolStripPanel2** 컨트롤 주 메뉴 아래 및 다른 컨트롤 위에 폼의 위쪽에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-203">The **ToolStripPanel2** control is docked to the top of the form, underneath the main menu and above the other controls.</span></span>  
  
6.  <span data-ttu-id="1b37b-204">다양 한 컨트롤을 선택는 **문서 개요** 창이 z-순서에서 다른 위치로 이동 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-204">Select various controls in the **Document Outline** window and move them to different positions in the z-order.</span></span> <span data-ttu-id="1b37b-205">Note z-순서 도킹 된 컨트롤의 배치에 미치는 영향입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-205">Note the effect of the z-order on the placement of docked controls.</span></span> <span data-ttu-id="1b37b-206">CTRL + Z를 사용 하 여 또는 **실행 취소** 에 **편집** 변경 내용을 취소 하는 메뉴입니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-206">Use CTRL-Z or **Undo** on the **Edit** menu to undo your changes.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="1b37b-207">검사점</span><span class="sxs-lookup"><span data-stu-id="1b37b-207">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="1b37b-208">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="1b37b-208">To test your form</span></span>  
  
1.  <span data-ttu-id="1b37b-209">F5 키를 눌러를 컴파일 및 폼을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-209">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="1b37b-210">그립을 클릭 한 <xref:System.Windows.Forms.ToolStrip> 제어 하 고 양식에서 컨트롤을 다른 위치로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-210">Click the grip of a <xref:System.Windows.Forms.ToolStrip> control and drag the control to different positions on the form.</span></span>  
  
     <span data-ttu-id="1b37b-211">끌 수는 <xref:System.Windows.Forms.ToolStrip> 하나에서 제어 <xref:System.Windows.Forms.ToolStripPanel> 다른 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-211">You can drag a <xref:System.Windows.Forms.ToolStrip> control from one <xref:System.Windows.Forms.ToolStripPanel> control to another.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1b37b-212">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1b37b-212">Next Steps</span></span>  
 <span data-ttu-id="1b37b-213">이 연습에서 사용 하 여 MDI 부모 폼을 만든 <xref:System.Windows.Forms.ToolStrip> 컨트롤과 메뉴 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-213">In this walkthrough, you have created an MDI parent form with <xref:System.Windows.Forms.ToolStrip> controls and menu merging.</span></span> <span data-ttu-id="1b37b-214">사용할 수는 <xref:System.Windows.Forms.ToolStrip> 패밀리 등과 같은 용도로 컨트롤:</span><span class="sxs-lookup"><span data-stu-id="1b37b-214">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="1b37b-215">사용자 컨트롤에 대 한 바로 가기 메뉴 만들기 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-215">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="1b37b-216">자세한 내용은 참조 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-216">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="1b37b-217">자동으로 채워지는 표준 메뉴를 사용 하 여 폼을 만든 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-217">Created a form with an automatically populated standard menu.</span></span> <span data-ttu-id="1b37b-218">자세한 내용은 참조 [연습: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-218">For more information, see [Walkthrough: Providing Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/walkthrough-providing-standard-menu-items-to-a-form.md).</span></span>  
  
-   <span data-ttu-id="1b37b-219">지정 하면 <xref:System.Windows.Forms.ToolStrip> 전문적인 모양 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-219">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="1b37b-220">자세한 내용은 참조 [하는 방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b37b-220">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b37b-221">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b37b-221">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="1b37b-222">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="1b37b-222">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="1b37b-223">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="1b37b-223">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="1b37b-224">방법: MDI 드롭다운 메뉴에 MenuStrip 삽입</span><span class="sxs-lookup"><span data-stu-id="1b37b-224">How to: Insert a MenuStrip into an MDI Drop-Down Menu</span></span>](../../../../docs/framework/winforms/controls/how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms.md)  
 [<span data-ttu-id="1b37b-225">ToolStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1b37b-225">ToolStrip Control</span></span>](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
