---
title: "Windows Forms 인쇄 지원 | Microsoft Docs"
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
  - "폼, 인쇄(디자이너 사용)"
  - "인쇄[Windows Forms]"
  - "인쇄[Windows Forms], 인쇄 지원"
  - "인쇄, Windows Forms, 지원"
  - "Windows Forms, 인쇄"
ms.assetid: a4a2960c-eb70-48e2-b641-cfb222704e46
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms 인쇄 지원
Windows Forms에서는 주로 사용자의 인쇄 작업을 가능하게 하는 [PrintDocument 구성 요소](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) 구성 요소와 Windows 운영 체제에 익숙해진 사용자에게 친숙한 그래픽 인터페이스를 제공하는 [PrintPreviewDialog 컨트롤](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md) 컨트롤, [PrintDialog 구성 요소](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) 및 [PageSetupDialog 구성 요소](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md) 구성 요소를 통해 인쇄 작업이 수행됩니다.  
  
 일반적으로 <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 새 인스턴스를 만들고, <xref:System.Drawing.Printing.PrinterSettings> 및 <xref:System.Drawing.Printing.PageSettings> 클래스를 사용하여 인쇄할 내용을 설명하는 속성을 설정하며, <xref:System.Drawing.Printing.PrintDocument.Print%2A> 메서드를 호출하여 실제 문서를 인쇄합니다.  
  
 Windows 기반 응용 프로그램에서 인쇄하는 동안 <xref:System.Drawing.Printing.PrintDocument> 구성 요소는 사용자에게 인쇄 중임을 알리고 인쇄 작업을 취소할 수 있도록 인쇄 중단 대화 상자를 표시합니다.  
  
## 단원 내용  
 [방법: 표준 Windows Forms 인쇄 작업 만들기](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)  
 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용하여 Windows Form에서 인쇄하는 방법을 설명합니다.  
  
 [방법: 런타임에 PrintDialog에서 사용자 입력 캡처](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)  
 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 사용하여 프로그래밍 방식으로 선택한 인쇄 옵션을 수정하는 방법을 설명합니다.  
  
 [방법: Windows Forms에서 사용자의 컴퓨터에 연결된 프린터 선택](../../../../docs/framework/winforms/advanced/how-to-choose-the-printers-attached-to-user-computer-in-windows-forms.md)  
 런타임에 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 사용하여 인쇄할 프린터를 변경하는 방법을 설명합니다.  
  
 [방법: Windows Forms의 그래픽 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)  
 프린터에 그래픽을 보내는 방법을 설명합니다.  
  
 [방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)  
 프린터에 텍스트를 보내는 방법을 설명합니다.  
  
 [방법: Windows Forms 인쇄 작업 완료](../../../../docs/framework/winforms/advanced/how-to-complete-windows-forms-print-jobs.md)  
 사용자에게 인쇄 작업이 완료되었음을 알리는 방법을 설명합니다.  
  
 [방법: Windows Form 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-a-windows-form.md)  
 현재 폼의 복사본을 인쇄하는 방법을 보여 줍니다.  
  
 [방법: Windows Forms에서 인쇄 미리 보기를 사용하여 인쇄](../../../../docs/framework/winforms/advanced/how-to-print-in-windows-forms-using-print-preview.md)  
 <xref:System.Windows.Forms.PrintPreviewDialog>를 사용하여 문서를 인쇄하는 방법을 보여 줍니다.  
  
## 관련 단원  
 [PrintDocument 구성 요소](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)  
 <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 사용법을 설명합니다.  
  
 [PrintDialog 구성 요소](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)  
 <xref:System.Windows.Forms.PrintDialog> 구성 요소의 사용법을 설명합니다.  
  
 [PrintPreviewDialog 컨트롤](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)  
 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 사용법을 설명합니다.  
  
 [PageSetupDialog 구성 요소](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)  
 <xref:System.Windows.Forms.PageSetupDialog> 구성 요소의 사용법을 설명합니다.  
  
 <xref:System.Drawing.Printing>  
 <xref:System.Drawing.Printing> 네임스페이스의 클래스를 설명합니다.