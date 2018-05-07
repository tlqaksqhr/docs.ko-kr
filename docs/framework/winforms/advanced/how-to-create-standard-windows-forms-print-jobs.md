---
title: '방법: 표준 Windows Forms 인쇄 작업 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: b580268a6af3f56f240a1c511c3d473a4a5ddc15
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>방법: 표준 Windows Forms 인쇄 작업 만들기
Windows Forms의 인쇄의 기초가 되는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소-보다 구체적으로 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트입니다. 처리 하는 코드를 작성 하 여는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 인쇄 대상 및 인쇄 하는 방법을 지정할 수 있습니다.  
  
### <a name="to-create-a-print-job"></a>인쇄 작업을 만들려면  
  
1.  추가 <xref:System.Drawing.Printing.PrintDocument> 폼 구성 요소입니다.  
  
2.  <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 처리할 코드를 작성합니다.  
  
     인쇄 논리를 코딩 해야 합니다. 또한 인쇄 자료를 지정 해야 합니다.  
  
     다음 코드 예제에서에 빨간색 사각형의 모양 샘플 그래픽 만들어집니다는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 를 인쇄할 프록시로 이벤트 처리기입니다.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Visual C# 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     코드를 작성 해야 할 수는 <xref:System.Drawing.Printing.PrintDocument.BeginPrint> 및 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 정수 페이지의 총 수를 나타내는 인쇄 감소 하 각 페이지가 인쇄를 포함 하 여 이벤트입니다.  
  
    > [!NOTE]
    >  추가할 수는 <xref:System.Windows.Forms.PrintDialog> 양식을 사용자에 게 명확 하 고 효율적인 사용자 인터페이스 (UI)를 제공 하도록 구성 요소입니다. 설정의 <xref:System.Windows.Forms.PrintDialog.Document%2A> 의 속성은 <xref:System.Windows.Forms.PrintDialog> 문서 인쇄와 관련 된 속성을 설정 하는 구성 요소 사용 폼에서 작업을 합니다. 에 대 한 자세한 내용은 <xref:System.Windows.Forms.PrintDialog> 구성 요소 참조 [PrintDialog 구성 요소](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)합니다.  
  
     인쇄 작업을 프로그래밍 방식으로 인쇄 작업을 만드는 방법을 포함 하 여 Windows Forms의 세부 사항에 대 한 자세한 내용은 참조 <xref:System.Drawing.Printing.PrintPageEventArgs>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
