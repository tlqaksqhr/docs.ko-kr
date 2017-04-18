---
title: "PrintPreviewDialog 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "PrintPreviewDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "PrintPreviewDialog 컨트롤(디자이너 사용), PrintPreviewDialog 정보"
ms.assetid: efd4ee8d-6edd-47ec-88e4-4a4759bd2384
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# PrintPreviewDialog 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)의 인쇄 모양을 미리 보는 데 사용하는 미리 구성된 대화 상자입니다.  사용자가 직접 대화 상자를 구성하는 대신 Windows 기반 응용 프로그램에 이 구성 요소를 간단한 솔루션으로 포함시켜 사용합니다.  이 컨트롤에는 인쇄, 확대, 단일 또는 여러 페이지 표시 및 대화 상자 닫기에 사용하는 단추가 포함되어 있습니다.  
  
## 주요 속성 및 메서드  
 이 컨트롤의 주요 속성인 <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A>에서는 미리 보기를 할 문서를 설정합니다.  문서는 <xref:System.Drawing.Printing.PrintDocument> 개체여야 합니다.  대화 상자를 표시하려면 <xref:System.Windows.Forms.Form.ShowDialog%2A> 메서드를 호출해야 합니다.  앤티 앨리어싱을 사용하면 텍스트가 더욱 부드럽게 표시되지만 표시 속도가 느려질 수 있습니다. 앤티 앨리어싱을 사용하려면 <xref:System.Windows.Forms.PrintPreviewDialog.UseAntiAlias%2A> 속성을 `true`로 설정합니다.  
  
 몇몇 속성은 <xref:System.Windows.Forms.PrintPreviewDialog>에 포함된 <xref:System.Windows.Forms.PrintPreviewControl>을 통해 사용할 수 있습니다.  <xref:System.Windows.Forms.PrintPreviewDialog>를 폼에 추가하면 <xref:System.Windows.Forms.PrintPreviewControl>도 자동으로 포함되므로 이 컨트롤을 폼에 따로 추가할 필요는 없습니다. <xref:System.Windows.Forms.PrintPreviewControl>을 통해 사용할 수 있는 속성으로는 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 및 <xref:System.Windows.Forms.PrintPreviewControl.Rows%2A> 속성이 있으며 이 속성은 컨트롤에 가로와 세로로 표시되는 페이지 수를 결정합니다.  [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]에서는 `PrintPreviewDialog1.PrintPreviewControl.Columns`로, [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]에서는 `printPreviewDialog1.PrintPreviewControl.Columns`로, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]에서는 `printPreviewDialog1->PrintPreviewControl->Columns`로 <xref:System.Windows.Forms.PrintPreviewControl.Columns%2A> 속성에 액세스할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.PrintPreviewDialog>   
 [PrintPreviewControl 컨트롤 개요](../../../../docs/framework/winforms/controls/printpreviewcontrol-control-overview-windows-forms.md)   
 [PrintPreviewDialog 컨트롤](../../../../docs/framework/winforms/controls/printpreviewdialog-control-windows-forms.md)   
 [대화 상자 컨트롤 및 구성 요소](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)