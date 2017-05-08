---
title: "방법: 런타임에 PrintDialog에서 사용자 입력 캡처 | Microsoft Docs"
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
  - "인쇄 옵션"
  - "인쇄 옵션, 런타임에 변경"
  - "인쇄[Windows Forms], 옵션"
  - "런타임, 인쇄 옵션 변경"
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: 런타임에 PrintDialog에서 사용자 입력 캡처
디자인 타임에 인쇄와 관련된 옵션을 설정할 수 있지만 사용자가 선택한 내용으로 인해 런타임에 이러한 옵션을 변경하는 경우가 있습니다.  <xref:System.Windows.Forms.PrintDialog> 및 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하여 문서를 인쇄하기 위한 사용자 입력을 캡처할 수 있습니다.  
  
### 프로그래밍 방식으로 인쇄 옵션을 변경하려면  
  
1.  폼에 <xref:System.Windows.Forms.PrintDialog> 및 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 추가합니다.  
  
2.  <xref:System.Windows.Forms.PrintDialog>의 <xref:System.Windows.Forms.PrintDialog.Document%2A> 속성을 폼에 추가한 <xref:System.Drawing.Printing.PrintDocument>로 설정합니다.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 표시합니다.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  대화 상자에서 사용자가 선택한 인쇄 옵션이 <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 <xref:System.Drawing.Printing.PrinterSettings> 속성에 복사됩니다.  
  
## 참고 항목  
 [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)   
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)