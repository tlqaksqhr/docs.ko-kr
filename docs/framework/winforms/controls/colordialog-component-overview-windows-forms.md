---
title: "ColorDialog 구성 요소 개요(Windows Forms) | Microsoft Docs"
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
  - "ColorDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "색 대화 상자, 색 대화 상자 정보"
  - "ColorDialog 구성 요소, ColorDialog 정보"
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# ColorDialog 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ColorDialog> 구성 요소는 사용자가 색상표에서 색을 선택할 수 있고 색상표에 사용자 지정 색을 추가할 수 있는 미리 구성된 대화 상자입니다.  이 구성 요소는 다른 Windows 기반 응용 프로그램에서 색을 선택하는 데 사용하는 대화 상자와 같습니다.  사용자가 직접 대화 상자를 구성하는 대신 Windows 기반 응용 프로그램에 이 구성 요소를 간단한 솔루션으로 포함하여 사용합니다.  
  
 대화 상자에서 선택한 색은 <xref:System.Windows.Forms.ColorDialog.Color%2A> 속성에 반환됩니다.  <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 속성을 `false`로 설정하면 "사용자 지정 색 만들기" 단추를 사용할 수 없으며 사용자는 색상표에 미리 정의된 색만 사용할 수 있습니다.  <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 속성을 `true`로 설정하면 사용자는 디더링된 색을 선택할 수 없습니다.  이 대화 상자를 표시하려면 해당 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 호출해야 합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ColorDialog>   
 [ColorDialog 구성 요소](../../../../docs/framework/winforms/controls/colordialog-component-windows-forms.md)   
 [대화 상자 컨트롤 및 구성 요소](../../../../docs/framework/winforms/controls/dialog-box-controls-and-components-windows-forms.md)   
 [방법: Windows Forms ColorDialog 구성 요소의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)