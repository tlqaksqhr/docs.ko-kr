---
title: "방법: PrintDialog 구성 요소 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "인쇄 대화 상자, 표시"
  - "PrintDialog 구성 요소[Windows Forms], 표시"
  - "인쇄[Windows Forms], 인쇄 대화 상자 표시"
ms.assetid: 745a8db7-0526-4b21-b09d-18e13ed32014
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: PrintDialog 구성 요소 표시
<xref:System.Windows.Forms.PrintDialog> 구성 요소는 많은 사용자들에게 친숙한 표준 Windows 인쇄 대화 상자입니다.  <xref:System.Windows.Forms.PrintDialog> 구성 요소는 사용자에게 매우 익숙하다는 장점이 있습니다.  
  
### PrintDialog 구성 요소를 표시하려면  
  
-   응용 프로그램 코드 안에서 <xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드를 호출합니다.  
  
     구성 요소가 일단 표시되면 이 구성 요소를 사용하여 대화식으로 인쇄 작업에 대한 속성을 설정할 수 있습니다.  이러한 속성은 해당 인쇄 작업에 연결된 [PrinterSettings](frlrfSystemDrawingPrintingPrinterSettingsMembersTopic) 클래스에 저장되며, 사용자가 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 통해 [PageSetupDialog 구성 요소](../../../../docs/framework/winforms/controls/pagesetupdialog-component-windows-forms.md)에 액세스하는 경우에는 [PageSettings](frlrfSystemDrawingPrintingPageSettingsMembersTopic) 클래스에도 저장됩니다.  그런 다음 이들이 설정한 속성을 호출하여 인쇄 작업에 관한 세부 사항을 결정할 수 있습니다.  
  
## 참고 항목  
 [방법: 표준 Windows Forms 인쇄 작업 만들기](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md)   
 [방법: 런타임에 PrintDialog에서 사용자 입력 캡처](../../../../docs/framework/winforms/advanced/how-to-capture-user-input-from-a-printdialog-at-run-time.md)   
 [PrintPreviewDialog 컨트롤](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [PrintDialog 구성 요소](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)   
 [Windows Forms 인쇄 지원](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)   
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)