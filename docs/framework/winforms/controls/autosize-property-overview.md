---
title: "AutoSize 속성 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c8216880ebdede03bbd01fe53b622c14ca8c514d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="autosize-property-overview"></a>AutoSize 속성 개요
<xref:System.Windows.Forms.Control.AutoSize%2A> 속성으로 지정 된 값을 사용 하기 위해 필요한 경우 크기를 변경 하는 컨트롤을 사용 하면는 <xref:System.Windows.Forms.Control.PreferredSize%2A> 속성입니다. 특정 컨트롤에 대 한 크기 조정 동작을 설정 하 여 조정 된 `AutoSizeMode` 속성입니다.  
  
## <a name="autosize-behavior"></a>AutoSize 동작  
 일부 컨트롤에만 지원는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다. 또한 일부 컨트롤을 지 원하는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성도 지원 합니다.는 `AutoSizeMode` 속성입니다.  
  
 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성의 값 및 특정 컨트롤 형식에 따라 다르게 동작을 생성 합니다.는 `AutoSizeMode` 속성이 있으면 속성입니다. 다음 표에서 항상 true 인 동작을 설명 하 고 각각에 대 한 간략 한 설명을 제공.  
  
|항상 true 동작|설명|  
|--------------------------|-----------------|  
|자동 크기 조정 런타임 기능입니다.|즉, 것 하지 증가 하거나 축소 하는 컨트롤 다음 영향을 주지 않습니다 추가 합니다.|  
|컨트롤의 값 크기를 변경 하는 경우 해당 <xref:System.Windows.Forms.Control.Location%2A> 속성은 항상 상수를 유지 합니다.|컨트롤의 내용이 너무 많아 증가 하 게 하면, 오른쪽으로 이동 하 고 아래로 컨트롤 증가 합니다. 컨트롤 왼쪽에 증가 하지 않습니다.|  
|<xref:System.Windows.Forms.Control.Dock%2A> 및 <xref:System.Windows.Forms.Control.Anchor%2A> 속성 경우에 적용 됩니다 <xref:System.Windows.Forms.Control.AutoSize%2A> 은 `true`합니다.|컨트롤의 값 <xref:System.Windows.Forms.Control.Location%2A> 속성을 올바른 값으로 조정 됩니다.<br /><br /> **참고** 는 <xref:System.Windows.Forms.Label> 컨트롤은이 규칙의 예외입니다. 도킹 된 값을 설정 하면 <xref:System.Windows.Forms.Label> 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`, <xref:System.Windows.Forms.Label> 컨트롤이 늘어나지 것입니다.|  
|컨트롤의 <xref:System.Windows.Forms.Control.MaximumSize%2A> 및 <xref:System.Windows.Forms.Control.MinimumSize%2A> 속성은 적용 항상의 값에 관계 없이 해당 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.|<xref:System.Windows.Forms.Control.MaximumSize%2A> 및 <xref:System.Windows.Forms.Control.MinimumSize%2A> 속성 영향을 받지 않습니다는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.|  
|기본적으로 설정 최소 크기가 없습니다.|즉, 컨트롤에서 축소로 설정 되어 있으면 <xref:System.Windows.Forms.Control.AutoSize%2A> 에 내용이, 값 및 해당 <xref:System.Windows.Forms.Control.Size%2A> 속성은 0, 0입니다. 이 경우 컨트롤은 지점으로 축소 하 고 즉시 표시 되지 않습니다.|  
|컨트롤을 구현 하지 않는 경우는 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 메서드는 <xref:System.Windows.Forms.Control.GetPreferredSize%2A> 에 할당 된 마지막 값을 반환 하는 메서드는 <xref:System.Windows.Forms.Control.Size%2A> 속성입니다.|즉, 해당 설정을 <xref:System.Windows.Forms.Control.AutoSize%2A> 를 `true` 아무런 효과가 없습니다.|  
|컨트롤에는 <xref:System.Windows.Forms.TableLayoutPanel> 셀 항상 축소 될 때까지 셀에 맞게 해당 <xref:System.Windows.Forms.Control.MinimumSize%2A> 에 도달 합니다.|이 크기는 최대 크기가 적용 됩니다. 이 경우가 아니라면 셀의 일부인 경우는 <xref:System.Windows.Forms.SizeType.AutoSize> 행 또는 열입니다.|  
  
## <a name="autosizemode-property"></a>AutoSizeMode 속성  
 `AutoSizeMode` 속성은 기본값 보다 세부적으로 제어를 제공 <xref:System.Windows.Forms.Control.AutoSize%2A> 동작 합니다. `AutoSizeMode` 방법을 컨트롤 크기가 자동으로 조정 내용에 맞게 속성을 지정 합니다. 콘텐츠를 예를 들어 수에 대 한 텍스트는 <xref:System.Windows.Forms.Button> 컨트롤이 나 컨테이너에 대 한 자식 컨트롤입니다.  
  
 다음 표는 <xref:System.Windows.Forms.AutoSizeMode> 설정 및 동작에 대 한 설명을 각 설정 이끌어 냅니다.  
  
|AutoSizeMode 설정|동작|  
|--------------------------|--------------|  
|GrowAndShrink|컨트롤 증가 속도 또는 내용을 포함을 축소 합니다.<br /><br /> <xref:System.Windows.Forms.Control.MinimumSize%2A> 및 <xref:System.Windows.Forms.Control.MaximumSize%2A> 의 현재 값을 제외한 값을 적용할는 <xref:System.Windows.Forms.Control.Size%2A> 속성은 무시 됩니다.<br /><br /> 이 동일한 동작을 사용 하 여 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 `AutoSizeMode` 속성입니다.|  
|GrowOnly|컨트롤 내용을 포함 하 여 필요에 따라 증가 하지만 지정 된 값 보다 작게 축소 되지는 것입니다 해당 <xref:System.Windows.Forms.Control.Size%2A> 속성입니다.<br /><br /> 이것이 `AutoSizeMode`의 기본값입니다.|  
  
## <a name="controls-that-support-the-autosize-property"></a>AutoSize 속성을 지 원하는 컨트롤을  
 다음 표에서 지 원하는 컨트롤의 <xref:System.Windows.Forms.Control.AutoSize%2A> 및 `AutoSizeMode` 속성입니다.  
  
|자동 크기 조정 지원|컨트롤 종류|  
|----------------------|------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A>지원 되는 속성입니다.<br />-더 `AutoSizeMode` 속성입니다.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox>(<xref:System.Windows.Forms.TextBox> 기본)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A>지원 되는 속성입니다.<br />-   `AutoSizeMode`지원 되는 속성입니다.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|  
|-더 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|  
  
## <a name="autosize-in-the-design-environment"></a>디자인 환경에서 자동 크기 조정  
 다음 표에서 컨트롤의 크기 조정 동작 디자인 타임에 값에 따라 해당 <xref:System.Windows.Forms.Control.AutoSize%2A> 및 `AutoSizeMode` 속성입니다.  
  
 재정의 <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> 속성을 제공 된 컨트롤의 사용자를 크기 조정 가능한 상태에 있는지 확인 합니다. 다음 표에 "없습니다" 의미 <xref:System.Windows.Forms.Design.SelectionRules.Moveable> 만 "수" 의미 <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> 및 <xref:System.Windows.Forms.Design.SelectionRules.Moveable>합니다.  
  
|자동 크기 조정 설정|디자인 타임 크기 조정 동작|  
|-----------------------|---------------------------------|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-더 `AutoSizeMode` 속성입니다.|사용자를 제외 하 고 다음과 같은 컨트롤의 디자인 타임에 컨트롤의 크기를 조정할 수 없습니다.<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|사용자는 디자인 타임에 컨트롤의 크기를 조정할 수 없습니다.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|사용자는 디자인 타임에 컨트롤의 크기를 조정할 수 있습니다. 경우는 <xref:System.Windows.Forms.Control.Size%2A> 속성이 설정 되어 있으면 사용자 컨트롤의 크기를 늘릴 수만 있습니다.|  
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`또는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 숨겨집니다.|사용자는 디자인 타임에 컨트롤의 크기를 조정할 수 있습니다.|  
  
> [!NOTE]
>  생산성, Windows Forms 디자이너 그림자를 최대화 하기 위해는 <xref:System.Windows.Forms.Control.AutoSize%2A> 에 대 한 속성의 <xref:System.Windows.Forms.Form> 클래스입니다. 디자인 타임에 폼 것 처럼 동작의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 `false`실제 설정과 관계 없이 합니다. 런타임 시 특별 한 조정 없이 설정 되 면 및 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성이 적용 되는지 속성 설정으로 지정 된 대로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.Control.PreferredSize%2A>  
 <xref:System.Windows.Forms.Control.GetPreferredSize%2A>
