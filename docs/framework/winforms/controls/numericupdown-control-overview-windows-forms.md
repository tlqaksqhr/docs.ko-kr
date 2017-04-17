---
title: "NumericUpDown 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "NumericUpDown"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "숫자 스핀 단추 컨트롤, Windows Forms"
  - "NumericUpDown 컨트롤[Windows Forms], NumericUpDown 컨트롤 정보"
  - "spin button 컨트롤, Windows Forms"
ms.assetid: cff3cf30-4d46-4381-87df-37bfe83c71c5
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# NumericUpDown 컨트롤 개요(Windows Forms)
<xref:System.Windows.Forms.NumericUpDown> 컨트롤은 텍스트 상자와 값을 조정하기 위해 클릭할 수 있는 한 쌍의 화살표가 결합된 것처럼 보입니다.  이 컨트롤은 고정 숫자 값 선택 목록에 있는 단일 숫자 값을 표시하거나 설정합니다.  사용자는 위로 이동 또는 아래로 이동 화살표를 클릭하거나, 위쪽 또는 아래쪽 화살표 키를 누르거나, 컨트롤의 텍스트 상자에 숫자를 입력하여 숫자를 증가 또는 감소시킬 수 있습니다.  위쪽 화살표 키를 클릭하여 최대값으로 이동하거나 아래쪽 화살표 키를 클릭하여 최소값으로 이동할 수 있습니다.  
  
 이 컨트롤은 여러 유용한 기능을 제공하므로 음악 플레이어 응용 프로그램의 볼륨 컨트롤을 만드는 경우에도 이 컨트롤을 사용하는 것이 좋습니다.  <xref:System.Windows.Forms.NumericUpDown> 컨트롤은 Windows 제어판 응용 프로그램에 많이 사용됩니다.  
  
## 주요 속성 및 메서드  
 숫자는 16진수를 포함하여 다양한 형식으로 컨트롤의 텍스트 상자에 표시될 수 있습니다.  자세한 내용은 [방법: Windows Forms NumericUpDown 컨트롤의 형식 설정](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)를 참조하십시오.  컨트롤의 주요 속성은 <xref:System.Windows.Forms.NumericUpDown.Value%2A>, <xref:System.Windows.Forms.NumericUpDown.Maximum%2A>\(기본값 100\), <xref:System.Windows.Forms.NumericUpDown.Minimum%2A>\(기본값 0\) 및 <xref:System.Windows.Forms.NumericUpDown.Increment%2A>\(기본값 1\)입니다.  <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성은 컨트롤에서 선택된 현재 숫자를 설정합니다.  <xref:System.Windows.Forms.NumericUpDown.Increment%2A> 속성은 사용자가 위로\/아래로 화살표를 클릭할 때 조정되는 숫자 값의 크기를 설정합니다.  포커스가 컨트롤 밖으로 이동하는 경우 입력된 모든 값의 유효성을 최대 숫자 값 및 최소 숫자 값과 비교하여 검사합니다.  사용자가 위쪽 또는 아래쪽 화살표를 계속 누르는 경우 <xref:System.Windows.Forms.NumericUpDown.Accelerations%2A> 속성을 사용하여 컨트롤이 숫자 사이에서 이동하는 속도를 높일 수 있습니다.  이 컨트롤의 주요 메서드는 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 및 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>입니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.NumericUpDown>   
 [NumericUpDown 컨트롤](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)   
 [방법: Windows Forms NumericUpDown 컨트롤의 형식 설정](../../../../docs/framework/winforms/controls/how-to-set-the-format-for-the-windows-forms-numericupdown-control.md)   
 [TextBox 컨트롤](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)