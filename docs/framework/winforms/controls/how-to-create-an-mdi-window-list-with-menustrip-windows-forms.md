---
title: '방법: MenuStrip이 포함된 MDI 창 목록 만들기(Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: c87ffadaef2842f10d40f6fd84eb1c70c6dfe37e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530825"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="dc955-102">방법: MenuStrip이 포함된 MDI 창 목록 만들기(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="dc955-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="dc955-103">다중 문서 인터페이스 MDI ()를 사용 하 여 동일한 시간 및 복사에 여러 문서를 열고 다른 한 문서에서 콘텐츠를 붙여 넣을 수 있는 응용 프로그램을 만드는 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="dc955-104">이 절차는 부모의 창 메뉴에 모든 활성 자식 폼 목록을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="dc955-105">MenuStrip에서 된 MDI 창 목록 만들기를</span><span class="sxs-lookup"><span data-stu-id="dc955-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1.  <span data-ttu-id="dc955-106">폼을 만들고 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="dc955-107">폼에 <xref:System.Windows.Forms.MenuStrip>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3.  <span data-ttu-id="dc955-108">에 최상위 메뉴 항목을 두 개의 추가 <xref:System.Windows.Forms.MenuStrip> 설정 하 고 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File` 및 `&Window`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4.  <span data-ttu-id="dc955-109">`&File` 메뉴 항목에 하위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5.  <span data-ttu-id="dc955-110">설정의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 의 속성은 <xref:System.Windows.Forms.MenuStrip> 에 `&Window` <xref:System.Windows.Forms.ToolStripMenuItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6.  <span data-ttu-id="dc955-111">프로젝트에 폼을 추가 하 고 추가할 컨트롤을 있으므로, 예: 다른 <xref:System.Windows.Forms.MenuStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7.  <span data-ttu-id="dc955-112">`&New`<xref:System.Windows.Forms.ToolStripMenuItem>의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8.  <span data-ttu-id="dc955-113">이벤트 처리기에서 만들고의 새 인스턴스를 표시 하려면 다음과 유사한 코드를 삽입 `Form2` 의 MDI 자식으로 `Form1`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="dc955-114">다음과 같은 코드를 추가 하는 `&New` <xref:System.Windows.Forms.ToolStripMenuItem> 이벤트 처리기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dc955-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dc955-115">Compiling the Code</span></span>  
 <span data-ttu-id="dc955-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dc955-116">This example requires:</span></span>  
  
-   <span data-ttu-id="dc955-117">`Form1` 및 `Form2`라는 두 개의 <xref:System.Windows.Forms.Form> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dc955-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="dc955-118">`menuStrip1`이라는 `Form1`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 및 `menuStrip2`라는 `Form2`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dc955-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="dc955-119"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="dc955-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc955-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc955-120">See Also</span></span>  
 [<span data-ttu-id="dc955-121">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="dc955-121">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="dc955-122">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="dc955-122">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="dc955-123">MenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="dc955-123">MenuStrip Control</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)
