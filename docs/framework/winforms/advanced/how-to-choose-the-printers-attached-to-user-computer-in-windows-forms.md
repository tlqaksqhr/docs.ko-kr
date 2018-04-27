---
title: '방법: 사용자에 연결 된 프린터 선택&#39;Windows Forms에서의 컴퓨터'
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
- printing [Windows Forms], choosing printers
- printers [Windows Forms], choosing
ms.assetid: 63c1172b-2931-4ac0-953f-37f629494bbf
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 90feca3e1efeeae45b26a747e97ad8b5b945ec56
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-choose-the-printers-attached-to-a-user39s-computer-in-windows-forms"></a><span data-ttu-id="eb90a-102">방법: 사용자에 연결 된 프린터 선택&#39;Windows Forms에서의 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="eb90a-102">How to: Choose the Printers Attached to a User&#39;s Computer in Windows Forms</span></span>
<span data-ttu-id="eb90a-103">사용자는 기본 프린터 이외의 프린터를 선택하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="eb90a-103">Often, users want to choose a printer other than the default printer to print to.</span></span> <span data-ttu-id="eb90a-104"><xref:System.Windows.Forms.PrintDialog> 구성 요소를 사용하면 현재 설치된 프린터 중에서 사용자가 원하는 프린터를 선택하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb90a-104">You can enable users to choose a printer from among those currently installed by using the <xref:System.Windows.Forms.PrintDialog> component.</span></span> <span data-ttu-id="eb90a-105"><xref:System.Windows.Forms.PrintDialog> 구성 요소를 통해 <xref:System.Windows.Forms.DialogResult> 구성 요소의 <xref:System.Windows.Forms.PrintDialog> 가 캡처되고 프린터 선택에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb90a-105">Through the <xref:System.Windows.Forms.PrintDialog> component, the <xref:System.Windows.Forms.DialogResult> of the <xref:System.Windows.Forms.PrintDialog> component is captured and used to select the printer.</span></span>  
  
 <span data-ttu-id="eb90a-106">다음 절차에서는 텍스트 파일이 기본 프린터로 인쇄되도록 선택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eb90a-106">In the following procedure, a text file is selected to be printed to the default printer.</span></span> <span data-ttu-id="eb90a-107">그런 다음 <xref:System.Windows.Forms.PrintDialog> 클래스가 인스턴스화됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb90a-107">The <xref:System.Windows.Forms.PrintDialog> class is then instantiated.</span></span>  
  
### <a name="to-choose-a-printer-and-then-print-a-file"></a><span data-ttu-id="eb90a-108">프린터를 선택한 다음 파일을 인쇄하려면</span><span class="sxs-lookup"><span data-stu-id="eb90a-108">To choose a printer and then print a file</span></span>  
  
1.  <span data-ttu-id="eb90a-109">사용 하 여 사용할 프린터를 선택는 <xref:System.Windows.Forms.PrintDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="eb90a-109">Select the printer to be used using the <xref:System.Windows.Forms.PrintDialog> component.</span></span>  
  
     <span data-ttu-id="eb90a-110">다음 코드 예제에서는 두 이벤트가 처리되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb90a-110">In the following code example, there are two events being handled.</span></span> <span data-ttu-id="eb90a-111">첫 번째 호출는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트에는 <xref:System.Windows.Forms.PrintDialog> 클래스가 인스턴스화되고 사용자가 선택한 프린터에 캡처되는 <xref:System.Windows.Forms.DialogResult> 속성.</span><span class="sxs-lookup"><span data-stu-id="eb90a-111">In the first, a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event, the <xref:System.Windows.Forms.PrintDialog> class is instantiated and the printer selected by the user is captured in the <xref:System.Windows.Forms.DialogResult> property.</span></span>  
  
     <span data-ttu-id="eb90a-112">두 번째 이벤트에서는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 의 이벤트는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 지정 된 프린터에는 예제 문서를 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb90a-112">In the second event, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event of the <xref:System.Drawing.Printing.PrintDocument> component, a sample document is printed to the printer specified.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim PrintDialog1 As New PrintDialog()  
       PrintDialog1.Document = PrintDocument1  
       Dim result As DialogResult = PrintDialog1.ShowDialog()  
  
       If (result = DialogResult.OK) Then  
         PrintDocument1.Print()  
       End If   
  
    End Sub  
  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))          
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       PrintDialog printDialog1 = new PrintDialog();  
       printDialog1.Document = printDocument1;  
       DialogResult result = printDialog1.ShowDialog();  
       if (result == DialogResult.OK)  
       {  
          printDocument1.Print();  
       }  
    }  
  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          PrintDialog ^ printDialog1 = gcnew PrintDialog();  
          printDialog1->Document = printDocument1;  
          System::Windows::Forms::DialogResult result =   
             printDialog1->ShowDialog();  
          if (result == DialogResult::OK)  
          {  
             printDocument1->Print();  
          }  
       }  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="eb90a-113">(Visual C# 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb90a-113">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="eb90a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb90a-114">See Also</span></span>  
 [<span data-ttu-id="eb90a-115">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="eb90a-115">Windows Forms Print Support</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
