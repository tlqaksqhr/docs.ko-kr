---
title: "PrintDialog 구성 요소 개요(Windows Forms) | Microsoft Docs"
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
  - "PrintDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "인쇄 대화 상자, 표시"
  - "PrintDialog 구성 요소[Windows Forms], PrintDialog 구성 요소 정보"
ms.assetid: 8327b8ac-1017-4b5e-a88b-fea9dd56999c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# PrintDialog 구성 요소 개요(Windows Forms)
Windows Forms [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) 구성 요소는 Windows 기반 응용 프로그램에서 프린터를 선택하거나, 인쇄할 페이지를 선택하거나, 기타 인쇄 관련 설정을 결정하는 데 사용되는 미리 구성된 대화 상자입니다.  직접 대화 상자를 구성하는 대신 이 구성 요소를 간단한 솔루션으로 사용하여 프린터 및 인쇄 관련 설정을 선택합니다.  모두 인쇄, 선택 페이지 인쇄, 선택 영역 인쇄 등 문서의 인쇄 범위를 다양하게 지정할 수 있습니다.  표준 Windows 대화 상자를 사용하여 사용자가 기본 기능을 쉽게 이해할 수 있는 응용 프로그램을 만들 수 있습니다.  <xref:System.Windows.Forms.CommonDialog> 클래스에서 <xref:System.Windows.Forms.PrintDialog> 구성 요소가 상속됩니다.  
  
## 구성 요소 작업  
 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 런타임에 대화 상자를 표시합니다.  이 구성 요소에는 단일 인쇄 작업\(<xref:System.Drawing.Printing.PrintDocument> 클래스\) 또는 개별 프린터 설정\(<xref:System.Drawing.Printing.PrinterSettings> 클래스\)과 관련된 속성이 포함되어 있습니다.  이러한 속성은 여러 프린터에서 공유할 수 있습니다.  
  
 <xref:System.Windows.Forms.PrintDialog> 구성 요소가 폼에 추가되면 Windows Forms 디자이너의 아래쪽에 있는 트레이에 나타납니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.PrintDialog>   
 [PrintDialog 구성 요소](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md)