---
title: "방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택 | Microsoft Docs"
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
  - "달력, 날짜 범위 선택"
  - "날짜, calendar 컨트롤에서 범위 선택"
  - "예제[Windows Forms], calendar 컨트롤"
  - "MonthCalendar 컨트롤[Windows Forms], 날짜 범위 선택"
ms.assetid: 95d9ab95-b0f8-4c19-9f63-b5cd4593a5d0
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤의 중요한 기능 중에는 사용자가 날짜 범위를 선택할 수 있는 기능이 있습니다.  이 기능은 사용자가 단일 날짜\/시간 값을 선택할 수 있는 <xref:System.Windows.Forms.DateTimePicker> 컨트롤의 날짜 선택 기능을 향상시킨 것입니다.  <xref:System.Windows.Forms.MonthCalendar> 컨트롤의 속성을 사용하면 사용자가 설정한 선택 범위를 가져오거나 날짜 범위를 설정할 수 있습니다.  다음 코드 예제에서는 선택 범위를 설정하는 방법을 보여 줍니다.  
  
### 날짜 범위를 선택하려면  
  
1.  범위의 첫 날짜와 마지막 날짜를 나타내는 <xref:System.DateTime> 개체를 만듭니다.  
  
    ```vb  
    Dim projectStart As Date = New DateTime(2001, 2, 13)  
    Dim projectEnd As Date = New DateTime(2001, 2, 28)  
    ```  
  
    ```csharp  
    DateTime projectStart = new DateTime(2001, 2, 13);  
    DateTime projectEnd = new DateTime(2001, 2, 28);  
    ```  
  
    ```cpp  
    DateTime projectStart = DateTime(2001, 2, 13);  
    DateTime projectEnd = DateTime(2001, 2, 28);  
    ```  
  
2.  <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> 속성을 설정합니다.  
  
    ```vb  
    MonthCalendar1.SelectionRange = New SelectionRange(projectStart, projectEnd)  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionRange = new SelectionRange(projectStart, projectEnd);  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionRange = gcnew  
       SelectionRange(projectStart, projectEnd);  
    ```  
  
     – 또는 –  
  
     <xref:System.Windows.Forms.MonthCalendar.SelectionStart%2A> 및 <xref:System.Windows.Forms.MonthCalendar.SelectionEnd%2A> 속성을 설정합니다.  
  
    ```vb  
    MonthCalendar1.SelectionStart = projectStart  
    MonthCalendar1.SelectionEnd = projectEnd  
    ```  
  
    ```csharp  
    monthCalendar1.SelectionStart = projectStart;  
    monthCalendar1.SelectionEnd = projectEnd;  
    ```  
  
    ```cpp  
    monthCalendar1->SelectionStart = projectStart;  
    monthCalendar1->SelectionEnd = projectEnd;  
    ```  
  
## 참고 항목  
 [MonthCalendar 컨트롤](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [방법: Windows Forms MonthCalendar 컨트롤의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)   
 [방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)   
 [방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)