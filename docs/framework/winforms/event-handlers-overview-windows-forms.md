---
title: "이벤트 처리기 개요(Windows Forms) | Microsoft Docs"
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
  - "이벤트 처리기, 이벤트 처리기 정보"
  - "이벤트 처리, Windows Forms"
  - "Windows Forms, 이벤트 처리"
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 이벤트 처리기 개요(Windows Forms)
이벤트 처리기는 이벤트에 바인딩되는 메서드입니다.  이벤트가 발생하면 이벤트 처리기의 코드가 실행됩니다.  각 이벤트 처리기는 이벤트를 적절히 처리할 수 있도록 두 개의 매개 변수를 제공합니다.  다음 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 보여 줍니다.  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 첫 번째 매개 변수인`sender`는 이벤트를 발생시키는 개체에 대한 참조를 제공합니다.  위의 예제에서 두 번째 매개 변수인 `e`는 처리 중인 이벤트에 특정한 개체를 전달합니다.  개체의 속성 또는 경우에 따라 개체의 메서드를 참조하면 마우스 이벤트의 마우스 위치나 끌어서 놓기 이벤트에서 전송 중인 데이터와 같은 정보를 가져올 수 있습니다.  
  
 일반적으로 각 이벤트는 두 번째 매개 변수에 대해 다른 이벤트 개체 형식을 가진 이벤트 처리기를 만듭니다.  <xref:System.Windows.Forms.Control.MouseDown> 및 <xref:System.Windows.Forms.Control.MouseUp> 이벤트의 이벤트 처리기와 같은 일부 이벤트 처리기는 두 번째 매개 변수에 대해 같은 개체 형식을 사용합니다.  이러한 이벤트의 경우 동일한 이벤트 처리기를 사용하여 두 개의 이벤트를 모두 처리할 수 있습니다.  
  
 또한 동일한 이벤트 처리기를 사용하여 다른 컨트롤의 같은 이벤트를 처리할 수 있습니다.  예를 들어 폼에 <xref:System.Windows.Forms.RadioButton> 컨트롤 그룹이 있는 경우 <xref:System.Windows.Forms.Control.Click> 이벤트에 대해 단일 이벤트 처리기를 만들고 각 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트가 이 이벤트 처리기에 바인딩되도록 설정할 수 있습니다.  자세한 내용은 [방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)을 참조하십시오.  
  
## 참고 항목  
 [Windows Forms에서 이벤트 처리기 만들기](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [이벤트 개요](../../../docs/framework/winforms/events-overview-windows-forms.md)