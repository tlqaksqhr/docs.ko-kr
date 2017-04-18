---
title: "PrintDocument 구성 요소 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PrintDocument"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "PrintDocument 구성 요소[Windows Forms], PrintDocument 구성 요소 정보"
  - "인쇄[Windows Forms], PrintDocument 구성 요소"
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# PrintDocument 구성 요소 개요(Windows Forms)
Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) 구성 요소는 Windows 기반 응용 프로그램에서 인쇄할 내용을 설명하는 속성을 설정한 다음 문서를 인쇄하는 데 사용됩니다.  이 구성 요소를 [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) 구성 요소와 함께 사용하면 문서 인쇄에 관련된 모든 측면을 제어할 수 있습니다.  
  
## PrintDocument 구성 요소 작업  
 <xref:System.Drawing.Printing.PrintDocument> 구성 요소와 관련된 두 가지 주요 시나리오는 다음과 같습니다.  
  
-   개별 텍스트 파일의 인쇄와 같은 단순 인쇄 작업.  이 경우 Windows Form에 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 추가한 다음 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기에 파일을 인쇄하는 프로그래밍 논리를 추가합니다.  프로그래밍 논리는 문서를 인쇄하는 <xref:System.Drawing.Printing.PrintDocument.Print%2A> 메서드로 끝나야 합니다.  이 메서드는 <xref:System.Drawing.Printing.PrintPageEventArgs> 클래스의 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 속성에 포함된 <xref:System.Drawing.Graphics> 개체를 프린터로 보냅니다.  <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하여 텍스트 문서를 인쇄하는 방법에 대한 예제를 보려면 [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)를 참조하십시오.  
  
-   작성한 인쇄 논리를 다시 사용하려는 경우과 같은 복잡한 인쇄 작업.  이 경우 <xref:System.Drawing.Printing.PrintDocument> 구성 요소에서 새 구성 요소를 파생시키고 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 재정의합니다\(Visual Basic의 경우[Overrides](../Topic/Overrides%20\(Visual%20Basic\).md), C\#의 경우 [override](../Topic/override%20\(C%23%20Reference\).md) 참조\).  
  
 <xref:System.Drawing.Printing.PrintDocument> 구성 요소가 폼에 추가되면 Windows Forms 디자이너의 아래쪽에 있는 트레이에 나타납니다.  
  
## 참고 항목  
 <xref:System.Drawing.Graphics>   
 <xref:System.Drawing.Printing.PrintDocument>   
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [PrintDocument 구성 요소](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)