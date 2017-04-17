---
title: "방법: Windows Forms 응용 프로그램에서 인쇄 미리 보기 표시 | Microsoft Docs"
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
  - "예제[Windows Forms], 인쇄 미리 보기"
  - "인쇄 미리 보기, 표시"
  - "인쇄[Windows Forms], 인쇄 미리 보기"
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: Windows Forms 응용 프로그램에서 인쇄 미리 보기 표시
<xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤을 사용하면 사용자가 문서를 인쇄하기 전에 미리 볼 수 있습니다.  
  
 이렇게 하려면 <xref:System.Drawing.Printing.PrintDocument> 클래스의 인스턴스 즉, 인쇄할 문서를 지정해야 합니다.  <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 통해 인쇄 미리 보기를 사용하는 방법에 대한 자세한 내용은 [방법: Windows Forms에서 인쇄 미리 보기를 사용하여 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)를 참조하십시오.  
  
> [!NOTE]
>  런타임에 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤을 사용하려면 사용자의 컴퓨터에 로컬로 또는 네트워크를 통해 설치된 프린터가 있어야 합니다. 왜냐하면 이러한 프린터가 <xref:System.Windows.Forms.PrintPreviewDialog> 구성 요소에서 문서의 인쇄 모양을 결정하는 데 영향을 주기 때문입니다.  
  
 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 <xref:System.Drawing.Printing.PrinterSettings> 클래스를 사용합니다.  또한 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 <xref:System.Windows.Forms.PrintPreviewDialog> 구성 요소가 사용하는 것처럼 <xref:System.Drawing.Printing.PageSettings> 클래스를 사용합니다.  <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> 속성에 지정된 인쇄 문서는 <xref:System.Drawing.Printing.PrinterSettings> 및 <xref:System.Drawing.Printing.PageSettings> 클래스의 인스턴스를 참조하며 이러한 인스턴스는 미리 보기 창에서 문서를 렌더링하는 데 사용됩니다.  
  
### PrintPreviewDialog 컨트롤을 사용하여 페이지를 보려면  
  
-   <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 대화 상자를 표시하고 사용할 <xref:System.Drawing.Printing.PrintDocument>를 지정합니다.  
  
     다음 코드 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기를 사용하여 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 인스턴스를 엽니다.  인쇄 문서는 <xref:System.Windows.Forms.PrintDialog.Document%2A> 속성에 지정됩니다.  다음 예제에서는 인쇄 문서가 지정되지 않습니다.  
  
     이 예제에서는 폼에 <xref:System.Windows.Forms.Button> 컨트롤, 이름이 `myDocument`인 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 및 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤이 있다고 가정합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## 참고 항목  
 [PrintDocument 구성 요소](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)   
 [PrintPreviewDialog 컨트롤](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [Windows Forms](../../../../docs/framework/winforms/index.md)