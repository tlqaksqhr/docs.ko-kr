---
title: '방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- calendars [Windows Forms], formatting display
- examples [Windows Forms], calendar controls
- calendars [Windows Forms], multiple months
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
ms.openlocfilehash: a71f85af2d51faf37160aba7fa89a8421b4523d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524875"
---
# <a name="how-to-display-more-than-one-month-in-the-windows-forms-monthcalendar-control"></a>방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤 12 개월까지 한 번에 표시할 수 있습니다. 기본적으로이 컨트롤은 한 달만 표시 되지만 몇 달 표시 되 고 컨트롤 내에서 정렬 되는 방식을 지정할 수 있습니다. 컨트롤의 크기 조정 달력 크기를 변경 하면 때문에 새 차원에 대 한 폼에 충분 한 공간이 해야 합니다.  
  
### <a name="to-display-multiple-months"></a>여러 달 표시 하려면  
  
-   설정의 <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 속성 가로 및 세로로 표시할 월의 수입니다.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [MonthCalendar 컨트롤](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [방법: Windows Forms MonthCalendar 컨트롤의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)
