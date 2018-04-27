---
title: '방법: Windows Forms MonthCalendar 컨트롤 변경&#39;s 모양'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6d2a3f12368d5215f7fe7611aa2f06e6b0fb1192
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-the-windows-forms-monthcalendar-control39s-appearance"></a>방법: Windows Forms MonthCalendar 컨트롤 변경&#39;s 모양
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤을 사용 하면 여러 가지 방법으로 달력의 모양을 사용자 지정할 수 있습니다. 예를 들어 색 구성표를 설정할 수 있으며 주 번호 및 현재 날짜를 표시 하거나 숨기려면 선택.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>월 달력 색 구성표를 변경 하려면  
  
-   와 같은 속성을 설정 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> 및 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>합니다. <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> 도 속성은 요일에 대 한 글꼴 색을 결정 합니다. <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 속성 앞과 뒤 표시 된 월 또는 개월 하는 날짜의 색을 결정 합니다.  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    >  Windows vista 및 테마에 따라 부터는 일부 속성을 설정 변경 되지 않는 달력 모양을 합니다. 예를 들어 Windows Aero 테마를 사용 하도록 설정 되어, 설정 된 <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, 또는 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 속성의 영향을 주지 않습니다. 즉, 달력의 업데이트 된 버전 실행 시 현재 운영 체제 테마에서 파생 된 모양으로 렌더링 됩니다. 이러한 속성을 사용 하 고 이전 버전의 달력을 사용 하도록 설정 하려는 경우에 응용 프로그램에 대 한 비주얼 스타일을 비활성화할 수 있습니다. 비주얼 스타일을 사용 하지 않도록 설정 하면 모양 및 동작의 응용 프로그램의 다른 컨트롤과 달라질 수 있습니다. Visual Basic의 비주얼 스타일을 사용 하지 않으려면 프로젝트 디자이너를 열고 및 선택 취소 된 **XP 시각적 스타일 사용** 확인란 합니다. C#에서 비주얼 스타일을 사용 하지 않으려면 Program.cs를 열고 주석으로 처리 `Application.EnableVisualStyles();`합니다. 비주얼 스타일에 대 한 자세한 내용은 참조 [하는 방법: Windows XP 시각적 스타일 사용](http://msdn.microsoft.com/library/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f)합니다.  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>컨트롤의 맨 아래에 현재 날짜를 표시 하려면  
  
-   <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 속성을 `true`으로 설정합니다. 다음 예제에서는 표시 하 고 폼을 두 번 클릭할 때 오늘 날짜를 생략 하는 것 사이 전환 합니다.  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     (Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>주 번호를 표시 하려면  
  
-   <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 속성을 `true`으로 설정합니다. 코드 또는 속성 창에서이 속성을 설정할 수 있습니다.  
  
     주 번호는 해당 주의 첫 번째 날의 왼쪽에 별도 열에 표시 합니다.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [MonthCalendar 컨트롤](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)  
 [방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)  
 [방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)  
 [방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)
