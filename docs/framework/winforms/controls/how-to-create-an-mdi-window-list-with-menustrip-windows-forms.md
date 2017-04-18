---
title: "방법: MenuStrip이 포함된 MDI 창 목록 만들기(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MDI, 창 목록 만들기"
  - "MenuStrip 컨트롤[Windows Forms], 창 목록 만들기"
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: MenuStrip이 포함된 MDI 창 목록 만들기(Windows Forms)
MDI\(다중 문서 인터페이스\)를 사용하면 여러 개의 문서를 동시에 열고 문서의 내용을 복사한 후 다른 문서에 붙여넣을 수 있는 응용 프로그램을 만들 수 있습니다.  
  
 이 절차에서는 부모 창 메뉴에 활성화된 모든 자식 폼의 목록을 만드는 방법을 보여 줍니다.  
  
### MenuStrip에 MDI 창 목록을 만들려면  
  
1.  폼을 만들고 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.  
  
2.  <xref:System.Windows.Forms.MenuStrip>을 폼에 추가합니다.  
  
3.  <xref:System.Windows.Forms.MenuStrip>에 두 개의 최상위 메뉴 항목을 추가하고 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File` 및 `&Window`로 설정합니다.  
  
4.  `&File` 메뉴 항목에 하위 메뉴 항목을 추가하고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`으로 설정합니다.  
  
5.  Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
6.  프로젝트에 폼을 추가하고 해당 폼에 다른 <xref:System.Windows.Forms.MenuStrip>과 같은 컨트롤을 추가합니다.  
  
7.  이벤트 처리기를 만들는 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
8.  이벤트 처리기에서 `Form2`의 새 인스턴스를 `Form1`의 MDI 자식 폼으로 만들고 표시하는 다음과 비슷한 코드를 삽입합니다.  
  
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
  
     \[C\#\]  
  
    ```  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
  
    ```  
  
9. 코드에서 다음과 같은 배치는 `&New`<xref:System.Windows.Forms.ToolStripMenuItem> 이벤트 처리기를 등록 합니다.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
  
    ```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   두 개의 <xref:System.Windows.Forms.Form> 컨트롤 `Form1` 및 `Form2`  
  
-   `Form1`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 `menuStrip1` 및 `Form2`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 `menuStrip2`  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [MenuStrip 컨트롤](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)