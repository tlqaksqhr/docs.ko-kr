---
title: "방법: 표준 Windows Forms 인쇄 작업 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "인쇄[Visual Basic], Windows 응용 프로그램"
  - "인쇄[Windows Forms]"
  - "인쇄[Windows Forms], 인쇄 작업 만들기"
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: 표준 Windows Forms 인쇄 작업 만들기
Windows Forms에서 인쇄의 기초가 되는 것은 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다. 더 자세히 말하면 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트입니다.  <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 처리하는 코드를 작성하여 인쇄할 내용과 인쇄 방법을 지정할 수 있습니다.  
  
### 인쇄 작업을 만들려면  
  
1.  폼에 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 추가합니다.  
  
2.  <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 처리하는 코드를 작성합니다.  
  
     자신만의 인쇄 논리를 코드로 작성해야 합니다.  또한, 인쇄할 내용을 지정해야 합니다.  
  
     다음 코드 예제에서는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기에서 인쇄할 내용인 빨간 사각형의 샘플 그래픽을 만듭니다.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
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
  
     인쇄할 전체 페이지 수를 나타내면서 한 페이지가 인쇄될 때마다 감소하는 정수를 포함하여 <xref:System.Drawing.Printing.PrintDocument.BeginPrint> 및 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 이벤트에 대한 코드를 작성할 수 있습니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.PrintDialog> 구성 요소를 폼에 추가하여 사용자에게 세련되고 효과적인 UI\(사용자 인터페이스\)를 제공할 수 있습니다.  <xref:System.Windows.Forms.PrintDialog> 구성 요소의 <xref:System.Windows.Forms.PrintDialog.Document%2A> 속성을 설정하여 폼에서 작업 중인 인쇄 문서와 관련된 속성을 설정할 수 있습니다.  <xref:System.Windows.Forms.PrintDialog> 구성 요소에 대한 자세한 내용은 [PrintDialog 구성 요소](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)를 참조하십시오.  
  
     프로그래밍 방식으로 인쇄 작업을 만드는 방법을 비롯하여 Windows Forms 인쇄 작업의 세부 사항에 대한 자세한 내용은 <xref:System.Drawing.Printing.PrintPageEventArgs>를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)