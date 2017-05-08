---
title: "Calendar | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Calendar 컨트롤[WPF]"
  - "컨트롤[WPF], Calendar"
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Calendar
달력을 사용하면 사용자가 시각적으로 표시된 달력에서 날짜를 선택할 수 있습니다.  
  
 <xref:System.Windows.Controls.Calendar> 컨트롤은 단독으로 사용하거나 <xref:System.Windows.Controls.DatePicker> 컨트롤의 드롭다운 부분으로 사용할 수 있습니다.  자세한 내용은 <xref:System.Windows.Controls.DatePicker>를 참조하십시오.  
  
 다음 그림에서는 두 개의 <xref:System.Windows.Controls.Calendar> 컨트롤을 보여 줍니다. 하나는 선택 사항과 블랙아웃 날짜가 있고 다른 하나는 이러한 항목이 없습니다.  
  
 ![달력 컨트롤](../../../../docs/framework/wpf/controls/media/ndp-calendarcontrols.png "NDP\_CalendarControls")  
Calendar 컨트롤  
  
 다음 표에서는 일반적으로 <xref:System.Windows.Controls.Calendar>와 관련된 작업에 대한 정보를 제공합니다.  
  
|Task|구현|  
|----------|--------|  
|선택할 수 없는 날짜를 지정합니다.|<xref:System.Windows.Controls.Calendar.BlackoutDates%2A> 속성을 사용합니다.|  
|<xref:System.Windows.Controls.Calendar>가 월, 전체 연도 또는 10년을 표시하도록 합니다.|<xref:System.Windows.Controls.Calendar.DisplayMode%2A> 속성을 월, 년, 10년으로 설정합니다.|  
|사용자가 날짜, 날짜 범위, 또는 여러 날짜 범위를 선택할 수 있는지 여부를 지정합니다.|<xref:System.Windows.Controls.Calendar.SelectionMode%2A>를 사용합니다.|  
|<xref:System.Windows.Controls.Calendar>가 표시하는 날짜의 범위를 지정합니다.|<xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> 및 <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A> 속성을 사용합니다.|  
|현재 날짜를 강조 표시할지 여부를 지정합니다.|<xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> 속성을 사용합니다.  <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>의 기본값은 `true`입니다.|  
|<xref:System.Windows.Controls.Calendar>의 크기를 변경합니다.|<xref:System.Windows.Controls.Viewbox>를 사용하거나 <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 속성을 <xref:System.Windows.Media.ScaleTransform>으로 설정합니다.  <xref:System.Windows.Controls.Calendar>의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 설정하면 실제 달력의 크기는 변경되지 않습니다.|  
  
 <xref:System.Windows.Controls.Calendar> 컨트롤은 마우스 또는 키보드를 사용하는 기본 탐색을 제공합니다.  다음 표에서는 키보드 탐색을 요약하여 보여 줍니다.  
  
|키 조합|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|동작|  
|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|--------|  
|위쪽 화살표|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.SelectionMode%2A> 속성이 <xref:System.Windows.Controls.CalendarSelectionMode>로 설정되지 않은 경우 <xref:System.Windows.Controls.Calendar.SelectedDate%2A> 속성을 변경합니다.|  
|위쪽 화살표|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A> 속성의 월을 변경합니다.  <xref:System.Windows.Controls.Calendar.SelectedDate%2A>는 변경되지 않습니다.|  
|위쪽 화살표|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A>의 연도를 변경합니다.  <xref:System.Windows.Controls.Calendar.SelectedDate%2A>는 변경되지 않습니다.|  
|Shift\+위쪽 화살표|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.SelectionMode%2A>가 <xref:System.Windows.Controls.CalendarSelectionMode> 또는 <xref:System.Windows.Controls.CalendarSelectionMode>으로 설정되지 않은 경우 선택한 날짜 범위를 확장합니다.|  
|Home|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.SelectedDate%2A>를 현재 월의 첫 일자로 변경합니다.|  
|Home|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A>의 월을 해당 연도의 첫 달로 변경합니다.  <xref:System.Windows.Controls.Calendar.SelectedDate%2A>는 변경되지 않습니다.|  
|Home|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A>의 연도를 해당 연대의 첫 연도로 변경합니다.  <xref:System.Windows.Controls.Calendar.SelectedDate%2A>는 변경되지 않습니다.|  
|End|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.SelectedDate%2A>를 현재 월의 마지막 일자로 변경합니다.|  
|End|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A>의 월을 해당 연도의 마지막 달로 변경합니다.  <xref:System.Windows.Controls.Calendar.SelectedDate%2A>는 변경되지 않습니다.|  
|End|<xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.DisplayDate%2A>의 연도를 해당 연대의 마지막 연도로 변경합니다.  <xref:System.Windows.Controls.Calendar.SelectedDate%2A>는 변경되지 않습니다.|  
|Ctrl\+위쪽 화살표|임의|다음으로 큰 <xref:System.Windows.Controls.Calendar.DisplayMode%2A>로 전환합니다.  <xref:System.Windows.Controls.Calendar.DisplayMode%2A>가 이미 <xref:System.Windows.Controls.CalendarMode>인 경우 아무 작업도 수행되지 않습니다.|  
|\<Ctrl\+아래쪽 화살표\>|임의|다음으로 작은 <xref:System.Windows.Controls.Calendar.DisplayMode%2A>로 전환합니다.  <xref:System.Windows.Controls.Calendar.DisplayMode%2A>가 이미 <xref:System.Windows.Controls.CalendarMode>인 경우 아무 작업도 수행되지 않습니다.|  
|스페이스바 또는 Enter|<xref:System.Windows.Controls.CalendarMode> 또는 <xref:System.Windows.Controls.CalendarMode>|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>를 포커스가 있는 항목이 나타내는 <xref:System.Windows.Controls.CalendarMode> 또는 <xref:System.Windows.Controls.CalendarMode>로 전환합니다.|  
  
## 참고 항목  
 [컨트롤](../../../../docs/framework/wpf/controls/index.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)