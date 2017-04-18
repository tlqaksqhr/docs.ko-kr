---
title: "방법: Windows Forms 인쇄 작업 완료 | Microsoft Docs"
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
  - "인쇄 작업, Windows Forms에서 완료"
  - "인쇄[Windows Forms], 인쇄 작업"
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# 방법: Windows Forms 인쇄 작업 완료
인쇄와 관련된 워드프로세서 및 기타 응용 프로그램에서는 종종 인쇄 작업이 완료되었다는 메시지를 표시하는 옵션을 제공합니다.  <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 이벤트를 처리하여 Windows Forms에서 이 기능을 제공할 수 있습니다.  
  
 다음 절차가 제대로 실행되려면 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하여 Windows 기반 응용 프로그램을 만들어야 합니다. 이것은 Windows 기반 응용 프로그램에서 인쇄를 사용 가능하게 하는 표준 방법입니다.  <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하는 Windows Forms에서의 인쇄에 대한 자세한 내용은 [방법: 표준 Windows Forms 인쇄 작업 만들기](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)를 참조하십시오.  
  
### 인쇄 작업을 완료하려면  
  
1.  <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> 속성을 설정합니다.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  <xref:System.Drawing.Printing.PrintDocument.EndPrint> 이벤트를 처리하는 코드를 작성합니다.  
  
     다음 코드 예제에서는 문서 인쇄가 완료되었음을 나타내는 메시지 상자를 보여 줍니다.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## 참고 항목  
 <xref:System.Drawing.Printing.PrintDocument>   
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)