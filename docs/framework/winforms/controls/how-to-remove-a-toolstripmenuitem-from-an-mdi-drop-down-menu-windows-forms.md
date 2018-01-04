---
title: "방법: MDI 드롭다운 메뉴에서 ToolStripMenuItem 제거(Windows Forms)"
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
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4ef6927c56e18f74e04648c541f8cff4d29167cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="45e68-102">방법: MDI 드롭다운 메뉴에서 ToolStripMenuItem 제거(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="45e68-102">How to: Remove a ToolStripMenuItem from an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="45e68-103">일부 응용 프로그램에서는 MDI(다중 문서 인터페이스) 자식 창의 종류가 MDI 부모 창과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="45e68-104">예를 들어 MDI 부모는 스프레드시트이고 MDI 자식은 차트일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="45e68-105">이 경우 다른 종류의 MDI 자식 창이 활성화될 때 MDI 부모 메뉴의 내용을 MDI 자식 메뉴의 내용으로 업데이트하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="45e68-106">다음 절차를 사용 하 여는 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 MDI 부모 메뉴의 드롭다운 부분에서 메뉴 항목을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to remove a menu item from the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="45e68-107">MDI 자식 창을 닫으면 MDI 부모 메뉴를 제거 하는 메뉴 항목을 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-107">Closing the MDI child window restores the removed menu items to the MDI parent menu.</span></span>  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a><span data-ttu-id="45e68-108">MDI 드롭 다운 메뉴에서 MenuStrip을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="45e68-108">To remove a MenuStrip from an MDI drop-down menu</span></span>  
  
1.  <span data-ttu-id="45e68-109">폼을 만들고 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="45e68-110">`Form1`에 <xref:System.Windows.Forms.MenuStrip>을 추가하고 <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3.  <span data-ttu-id="45e68-111">`Form1`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4.  <span data-ttu-id="45e68-112">3 개의 하위 메뉴 항목을 추가 `&File` 메뉴 항목 집합과 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`, `&Import from`, 및 `E&xit`합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5.  <span data-ttu-id="45e68-113">두 개의 하위 메뉴 항목을 추가 `&Import from` 하위 메뉴 항목 집합과 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Word` 및 `&Excel`합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6.  <span data-ttu-id="45e68-114">프로젝트에 폼을 추가하고, 폼에 <xref:System.Windows.Forms.MenuStrip>을 추가한 다음 `Form2`<xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7.  <span data-ttu-id="45e68-115">`Form2`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&File`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8.  <span data-ttu-id="45e68-116">추가 `&Import from` 하위 메뉴 항목에는 `&File` 의 메뉴 `Form2`, 추가 하 고는 `&Word` 하위 메뉴 항목을는 `&File` 메뉴.</span><span class="sxs-lookup"><span data-stu-id="45e68-116">Add an `&Import from` submenu item to the `&File` menu of `Form2`, and add an `&Word` submenu item to the `&File` menu.</span></span>  
  
9. <span data-ttu-id="45e68-117">설정는 <xref:System.Windows.Forms.MergeAction> 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 의 속성은 `Form2` 다음 표와 같이 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="45e68-118">Form2 메뉴 항목</span><span class="sxs-lookup"><span data-stu-id="45e68-118">Form2 menu item</span></span>|<span data-ttu-id="45e68-119">MergeAction 값</span><span class="sxs-lookup"><span data-stu-id="45e68-119">MergeAction value</span></span>|<span data-ttu-id="45e68-120">MergeIndex 값</span><span class="sxs-lookup"><span data-stu-id="45e68-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="45e68-121">파일</span><span class="sxs-lookup"><span data-stu-id="45e68-121">File</span></span>|<span data-ttu-id="45e68-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="45e68-122">MatchOnly</span></span>|<span data-ttu-id="45e68-123">-1</span><span class="sxs-lookup"><span data-stu-id="45e68-123">-1</span></span>|  
    |<span data-ttu-id="45e68-124">가져오기</span><span class="sxs-lookup"><span data-stu-id="45e68-124">Import from</span></span>|<span data-ttu-id="45e68-125">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="45e68-125">MatchOnly</span></span>|<span data-ttu-id="45e68-126">-1</span><span class="sxs-lookup"><span data-stu-id="45e68-126">-1</span></span>|  
    |<span data-ttu-id="45e68-127">단어</span><span class="sxs-lookup"><span data-stu-id="45e68-127">Word</span></span>|<span data-ttu-id="45e68-128">제거</span><span class="sxs-lookup"><span data-stu-id="45e68-128">Remove</span></span>|<span data-ttu-id="45e68-129">-1</span><span class="sxs-lookup"><span data-stu-id="45e68-129">-1</span></span>|  
  
10. <span data-ttu-id="45e68-130">`Form1`에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-130">In `Form1`, create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="45e68-131">이벤트 처리기에서 만들고의 새 인스턴스를 표시 하려면 다음 코드 예제와 비슷한 코드를 삽입 `Form2` 의 MDI 자식으로 `Form1`:</span><span class="sxs-lookup"><span data-stu-id="45e68-131">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`:</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. <span data-ttu-id="45e68-132">`&Open`<xref:System.Windows.Forms.ToolStripMenuItem>에 다음 코드 예제와 비슷한 코드를 배치하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-132">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="45e68-133">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="45e68-133">Compiling the Code</span></span>  
 <span data-ttu-id="45e68-134">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="45e68-134">This example requires:</span></span>  
  
-   <span data-ttu-id="45e68-135">`Form1` 및 `Form2`라는 두 개의 <xref:System.Windows.Forms.Form> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="45e68-135">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="45e68-136">`menuStrip1`이라는 `Form1`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 및 `menuStrip2`라는 `Form2`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="45e68-136">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="45e68-137"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="45e68-137">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45e68-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45e68-138">See Also</span></span>  
 [<span data-ttu-id="45e68-139">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="45e68-139">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="45e68-140">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="45e68-140">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="45e68-141">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="45e68-141">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
