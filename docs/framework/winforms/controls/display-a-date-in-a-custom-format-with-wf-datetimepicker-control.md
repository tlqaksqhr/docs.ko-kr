---
title: "방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b92fec7565aad2a881f714f9232eae10bf7633c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a>방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시
Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤의 컨트롤에서 날짜와 시간 표시를 서식 지정에 유연성을 제공 합니다. <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성에 나열 된 미리 정의 된 형식에서 선택할 수 있습니다는 <xref:System.Windows.Forms.DateTimePickerFormat>합니다. 아무것도 용도 맞게 충분 않으면에 나열 된 형식 문자를 사용 하 여 사용자 고유의 형식 스타일을 만들 수 있습니다 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>합니다.  
  
### <a name="to-display-a-custom-format"></a>사용자 지정 형식을 표시 하려면  
  
1.  <xref:System.Windows.Forms.DateTimePicker.Format%2A> 속성을 `DateTimePickerFormat.Custom`으로 설정합니다.  
  
2.  설정의 <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> 서식 문자열에는 속성입니다.  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a>형식이 지정 된 값에 텍스트를 추가 하려면  
  
1.  "M"과 같은 형식 문자 또는 같은 구분 기호가 아닌 모든 문자를 포함 하려면 작은따옴표를 사용 하 여 ":". 아래의 형식 문자열 형식으로 현재 날짜를 표시 하는 예를 들어 "임: 05시 30분: 31 2012 년 3 월 2 일 금요일" 영어 (미국) 문화권입니다.  
  
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
  
     문화권 설정에 따라 따옴표로 묶이지 않은 문자를 변경할 수 있습니다. 위의 형식 문자열 형식으로 현재 날짜를 표시 하는 예를 들어 "임: 05시 30분: 31 2012 년 3 월 2 일 금요일" 영어 (미국) 문화권입니다. 참고 것이 아니기 때문에 "hh: mm:"에서 같이 구분 기호 문자를 첫 번째 콜론 단일 따옴표에 포함 되어 있습니다. 다른 문화권이 형식으로 나타날 수 있습니다 "임: 2012 년 3 월 2 일 금요일 05.30.31"입니다.  
  
## <a name="see-also"></a>참고 항목  
 [DateTimePicker 컨트롤](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
