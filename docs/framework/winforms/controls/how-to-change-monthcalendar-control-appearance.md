---
title: "방법: Windows Forms MonthCalendar 컨트롤의 모양 변경 | Microsoft Docs"
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
  - "예제[Windows Forms], calendar 컨트롤"
  - "MonthBackColor 속성"
  - "MonthCalendar 컨트롤[Windows Forms], 표시 형식 지정"
  - "TitleBackColor 속성"
  - "TitleForeColor 속성"
  - "TrailingForeColor 속성"
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: Windows Forms MonthCalendar 컨트롤의 모양 변경
Windows Forms <xref:System.Windows.Forms.MonthCalendar> 컨트롤을 사용하여 달력 모양을 다양한 방식으로 사용자 지정할 수 있습니다.  예를 들어 색 구성표를 설정하고 주 번호 및 현재 날짜를 표시하거나 숨기도록 선택할 수 있습니다.  
  
### 달력의 색 구성표를 변경하려면  
  
-   <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> 및 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 같은 속성을 설정합니다.  또한 <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> 속성은 요일의 글꼴 색을 결정하고  <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 속성은 표시된 월의 이전 및 이후 월의 날짜 색을 결정합니다.  
  
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
    >  Windows Vista부터는 테마에 따라 일부 속성을 설정해도 달력의 모양이 변경되지 않을 수 있습니다.  예를 들어 Windows가 Aero 테마를 사용하도록 설정된 경우에는 <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> 또는 <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> 속성을 설정해도 아무 효과가 없습니다.  그 이유는 업데이트된 달력 버전이 현재 운영 체제 테마에서 런타임에 파생되는 모양을 사용하여 렌더링되기 때문입니다.  이러한 속성을 사용하고 이전 버전의 달력을 사용하도록 설정하려면 응용 프로그램의 비주얼 스타일을 사용하지 않도록 설정해야 합니다.  비주얼 스타일을 사용하지 않도록 설정하면 응용 프로그램에서 다른 컨트롤의 모양과 동작에 영향을 줄 수 있습니다.  Visual Basic에서 비주얼 스타일을 사용하지 않도록 설정하려면 프로젝트 디자이너를 열고 **XP 비주얼 스타일 사용** 확인란을 선택 취소합니다.  C\#에서 비주얼 스타일을 사용하지 않도록 설정하려면 Program.cs를 열고 `Application.EnableVisualStyles();`를 주석 처리합니다.  비주얼 스타일에 대한 자세한 내용은 [How to: Enable Windows XP Visual Styles](http://msdn.microsoft.com/ko-kr/0a038ade-31cf-4e56-9cfe-7a1e6b83b57f)을 참조하십시오.  
  
### 컨트롤의 아래쪽에 현재 날짜를 표시하려면  
  
-   <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> 속성을 `true`으로 설정합니다.  아래 예제에서는 폼을 두 번 클릭할 때마다 오늘 날짜의 표시\/생략 상태를 전환합니다.  
  
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
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### 주 번호를 표시하려면  
  
-   <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> 속성을 `true`으로 설정합니다.  속성 창을 사용하거나 코드를 통해 이 속성을 설정할 수 있습니다.  
  
     주 번호는 각 주의 첫째 요일 왼쪽에서 별도의 열에 표시됩니다.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## 참고 항목  
 [MonthCalendar 컨트롤](../../../../docs/framework/winforms/controls/monthcalendar-control-windows-forms.md)   
 [방법: Windows Forms MonthCalendar 컨트롤에서 날짜 범위 선택](../../../../docs/framework/winforms/controls/how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)   
 [방법: Windows Forms MonthCalendar 컨트롤을 사용하여 특정 날짜를 굵게 표시](../../../../docs/framework/winforms/controls/display-specific-days-in-bold-with-wf-monthcalendar-control.md)   
 [방법: Windows Forms MonthCalendar 컨트롤에서 여러 달 표시](../../../../docs/framework/winforms/controls/display-more-than-one-month-wf-monthcalendar-control.md)