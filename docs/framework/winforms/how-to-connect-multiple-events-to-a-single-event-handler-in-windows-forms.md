---
title: "방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4aa22b011b895a20cefdcc5a7c9e6c1cd0531923
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결
응용 프로그램 디자인에서 있습니다 경우가 여러 이벤트에 대 한 단일 이벤트 처리기를 사용 하거나 동일한 절차를 수행 하는 여러 개의 이벤트가 포함 합니다. 예를 들어 것이 강력한 시간을 절약할에 메뉴 명령을 폼의 단추를 구현 하는 경우 동일한 기능으로 같은 이벤트를 발생 시킵니다. 사용 하거나 속성 창에 C#의 이벤트 보기를 사용 하 여이 작업을 수행할 수는 `Handles` 키워드 및 **클래스 이름** 및 **메서드 이름** Visual Basic 코드 편집기에서 드롭다운 상자입니다.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Visual Basic에서 단일 이벤트 처리기에 여러 이벤트 연결 하려면  
  
1.  폼을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다.  
  
2.  **클래스 이름** 드롭다운 목록 상자에서 처리할 이벤트 처리기를 컨트롤 중 하나를 선택 합니다.  
  
3.  **메서드 이름** 드롭다운 목록 상자에서 이벤트를 처리할 이벤트 처리기를 중 하나를 선택 합니다.  
  
4.  코드 편집기는 적절 한 이벤트 처리기를 삽입 하 고 메서드 내에서 삽입 포인터를 놓습니다. 아래 예제에서는 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트는 <xref:System.Windows.Forms.Button> 제어 합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  다른 처리 하는 이벤트 선택에 추가 하는 `Handles` 절.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  이벤트 처리기에 적절 한 코드를 추가 합니다.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>C#에서 단일 이벤트 처리기에 여러 이벤트 연결 하려면  
  
1.  이벤트 처리기를 연결 하려면 컨트롤을 선택 합니다.  
  
2.  속성 창에서 클릭 된 **이벤트** 단추 (![이벤트 단추](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3.  처리할 이벤트의 이름을 클릭 합니다.  
  
4.  이벤트 이름 옆에 있는 값 섹션을 처리 하려면 이벤트의 메서드 시그니처를 일치 하는 기존 이벤트 처리기의 목록을 표시 하려면 드롭다운 단추를 클릭 합니다.  
  
5.  목록에서 적절 한 이벤트 처리기를 선택 합니다.  
  
     코드에서 기존 이벤트 처리기에 이벤트를 바인딩할 폼에 추가 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms에서 이벤트 처리기 만들기](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [이벤트 처리기 개요](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
