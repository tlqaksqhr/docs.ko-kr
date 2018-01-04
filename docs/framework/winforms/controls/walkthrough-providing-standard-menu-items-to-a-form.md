---
title: "연습: 폼에 표준 메뉴 항목 제공"
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
- menu items [Windows Forms], standard
- toolbars [Windows Forms], walkthroughs
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: dac37d98-589e-4d6d-9673-6437e8943122
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f1b976a0b5e0962cae155f380b17737077c5353
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-providing-standard-menu-items-to-a-form"></a><span data-ttu-id="f74d5-102">연습: 폼에 표준 메뉴 항목 제공</span><span class="sxs-lookup"><span data-stu-id="f74d5-102">Walkthrough: Providing Standard Menu Items to a Form</span></span>
<span data-ttu-id="f74d5-103"><xref:System.Windows.Forms.MenuStrip> 컨트롤을 사용하여 폼에 표준 메뉴를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-103">You can provide a standard menu for your forms with the <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="f74d5-104">이 연습에서는 사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.MenuStrip> 표준 메뉴를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-104">This walkthrough demonstrates how to use a <xref:System.Windows.Forms.MenuStrip> control to create a standard menu.</span></span> <span data-ttu-id="f74d5-105">사용자가 메뉴 항목을 선택할 때에 폼 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-105">The form also responds when a user selects a menu item.</span></span> <span data-ttu-id="f74d5-106">같은 작업을이 연습에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-106">The following tasks are illustrated in this walkthrough:</span></span>  
  
-   <span data-ttu-id="f74d5-107">Windows Forms 프로젝트를 만드는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-107">Creating a Windows Forms project.</span></span>  
  
-   <span data-ttu-id="f74d5-108">표준 메뉴를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-108">Creating a standard menu.</span></span>  
  
-   <span data-ttu-id="f74d5-109">만들기는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-109">Creating a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
-   <span data-ttu-id="f74d5-110">메뉴 항목 선택을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-110">Handling menu item selection.</span></span>  
  
 <span data-ttu-id="f74d5-111">작업을 완료 하는 경우 메뉴 항목에서 표시 하는 표준 메뉴를 사용 하 여 폼 것는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-111">When you are finished, you will have a form with a standard menu that displays menu item selections in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
 <span data-ttu-id="f74d5-112">단일 목록으로이 항목의 코드를 복사 하려면 참조 [하는 방법: 폼에 표준 메뉴 항목 제공](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-112">To copy the code in this topic as a single listing, see [How to: Provide Standard Menu Items to a Form](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f74d5-113">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f74d5-114">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f74d5-115">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f74d5-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f74d5-116">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="f74d5-116">Prerequisites</span></span>  
 <span data-ttu-id="f74d5-117">이 연습을 완료하려면 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-117">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="f74d5-118">만들고 컴퓨터에 Windows Forms 응용 프로그램 프로젝트를 실행할 수 있는 충분 한 권한이 있는 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 가 설치 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-118">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] is installed.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="f74d5-119">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="f74d5-119">Creating the Project</span></span>  
 <span data-ttu-id="f74d5-120">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="f74d5-121">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f74d5-121">To create the project</span></span>  
  
1.  <span data-ttu-id="f74d5-122">호출 하는 Windows 응용 프로그램 프로젝트 만들기 **StandardMenuForm**합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-122">Create a Windows application project called **StandardMenuForm**.</span></span>  
  
     <span data-ttu-id="f74d5-123">자세한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f74d5-123">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="f74d5-124">Windows Forms 디자이너에서 폼을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-124">In the Windows Forms Designer, select the form.</span></span>  
  
## <a name="creating-a-standard-menu"></a><span data-ttu-id="f74d5-125">표준 메뉴 만들기</span><span class="sxs-lookup"><span data-stu-id="f74d5-125">Creating a Standard Menu</span></span>  
 <span data-ttu-id="f74d5-126">Windows Forms 디자이너가 자동으로 채울 수는 <xref:System.Windows.Forms.MenuStrip> 표준 메뉴 항목 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-126">The Windows Forms Designer can automatically populate a <xref:System.Windows.Forms.MenuStrip> control with standard menu items.</span></span>  
  
#### <a name="to-create-a-standard-menu"></a><span data-ttu-id="f74d5-127">표준 메뉴를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f74d5-127">To create a standard menu</span></span>  
  
1.  <span data-ttu-id="f74d5-128">**도구 상자**를 끌어 한 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-128">From the **Toolbox**, drag a <xref:System.Windows.Forms.MenuStrip> control onto your form.</span></span>  
  
2.  <span data-ttu-id="f74d5-129">클릭는 <xref:System.Windows.Forms.MenuStrip> 컨트롤의 스마트 태그 문자 모양 (![스마트 태그 문자 모양](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))을 선택 하 고 **표준 항목 삽입**합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-129">Click the <xref:System.Windows.Forms.MenuStrip> control's smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) and select **Insert Standard Items**.</span></span>  
  
     <span data-ttu-id="f74d5-130"><xref:System.Windows.Forms.MenuStrip> 컨트롤이 표준 메뉴 항목으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-130">The <xref:System.Windows.Forms.MenuStrip> control is populated with the standard menu items.</span></span>  
  
3.  <span data-ttu-id="f74d5-131">클릭는 **파일** 메뉴 항목의 기본 메뉴 항목과 해당 아이콘을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-131">Click the **File** menu item to see its default menu items and corresponding icons.</span></span>  
  
## <a name="creating-a-statusstrip-control"></a><span data-ttu-id="f74d5-132">StatusStrip 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="f74d5-132">Creating a StatusStrip Control</span></span>  
 <span data-ttu-id="f74d5-133">사용 된 <xref:System.Windows.Forms.StatusStrip> 컨트롤에 Windows Forms 응용 프로그램에 대 한 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-133">Use the <xref:System.Windows.Forms.StatusStrip> control to display status for your Windows Forms applications.</span></span> <span data-ttu-id="f74d5-134">현재 예제에서는 사용자가 선택한 메뉴 항목에 표시 됩니다는 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-134">In the current example, menu items selected by the user are displayed in a <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
#### <a name="to-create-a-statusstrip-control"></a><span data-ttu-id="f74d5-135">StatusStrip 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="f74d5-135">To create a StatusStrip control</span></span>  
  
1.  <span data-ttu-id="f74d5-136">**도구 상자**를 끌어 한 <xref:System.Windows.Forms.StatusStrip> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-136">From the **Toolbox**, drag a <xref:System.Windows.Forms.StatusStrip> control onto your form.</span></span>  
  
     <span data-ttu-id="f74d5-137"><xref:System.Windows.Forms.StatusStrip> 자동으로 폼의 아래쪽에 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-137">The <xref:System.Windows.Forms.StatusStrip> control automatically docks to the bottom of the form.</span></span>  
  
2.  <span data-ttu-id="f74d5-138">클릭는 <xref:System.Windows.Forms.StatusStrip> 컨트롤의 드롭다운 단추 및 선택 **StatusLabel** 추가 하는 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 <xref:System.Windows.Forms.StatusStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-138">Click the <xref:System.Windows.Forms.StatusStrip> control's drop-down button and select **StatusLabel** to add a <xref:System.Windows.Forms.ToolStripStatusLabel> control to the <xref:System.Windows.Forms.StatusStrip> control.</span></span>  
  
## <a name="handling-item-selection"></a><span data-ttu-id="f74d5-139">항목 선택 처리</span><span class="sxs-lookup"><span data-stu-id="f74d5-139">Handling Item Selection</span></span>  
 <span data-ttu-id="f74d5-140">처리는 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트를 사용자가 메뉴 항목을 선택할 때 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-140">Handle the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event to respond when the user selects a menu item.</span></span>  
  
#### <a name="to-handle-item-selection"></a><span data-ttu-id="f74d5-141">항목 선택을 처리 하려면</span><span class="sxs-lookup"><span data-stu-id="f74d5-141">To handle item selection</span></span>  
  
1.  <span data-ttu-id="f74d5-142">클릭는 **파일** 메뉴 항목 만들기에서 만든 표준 메뉴 섹션.</span><span class="sxs-lookup"><span data-stu-id="f74d5-142">Click the **File** menu item that you created in the Creating a Standard Menu section.</span></span>  
  
2.  <span data-ttu-id="f74d5-143">에 **속성** 창 클릭 **이벤트**합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-143">In the **Properties** window, click **Events**.</span></span>  
  
3.  <span data-ttu-id="f74d5-144">두 번 클릭 하 여 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-144">Double-click the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
     <span data-ttu-id="f74d5-145">Windows Forms 디자이너에 대 한 이벤트 처리기가 생성 된 <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-145">The Windows Forms Designer generates an event handler for the <xref:System.Windows.Forms.ToolStripDropDownItem.DropDownItemClicked> event.</span></span>  
  
4.  <span data-ttu-id="f74d5-146">이벤트 처리기에 다음 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-146">Insert the following code into the event handler.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#3)]  
  
5.  <span data-ttu-id="f74d5-147">삽입 된 `UpdateStatus` 양식에 유틸리티 메서드 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-147">Insert the `UpdateStatus` utility method definition into the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ToolStrip.StandardMenu#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StandardMenu/VB/Form1.vb#2)]  
  
## <a name="checkpoint"></a><span data-ttu-id="f74d5-148">검사점</span><span class="sxs-lookup"><span data-stu-id="f74d5-148">Checkpoint</span></span>  
  
#### <a name="to-test-your-form"></a><span data-ttu-id="f74d5-149">폼을 테스트 하려면</span><span class="sxs-lookup"><span data-stu-id="f74d5-149">To test your form</span></span>  
  
1.  <span data-ttu-id="f74d5-150">F5 키를 눌러를 컴파일 및 폼을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-150">Press F5 to compile and run your form.</span></span>  
  
2.  <span data-ttu-id="f74d5-151">클릭는 **파일** 메뉴 항목 메뉴를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-151">Click the **File** menu item to open the menu.</span></span>  
  
3.  <span data-ttu-id="f74d5-152">에 **파일** 메뉴에서 선택 항목 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-152">On the **File** menu, click one of the items to select it.</span></span>  
  
     <span data-ttu-id="f74d5-153"><xref:System.Windows.Forms.StatusStrip> 컨트롤 선택한 항목을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-153">The <xref:System.Windows.Forms.StatusStrip> control displays the selected item.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f74d5-154">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f74d5-154">Next Steps</span></span>  
 <span data-ttu-id="f74d5-155">이 연습에서는 표준 메뉴가 있는 폼을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-155">In this walkthrough, you have created a form with a standard menu.</span></span> <span data-ttu-id="f74d5-156">사용할 수는 <xref:System.Windows.Forms.ToolStrip> 패밀리 등과 같은 용도로 컨트롤:</span><span class="sxs-lookup"><span data-stu-id="f74d5-156">You can use the <xref:System.Windows.Forms.ToolStrip> family of controls for many other purposes:</span></span>  
  
-   <span data-ttu-id="f74d5-157">사용자 컨트롤에 대 한 바로 가기 메뉴 만들기 <xref:System.Windows.Forms.ContextMenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-157">Create shortcut menus for your controls with <xref:System.Windows.Forms.ContextMenuStrip>.</span></span> <span data-ttu-id="f74d5-158">자세한 내용은 참조 [ContextMenu 구성 요소 개요](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-158">For more information, see [ContextMenu Component Overview](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).</span></span>  
  
-   <span data-ttu-id="f74d5-159">도킹 된 다중 문서 MDI (인터페이스) 폼 만들기 <xref:System.Windows.Forms.ToolStrip> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-159">Create a multiple document interface (MDI) form with docking <xref:System.Windows.Forms.ToolStrip> controls.</span></span> <span data-ttu-id="f74d5-160">자세한 내용은 참조 [연습: 메뉴 병합 및 ToolStrip 컨트롤을 사용 하 여 MDI 폼 만들기](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-160">For more information, see [Walkthrough: Creating an MDI Form with Menu Merging and ToolStrip Controls](../../../../docs/framework/winforms/controls/walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md).</span></span>  
  
-   <span data-ttu-id="f74d5-161">지정 하면 <xref:System.Windows.Forms.ToolStrip> 전문적인 모양 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-161">Give your <xref:System.Windows.Forms.ToolStrip> controls a professional appearance.</span></span> <span data-ttu-id="f74d5-162">자세한 내용은 참조 [하는 방법: 응용 프로그램에 대 한 ToolStrip 렌더러 설정](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f74d5-162">For more information, see [How to: Set the ToolStrip Renderer for an Application](../../../../docs/framework/winforms/controls/how-to-set-the-toolstrip-renderer-for-an-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f74d5-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f74d5-163">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 [<span data-ttu-id="f74d5-164">MenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="f74d5-164">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
