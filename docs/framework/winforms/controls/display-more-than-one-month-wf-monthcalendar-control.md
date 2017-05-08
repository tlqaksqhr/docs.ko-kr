---
title: "방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "달력, 표시 형식 지정"
  - "달력, 여러 달"
  - "예제[Windows Forms], calendar 컨트롤"
  - "MonthCalendar 컨트롤[Windows Forms], 표시 형식 지정"
ms.assetid: d197caa2-38a5-4cb4-acc3-562130c2ace3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤에는 최대 12개의 월을 한 번에 표시할 수 있습니다.  기본적으로 이 컨트롤에는 한 달만 표시되지만 표시되는 월 수와 컨트롤에서 월이 정렬되는 방식을 지정할 수 있습니다.  달력 크기를 변경하면 컨트롤 크기가 조정되므로 변경된 크기에 맞는 충분한 공간이 폼에 있어야 합니다.  
  
### 여러 월을 표시하려면  
  
-   <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> 속성에 가로 또는 세로로 표시할 월 수를 설정합니다.  
  
    ```vb  
    MonthCalendar1.CalendarDimensions = New System.Drawing.Size (3,2)  
  
    ```  
  
    ```csharp  
    monthCalendar1.CalendarDimensions = new System.Drawing.Size (3,2);  
  
    ```  
  
    ```cpp  
    monthCalendar1->CalendarDimensions = System::Drawing::Size (3,2);  
    ```  
  
## 참고 항목  
 [MonthCalendar 컨트롤](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [방법: Windows Forms MonthCalendar 컨트롤의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)