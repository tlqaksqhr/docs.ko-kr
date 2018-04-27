---
title: '방법: Windows Forms으로 다중 창 사용자 인터페이스 만들기'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], examples
- ListView control [Windows Forms], examples
- RichTextBox control [Windows Forms], examples
- Panel control [Windows Forms], examples
- TreeView control [Windows Forms], examples
- Splitter control [Windows Forms], examples
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6011eb2d49e537a2f5dfc540611af40a30b3e721
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a><span data-ttu-id="fb96a-102">방법: Windows Forms으로 다중 창 사용자 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="fb96a-102">How to: Create a Multipane User Interface with Windows Forms</span></span>
<span data-ttu-id="fb96a-103">다음 절차에서는 Microsoft Outlook으로 사용 되는 비슷한 다중 창 사용자 인터페이스 만들어집니다는 **폴더** 목록은 **메시지** 창 및 **미리보기** 창.</span><span class="sxs-lookup"><span data-stu-id="fb96a-103">In the following procedure, you will create a multipane user interface that is similar to the one used in Microsoft Outlook, with a **Folder** list, a **Messages** pane, and a **Preview** pane.</span></span> <span data-ttu-id="fb96a-104">이 정렬은 주로 폼에 컨트롤을 도킹을 통해 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-104">This arrangement is achieved chiefly through docking controls with the form.</span></span>  
  
 <span data-ttu-id="fb96a-105">컨트롤을 고정 하면 부모 컨테이너의 가장자리 컨트롤을 고정은 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-105">When you dock a control, you determine which edge of the parent container a control is fastened to.</span></span> <span data-ttu-id="fb96a-106">따라서 설정 하는 경우는 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Right>, 컨트롤의 오른쪽 가장자리 부모 컨트롤의 오른쪽 가장자리에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-106">Thus, if you set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Right>, the right edge of the control will be docked to the right edge of its parent control.</span></span> <span data-ttu-id="fb96a-107">또한 컨트롤의 도킹된 가장자리는 컨테이너 컨트롤에 맞게 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-107">Additionally, the docked edge of the control is resized to match that of its container control.</span></span> <span data-ttu-id="fb96a-108">방식에 대 한 자세한 내용은 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성은 참조 [하는 방법: Windows Forms에 컨트롤 도킹](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-108">For more information about how the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property works, see [How to: Dock Controls on Windows Forms](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md).</span></span>  
  
 <span data-ttu-id="fb96a-109">정렬에 중점을 두고이 절차는 <xref:System.Windows.Forms.SplitContainer> 및 기타 컨트롤이 폼에서가 아니라를 모방 Microsoft Outlook 응용 프로그램으로 설정 하는 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-109">This procedure focuses on arranging the <xref:System.Windows.Forms.SplitContainer> and the other controls on the form, not on adding functionality to make the application mimic Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="fb96a-110">내에서 모든 컨트롤을 배치 하면이 사용자 인터페이스를 만들려면는 <xref:System.Windows.Forms.SplitContainer> 포함 되는 제어는 <xref:System.Windows.Forms.TreeView> 왼쪽 패널에서 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-110">To create this user interface, you place all the controls within a <xref:System.Windows.Forms.SplitContainer> control, which contains a <xref:System.Windows.Forms.TreeView> control in the left-hand panel.</span></span> <span data-ttu-id="fb96a-111">오른쪽 패널은 <xref:System.Windows.Forms.SplitContainer> 두 번째 컨트롤에 포함 되어 <xref:System.Windows.Forms.SplitContainer> 보호로 <xref:System.Windows.Forms.ListView> 컨트롤 위의 <xref:System.Windows.Forms.RichTextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-111">The right-hand panel of the <xref:System.Windows.Forms.SplitContainer> control contains a second <xref:System.Windows.Forms.SplitContainer> control with a <xref:System.Windows.Forms.ListView> control above a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="fb96a-112">이러한 <xref:System.Windows.Forms.SplitContainer> 독립 폼에서 다른 컨트롤의 크기를 조정 컨트롤을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-112">These <xref:System.Windows.Forms.SplitContainer> controls enable independent resizing of the other controls on the form.</span></span> <span data-ttu-id="fb96a-113">자신만의 사용자 지정 사용자 인터페이스를 파악 하려면이 절차에 설명 된 기술을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-113">You can adapt the techniques in this procedure to craft custom user interfaces of your own.</span></span>  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a><span data-ttu-id="fb96a-114">프로그래밍 방식으로 Outlook 스타일 사용자 인터페이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="fb96a-114">To create an Outlook-style user interface programmatically</span></span>  
  
1.  <span data-ttu-id="fb96a-115">폼 내에서 사용자 인터페이스를 구성 하는 각 컨트롤을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-115">Within a form, declare each control that comprises your user interface.</span></span> <span data-ttu-id="fb96a-116">이 예제에서는 사용는 <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, 및 <xref:System.Windows.Forms.RichTextBox> Microsoft Outlook 사용자 인터페이스와 유사 하 게 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-116">For this example, use the <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, and <xref:System.Windows.Forms.RichTextBox> controls to mimic the Microsoft Outlook user interface.</span></span>  
  
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
  
2.  <span data-ttu-id="fb96a-117">사용자 인터페이스를 정의 하는 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-117">Create a procedure that defines your user interface.</span></span> <span data-ttu-id="fb96a-118">다음 코드 형식에는 Microsoft Outlook에서 사용자 인터페이스와 유사 합니다 되도록 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-118">The following code sets the properties so that the form will resemble the user interface in Microsoft Outlook.</span></span> <span data-ttu-id="fb96a-119">그러나 다른 컨트롤을 사용 하 여 다르게에 도킹, 이기 쉽게 시키면 하는 다른 사용자 인터페이스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-119">However, by using other controls or docking them differently, it is just as easy to create other user interfaces that are equally flexible.</span></span>  
  
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
  
3.  <span data-ttu-id="fb96a-120">Visual basic에서에서 방금 만든 프로시저 호출을 추가 `New()` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-120">In Visual Basic, add a call to the procedure you just created in the `New()` procedure.</span></span> <span data-ttu-id="fb96a-121">Visual C#, 폼 클래스에 대 한 생성자에 게이 줄의 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb96a-121">In Visual C#, add this line of code to the constructor for the form class.</span></span>  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fb96a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb96a-122">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="fb96a-123">SplitContainer 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fb96a-123">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [<span data-ttu-id="fb96a-124">방법: 디자이너를 사용하여 Windows Forms으로 다중 창 사용자 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="fb96a-124">How to: Create a Multipane User Interface with Windows Forms Using the Designer</span></span>](../../../../docs/framework/winforms/controls/create-a-multipane-user-interface-with-wf-using-the-designer.md)
