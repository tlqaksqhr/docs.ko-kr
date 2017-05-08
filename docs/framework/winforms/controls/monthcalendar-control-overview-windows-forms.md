---
title: "MonthCalendar 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "MonthCalendar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "calendar 컨트롤, Windows Forms"
  - "달력, Windows Forms 컨트롤"
  - "MonthCalendar 컨트롤[Windows Forms], 주의 첫째 요일 설정"
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# MonthCalendar 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 날짜 정보를 보고 설정할 수 있는 직관적인 그래픽 인터페이스를 제공합니다.  이 컨트롤은 날짜가 요일별로 나열된 표 형태의 달력을 표시하며 선택된 범위의 날짜는 강조 표시됩니다.  월 캡션의 양쪽에 있는 화살표 단추를 클릭하여 다른 월을 선택할 수 있습니다.  <xref:System.Windows.Forms.DateTimePicker> 컨트롤과 달리 이 컨트롤에서는 날짜를 두 개 이상 선택할 수 있습니다.  <xref:System.Windows.Forms.DateTimePicker> 컨트롤에 대한 자세한 내용은 [DateTimePicker 컨트롤](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)를 참조하십시오.  
  
## MonthCalendar 컨트롤 구성  
 <xref:System.Windows.Forms.MonthCalendar> 컨트롤의 모양을 매우 다양하게 구성할 수 있습니다.  기본적으로 오늘 날짜에는 원이 표시되고 표 아래쪽에도 오늘 날짜가 별도로 표기됩니다.  <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 및 <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> 속성을 `false`로 설정하여 이 기능을 변경할 수 있습니다.  <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 속성을 `true`로 설정하면 달력에 주 번호를 추가할 수도 있습니다.  <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 속성을 설정하면 가로나 세로 방향으로 여러 달을 표시할 수 있습니다.  기본적으로 일요일이 첫 번째 요일로 표시되지만 <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> 속성을 사용하여 다른 요일을 지정할 수 있습니다.  
  
 <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> 및 <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 속성에 <xref:System.DateTime> 개체를 추가하면 특정 날짜를 한 번만, 매년 또는 매월 굵게 표시할 수 있습니다.  자세한 내용은 [방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)를 참조하십시오.  
  
 <xref:System.Windows.Forms.MonthCalendar> 컨트롤의 주요 속성은 컨트롤에서 날짜 범위를 선택할 수 있는 <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>입니다.  <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 값은 <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> 속성에 설정된 선택 가능 날짜의 최대 수를 초과할 수 없습니다.  사용자가 선택할 수 있는 처음 날짜와 마지막 날짜는 <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> 및 <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> 속성으로 결정됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.MonthCalendar>   
 [MonthCalendar 컨트롤](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)