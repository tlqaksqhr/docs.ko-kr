---
title: "DateTimePicker 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DateTimePicker
helpviewer_keywords:
- DateTimePicker control [Windows Forms], about
- date and time picker controls
ms.assetid: 501af106-e9fc-4efc-b9b3-c9d8dcaf8c5c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0db5e532a2688d7f213fd42772234b9600192390
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="datetimepicker-control-overview-windows-forms"></a>DateTimePicker 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤 날짜 또는 시간 목록에서 단일 항목을 선택할 수 있습니다. 두 부분으로 표시 되는 날짜를 표시할 때: 텍스트와 목록 옆에서 아래쪽 화살표를 클릭할 때 표시 되는 모눈에 표시 된 날짜와 드롭 다운 목록입니다. 다음과 같은 눈금에서 <xref:System.Windows.Forms.MonthCalendar> 여러 날짜를 선택할 때 사용할 수 있는 컨트롤을 합니다. 대 한 자세한 내용은 <xref:System.Windows.Forms.MonthCalendar> 제어, 참조 [MonthCalendar 컨트롤 개요](../../../../docs/framework/winforms/controls/monthcalendar-control-overview-windows-forms.md)합니다.  
  
## <a name="key-properties"></a>키 속성  
 원하는 경우는 <xref:System.Windows.Forms.DateTimePicker> 설정의 컨트롤을 선택 하거나 편집 날짜 대신 시간을 표시는 <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> 속성을 `true` 및 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 <xref:System.Windows.Forms.DateTimePickerFormat.Time>합니다. 자세한 내용은 참조 [하는 방법: DateTimePicker 컨트롤에서 표시 시간](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md)합니다.  
  
 경우는 <xref:System.Windows.Forms.DateTimePicker.ShowCheckBox%2A> 속성이 `true`, 확인란 컨트롤에서 선택한 날짜 옆에 표시 됩니다. 확인란을 선택 하면 선택 된 날짜 및 시간 값을 업데이트할 수 있습니다. 확인란을 선택 하지 않으면 값이 사용할 수 없는 나타납니다.  
  
 컨트롤의 <xref:System.Windows.Forms.DateTimePicker.MaxDate%2A> 및 <xref:System.Windows.Forms.DateTimePicker.MinDate%2A> 속성의 날짜 및 시간 범위를 결정 합니다. <xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성 현재 날짜 및 컨트롤에 설정 된 시간을 포함 합니다. 자세한 내용은 참조 [하는 방법: 집합 및 Windows Forms DateTimePicker 컨트롤에서 날짜를 반환](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)합니다. 값으로 설정 되는 네 개의 형식으로 표시할 수 있습니다는 <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성: <xref:System.Windows.Forms.DateTimePickerFormat.Long>, <xref:System.Windows.Forms.DateTimePickerFormat.Short>, <xref:System.Windows.Forms.DateTimePickerFormat.Time>, 또는 <xref:System.Windows.Forms.DateTimePickerFormat.Custom>합니다. 사용자 지정 형식의 선택 하는 경우 설정 해야는 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 속성을 적절 한 문자열입니다. 자세한 내용은 참조 [하는 방법: Windows Forms DateTimePicker 컨트롤을 사용 하는 사용자 지정 형식에 날짜 표시](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)  
 [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
