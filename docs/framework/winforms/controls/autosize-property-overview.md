---
title: "AutoSize 속성 개요 | Microsoft Docs"
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
  - "자동 크기 조정"
  - "AutoSize 속성"
  - "AutoSizeMode 속성"
  - "레이아웃[Windows Forms], AutoSize"
  - "크기 조정, 자동"
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# AutoSize 속성 개요
<xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 사용하면 컨트롤이 크기를 변경하고 필요한 경우 <xref:System.Windows.Forms.Control.PreferredSize%2A> 속성에 지정된 값을 사용하도록 할 수 있습니다.  `AutoSizeMode` 속성을 설정하여 특정 컨트롤의 크기 조정 동작을 조정합니다.  
  
## AutoSize 동작  
 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성은 일부 컨트롤에서만 지원되며  `AutoSizeMode` 속성은 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 지원하는 컨트롤 중 일부에서만 지원됩니다.  
  
 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성은 특정 컨트롤 형식과 `AutoSizeMode` 속성\(있는 경우\)의 값에 따라 조금씩 다르게 동작합니다.  다음 표에서는 항상 true인 동작을 보여 주고 각 동작에 대해 간략하게 설명합니다.  
  
|항상 true인 동작|설명|  
|-----------------|--------|  
|자동 크기 조정은 런타임 기능입니다.|즉, 컨트롤이 증가하거나 축소되지 않으므로 더 이상의 효과는 없습니다.|  
|컨트롤의 크기가 변경되더라도 <xref:System.Windows.Forms.Control.Location%2A> 속성 값은 항상 그대로 유지됩니다.|컨트롤의 내용이 증가하여 컨트롤이 늘어나는 경우 컨트롤은 오른쪽 및 아래쪽으로 늘어납니다.  컨트롤은 왼쪽으로는 늘어나지 않습니다.|  
|<xref:System.Windows.Forms.Control.Dock%2A> 및 <xref:System.Windows.Forms.Control.Anchor%2A> 속성은 <xref:System.Windows.Forms.Control.AutoSize%2A>가 `true`인 경우에 적용됩니다.|컨트롤의 <xref:System.Windows.Forms.Control.Location%2A> 속성 값이 올바른 값으로 조정됩니다.<br /><br /> **참고** <xref:System.Windows.Forms.Label> 컨트롤은 이 규칙의 예외입니다.  도킹된 <xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값을 `true`로 설정하면 <xref:System.Windows.Forms.Label> 컨트롤이 늘어나지 않습니다.|  
|컨트롤의 <xref:System.Windows.Forms.Control.MaximumSize%2A> 및 <xref:System.Windows.Forms.Control.MinimumSize%2A> 속성은 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 값에 관계없이 항상 적용됩니다.|<xref:System.Windows.Forms.Control.MaximumSize%2A> 및 <xref:System.Windows.Forms.Control.MinimumSize%2A> 속성은 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성의 영향을 받지 않습니다.|  
|기본적으로 최소 크기 설정은 없습니다.|즉, 컨트롤이 <xref:System.Windows.Forms.Control.AutoSize%2A> 이하로 축소되도록 설정되어 있고 컨트롤에 내용이 없으면 이 컨트롤의 <xref:System.Windows.Forms.Control.Size%2A> 속성 값은 0,0이 됩니다.  이 경우 컨트롤이 한 점으로 축소되므로 쉽게 알아볼 수 없습니다.|  
|컨트롤이 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 메서드를 구현하지 않는 경우 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 메서드는 <xref:System.Windows.Forms.Control.Size%2A> 속성에 할당된 마지막 값을 반환합니다.|즉, <xref:System.Windows.Forms.Control.AutoSize%2A>를 `true`로 설정하면 아무런 효과가 없습니다.|  
|<xref:System.Windows.Forms.TableLayoutPanel> 셀의 컨트롤은 <xref:System.Windows.Forms.Control.MinimumSize%2A>에 도달할 때까지 항상 셀에 맞게 축소됩니다.|이 크기가 최대 크기로 적용됩니다.  셀이 <xref:System.Windows.Forms.SizeType> 행 또는 열의 일부인 경우에는 해당되지 않습니다.|  
  
## AutoSizeMode 속성  
 `AutoSizeMode` 속성을 사용하면 기본 <xref:System.Windows.Forms.Control.AutoSize%2A> 동작을 더욱 세밀하게 제어할 수 있습니다.  `AutoSizeMode` 속성은 컨트롤의 크기가 내용에 맞게 자동으로 조정되는 방법을 지정합니다.  예를 들어, 내용이 <xref:System.Windows.Forms.Button> 컨트롤의 텍스트 또는 컨테이너의 자식 컨트롤일 수 있습니다.  
  
 다음 표에서는 <xref:System.Windows.Forms.AutoSizeMode> 설정 및 각 설정의 동작에 대해 설명합니다.  
  
|AutoSizeMode 설정|동작|  
|---------------------|--------|  
|GrowAndShrink|컨트롤이 내용에 맞게 늘어나거나 축소됩니다.<br /><br /> <xref:System.Windows.Forms.Control.MinimumSize%2A> 및 <xref:System.Windows.Forms.Control.MaximumSize%2A> 값은 적용되지만 <xref:System.Windows.Forms.Control.Size%2A> 속성의 현재 값은 무시됩니다.<br /><br /> 이는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성은 있고 `AutoSizeMode` 속성은 없는 컨트롤과 동일한 동작입니다.|  
|GrowOnly|컨트롤이 내용을 포함하는 데 필요한 만큼 늘어나지만 <xref:System.Windows.Forms.Control.Size%2A> 속성에 지정된 값보다 작게 축소되지는 않습니다.<br /><br /> `AutoSizeMode`의 기본값입니다.|  
  
## AutoSize 속성을 지원하는 컨트롤  
 다음 표에서는 <xref:System.Windows.Forms.Control.AutoSize%2A> 및 `AutoSizeMode` 속성을 지원하는 컨트롤을 보여 줍니다.  
  
|AutoSize 지원|컨트롤 형식|  
|-----------------|------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 지원하는 컨트롤<br />-   `AutoSizeMode` 속성이 없는 컨트롤|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox>\(<xref:System.Windows.Forms.TextBox> 기반\)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 지원하는 컨트롤<br />-   `AutoSizeMode` 속성을 지원하는 컨트롤|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 없는 컨트롤|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## 디자인 환경의 AutoSize  
 다음 표에서는 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 및 `AutoSizeMode` 속성 값을 기반으로 디자인 타임에 컨트롤의 크기 조정 동작에 대해 설명합니다.  
  
 지정된 컨트롤이 사용자가 크기를 조정할 수 있는 상태인지 확인하려면 <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> 속성을 재정의합니다.  다음 표에서 "cannot"은 <xref:System.Windows.Forms.Design.SelectionRules>만을 의미하고 "can"은 <xref:System.Windows.Forms.Design.SelectionRules> 및 <xref:System.Windows.Forms.Design.SelectionRules>을 의미합니다.  
  
|AutoSize 설정|디자인 타임 크기 조정 동작|  
|-----------------|---------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   `AutoSizeMode` 속성이 없는 컨트롤|사용자는 다음 컨트롤을 제외하고 디자인 타임에 컨트롤의 크기를 조정할 수 없습니다.<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   `AutoSizeMode` \= <xref:System.Windows.Forms.AutoSizeMode>|사용자는 디자인 타임에 컨트롤의 크기를 조정할 수 없습니다.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `true`<br />-   `AutoSizeMode` \= <xref:System.Windows.Forms.AutoSizeMode>|사용자는 디자인 타임에 컨트롤의 크기를 조정할 수 있습니다.  <xref:System.Windows.Forms.Control.Size%2A> 속성이 설정된 경우 사용자는 컨트롤의 크기를 늘일 수만 있습니다.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> \= `false` 또는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 숨겨진 경우|사용자는 디자인 타임에 컨트롤의 크기를 조정할 수 있습니다.|  
  
> [!NOTE]
>  생산성을 최대화할 수 있도록 Windows Forms 디자이너에서 <xref:System.Windows.Forms.Form> 클래스의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 숨깁니다.  폼은 디자인 타임에 실제 설정과 관계없이 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 `false`로 설정된 것처럼 동작합니다.  런타임에 특별한 조정 없이 속성 설정에서 지정된 대로 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 적용됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.Control.PreferredSize%2A>   
 <xref:System.Windows.Forms.Control.GetPreferredSize%2A>