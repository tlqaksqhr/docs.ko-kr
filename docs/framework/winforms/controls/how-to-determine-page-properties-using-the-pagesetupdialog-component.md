---
title: "방법: PageSetupDialog 구성 요소를 사용하여 페이지 속성 설정"
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
- page properties
- page setup
- PageSetupDialog component
ms.assetid: 6dae05bc-c0fd-4357-bb93-841a1631d98f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7dc3603d37106c122f3e92503b37dcfc02d7fef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="2242f-102">방법: PageSetupDialog 구성 요소를 사용하여 페이지 속성 설정</span><span class="sxs-lookup"><span data-stu-id="2242f-102">How to: Determine Page Properties Using the PageSetupDialog Component</span></span>
<span data-ttu-id="2242f-103">[PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) 구성 요소는 문서의 사용자에게 레이아웃, 용지 크기 및 기타 페이지 레이아웃 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-103">The [PageSetupDialog](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) component presents layout, paper size, and other page layout choices to the user for a document.</span></span>  
  
 <span data-ttu-id="2242f-104"><xref:System.Drawing.Printing.PrintDocument> 클래스의 인스턴스를 지정해야 합니다(인쇄할 문서).</span><span class="sxs-lookup"><span data-stu-id="2242f-104">You need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class—this is the document to be printed.</span></span> <span data-ttu-id="2242f-105">또한 사용자 컴퓨터에 로컬로 또는 네트워크를 통해 프린터가 설치되어 있어야 합니다. 부분적으로 이것이 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소가 사용자에게 표시되는 페이지 서식 지정 옵션을 결정하는 방법이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-105">Additionally, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PageSetupDialog> component determines the page formatting choices presented to the user.</span></span>  
  
 <span data-ttu-id="2242f-106"><xref:System.Windows.Forms.PageSetupDialog> 구성 요소 작업의 중요한 측면은 <xref:System.Drawing.Printing.PageSettings> 클래스와의 상호 작용 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-106">An important aspect of working with the <xref:System.Windows.Forms.PageSetupDialog> component is how it interacts with the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="2242f-107"><xref:System.Drawing.Printing.PageSettings> 클래스는 용지 방향, 페이지의 크기, 여백 등 페이지가 인쇄되는 방법을 수정하는 설정을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-107">The <xref:System.Drawing.Printing.PageSettings> class is used to specify settings that modify the way a page will be printed, such as paper orientation, the size of the page, and the margins.</span></span> <span data-ttu-id="2242f-108">이러한 각 설정은 <xref:System.Drawing.Printing.PageSettings> 클래스의 속성으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-108">Each of these settings is represented as a property of the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="2242f-109"><xref:System.Windows.Forms.PageSetupDialog> 클래스는 문서와 연결된(그리고 <xref:System.Drawing.Printing.PageSettings> 속성으로 표시되는) <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> 클래스의 지정된 인스턴스에 대해 이러한 속성 값을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-109">The <xref:System.Windows.Forms.PageSetupDialog> class modifies these property values for a given instance of the <xref:System.Drawing.Printing.PageSettings> class that is associated with the document (and is represented as a <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> property).</span></span>  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="2242f-110">PageSetupDialog 구성 요소를 사용하여 페이지 속성을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2242f-110">To set page properties using the PageSetupDialog component</span></span>  
  
1.  <span data-ttu-id="2242f-111"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 대화 상자를 표시하고, 사용할 <xref:System.Drawing.Printing.PrintDocument> 를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="2242f-112">다음 예제에는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소의 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-112">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span> <span data-ttu-id="2242f-113"><xref:System.Windows.Forms.PageSetupDialog.Document%2A> 속성에서 기존 문서가 지정되고, 해당 <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> 속성은 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-113">An existing document is specified in the <xref:System.Windows.Forms.PageSetupDialog.Document%2A> property, and its <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> property is set to `false`.</span></span>  
  
     <span data-ttu-id="2242f-114">이 예에서는 가정 폼에는 <xref:System.Windows.Forms.Button> 컨트롤은 <xref:System.Drawing.Printing.PrintDocument> 라는 구성 요소가 `myDocument`, 및 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-114">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       'You will have to specify your own print document.  
       PageSetupDialog1.Document = myDocument  
       ' Sets the print document's color setting to false,  
       ' so that the page will not be printed in color.  
       PageSetupDialog1.Document.DefaultPageSettings.Color = False  
       PageSetupDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       pageSetupDialog1.Document = myDocument;  
       // Sets the print document's color setting to false,  
       // so that the page will not be printed in color.  
       pageSetupDialog1.Document.DefaultPageSettings.Color = false;  
       pageSetupDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void button1_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          pageSetupDialog1->Document = myDocument;  
          // Sets the print document's color setting to false,  
          // so that the page will not be printed in color.  
          pageSetupDialog1->Document->DefaultPageSettings->Color = false;  
          pageSetupDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="2242f-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2242f-115">([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew   
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="2242f-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2242f-116">See Also</span></span>  
 <xref:System.Windows.Forms.PageSetupDialog>  
 [<span data-ttu-id="2242f-117">방법: 표준 Windows Forms 인쇄 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="2242f-117">How to: Create Standard Windows Forms Print Jobs</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 [<span data-ttu-id="2242f-118">PageSetupDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="2242f-118">PageSetupDialog Component</span></span>](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)
