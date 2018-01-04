---
title: "방법: Windows Forms 인쇄 작업 완료"
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
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 00c43ff4ca418d272dc00132907c5bcbc0c5bc8b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>방법: Windows Forms 인쇄 작업 완료
대부분의 경우 워드 프로세서 및 인쇄와 관련 된 기타 응용 프로그램 인쇄 작업이 완료 되는 사용자에 게 메시지를 표시 하는 옵션을 제공 합니다. 처리 하 여 Windows Forms에서이 기능을 제공할 수는 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 의 이벤트는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다.  
  
 다음 절차를 수행 하려면 Windows 기반 응용 프로그램을 만든는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 Windows 기반 응용 프로그램에서 인쇄를 사용 하도록 설정 하는 표준 방법입니다. 사용 하 여 Windows Forms에서 인쇄에 대 한 자세한 내용은 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 참조 [하는 방법: 표준 Windows Forms 인쇄 작업 만들기](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)합니다.  
  
### <a name="to-complete-a-print-job"></a>인쇄 작업을 완료 하려면  
  
1.  설정의 <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> 의 속성은 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  <xref:System.Drawing.Printing.PrintDocument.EndPrint> 이벤트를 처리할 코드를 작성합니다.  
  
     다음 코드 예제에서는 문서 인쇄가 완료를 나타내는 메시지 상자가 표시 됩니다.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
