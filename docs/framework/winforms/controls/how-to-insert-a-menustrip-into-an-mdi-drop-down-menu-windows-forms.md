---
title: "방법: MDI 드롭다운 메뉴에 MenuStrip 삽입(Windows Forms)"
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
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2befec35090cf69c6a12cfe24c3512ae9a9b1bfa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a>방법: MDI 드롭다운 메뉴에 MenuStrip 삽입(Windows Forms)
일부 응용 프로그램에서는 MDI(다중 문서 인터페이스) 자식 창의 종류가 MDI 부모 창과 다를 수 있습니다. 예를 들어 MDI 부모는 스프레드시트이고 MDI 자식은 차트일 수 있습니다. 이 경우 다른 종류의 MDI 자식 창이 활성화될 때 MDI 부모 메뉴의 내용을 MDI 자식 메뉴의 내용으로 업데이트하려고 합니다.  
  
 다음 절차는 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> MDI 자식 메뉴의 메뉴 항목 그룹 MDI 부모 메뉴의 드롭다운 부분에 삽입 하는 속성입니다. MDI 자식 창을 닫으면 MDI 부모에서 삽입 된 메뉴 항목을 제거 합니다.  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a>MDI 드롭 다운 메뉴에 MenuStrip 삽입 하려면  
  
1.  폼을 만들고 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.  
  
2.  `Form1`에 <xref:System.Windows.Forms.MenuStrip>을 추가하고 <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.  
  
3.  `Form1`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File`로 설정합니다.  
  
4.  3 개의 하위 메뉴 항목을 추가 `&File` 메뉴 항목 집합과 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`, `&Import from`, 및 `E&xit`합니다.  
  
5.  두 개의 하위 메뉴 항목을 추가 `&Import from` 하위 메뉴 항목 집합과 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Word` 및 `&Excel`합니다.  
  
6.  프로젝트에 폼을 추가하고, 폼에 <xref:System.Windows.Forms.MenuStrip>을 추가한 다음 `Form2`<xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.  
  
7.  `Form2`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&File`로 설정합니다.  
  
8.  하위 메뉴 항목을 추가 `&File` 의 메뉴 `Form2` 다음과 같은 순서로:는 <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `&Close``and Save`, 또 다른 <xref:System.Windows.Forms.ToolStripSeparator>합니다.  
  
9. 설정는 <xref:System.Windows.Forms.MergeAction> 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 의 속성은 `Form2` 다음 표와 같이 메뉴 항목입니다.  
  
    |Form2 메뉴 항목|MergeAction 값|MergeIndex 값|  
    |---------------------|-----------------------|----------------------|  
    |파일|MatchOnly|-1|  
    |구분 기호|Insert|2|  
    |저장|Insert|3|  
    |저장 후 닫기|Insert|4|  
    |구분 기호|Insert|5|  
  
10. `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 만듭니다.  
  
11. 이벤트 처리기 내에서 다음 코드 예제와 비슷한 코드를 삽입하여 `Form2`의 새 인스턴스를 만들고 `Form1`의 MDI 자식으로 표시합니다.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
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
  
12. `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>에 다음 코드 예제와 비슷한 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `Form1` 및 `Form2`라는 두 개의 <xref:System.Windows.Forms.Form> 컨트롤  
  
-   `menuStrip1`이라는 `Form1`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 및 `menuStrip2`라는 `Form2`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤  
  
-   <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
