---
title: "HScrollBar 및 VScrollBar 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "HScrollBar"
  - "VScrollBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "HScrollBar 컨트롤[Windows Forms], HScrollBar 정보"
  - "스크롤 막대, 스크롤 막대 정보"
  - "ScrollBar 컨트롤[Windows Forms]"
  - "ScrollBar 컨트롤[Windows Forms], ScrollBar 컨트롤 정보"
  - "VScrollBar 컨트롤[Windows Forms], VScrollBar 컨트롤 정보"
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# HScrollBar 및 VScrollBar 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.ScrollBar> 컨트롤은 응용 프로그램이나 컨트롤 내에서 가로 또는 세로로 스크롤하여 긴 항목 목록과 많은 양의 정보를 쉽게 탐색하는 데 사용됩니다.  스크롤 막대는 Windows 인터페이스의 공통 요소이므로 주로 <xref:System.Windows.Forms.ScrollableControl> 클래스에서 파생되지 않는 컨트롤과 함께 <xref:System.Windows.Forms.ScrollBar> 컨트롤이 사용됩니다.  마찬가지로 대부분의 개발자들은 고유의 사용자 정의 컨트롤을 만들 때 <xref:System.Windows.Forms.ScrollBar> 컨트롤을 포함합니다.  
  
 <xref:System.Windows.Forms.HScrollBar>\(가로\) 컨트롤과 <xref:System.Windows.Forms.VScrollBar>\(세로\) 컨트롤은 다른 컨트롤에 종속되지 않고 독립적으로 동작하며 고유의 이벤트, 속성 및 메서드 집합을 갖습니다.  <xref:System.Windows.Forms.ScrollBar> 컨트롤은 텍스트 상자, 목록 상자, 콤보 상자 또는 MDI 폼에 기본적으로 연결되는 스크롤 막대와는 다릅니다. 예를 들어 <xref:System.Windows.Forms.TextBox> 컨트롤에는 컨트롤에 연결된 스크롤 막대를 표시하거나 숨길 수 있는 <xref:System.Windows.Forms.TextBox.ScrollBars%2A> 속성이 있습니다.  
  
 <xref:System.Windows.Forms.ScrollBar> 컨트롤은 <xref:System.Windows.Forms.ScrollBar.Scroll> 이벤트를 사용하여 스크롤 막대에서 스크롤 상자\(엄지 단추\)의 이동을 모니터링합니다.  <xref:System.Windows.Forms.ScrollBar.Scroll> 이벤트를 사용하면 스크롤 막대를 끌 때 스크롤 막대의 값에 액세스할 수 있습니다.  
  
## Value 속성  
 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성의 값은 스크롤 막대에서 스크롤 상자의 위치를 나타내는 `integer` 값으로, 기본값은 0입니다.  스크롤 상자의 위치가 최소값인 경우, 스크롤 상자는 가로 스크롤 막대에서는 왼쪽 끝으로 이동하고 세로 스크롤 막대에서는 위쪽 끝으로 이동합니다.  스크롤 상자의 위치가 최대값이면 스크롤 상자가 오른쪽 끝이나 아래쪽 끝으로 이동합니다.  마찬가지로, 값이 아래쪽 끝과 위쪽 끝의 중간 범위에 있으면 스크롤 상자의 앞쪽 가장자리가 스크롤 막대의 중간에 위치합니다.  
  
 사용자는 마우스를 클릭하여 스크롤 막대의 값을 변경할 수 있을 뿐 아니라 스크롤 막대에서 원하는 위치로 스크롤 상자를 끌어올 수도 있습니다.  결과 값은 스크롤 상자의 위치에 따라 다르지만 항상 사용자가 설정한 <xref:System.Windows.Forms.ScrollBar.Minimum%2A> 속성과 <xref:System.Windows.Forms.ScrollBar.Maximum%2A> 속성의 범위 내에 있습니다.  
  
## LargeChange 및 SmallChange 속성  
 사용자가 Page Up 키 또는 Page Down 키를 누르거나 스크롤 막대 트랙에서 스크롤 상자의 한 쪽 가장자리를 클릭하면 <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> 속성에 설정된 값에 따라 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성이 변경됩니다.  
  
 사용자가 화살표 키 중 하나를 누르거나 스크롤 막대 단추 중 하나를 클릭하면 <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> 속성에 설정된 값에 따라 <xref:System.Windows.Forms.ScrollBar.Value%2A> 속성이 변경됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.HScrollBar>   
 <xref:System.Windows.Forms.VScrollBar>   
 [Additions to Windows Forms for the .NET Framework 2.0](http://msdn.microsoft.com/ko-kr/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)   
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)