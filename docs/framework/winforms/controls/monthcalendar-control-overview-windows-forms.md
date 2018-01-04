---
title: "MonthCalendar 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a22667e4227067dfbf0baaad1838ab520e0ac7e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="monthcalendar-control-overview-windows-forms"></a>MonthCalendar 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤을 보고 설정할 날짜 정보는 사용자를 위한 직관적인 그래픽 인터페이스를 제공 합니다. 달력을 표시 하는 컨트롤: 선택한 범위를 강조 표시 하는 날짜, 요일 일 요일별으로 나열 된 해당 월의 번호가 매겨진된 날짜를 포함 하는 표입니다. 월 캡션 어느 한 쪽에 있는 화살표 단추를 클릭 하 여 다른 월을 선택할 수 있습니다. 달리 <xref:System.Windows.Forms.DateTimePicker> 컨트롤을이 컨트롤을 사용 하 여 둘 이상의 날짜를 선택할 수 있습니다. 에 대 한 자세한 내용은 <xref:System.Windows.Forms.DateTimePicker> 제어, 참조 [DateTimePicker 컨트롤](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)합니다.  
  
## <a name="configuring-the-monthcalendar-control"></a>MonthCalendar 컨트롤 구성  
 <xref:System.Windows.Forms.MonthCalendar> 컨트롤의 모양이 되 게 구성 합니다. 기본적으로 현재 날짜, 원이 표시 되 고 모눈의 맨 아래에 설명 되어 합니다. 이 기능을 설정 하 여 변경할 수 있습니다는 <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 및 <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> 속성을 `false`합니다. 설정 하 여 일정에 주 번호를 추가할 수도 있습니다는 <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 속성을 `true`합니다. 설정 하 여는 <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 속성을 표시 되는 월 가로 및 세로로 여러 개 있을 수 있습니다. 기본적으로 일요일 첫 번째 요일으로 표시 하지만 사용 하 여 임의의 날짜에 지정 될 수 있습니다는 <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> 속성입니다.  
  
 설정할 수도 있습니다에 표시할 특정 날짜를 한 번만, 매년 또는 매월 굵게 표시를 추가 하 여 <xref:System.DateTime> 개체는 <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A>, 및 <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 속성입니다. 자세한 내용은 참조 [하는 방법: Windows Forms MonthCalendar 컨트롤에서 굵게에서 표시 특정 일](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)합니다.  
  
 키 속성은 <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A>, 컨트롤에서 선택한 날짜 범위입니다. <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 값을 선택할 수에서 설정 하는 일 최대 수를 초과할 수 없습니다는 <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> 속성입니다. 선택할 수 있는 시작 및 완료 날짜에 따라 결정 됩니다는 <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> 및 <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MonthCalendar>  
 [MonthCalendar 컨트롤](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)
