---
title: '방법: Windows Forms RichTextBox 컨트롤에서 끌어서 놓기 작업 사용'
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
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 17bf3b8e50c4e51cb14225e402903428a309d67a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="16ab4-102">방법: Windows Forms RichTextBox 컨트롤에서 끌어서 놓기 작업 사용</span><span class="sxs-lookup"><span data-stu-id="16ab4-102">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="16ab4-103">Windows Forms <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용한 끌어서 놓기 작업은 <xref:System.Windows.Forms.RichTextBox.DragEnter> 및 <xref:System.Windows.Forms.RichTextBox.DragDrop> 이벤트를 처리하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-103">Drag-and-drop operations with the Windows Forms <xref:System.Windows.Forms.RichTextBox> control are done by handling the <xref:System.Windows.Forms.RichTextBox.DragEnter> and <xref:System.Windows.Forms.RichTextBox.DragDrop> events.</span></span> <span data-ttu-id="16ab4-104">따라서 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용하면 끌어서 놓기 작업이 매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-104">Thus, drag-and-drop operations are extremely simple with the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a><span data-ttu-id="16ab4-105">RichTextBox 컨트롤에서 끌기 작업을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="16ab4-105">To enable drag operations in a RichTextBox control</span></span>  
  
1.  <span data-ttu-id="16ab4-106"><xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> 컨트롤의 <xref:System.Windows.Forms.RichTextBox> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-106">Set the <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> property of the <xref:System.Windows.Forms.RichTextBox> control to `true`.</span></span>  
  
2.  <span data-ttu-id="16ab4-107"><xref:System.Windows.Forms.RichTextBox.DragEnter> 이벤트의 이벤트 처리기에서 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-107">Write code in the event handler of the <xref:System.Windows.Forms.RichTextBox.DragEnter> event.</span></span> <span data-ttu-id="16ab4-108">`if` 문을 사용하여 끌고 있는 데이터가 허용되는 형식(이 경우 텍스트)인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-108">Use an `if` statement to ensure that the data being dragged is of an acceptable type (in this case, text).</span></span> <span data-ttu-id="16ab4-109"><xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> 속성은 <xref:System.Windows.Forms.DragDropEffects> 열거형의 값 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-109">The <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> property can be set to any value of the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     <span data-ttu-id="16ab4-110">(Visual C# 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-110">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3.  <span data-ttu-id="16ab4-111"><xref:System.Windows.Forms.RichTextBox.DragDrop> 이벤트를 처리할 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-111">Write code to handle the <xref:System.Windows.Forms.RichTextBox.DragDrop> event.</span></span> <span data-ttu-id="16ab4-112"><xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> 메서드를 사용하여 끌고 있는 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-112">Use the <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> method to retrieve the data being dragged.</span></span>  
  
     <span data-ttu-id="16ab4-113">아래 예제에서 코드는 <xref:System.Windows.Forms.RichTextBox.Text%2A> 컨트롤의 <xref:System.Windows.Forms.RichTextBox> 속성을 끌고 있는 데이터와 같도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-113">In the example below, the code sets the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control equal to the data being dragged.</span></span> <span data-ttu-id="16ab4-114"><xref:System.Windows.Forms.RichTextBox> 컨트롤에 이미 텍스트가 있는 경우에는 끌어온 텍스트가 삽입 지점에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-114">If there is already text in the <xref:System.Windows.Forms.RichTextBox> control, the dragged text is inserted at the insertion point.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _   
       ByVal e As System.Windows.Forms.DragEventArgs) _   
       Handles RichTextBox1.DragDrop  
       Dim i As Int16   
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +   
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());   
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     <span data-ttu-id="16ab4-115">(Visual C# 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-115">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew   
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a><span data-ttu-id="16ab4-116">응용 프로그램에서 끌어서 놓기 기능을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="16ab4-116">To test the drag-and-drop functionality in your application</span></span>  
  
1.  <span data-ttu-id="16ab4-117">응용 프로그램을 저장하고 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-117">Save and build your application.</span></span> <span data-ttu-id="16ab4-118">응용 프로그램이 실행되는 동안 워드패드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-118">While it is running, run WordPad.</span></span>  
  
     <span data-ttu-id="16ab4-119">워드패드는 끌어서 놓기 작업을 허용하는 Windows에 설치된 텍스트 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-119">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="16ab4-120">**시작** 단추를 클릭하고 **실행**을 선택한 다음 `WordPad` 실행 **대화 상자의 텍스트 상자에** 를 입력하고 **확인**을 클릭하면 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-120">It is accessible by clicking the **Start** button, selecting **Run**, typing `WordPad` in the text box of the **Run** dialog box, and then clicking **OK**.</span></span>  
  
2.  <span data-ttu-id="16ab4-121">워드패드가 열리면 텍스트 문자열을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-121">Once WordPad is open, type a string of text in it.</span></span> <span data-ttu-id="16ab4-122">마우스를 사용하여 텍스트를 선택한 다음 Windows 응용 프로그램의 <xref:System.Windows.Forms.RichTextBox> 컨트롤 위로 선택한 텍스트를 끕니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-122">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.RichTextBox> control in your Windows application.</span></span>  
  
     <span data-ttu-id="16ab4-123"><xref:System.Windows.Forms.RichTextBox> 컨트롤을 마우스로 가리키면(결과적으로 <xref:System.Windows.Forms.RichTextBox.DragEnter> 이벤트 발생) 마우스 포인터가 바뀌고 선택한 텍스트를 <xref:System.Windows.Forms.RichTextBox> 컨트롤로 끌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-123">Notice that when you point the mouse at the <xref:System.Windows.Forms.RichTextBox> control (and, consequently, raise the <xref:System.Windows.Forms.RichTextBox.DragEnter> event), the mouse pointer changes and you can drop the selected text into the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
     <span data-ttu-id="16ab4-124">마우스 단추를 놓으면 선택한 텍스트가 놓이고(즉, <xref:System.Windows.Forms.RichTextBox.DragDrop> 이벤트 발생) <xref:System.Windows.Forms.RichTextBox> 컨트롤 내에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="16ab4-124">When you release the mouse button, the selected text is dropped (that is, the <xref:System.Windows.Forms.RichTextBox.DragDrop> event is raised) and is inserted within the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ab4-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16ab4-125">See Also</span></span>  
 <xref:System.Windows.Forms.RichTextBox>  
 [<span data-ttu-id="16ab4-126">방법: 응용 프로그램 간에 끌어서 놓기 작업 수행</span><span class="sxs-lookup"><span data-stu-id="16ab4-126">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 [<span data-ttu-id="16ab4-127">RichTextBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="16ab4-127">RichTextBox Control</span></span>](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [<span data-ttu-id="16ab4-128">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="16ab4-128">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
