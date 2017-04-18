---
title: "방법: Windows Forms으로 다중 창 사용자 인터페이스 만들기 | Microsoft Docs"
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
  - "ListView 컨트롤[Windows Forms], 예제"
  - "Panel 컨트롤[Windows Forms], 예제"
  - "RichTextBox 컨트롤[Windows Forms], 예제"
  - "SplitContainer 컨트롤[Windows Forms], 예제"
  - "Splitter 컨트롤[Windows Forms], 예제"
  - "TreeView 컨트롤[Windows Forms], 예제"
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 방법: Windows Forms으로 다중 창 사용자 인터페이스 만들기
다음 프로시저에서는 Microsoft Outlook의 사용자 인터페이스와 비슷하게 **폴더** 목록, **메시지** 창 및 **미리 보기** 창이 있는 다중 창 사용자 인터페이스를 만듭니다.  이 배열은 주로 폼에 컨트롤을 도킹하여 만듭니다.  
  
 컨트롤을 도킹할 때는 컨트롤이 고정될 부모 컨테이너의 가장자리를 결정해야 합니다.  따라서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle>로 설정하면 컨트롤의 오른쪽 가장자리가 부모 컨트롤의 오른쪽 가장자리에 도킹됩니다.  또한 컨트롤의 도킹된 가장자리는 컨테이너 컨트롤에 맞게 크기가 조정됩니다.  <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성의 작동 방식에 대한 자세한 내용은 [방법: Windows Forms에 컨트롤 도킹](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)을 참조하십시오.  
  
 이 절차에서는 응용 프로그램을 Microsoft Outlook과 유사하게 만들기 위해 기능을 추가하는 것이 아니라 <xref:System.Windows.Forms.SplitContainer> 및 다른 컨트롤을 폼에 배열하는 방법에 초점을 맞춥니다.  
  
 이 사용자 인터페이스를 만들려면 모든 컨트롤을 <xref:System.Windows.Forms.SplitContainer> 컨트롤에 배열합니다. 이 컨트롤의 왼쪽 패널에 <xref:System.Windows.Forms.TreeView> 컨트롤이 포함됩니다.  <xref:System.Windows.Forms.SplitContainer> 컨트롤의 오른쪽 패널에는 <xref:System.Windows.Forms.RichTextBox> 컨트롤 위에 <xref:System.Windows.Forms.ListView> 컨트롤이 있는 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤이 포함됩니다.  이 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 사용하여 폼에 있는 나머지 컨트롤의 크기를 독립적으로 조정할 수 있습니다.  여기서 고유의 사용자 인터페이스를 만드는 기술을 적용할 수도 있습니다.  
  
### 프로그래밍 방식으로 Outlook 스타일의 사용자 인터페이스를 만들려면  
  
1.  폼 안에서 사용자 인터페이스를 구성하는 각 컨트롤을 선언합니다.  이 예제에서는 <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer> 및 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용하여 Microsoft Outlook 사용자 인터페이스와 비슷한 인터페이스를 만듭니다.  
  
    ```vb  
    Private WithEvents treeView1 As System.Windows.Forms.TreeView  
    Private WithEvents listView1 As System.Windows.Forms.ListView  
    Private WithEvents richTextBox1 As System.Windows.Forms.RichTextBox  
    Private WithEvents splitContainer1 As _  
        System.Windows.Forms.SplitContainer  
    Private WithEvents splitContainer2 As _  
        System.Windows.Forms.SplitContainer  
  
    ```  
  
    ```csharp  
    private System.Windows.Forms.TreeView treeView1;  
    private System.Windows.Forms.ListView listView1;  
    private System.Windows.Forms.RichTextBox richTextBox1;  
    private System.Windows.Forms. SplitContainer splitContainer2;  
    private System.Windows.Forms. SplitContainer splitContainer1;  
  
    ```  
  
2.  사용자 인터페이스를 정의하는 프로시저를 작성합니다.  다음 코드에서는 폼이 Microsoft Outlook의 사용자 인터페이스와 유사하도록 속성을 설정합니다.  그러나 다른 컨트롤을 사용하거나 컨트롤을 다르게 도킹시키면 크기 조정이 가능한 사용자 인터페이스를 쉽게 만들 수 있습니다.  
  
    ```vb  
    Public Sub CreateOutlookUI()  
        ' Create an instance of each control being used.  
        Me.components = New System.ComponentModel.Container()  
        Me.treeView1 = New System.Windows.Forms.TreeView()  
        Me.listView1 = New System.Windows.Forms.ListView()  
        Me.richTextBox1 = New System.Windows.Forms.RichTextBox()  
        Me.splitContainer1 = New System.Windows.Forms.SplitContainer()  
        Me.splitContainer2= New System.Windows.Forms. SplitContainer()  
  
        ' Should you develop this into a working application,  
        ' use the AddHandler method to hook up event procedures here.  
  
        ' Set properties of TreeView control.  
        ' Use the With statement to avoid repetitive code.  
        With Me.treeView1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 0  
            .Nodes.Add("treeView")  
        End With  
  
    ' Set properties of ListView control.  
       With Me.listView1  
          .Dock = System.Windows.Forms.DockStyle.Top  
          .TabIndex = 2  
          .Items.Add("listView")  
       End With  
  
    ' Set properties of RichTextBox control.  
       With Me.richTextBox1  
          .Dock = System.Windows.Forms.DockStyle.Fill  
          .TabIndex = 3  
          .Text = "richTextBox1"  
       End With  
  
        ' Set properties of the first SplitContainer control.  
        With Me.splitContainer1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 1  
            .SplitterWidth = 4  
            .SplitterDistance = 150  
            .Orientation = Orientation.Horizontal  
            .Panel1.Controls.Add(Me.listView1)  
            .Panel2.Controls.Add(Me.richTextBox1)  
    End With  
  
        ' Set properties of the second SplitContainer control.  
        With Me.splitContainer2  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 4  
            .SplitterWidth = 4  
            .SplitterDistance = 100  
            .Panel1.Controls.Add(Me.treeView1)  
            .Panel2.Controls.Add(Me.SplitContainer1)  
    End With  
  
    ' Add the main SplitContainer control to the form.  
        Me.Controls.Add(Me.splitContainer2)  
        Me.Text = "Intricate UI Example"  
    End Sub  
  
    ```  
  
    ```csharp  
    public void createOutlookUI()  
    {  
        // Create an instance of each control being used.  
        treeView1 = new System.Windows.Forms.TreeView();  
        listView1 = new System.Windows.Forms.ListView();  
        richTextBox1 = new System.Windows.Forms.RichTextBox();  
        splitContainer2 = new System.Windows.Forms.SplitContainer();  
        splitContainer1 = new System.Windows.Forms.SplitContainer();  
  
        // Insert code here to hook up event methods.  
  
        // Set properties of TreeView control.  
        treeView1.Dock = System.Windows.Forms.DockStyle.Fill;  
        treeView1.TabIndex = 0;  
        treeView1.Nodes.Add("treeView");  
  
        // Set properties of ListView control.  
        listView1.Dock = System.Windows.Forms.DockStyle.Top;  
        listView1.TabIndex = 2;  
        listView1.Items.Add("listView");  
  
        // Set properties of RichTextBox control.  
        richTextBox1.Dock = System.Windows.Forms.DockStyle.Fill;  
        richTextBox1.TabIndex = 3;  
        richTextBox1.Text = "richTextBox1";  
  
        // Set properties of first SplitContainer control.  
        splitContainer1.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 1;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 150;  
        splitContainer2.Orientation = Orientation.Horizontal;  
        splitContainer2.Panel1.Controls.Add(this.listView1);  
        splitContainer2.Panel1.Controls.Add(this.richTextBox1);  
  
        // Set properties of second SplitContainer control.  
        splitContainer2.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 4;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 100;  
        splitContainer2.Panel1.Controls.Add(this.treeView1);  
        splitContainer2.Panel1.Controls.Add(this.splitContainer1);  
  
        // Add the main SplitContainer control to the form.  
        this.Controls.Add(this.splitContainer2);  
        this.Text = "Intricate UI Example";  
    }  
  
    ```  
  
3.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서 방금 만든 프로시저에 대한 호출을 `New()` 프로시저에 추가합니다.  [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]에서는 폼 클래스의 생성자에 다음 코드 줄을 추가합니다.  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
  
    ```  
  
## 참고 항목  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer 컨트롤](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)   
 [방법: 디자이너를 사용하여 Windows Forms으로 다중 창 사용자 인터페이스 만들기](../../../../docs/framework/winforms/controls/create-a-multipane-user-interface-with-wf-using-the-designer.md)