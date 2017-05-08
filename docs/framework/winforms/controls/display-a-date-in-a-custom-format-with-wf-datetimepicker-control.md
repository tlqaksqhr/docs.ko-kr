---
title: "방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시 | Microsoft Docs"
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
  - "날짜, DateTimePicker 컨트롤에 표시"
  - "DateTimePicker 컨트롤[Windows Forms], 표시 스타일"
  - "예제[Windows Forms], DateTimePicker 컨트롤"
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시
Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤을 사용하면 컨트롤에 표시되는 날짜 및 시간 서식을 융통성 있게 지정할 수 있습니다.  <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 사용하면 <xref:System.Windows.Forms.DateTimePickerFormat>에 나열된 미리 정의된 서식 중에서 선택할 수 있습니다.  필요한 서식이 없을 경우에는 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>에 나열된 서식 문자를 사용하여 사용자 서식 스타일을 만들 수 있습니다.  
  
### 사용자 지정 서식을 표시하려면  
  
1.  <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 `DateTimePickerFormat.Custom`으로 설정합니다.  
  
2.  <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 속성을 형식 문자열로 설정합니다.  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### 서식이 지정된 값에 텍스트를 추가하려면  
  
1.  "M"과 같은 서식 문자나 ":"과 같은 구분 기호 이외의 문자는 작은따옴표로 묶습니다.  예를 들어, 영어\(미국\) 문화권에서 아래의 형식 문자열은 "Today is: 05:30:31 Friday March 02, 2012"의 형식으로 현재 날짜를 표시합니다.  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     문화권 설정에 따라 작은따옴표로 묶이지 않은 문자는 변경될 수 있습니다.  예를 들어, 영어\(미국\) 문화권에서 위의 형식 문자열은 "Today is: 05:30:31 Friday March 02, 2012"의 형식으로 현재 날짜를 표시합니다.  첫 번째 콜론은 "hh:mm:ss"에서처럼 구분 기호로 사용하기 위한 것이 아니므로 작은따옴표로 묶여 있습니다.  다른 문화권에서는 이 서식이 "Today is: 05.30.31 Friday March 02, 2012" 형식으로 나타날 수 있습니다.  
  
## 참고 항목  
 [DateTimePicker 컨트롤](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)   
 [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)