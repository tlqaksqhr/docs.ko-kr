---
title: "방법: Windows Forms 단추 클릭에 응답 | Microsoft Docs"
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
  - "Button 컨트롤[Windows Forms], click 응답"
  - "단추, Click 이벤트에 응답"
  - "Click 이벤트, Button 컨트롤"
  - "Click 이벤트, 응답"
  - "두 번 클릭"
  - "이벤트[Windows Forms], Click 이벤트"
  - "예제[Windows Forms], 컨트롤"
  - "MouseDown 이벤트"
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms 단추 클릭에 응답
Windows Forms <xref:System.Windows.Forms.Button> 컨트롤의 가장 기본적인 용도는 단추가 클릭될 경우 해당 코드를 실행하는 것입니다.  
  
 <xref:System.Windows.Forms.Button> 컨트롤을 클릭하면 <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown> 및 <xref:System.Windows.Forms.Control.MouseUp> 이벤트와 같은 여러 가지 이벤트도 생성됩니다.  이러한 관련 이벤트에 이벤트 처리기를 연결하려면 각 이벤트의 동작이 충돌하지 않아야 합니다.  예를 들어, 단추를 클릭하면 텍스트 상자에 입력한 정보가 지워지는 경우에는 단추 위로 마우스를 가져가도 이미 지워진 정보의 도구 설명이 표시되지 않아야 합니다.  
  
 <xref:System.Windows.Forms.Button> 컨트롤을 두 번 클릭하는 경우 각 클릭은 별도로 처리됩니다. 즉, 해당 컨트롤은 두 번 클릭 이벤트를 지원하지 않습니다.  
  
### 단추 클릭에 응답하려면  
  
-   실행할 코드를 단추의`Click` <xref:System.EventHandler>에서 작성합니다.  `Button1_Click`은 해당 컨트롤에 바인딩되어야 합니다.  자세한 내용은 [방법: 런타임에 Windows Forms의 이벤트 처리기 만들기](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)을 참조하십시오.  
  
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
  
    ```cpp#  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## 참고 항목  
 [Button 컨트롤 개요](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)