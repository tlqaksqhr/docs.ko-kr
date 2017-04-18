---
title: "방법: Windows Forms의 그래픽 인쇄 | Microsoft Docs"
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
  - "그래픽, 인쇄"
  - "인쇄[Windows Forms], 그래픽"
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 방법: Windows Forms의 그래픽 인쇄
Windows 기반 응용 프로그램에서는 종종 그래픽을 인쇄하게 됩니다.  <xref:System.Drawing.Graphics> 클래스는 화면 또는 프린터와 같은 장치에 개체를 그릴 수 있는 방법을 제공합니다.  
  
### 그래픽을 인쇄하려면  
  
1.  폼에 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 추가합니다.  
  
2.  <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기에서 <xref:System.Drawing.Printing.PrintPageEventArgs> 클래스의 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 속성을 사용하여 인쇄할 그래픽 종류에 관한 내용을 프린터에 알립니다.  
  
     다음 코드 예제에서는 이벤트 처리기를 사용하여 경계 사각형 내에 파란 타원을 만드는 것을 보여 줍니다.  해당 사각형은 100, 150 위치에서 시작되며 너비 250, 높이 250입니다.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## 참고 항목  
 <xref:System.Drawing.Graphics>   
 <xref:System.Drawing.Brush>   
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)