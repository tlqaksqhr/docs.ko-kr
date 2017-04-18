---
title: "DateTimePicker 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "DateTimePicker"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "날짜 및 시간 선택 컨트롤"
  - "DateTimePicker 컨트롤[Windows Forms], 정보"
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# DateTimePicker 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 사용하면 날짜 또는 시간 목록에서 하나의 항목을 선택할 수 있습니다.  이 컨트롤은 데이터를 표시할 때 두 부분으로 나타납니다. 텍스트로 날짜를 표시하는 드롭다운 목록 부분과 목록 옆에 있는 아래쪽 화살표를 클릭했을 때 나타나는 모눈 부분이 있습니다.  모눈은 날짜를 여러 개 선택할 때 사용할 수 있는 <xref:System.Windows.Forms.MonthCalendar> 컨트롤처럼 표시됩니다.  <xref:System.Windows.Forms.MonthCalendar> 컨트롤에 대한 자세한 내용은 [MonthCalendar 컨트롤 개요](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md)를 참조하십시오.  
  
## 키 속성  
 <xref:System.Windows.Forms.DateTimePicker>를 날짜 대신 시간을 선택하거나 편집하기 위한 컨트롤로 표시하려면 <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> 속성을 `true`로 설정하고 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 <xref:System.Windows.Forms.DateTimePickerFormat>으로 설정합니다.  자세한 내용은 [방법: DateTimePicker 컨트롤을 사용하여 시간 표시](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md)를 참조하십시오.  
  
 <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> 속성을 `true`로 설정하면 컨트롤에서 선택한 날짜 옆에 확인란이 표시됩니다.  확인란을 선택하면 선택한 날짜\/시간 값을 업데이트할 수 있습니다.  확인란을 선택하지 않으면 해당 값이 사용할 수 없는 것으로 표시됩니다.  
  
 이 컨트롤의 <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> 및 <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> 속성은 날짜와 시간 범위를 결정합니다.  <xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성에는 컨트롤에 설정되어 있는 현재 날짜 및 시간이 포함됩니다.  자세한 내용은 [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)를 참조하십시오.  값은 네 가지 형식으로 표시될 수 있으며, 이 형식은 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성인 <xref:System.Windows.Forms.DateTimePickerFormat>, <xref:System.Windows.Forms.DateTimePickerFormat>, <xref:System.Windows.Forms.DateTimePickerFormat> 또는 <xref:System.Windows.Forms.DateTimePickerFormat>을 통해 설정됩니다.  사용자 지정 형식을 선택한 경우에는 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 속성을 해당 문자열로 설정해야 합니다.  자세한 내용은 [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)를 참조하십시오.  
  
## 참고 항목  
 [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)   
 [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)