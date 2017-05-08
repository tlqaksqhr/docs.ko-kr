---
title: "구성 요소 컨트롤 | Microsoft Docs"
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
  - "구성 요소 컨트롤"
  - "사용자 지정 컨트롤[Windows Forms], 구성 요소 컨트롤"
  - "사용자 정의 컨트롤[Windows Forms], 구성 요소 컨트롤"
  - "UserControl 클래스"
ms.assetid: 5565e720-198b-4bbd-a2bd-c447ba641798
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 구성 요소 컨트롤
사용자 정의 컨트롤을 구성하는 컨트롤, 즉 *구성 요소 컨트롤*은 사용자 지정 그래픽 렌더링을 수행할 때 사용 범위가 상대적으로 제한됩니다.  모든 Windows Forms 컨트롤은 자신의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 통해 자신의 렌더링을 처리합니다.  메서드는 protected로 선언되므로 개발자가 액세스할 수 없으며 따라서 컨트롤이 칠해질 때 실행되는 것을 막을 수 없습니다.  그러나 이런 이유로 구성 요소 컨트롤의 모양에 영향을 주는 코드를 추가할 수 없는 것은 아닙니다.  이벤트 처리기를 추가하면 추가적인 렌더링을 수행할 수 있습니다.  예를 들어 `MyButton`이라는 단추를 포함하는 <xref:System.Windows.Forms.UserControl>을 작성한다고 가정합니다.  [Button 클래스](frlrfSystemWebUIWebControlsButtonClassTopic)에서 제공되는 것 외에 추가적인 렌더링을 제공하려면 사용자 정의 컨트롤에 다음과 같은 코드를 추가합니다.  
  
```vb  
Public Sub MyPaint(ByVal sender as Object, e as PaintEventArgs) Handles _  
   MyButton.Paint  
   'Additional rendering code goes here  
End Sub  
  
```  
  
```csharp  
// Add the event handler to the button's Paint event.  
MyButton.Paint +=   
   new System.Windows.Forms.PaintEventHandler (this.MyPaint);  
// Create the custom painting method.  
protected void MyPaint (object sender,   
System.Windows.Forms.PaintEventArgs e)  
{  
   // Additional rendering code goes here.  
}  
```  
  
> [!NOTE]
>  <xref:System.Windows.Forms.TextBox>와 같은 일부 Windows Forms 컨트롤은 Windows에서 직접 칠합니다.  이러한 인스턴스에서는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드가 호출되지 않으므로 위의 예제는 호출되지 않습니다.  
  
 이 예제에서는 `MyButton.Paint` 이벤트가 실행될 때마다 호출되어 컨트롤에 그래픽 표현을 추가하는 메서드를 만듭니다.  여기에서는 `MyButton.OnPaint`가 실행되므로 사용자 지정 칠하기뿐만 아니라 일반적으로 단추를 통해 수행되는 모든 칠하기도 수행됩니다.  GDI\+ 기술과 사용자 지정 렌더링에 대한 자세한 내용은 [GDI\+를 사용하여 그래픽 이미지 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)를 참조하십시오.  컨트롤에 고유한 표현을 제공하려면 상속된 컨트롤을 만들고 이 컨트롤에 필요한 사용자 지정 렌더링 코드를 작성하는 것이 가장 좋습니다.  자세한 내용은 [사용자가 그린 컨트롤](../../../../docs/framework/winforms/controls/user-drawn-controls.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.UserControl>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [사용자가 그린 컨트롤](../../../../docs/framework/winforms/controls/user-drawn-controls.md)   
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)