---
title: "DatePicker | Microsoft Docs"
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
  - "컨트롤[WPF], DatePicker"
  - "DatePicker 컨트롤[WPF]"
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# DatePicker
<xref:System.Windows.Controls.DatePicker> 컨트롤을 사용하면 사용자가 텍스트 필드에 날짜를 입력하거나 드롭다운 <xref:System.Windows.Controls.Calendar> 컨트롤을 통해 날짜를 선택할 수 있습니다.  
  
 다음 그림에서는 <xref:System.Windows.Controls.DatePicker>을 보여 줍니다.  
  
 ![DatePicker 컨트롤](../../../../docs/framework/wpf/controls/media/ndp-datepicker.png "NDP\_DatePicker")  
DatePicker 컨트롤  
  
 <xref:System.Windows.Controls.DatePicker> 컨트롤의 속성 중 다수는 기본 제공 <xref:System.Windows.Controls.Calendar>를 관리하기 위한 것이며, <xref:System.Windows.Controls.Calendar>에 있는 동등한 속성과 동일하게 작동합니다.  특히 <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=fullName>, <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=fullName> 및 <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=fullName> 속성은 <xref:System.Windows.Controls.Calendar>의 상응하는 속성과 동일하게 작동합니다.  자세한 내용은 <xref:System.Windows.Controls.Calendar>를 참조하십시오.  
  
 사용자는 <xref:System.Windows.Controls.DatePicker.Text%2A> 속성을 설정하는 텍스트 필드에 날짜를 직접 입력할 수 있습니다.  <xref:System.Windows.Controls.DatePicker>가 입력된 문자열을 유효한 날짜로 변환할 수 없는 경우에는 <xref:System.Windows.Controls.DatePicker.DateValidationError> 이벤트가 발생됩니다.  기본적으로 이는 예외를 발생시키지만 <xref:System.Windows.Controls.DatePicker.DateValidationError>의 이벤트 처리기가 <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> 속성을 `false`로 설정하고 예외 발생을 방지할 수 있습니다.  
  
## 참고 항목  
 [컨트롤](../../../../docs/framework/wpf/controls/index.md)   
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)