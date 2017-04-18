---
title: "ToolTip 구성 요소 개요(Windows Forms) | Microsoft Docs"
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
  - "ToolTip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolTip 구성 요소[Windows Forms], ToolTip 구성 요소 정보"
  - "도구 설명[Windows Forms], 도구 설명 정보"
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# ToolTip 구성 요소 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ToolTip> 구성 요소는 사용자가 컨트롤을 가리키면 텍스트를 표시합니다.  도구 설명은 모든 컨트롤과 연결될 수 있습니다.  이 구성 요소의 사용 예로는 폼의 공간을 절약하기 위해 단추에 작은 아이콘을 표시하고 도구 설명을 사용하여 단추의 기능을 설명하는 경우를 들 수 있습니다.  
  
## ToolTip 구성 요소 작업  
 <xref:System.Windows.Forms.ToolTip> 구성 요소는 Windows Form이나 기타 컨테이너의 여러 컨트롤에 `ToolTip` 속성을 제공합니다.  예를 들어, 폼에 하나의 <xref:System.Windows.Forms.ToolTip> 구성 요소를 배치한 다음 <xref:System.Windows.Forms.TextBox> 컨트롤에 대해 "여기에 이름을 입력하십시오."를 표시하고 <xref:System.Windows.Forms.Button> 컨트롤에 대해 "변경 내용을 저장하려면 여기를 클릭하십시오."를 표시할 수 있습니다.  
  
 <xref:System.Windows.Forms.ToolTip> 구성 요소의 주요 메서드는 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 및 <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>입니다.  <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드를 사용하여 컨트롤에 표시할 도구 설명을 설정할 수 있습니다.  자세한 내용은 [방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)를 참조하십시오.  주요 속성은 <xref:System.Windows.Forms.ToolTip.Active%2A>\(도구 설명을 나타내려면 `true`로 설정해야 함\) 및 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>\(도구 설명 문자열이 표시되는 시간, 도구 설명 표시를 위해 컨트롤을 가리키고 있어야 하는 시간 및 이후의 도구 설명 창이 나타나는 데 걸리는 시간 설정\)입니다.  자세한 내용은 [방법: Windows Forms ToolTip 구성 요소의 지연 변경](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolTip>   
 [방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)   
 [방법: Windows Forms ToolTip 구성 요소의 지연 변경](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)