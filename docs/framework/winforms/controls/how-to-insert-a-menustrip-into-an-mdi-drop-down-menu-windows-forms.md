---
title: "방법: MDI 드롭다운 메뉴에 MenuStrip 삽입(Windows Forms) | Microsoft Docs"
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
  - "MenuStrip 컨트롤[Windows Forms], 삽입"
  - "MenuStrip 컨트롤[Windows Forms], 병합"
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: MDI 드롭다운 메뉴에 MenuStrip 삽입(Windows Forms)
일부 응용 프로그램에서는 MDI\(다중 문서 인터페이스\) 자식 창의 종류가 MDI 부모 창의 종류와 다를 수 있습니다.  예를 들어, MDI 부모는 스프레드시트인데 MDI 자식은 차트일 수 있습니다.  이 경우 여러 종류의 MDI 자식 창이 활성화되어 있을 때 MDI 부모 메뉴의 내용을 MDI 자식 메뉴의 내용으로 업데이트해야 할 수 있습니다.  
  
 다음 절차에서는 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction> 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 사용하여 MDI 부모 메뉴의 드롭다운 부분에 MDI 자식 메뉴의 메뉴 항목 그룹을 삽입합니다.  MDI 자식 창을 닫으면 삽입한 메뉴 항목이 MDI 부모 메뉴에서 제거됩니다.  
  
### MDI 드롭다운 메뉴에 MenuStrip을 삽입하려면  
  
1.  폼을 만들고 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.  
  
2.  `Form1`에 <xref:System.Windows.Forms.MenuStrip>을 추가하고 <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.  
  
3.  `Form1` <xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File`로 설정합니다.  
  
4.  `&File` 메뉴 항목에 하위 메뉴 항목을 세 개 추가하고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`, `&Import from` 및 `E&xit`로 설정합니다.  
  
5.  `&Import from` 하위 메뉴 항목에 하위 메뉴 항목을 두 개 추가하고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Word` 및 `&Excel`로 설정합니다.  
  
6.  프로젝트에 폼을 추가하고 폼에 <xref:System.Windows.Forms.MenuStrip>을 추가한 다음 `Form2` <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.  
  
7.  `Form2` <xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&File`로 설정합니다.  
  
8.  `Form2`의 `&File` 메뉴에 <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `&Close` `and Save` 및 다른 <xref:System.Windows.Forms.ToolStripSeparator>의 순서로 하위 메뉴 항목을 추가합니다.  
  
9. `Form2` 메뉴 항목의 <xref:System.Windows.Forms.MergeAction> 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 다음 표에 표시된 대로 설정합니다.  
  
    |Form2 메뉴 항목|MergeAction 값|MergeIndex 값|  
    |-----------------|-------------------|------------------|  
    |파일|MatchOnly|\-1|  
    |Separator|Insert|2|  
    |저장|Insert|3|  
    |Save and Close|Insert|4|  
    |Separator|Insert|5|  
  
10. `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 만듭니다.  
  
11. 이벤트 처리기에서 `Form2`의 새 인스턴스를 `Form1`의 MDI 자식 폼으로 만들고 표시하는 다음 코드 예제와 비슷한 코드를 삽입합니다.  
  
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
  
12. `&Open` <xref:System.Windows.Forms.ToolStripMenuItem>에 다음 코드 예제와 비슷한 코드를 넣어 이벤트 처리기를 등록합니다.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
  
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