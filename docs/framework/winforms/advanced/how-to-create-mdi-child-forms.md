---
title: "방법: MDI 자식 폼 만들기"
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
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a779229a61d18ec835197bafac66579c026e2ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="73d43-102">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="73d43-102">How to: Create MDI Child Forms</span></span>
<span data-ttu-id="73d43-103">MDI 자식 폼의 중요 한 요소는 [다중 문서 MDI (인터페이스) 응용 프로그램](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)사용자 상호 작용의 중심 이므로, 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-103">MDI child forms are an essential element of [Multiple-Document Interface (MDI) Applications](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>  
  
 <span data-ttu-id="73d43-104">다음 절차에서는 대부분의 워드프로세싱 응용 프로그램과 비슷하게 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 표시하는 MDI 자식 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-104">In the following procedure, you will create MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="73d43-105"><xref:System.Windows.Forms> 컨트롤을 <xref:System.Windows.Forms.DataGridView> 컨트롤과 같은 다른 컨트롤이나 컨트롤 혼합으로 대체하면 다양한 가능성을 가진 MDI 자식 창(및 확장을 통해 MDI 응용 프로그램)을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-105">Substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls enables you to create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73d43-106">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="73d43-107">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="73d43-108">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73d43-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-mdi-child-forms"></a><span data-ttu-id="73d43-109">MDI 자식 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="73d43-109">To create MDI child forms</span></span>  
  
1.  <span data-ttu-id="73d43-110">새 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-110">Create a new Windows Forms project.</span></span> <span data-ttu-id="73d43-111">**속성 창** 폼에 대 한 설정의 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`, 및 해당 `WindowsState` 속성을 `Maximized`합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-111">In **the Properties Windows** for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`, and its `WindowsState` property to `Maximized`.</span></span>  
  
     <span data-ttu-id="73d43-112">그러면 폼이 자식 창의 MDI 컨테이너로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-112">This designates the form as an MDI container for child windows.</span></span>  
  
2.  <span data-ttu-id="73d43-113">`Toolbox`에서 <xref:System.Windows.Forms.MenuStrip> 컨트롤을 폼으로 끌어서 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-113">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="73d43-114">설정의 `Text` 속성을 **파일**합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-114">Set its `Text` property to **File**.</span></span>  
  
3.  <span data-ttu-id="73d43-115">옆에 있는 줄임표 (...)는 **항목** 속성과 클릭 **추가** 두 자식 도구 스트립 메뉴 항목을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-115">Click the ellipses (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="73d43-116">설정의 `Text` 속성에 이들이 항목에 대 한 **새로** 및 **창**합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-116">Set the `Text` property for these items to **New** and **Window**.</span></span>  
  
4.  <span data-ttu-id="73d43-117">**솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 가리킨 **추가**를 선택한 후 **새 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-117">In **Solution Explorer**, right-click the project, point to **Add**, and then select **Add New Item**.</span></span>  
  
5.  <span data-ttu-id="73d43-118">에 **새 항목 추가** 대화 상자에서 **Windows Form** (에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) 또는 **Windows Forms 응용 프로그램 (.NET)** (에서 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) **템플릿** 창.</span><span class="sxs-lookup"><span data-stu-id="73d43-118">In the **Add New Item** dialog box, select **Windows Form** (in [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]) or **Windows Forms Application (.NET)** (in [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) from the **Templates** pane.</span></span> <span data-ttu-id="73d43-119">에 **이름** 상자, 폼의 이름을 **Form2**합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-119">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="73d43-120">클릭는 **열려** 단추를 프로젝트에 폼을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-120">Click the **Open** button to add the form to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73d43-121">이 단계에서 만든 MDI 자식 폼은 표준 Windows Form입니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-121">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="73d43-122">따라서 폼의 투명도를 제어할 수 있는 <xref:System.Windows.Forms.Form.Opacity%2A> 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-122">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="73d43-123">그러나 <xref:System.Windows.Forms.Form.Opacity%2A> 속성은 최상위 창에 사용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-123">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="73d43-124">그리기 문제가 발생할 수 있으므로 MDI 자식 폼에는 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="73d43-124">Do not use it with MDI child forms, as painting problems can occur.</span></span>  
  
     <span data-ttu-id="73d43-125">이 폼은 MDI 자식 폼에 대한 템플릿이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-125">This form will be the template for your MDI child forms.</span></span>  
  
     <span data-ttu-id="73d43-126">**Windows Forms 디자이너** 열리는지 **Form2**합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-126">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>  
  
6.  <span data-ttu-id="73d43-127">**도구 상자**를 끌어 한 **RichTextBox** 컨트롤을 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-127">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>  
  
7.  <span data-ttu-id="73d43-128">에 **속성** 창에서 설정 된 `Anchor` 속성을 **위쪽, 왼쪽** 및 `Dock` 속성을 **채우기**합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-128">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>  
  
     <span data-ttu-id="73d43-129">이렇게 하면 폼의 크기를 조정하는 경우에도 <xref:System.Windows.Forms.RichTextBox> 컨트롤이 MDI 자식 폼의 영역을 완전히 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-129">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>  
  
8.  <span data-ttu-id="73d43-130">두 번 클릭는 **새로** 만들려는 메뉴 항목은 <xref:System.Windows.Forms.Control.Click> 것에 대 한 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-130">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>  
  
9. <span data-ttu-id="73d43-131">클릭할 때 새 MDI 자식 폼을 만들려면 다음과 비슷한 코드를 삽입는 **새로** 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-131">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73d43-132">다음 예제에서는 이벤트 처리기가 `MenuItem2`에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-132">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="73d43-133">주의 응용 프로그램 아키텍처의 세부 사항에 따라 프로그램 **새로** 메뉴 항목이 하지 않을 `MenuItem2`합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-133">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>  
  
    ```vb  
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click  
       Dim NewMDIChild As New Form2()  
       'Set the Parent Form of the Child window.  
       NewMDIChild.MdiParent = Me  
       'Display the new form.  
       NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    protected void MDIChildNew_Click(object sender, System.EventArgs e){  
       Form2 newMDIChild = new Form2();  
       // Set the Parent Form of the Child window.  
       newMDIChild.MdiParent = this;  
       // Display the new form.  
       newMDIChild.Show();  
    }  
    ```  
  
    ```cpp  
    private:  
       void menuItem2_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          Form2^ newMDIChild = gcnew Form2();  
          // Set the Parent Form of the Child window.  
          newMDIChild->MdiParent = this;  
          // Display the new form.  
          newMDIChild->Show();  
       }  
    ```  
  
     <span data-ttu-id="73d43-134">[!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]에서 Form1.h의 맨 위에 다음 `#include` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-134">In [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], add the following `#include` directive at the top of Form1.h:</span></span>  
  
    ```cpp  
    #include "Form2.h"  
    ```  
  
10. <span data-ttu-id="73d43-135">맨 위에 있는 드롭다운 목록에는 **속성** 창에 해당 하는 메뉴 스트립을 선택는 **파일** 메뉴 스트립 집합과 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 Window <xref:System.Windows.Forms.ToolStripMenuItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-135">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
     <span data-ttu-id="73d43-136">이렇게 하면는 **창** 메뉴 활성 자식 창 옆에 확인 표시가 있는 열린 MDI 자식 창의 목록을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-136">This will enable the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>  
  
11. <span data-ttu-id="73d43-137">F5 키를 눌러 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-137">Press F5 to run the application.</span></span> <span data-ttu-id="73d43-138">선택 하 여 **새로** 에서 **파일** 메뉴에는 추적 유지 되는 새 MDI 자식 폼을 만들 수 있습니다는 **창** 메뉴 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-138">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="73d43-139">MDI 자식 폼이 <xref:System.Windows.Forms.MainMenu> 구성 요소(일반적으로 메뉴 항목의 메뉴 구조 사용)를 포함하고 <xref:System.Windows.Forms.MainMenu> 구성 요소(일반적으로 메뉴 항목의 메뉴 구조 사용)가 있는 MDI 부모 폼 내에서 열린 경우 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성(및 필요에 따라 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성)을 설정했으면 메뉴 항목이 자동으로 병합됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-139">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="73d43-140">두 <xref:System.Windows.Forms.MainMenu> 구성 요소와 자식 폼의 모든 메뉴 항목에 대한 <xref:System.Windows.Forms.MenuItem.MergeType%2A> 속성을 <xref:System.Windows.Forms.MenuMerge.MergeItems>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-140">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="73d43-141">또한 두 메뉴의 메뉴 항목이 원하는 순서대로 표시되도록 <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-141">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="73d43-142">MDI 부모 폼을 닫을 경우 MDI 부모에 대한 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하기 전에 각 MDI 자식 폼에서 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-142">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="73d43-143">MDI 자식의 <xref:System.Windows.Forms.Form.Closing> 이벤트를 취소해도 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트가 발생하지 않도록 방지되지는 않습니다. 그러나 MDI 부모의 <xref:System.Windows.Forms.Form.Closing> 이벤트에 대한 <xref:System.ComponentModel.CancelEventArgs> 인수가 이제 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-143">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="73d43-144"><xref:System.ComponentModel.CancelEventArgs> 인수를 `false`로 설정하여 MDI 부모 및 모든 MDI 자식 폼을 강제로 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73d43-144">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73d43-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73d43-145">See Also</span></span>  
 [<span data-ttu-id="73d43-146">MDI(다중 문서 인터페이스) 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="73d43-146">Multiple-Document Interface (MDI) Applications</span></span>](../../../../docs/framework/winforms/advanced/multiple-document-interface-mdi-applications.md)  
 [<span data-ttu-id="73d43-147">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="73d43-147">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="73d43-148">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="73d43-148">How to: Determine the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-determine-the-active-mdi-child.md)  
 [<span data-ttu-id="73d43-149">방법: 활성 MDI 자식으로 데이터 전송</span><span class="sxs-lookup"><span data-stu-id="73d43-149">How to: Send Data to the Active MDI Child</span></span>](../../../../docs/framework/winforms/advanced/how-to-send-data-to-the-active-mdi-child.md)  
 [<span data-ttu-id="73d43-150">방법: MDI 자식 양식 정렬</span><span class="sxs-lookup"><span data-stu-id="73d43-150">How to: Arrange MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-arrange-mdi-child-forms.md)
