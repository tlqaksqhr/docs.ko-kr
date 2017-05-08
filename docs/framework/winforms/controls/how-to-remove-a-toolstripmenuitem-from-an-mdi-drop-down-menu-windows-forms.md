---
title: "방법: MDI 드롭다운 메뉴에서 ToolStripMenuItem 제거(Windows Forms) | Microsoft Docs"
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
  - "MDI, 메뉴 항목 병합"
  - "메뉴 항목, MDI 드롭 다운 메뉴에서 제거"
  - "MenuStrip 컨트롤[Windows Forms], 병합"
  - "MenuStrip 컨트롤[Windows Forms], 제거"
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: MDI 드롭다운 메뉴에서 ToolStripMenuItem 제거(Windows Forms)
일부 응용 프로그램에서는 MDI\(다중 문서 인터페이스\) 자식 창의 종류가 MDI 부모 창의 종류와 다를 수 있습니다.  예를 들어, MDI 부모는 스프레드시트인데 MDI 자식은 차트일 수 있습니다.  이 경우 여러 종류의 MDI 자식 창이 활성화되어 있을 때 MDI 부모 메뉴의 내용을 MDI 자식 메뉴의 내용으로 업데이트해야 할 수 있습니다.  
  
 다음 절차에서는 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 사용하여 MDI 부모 메뉴의 드롭다운 부분에서 메뉴 항목을 제거합니다.  MDI 자식 창을 닫으면 제거한 메뉴 항목이 MDI 부모 메뉴에 복원됩니다.  
  
### MDI 드롭다운 메뉴에서 MenuStrip을 제거하려면  
  
1.  폼을 만들고 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.  
  
2.  `Form1`에 <xref:System.Windows.Forms.MenuStrip>을 추가하고 <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.  
  
3.  최상위 메뉴 항목에 추가 `Form1`<xref:System.Windows.Forms.MenuStrip> 를 설정 하 고 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성에 `&File`.  
  
4.  `&File` 메뉴 항목에 하위 메뉴 항목을 세 개 추가하고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`, `&Import from` 및 `E&xit`로 설정합니다.  
  
5.  `&Import from` 하위 메뉴 항목에 하위 메뉴 항목을 두 개 추가하고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Word` 및 `&Excel`로 설정합니다.  
  
6.  폼을 프로젝트에 추가 하 고 추가 <xref:System.Windows.Forms.MenuStrip> 양식과 집합에는 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성에는 `Form2`<xref:System.Windows.Forms.MenuStrip> 에 `true`.  
  
7.  최상위 메뉴 항목에 추가 `Form2`<xref:System.Windows.Forms.MenuStrip> 를 설정 하 고 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성에 `&File`.  
  
8.  `Form2`의 `&File` 메뉴에 `&Import from` 하위 메뉴 항목을 추가하고 `&File` 메뉴에 `&Word` 하위 메뉴 항목을 추가합니다.  
  
9. `Form2` 메뉴 항목의 <xref:System.Windows.Forms.MergeAction> 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 다음 표에 표시된 대로 설정합니다.  
  
    |Form2 메뉴 항목|MergeAction 값|MergeIndex 값|  
    |-----------------|-------------------|------------------|  
    |파일|MatchOnly|\-1|  
    |Import from|MatchOnly|\-1|  
    |Word|제거|\-1|  
  
10. `Form1`에 대 한 이벤트 처리기를 만들는 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.  
  
11. 이벤트 처리기에서 `Form1`의 MDI 자식 폼으로 `Form2`의 새 인스턴스를 만들고 표시하는 다음 코드 예제와 비슷한 코드를 삽입합니다.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
  
    ```  
  
     \[C\#\]  
  
    ```  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
  
    ```  
  
12. 다음 코드 예제에서는 유사한 코드 배치는 `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> 이벤트 처리기를 등록 합니다.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
  
    ```  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   두 개의 <xref:System.Windows.Forms.Form> 컨트롤 `Form1` 및 `Form2`  
  
-   `Form1`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 `menuStrip1` 및 `Form2`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 `menuStrip2`  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 [방법: MDI 상위 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)   
 [방법: MDI 자식 폼 만들기](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)   
 [MenuStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)