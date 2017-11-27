---
title: "방법: MDI 부모 창에 MenuStrip 추가(Windows Forms)"
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
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], appending
- MDI [Windows Forms], merging menu items
ms.assetid: ab70c936-b452-4653-b417-17be57bb795b
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fd028271ad29ff539d10015dcfacf71fc980d98c
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-append-a-menustrip-to-an-mdi-parent-window-windows-forms"></a><span data-ttu-id="c0774-102">방법: MDI 부모 창에 MenuStrip 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c0774-102">How to: Append a MenuStrip to an MDI Parent Window (Windows Forms)</span></span>
<span data-ttu-id="c0774-103">일부 응용 프로그램에서는 MDI(다중 문서 인터페이스) 자식 창의 종류가 MDI 부모 창과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="c0774-104">예를 들어 MDI 부모는 스프레드시트이고 MDI 자식은 차트일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="c0774-105">이 경우 다른 종류의 MDI 자식 창이 활성화될 때 MDI 부모 메뉴의 내용을 MDI 자식 메뉴의 내용으로 업데이트하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="c0774-106">다음 절차에서는 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 사용하여 MDI 자식 메뉴를 MDI 부모 메뉴에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to append the MDI child menu to the MDI parent menu.</span></span> <span data-ttu-id="c0774-107">MDI 자식 창을 닫으면 MDI 부모에서 추가된 메뉴가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-107">Closing the MDI child window removes the appended menu from the MDI parent.</span></span>  
  
 <span data-ttu-id="c0774-108">또한 참조 [다중 문서 MDI (인터페이스) 응용 프로그램](http://msdn.microsoft.com/library/xyhh2e7e\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-108">Also see [Multiple-Document Interface (MDI) Applications](http://msdn.microsoft.com/library/xyhh2e7e\(v=vs.110\)).</span></span>  
  
### <a name="to-append-a-menu-item-to-an-mdi-parent"></a><span data-ttu-id="c0774-109">MDI 부모에 메뉴 항목을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="c0774-109">To append a menu item to an MDI parent</span></span>  
  
1.  <span data-ttu-id="c0774-110">폼을 만들고 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-110">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="c0774-111">`Form1`에 <xref:System.Windows.Forms.MenuStrip>을 추가하고 <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-111">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3.  <span data-ttu-id="c0774-112">`Form1`<xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStripItem.Visible%2A> 속성을 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of the `Form1`<xref:System.Windows.Forms.MenuStrip> to `false`.</span></span>  
  
4.  <span data-ttu-id="c0774-113">`Form1`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-113">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
5.  <span data-ttu-id="c0774-114">`&File` 메뉴 항목에 하위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.Form.Text%2A> 속성을 `&Open`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-114">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.Form.Text%2A> property to `&Open`.</span></span>  
  
6.  <span data-ttu-id="c0774-115">프로젝트에 폼을 추가하고, 폼에 <xref:System.Windows.Forms.MenuStrip>을 추가한 다음 `Form2`<xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-115">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7.  <span data-ttu-id="c0774-116">`Form2`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.Form.Text%2A> 속성을 `&Special`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-116">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Form.Text%2A> property to `&Special`.</span></span>  
  
8.  <span data-ttu-id="c0774-117">`&Special` 메뉴 항목에 두 개의 하위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.Form.Text%2A> 속성을 각각 `Command&1` 및 `Command&2`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-117">Add two submenu items to the `&Special` menu item and set their <xref:System.Windows.Forms.Form.Text%2A> properties to `Command&1` and `Command&2`, respectively.</span></span>  
  
9. <span data-ttu-id="c0774-118">`&Special`, `Command&1` 및 `Command&2` 메뉴 항목의 <xref:System.Windows.Forms.MergeAction> 속성을 <xref:System.Windows.Forms.MergeAction.Append>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-118">Set the <xref:System.Windows.Forms.MergeAction> property of the `&Special`, `Command&1`, and `Command&2` menu items to <xref:System.Windows.Forms.MergeAction.Append>.</span></span>  
  
10. <span data-ttu-id="c0774-119">`&New`<xref:System.Windows.Forms.ToolStripMenuItem>의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-119">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="c0774-120">이벤트 처리기 내에서 다음 코드 예제와 비슷한 코드를 삽입하여 `Form2`의 새 인스턴스를 만들고 `Form1`의 MDI 자식으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-120">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
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
  
12. <span data-ttu-id="c0774-121">`&Open`<xref:System.Windows.Forms.ToolStripMenuItem>에 다음 코드 예제와 비슷한 코드를 배치하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-121">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c0774-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c0774-122">Compiling the Code</span></span>  
 <span data-ttu-id="c0774-123">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c0774-123">This example requires:</span></span>  
  
-   <span data-ttu-id="c0774-124">`Form1` 및 `Form2`라는 두 개의 <xref:System.Windows.Forms.Form> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c0774-124">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="c0774-125">`menuStrip1`이라는 `Form1`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 및 `menuStrip2`라는 `Form2`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c0774-125">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="c0774-126"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="c0774-126">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>
