---
title: "방법: Windows Forms 단추 클릭에 응답"
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
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 923eb7d1b1b5b442ce897619253a958019b239a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>방법: Windows Forms 단추 클릭에 응답
Windows Forms의 가장 기본적인 사용법 <xref:System.Windows.Forms.Button> 컨트롤에서 단추를 클릭할 때 일부 코드를 실행 하는 것입니다.  
  
 클릭 하는 <xref:System.Windows.Forms.Button> 제어도 생성 된 수의 다른 이벤트와 같은 <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, 및 <xref:System.Windows.Forms.Control.MouseUp> 이벤트입니다. 이러한 관련된 이벤트에 대 한 이벤트 처리기를 연결 하려는 경우 수의 동작이 충돌 하지 않습니다. 예를 들어 경우 단추를 클릭 하는 사용자가 텍스트 상자에 입력 한 정보를 단추 위로 마우스 포인터를 일시 중지 해야 하지 표시 지워지는 정보를 포함 하는 도구 설명을 합니다.  
  
 사용자가을 두 번 클릭 하는 경우는 <xref:System.Windows.Forms.Button> 컨트롤을 클릭할 때마다은 별도로 처리 됩니다; 즉, 컨트롤이 두 번 클릭 이벤트 지원 하지 않습니다.  
  
### <a name="to-respond-to-a-button-click"></a>단추 클릭에 응답 하려면  
  
-   단추의 `Click` <xref:System.EventHandler> 실행 하는 코드를 작성 합니다. `Button1_Click`컨트롤에 바인딩해야 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms에 대 한 시간 실행에서 이벤트 처리기 만들기](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)합니다.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
