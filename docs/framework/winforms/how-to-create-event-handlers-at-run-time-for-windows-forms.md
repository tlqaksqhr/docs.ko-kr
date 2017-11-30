---
title: "방법: 런타임에 Windows Forms의 이벤트 처리기 만들기"
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
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 53664bcf8c776338399297687a16ec430bca128b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>방법: 런타임에 Windows Forms의 이벤트 처리기 만들기
Windows Forms 디자이너를 사용하여 이벤트를 만들 수 있을 뿐만 아니라 런타임에 이벤트 처리기를 만들 수도 있습니다. 이렇게 하면 프로그램이 처음 시작될 때 이벤트 처리기를 연결하는 대신 런타임에 코드를 사용하여 조건에 따라 이벤트 처리기를 연결할 수 있습니다.  
  
### <a name="to-create-an-event-handler-at-run-time"></a>런타임에 이벤트 처리기를 만들려면  
  
1.  이벤트 처리기를 추가할 양식을 코드 편집기에서 엽니다.  
  
2.  처리할 이벤트의 메서드 시그니처가 있는 양식에 메서드를 추가합니다.  
  
     예를 들어 처리 하는 경우는 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 <xref:System.Windows.Forms.Button> 컨트롤을 만들면 됩니다 다음과 같은 메서드:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  응용 프로그램에 적합한 코드를 이벤트 처리기에 추가합니다.  
  
4.  이벤트 처리기를 만들 양식 또는 컨트롤을 결정합니다.  
  
5.  양식의 클래스에 있는 메서드에 이벤트를 처리할 이벤트 처리기를 지정하는 코드를 추가합니다. 다음 코드에서는 이벤트 처리기를 지정 하는 예를 들어 `button1_Click` 핸들의 <xref:System.Windows.Forms.Control.Click> 의 이벤트는 <xref:System.Windows.Forms.Button> 제어:  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> 위의 Visual Basic 코드에서 보여 주는 메서드 단추의 click 이벤트 처리기를 설정 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms에서 이벤트 처리기 만들기](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [이벤트 처리기 개요](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 [Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
