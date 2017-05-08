---
title: "방법: 런타임에 Windows Forms의 이벤트 처리기 만들기 | Microsoft Docs"
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
  - "Button 컨트롤[Windows Forms], 이벤트 처리기"
  - "이벤트 처리기, 만들기"
  - "예제[Windows Forms], 이벤트 처리"
  - "런타임, 이벤트 처리기 만들기"
  - "Windows Forms, 이벤트 처리"
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 런타임에 Windows Forms의 이벤트 처리기 만들기
Windows Forms 디자이너를 사용하여 이벤트를 만들 수 있을 뿐만 아니라 런타임에 이벤트 처리기를 만들 수도 있습니다.  이렇게 하면 프로그램이 처음 시작될 때 이벤트 처리기를 연결하는 대신 런타임에 코드를 사용하여 조건에 따라 이벤트 처리기를 연결할 수 있습니다.  
  
### 런타임에 이벤트 처리기를 만들려면  
  
1.  코드 편집기에서 이벤트 처리기를 추가할 폼을 엽니다.  
  
2.  처리할 이벤트의 메서드 시그니처가 있는 폼에 메서드를 추가합니다.  
  
     예를 들어 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리하는 경우 다음과 같은 메서드가 만들어집니다.  
  
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
  
3.  이벤트 처리기에 응용 프로그램에 적합한 코드를 추가합니다.  
  
4.  이벤트 처리기를 만들 폼이나 컨트롤을 결정합니다.  
  
5.  폼의 클래스에 있는 메서드에서 이벤트를 처리할 이벤트 처리기를 지정하는 코드를 추가합니다.  예를 들어 다음 코드에서는 `button1_Click` 이벤트 처리기가 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리하도록 지정합니다.  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     위의 Visual Basic 코드 예제에서 <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> 메서드는 단추의 클릭 이벤트 처리기를 만듭니다.  
  
## 참고 항목  
 [Windows Forms에서 이벤트 처리기 만들기](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [이벤트 처리기 개요](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)   
 [Troubleshooting Inherited Event Handlers in Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)