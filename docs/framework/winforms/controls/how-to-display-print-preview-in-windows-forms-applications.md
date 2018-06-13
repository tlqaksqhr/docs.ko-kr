---
title: '방법: Windows Forms 응용 프로그램에서 인쇄 미리 보기 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 1c1291ea675d823fab3052b0fa365cb2d4c31088
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532810"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a>방법: Windows Forms 응용 프로그램에서 인쇄 미리 보기 표시
사용할 수는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤 사용자가 인쇄 하기 전에 자주 문서를 표시할 수 있도록 합니다.  
  
 이 작업을 수행 하려면 인스턴스를 지정 해야는 <xref:System.Drawing.Printing.PrintDocument> 클래스입니다;이 문서를 인쇄 합니다. 인쇄 미리 보기를 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 참조 [하는 방법: Windows Forms를 사용 하 여 인쇄 미리 보기에서 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)합니다.  
  
> [!NOTE]
>  사용 하는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤 런타임 시 사용자가 프린터가 있어야 로컬 또는 네트워크를 통해 자신의 컴퓨터에 설치 되어 방법을 <xref:System.Windows.Forms.PrintPreviewDialog> 구성 요소는 인쇄 된 문서의 모양을 결정 합니다.  
  
 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤이 사용 하 여 <xref:System.Drawing.Printing.PrinterSettings> 클래스입니다. 또한는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤이 사용 하는 <xref:System.Drawing.Printing.PageSettings> 클래스인 것과 마찬가지로 <xref:System.Windows.Forms.PrintPreviewDialog> 구성 요소가 수행 합니다. 에 지정 된 인쇄 문서는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> 속성은 모두의 인스턴스를 참조는 <xref:System.Drawing.Printing.PrinterSettings> 및 <xref:System.Drawing.Printing.PageSettings> 클래스 및 이러한는 미리 보기 창에서 문서를 렌더링 하는 데 사용 합니다.  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a>PrintPreviewDialog 컨트롤을 사용 하 여 페이지를 보려면  
  
-   <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 대화 상자를 표시하고, 사용할 <xref:System.Drawing.Printing.PrintDocument> 를 지정합니다.  
  
     다음 코드 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기의 인스턴스를 열고는 <xref:System.Windows.Forms.PrintPreviewDialog> 제어 합니다. 인쇄 문서에 지정 된는 <xref:System.Windows.Forms.PrintDialog.Document%2A> 속성입니다. 아래 예제에서는 인쇄 문서가 지정 됩니다.  
  
     이 예제에서는 폼에는 <xref:System.Windows.Forms.Button> 컨트롤은 <xref:System.Drawing.Printing.PrintDocument> 라는 구성 요소가 `myDocument`, 및 <xref:System.Windows.Forms.PrintPreviewDialog> 제어 합니다.  
  
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
  
     (Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [PrintDocument 구성 요소](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 [PrintPreviewDialog 컨트롤](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [Windows Forms](../../../../docs/framework/winforms/index.md)
