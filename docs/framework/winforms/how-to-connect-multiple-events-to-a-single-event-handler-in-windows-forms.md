---
title: "방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "이벤트 처리기[Windows Forms], 이벤트 연결"
  - "이벤트[Windows Forms], 하나의 이벤트 처리기에 여러 이벤트 연결"
  - "메뉴 항목, 멀티캐스팅 이벤트 처리 메서드"
  - "메뉴, 여러 메뉴 항목에 대한 이벤트 처리 메서드"
  - "Windows Forms 컨트롤, 이벤트"
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결
응용 프로그램 디자인 과정에서 여러 이벤트에 단일 이벤트 처리기를 사용하거나 여러 이벤트에서 같은 프로시저를 수행해야 하는 경우가 있습니다.  예를 들어 폼의 단추와 메뉴 명령이 같은 기능을 구현하는 경우 메뉴 명령에서 폼의 단추와 동일한 이벤트를 발생시키도록 하면 시간이 훨씬 절약될 수 있습니다.  C\#에서 속성 창의 이벤트 뷰를 사용하거나 Visual Basic 코드 편집기에서 `Handles` 키워드와 **클래스 이름** 및 **메서드 이름** 드롭다운 상자를 사용하여 이 작업을 수행할 수 있습니다.  
  
### Visual Basic에서 여러 이벤트를 단일 이벤트 처리기에 연결하려면  
  
1.  폼을 마우스 오른쪽 단추로 클릭한 다음 **코드 보기**를 선택합니다.  
  
2.  **클래스 이름** 드롭다운 상자에서 이벤트 처리기로 처리할 컨트롤 하나를 선택합니다.  
  
3.  **메서드 이름** 드롭다운 상자에서 이벤트 처리기로 처리할 이벤트 하나를 선택합니다.  
  
4.  코드 편집기에서 적절한 이벤트 처리기가 삽입되고 삽입 지점은 메서드 안에 위치합니다.  아래 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 보여 줍니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  처리할 다른 이벤트를 `Handles` 절에 추가합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  이벤트 처리기에 적절한 코드를 추가합니다.  
  
### C\#에서 여러 이벤트를 단일 이벤트 처리기에 연결하려면  
  
1.  이벤트 처리기를 연결할 컨트롤을 선택합니다.  
  
2.  속성 창에서 **이벤트** 단추\(![이벤트 단추](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton\_PropertiesWindow")\)를 클릭합니다.  
  
3.  처리할 이벤트 이름을 클릭합니다.  
  
4.  이벤트 이름 옆의 값 영역에서 드롭다운 단추를 클릭하여 처리할 이벤트의 메서드 시그니처과 일치하는 기존의 이벤트 처리기 목록을 표시합니다.  
  
5.  목록에서 적절한 이벤트 처리기를 선택합니다.  
  
     기존의 이벤트 처리기에 이벤트를 바인딩하는 코드가 폼에 추가됩니다.  
  
## 참고 항목  
 [Windows Forms에서 이벤트 처리기 만들기](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [이벤트 처리기 개요](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)