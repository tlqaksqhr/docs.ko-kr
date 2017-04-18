---
title: "방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시 | Microsoft Docs"
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
  - "달력, 날짜를 굵게 표시"
  - "예제[Windows Forms], calendar 컨트롤"
  - "GetDayBold 이벤트"
  - "MonthCalendar 컨트롤[Windows Forms], 굵게 표시된 날짜"
ms.assetid: 8b20db5b-8118-4825-90e8-2c45c186ac7d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤은 특정 날짜를 한 번 또는 반복적으로 굵게 표시할 수 있습니다.  공휴일이나 주말 같은 특정 날짜를 강조하려는 경우에도 이 기능을 사용합니다.  
  
 세 가지 속성을 사용하여 이 기능을 제어할 수 있습니다.  <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> 속성에는 단일 날짜가 포함되고  <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> 속성에는 매년 굵게 표시되는 날짜가 포함됩니다.  또한 <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> 속성에는 매월 굵게 표시되는 날짜가 포함됩니다.  각 속성에는 <xref:System.DateTime> 개체 배열이 포함됩니다.  이러한 목록에서 날짜를 추가 또는 제거하려면 <xref:System.DateTime> 개체를 추가하거나 제거해야 합니다.  
  
### 날짜를 굵게 표시하려면  
  
1.  <xref:System.DateTime> 개체를 만듭니다.  
  
    ```vb  
    Dim myVacation1 As Date = New DateTime(2001, 6, 10)  
    Dim myVacation2 As Date = New DateTime(2001, 6, 17)  
  
    ```  
  
    ```csharp  
    DateTime myVacation1 = new DateTime(2001, 6, 10);  
    DateTime myVacation2 = new DateTime(2001, 6, 17);  
  
    ```  
  
    ```cpp  
    DateTime myVacation1 = DateTime(2001, 6, 10);  
    DateTime myVacation2 = DateTime(2001, 6, 17);  
    ```  
  
2.  <xref:System.Windows.Forms.MonthCalendar> 컨트롤의 <xref:System.Windows.Forms.MonthCalendar.AddBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.AddAnnuallyBoldedDate%2A> 또는 <xref:System.Windows.Forms.MonthCalendar.AddMonthlyBoldedDate%2A> 메서드를 호출하여 단일 날짜를 굵게 표시합니다.  
  
    ```vb  
    MonthCalendar1.AddBoldedDate(myVacation1)  
    MonthCalendar1.AddBoldedDate(myVacation2)  
  
    ```  
  
    ```csharp  
    monthCalendar1.AddBoldedDate(myVacation1);  
    monthCalendar1.AddBoldedDate(myVacation2);  
  
    ```  
  
    ```cpp  
    monthCalendar1->AddBoldedDate(myVacation1);  
    monthCalendar1->AddBoldedDate(myVacation2);  
    ```  
  
     – 또는 –  
  
     여러 날짜를 한 번에 굵게 표시하려면 <xref:System.DateTime> 개체 배열을 만든 다음 이러한 속성 중 하나에 할당합니다.  
  
    ```vb  
    Dim VacationDates As DateTime() = {myVacation1, myVacation2}  
    MonthCalendar1.BoldedDates = VacationDates  
  
    ```  
  
    ```csharp  
    DateTime[] VacationDates = {myVacation1, myVacation2};  
    monthCalendar1.BoldedDates = VacationDates;  
  
    ```  
  
    ```cpp  
    Array<DateTime>^ VacationDates = {myVacation1, myVacation2};  
    monthCalendar1->BoldedDates = VacationDates;  
    ```  
  
### 날짜를 보통 글꼴로 표시하려면  
  
1.  <xref:System.Windows.Forms.MonthCalendar.RemoveBoldedDate%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAnnuallyBoldedDate%2A> 또는 <xref:System.Windows.Forms.MonthCalendar.RemoveMonthlyBoldedDate%2A> 메서드를 호출하여 굵게 표시된 단일 날짜를 보통 글꼴로 표시합니다.  
  
    ```vb  
    MonthCalendar1.RemoveBoldedDate(myVacation1)  
    MonthCalendar1.RemoveBoldedDate(myVacation2)  
  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveBoldedDate(myVacation1);  
    monthCalendar1.RemoveBoldedDate(myVacation2);  
  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveBoldedDate(myVacation1);  
    monthCalendar1->RemoveBoldedDate(myVacation2);  
    ```  
  
     – 또는 –  
  
     <xref:System.Windows.Forms.MonthCalendar.RemoveAllBoldedDates%2A>, <xref:System.Windows.Forms.MonthCalendar.RemoveAllAnnuallyBoldedDates%2A> 또는 <xref:System.Windows.Forms.MonthCalendar.RemoveAllMonthlyBoldedDates%2A> 메서드를 호출하여 세 목록 중 한 목록에서 굵게 표시된 모든 날짜를 제거합니다.  
  
    ```vb  
    MonthCalendar1.RemoveAllBoldedDates()  
  
    ```  
  
    ```csharp  
    monthCalendar1.RemoveAllBoldedDates();  
  
    ```  
  
    ```cpp  
    monthCalendar1->RemoveAllBoldedDates();  
    ```  
  
2.  <xref:System.Windows.Forms.MonthCalendar.UpdateBoldedDates%2A> 메서드를 호출하여 글꼴 모양을 업데이트합니다.  
  
    ```vb  
    MonthCalendar1.UpdateBoldedDates()  
  
    ```  
  
    ```csharp  
    monthCalendar1.UpdateBoldedDates();  
  
    ```  
  
    ```cpp  
    monthCalendar1->UpdateBoldedDates();  
    ```  
  
## 참고 항목  
 [MonthCalendar 컨트롤](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [방법: Windows Forms MonthCalendar 컨트롤의 모양 변경](../../../../docs/framework/winforms/controls/how-to-change-monthcalendar-control-appearance.md)   
 [방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)