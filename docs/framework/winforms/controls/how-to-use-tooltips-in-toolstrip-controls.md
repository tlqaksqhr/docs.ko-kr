---
title: "방법: ToolStrip 컨트롤의 도구 설명 사용 | Microsoft Docs"
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
  - "도구 모음[Windows Forms], 도구 설명 추가"
  - "ToolStrip 컨트롤[Windows Forms], 도구 설명 추가"
  - "도구 설명[Windows Forms], 추가"
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: ToolStrip 컨트롤의 도구 설명 사용
컨트롤의 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 속성을 `true`로 설정하여 원하는 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 대한 <xref:System.Windows.Forms.ToolTip>을 표시할 수 있습니다.  
  
### ToolTip을 표시하려면  
  
-   컨트롤의 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 속성을 `true`로 설정합니다.  
  
     <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=fullName>의 기본값은 `true`이고 <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=fullName> 및 <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=fullName>의 기본값은 `false`입니다.  
  
### ToolStripButton의 ToolTip 텍스트에 ToolTipText 속성을 사용하려면  
  
1.  단추의 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> 속성을 `true`로 설정합니다.  
  
2.  단추의 <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=fullName> 속성을 `false`로 설정합니다.  
  
     <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton> 및 <xref:System.Windows.Forms.ToolStripSplitButton>에 대한 `AutoToolTip` 속성의 기본값은 `true`입니다.  
  
     <xref:System.Windows.Forms.ToolStripButton>에서는 기본적으로 <xref:System.Windows.Forms.ToolTip> 텍스트에 `Text` 속성을 사용합니다.  이 절차에 따라 <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>에 사용자 지정 텍스트를 표시할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripItemDisplayStyle>을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle> 또는 <xref:System.Windows.Forms.ToolStripItemDisplayStyle>로 설정하면 단추에 텍스트가 표시되지 않고 도구 설명은 표시됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>   
 <xref:System.Windows.Forms.ToolStripButton>   
 <xref:System.Windows.Forms.ToolStripDropDownButton>   
 <xref:System.Windows.Forms.ToolStripSplitButton>   
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)