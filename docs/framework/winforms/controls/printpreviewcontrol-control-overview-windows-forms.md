---
title: "PrintPreviewControl 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "PrintPreviewControl"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "인쇄 미리 보기"
  - "PrintPreviewControl 컨트롤"
ms.assetid: 4513c6c7-5e9b-4f4c-82ca-00f993a26955
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# PrintPreviewControl 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewControl>은 [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)의 인쇄 모양을 미리 보는 데 사용합니다.  이 컨트롤에는 단추나 기타 사용자 인터페이스 요소가 없기 때문에 대개 인쇄 미리 보기 사용자 인터페이스를 작성하는 경우에만 <xref:System.Windows.Forms.PrintPreviewControl>을 사용합니다.  표준 사용자 인터페이스를 사용하려면 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤을 사용합니다. 개요를 보려면 [PrintPreviewDialog 컨트롤 개요](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)를 참조하십시오.  
  
## 키 속성  
 이 컨트롤의 주요 속성인 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A>에서는 미리 보기를 할 문서를 설정합니다.  문서는 <xref:System.Drawing.Printing.PrintDocument> 개체여야 합니다.  인쇄할 문서 만들기에 대한 개요는 [PrintDocument 구성 요소 개요](../../../../docs/framework/winforms/controls/printdocument-component-overview-windows-forms.md) 및 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)을 참조하십시오.  <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 및 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 속성은 컨트롤에 가로와 세로로 표시되는 페이지 수를 결정합니다.  앤티 앨리어싱을 사용하면 텍스트가 더욱 부드럽게 표시되지만 표시 속도가 느려질 수 있습니다. 앤티 앨리어싱을 사용하려면 <xref:System.Windows.Forms.PrintPreviewControl.UseAntiAlias%2A> 속성을 `true`로 설정합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.PrintPreviewControl>   
 [PrintPreviewDialog 컨트롤 개요](../../../../docs/framework/winforms/controls/printpreviewdialog-control-overview-windows-forms.md)   
 [PrintPreviewControl 컨트롤](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-windows-forms.md)   
 [대화 상자 컨트롤 및 구성 요소](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)