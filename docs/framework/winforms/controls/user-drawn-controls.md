---
title: "사용자가 그린 컨트롤 | Microsoft Docs"
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
  - "사용자 지정 컨트롤[Windows Forms], 사용자가 그림"
  - "OnPaint 메서드[Windows Forms]"
  - "사용자 그리기 컨트롤[Windows Forms]"
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 사용자가 그린 컨트롤
.NET Framework를 사용하면 고유한 컨트롤을 쉽게 개발할 수 있습니다.  코드에 의해 함께 바인딩된 표준 컨트롤의 집합인 사용자 정의 컨트롤을 만들거나 고유한 컨트롤을 처음부터 디자인할 수 있습니다.  또한 상속을 사용하여 기존 컨트롤에서 상속한 컨트롤을 만들어 해당 컨트롤의 고유 기능에 추가할 수 있습니다.  어떤 방법을 사용하든 .NET Framework에서는 만드는 모든 컨트롤에 대해 사용자 지정 그래픽 인터페이스를 그릴 수 있습니다.  
  
 컨트롤 칠하기는 컨트롤의 <xref:System.Windows.Forms.Control.OnPaint%2A>에 있는 코드의 실행을 통해 수행됩니다.  <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드의 인수는 컨트롤을 렌더링하는 데 필요한 모든 정보와 기능을 제공하는 <xref:System.Windows.Forms.PaintEventArgs> 개체뿐입니다.  <xref:System.Windows.Forms.PaintEventArgs>는 다음과 같이 컨트롤을 렌더링하는 데 사용되는 두 개의 기본 개체를 속성으로 제공합니다.  
  
-   <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 개체 – 그려지는 컨트롤의 부분을 나타내는 사각형.  컨트롤이 그려지는 방법에 따라 컨트롤 전체가 될 수도 있고 컨트롤의 일부가 될 수도 있습니다.  
  
-   <xref:System.Drawing.Graphics> 개체 \- 컨트롤을 그리는 데 필요한 기능을 제공하는 여러 그래픽 지향 개체와 메서드를 캡슐화합니다.  
  
 <xref:System.Drawing.Graphics> 개체에 대한 설명 및 개체 사용 방법에 대한 자세한 내용은 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)를 참조하십시오.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트는 화면에서 컨트롤을 그리거나 새로 고칠 때마다 발생하고 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 개체는 그리기 작업을 수행할 사각형을 나타냅니다.  전체 컨트롤을 새로 고쳐야 할 경우 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>은 전체 컨트롤의 크기를 나타냅니다.  그러나 컨트롤의 일부만 새로 고쳐야 하는 경우 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 개체는 다시 그려야 할 영역만 나타냅니다.  예를 들면 사용자 인터페이스에서 컨트롤이 다른 컨트롤이나 폼에 의해 부분적으로 가려져 있는 경우입니다.  
  
 <xref:System.Windows.Forms.Control> 클래스에서 상속하는 경우 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하고 메서드 내에 그래픽 렌더링 코드를 추가해야 합니다.  사용자 정의 컨트롤이나 상속된 컨트롤에 사용자 지정 그래픽 인터페이스를 제공할 경우에도 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하면 됩니다.  예제는 아래와 같습니다.  
  
```vb  
Protected Overrides Sub OnPaint(ByVal pe As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(pe)  
  
   ' Declare and instantiate a drawing pen.  
   Dim myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
  
   ' Draw an aqua rectangle in the rectangle represented by the control.  
   pe.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
End Sub  
  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs pe)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(pe);  
  
   // Declare and instantiate a new pen.  
   System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua);  
  
   // Draw an aqua rectangle in the rectangle represented by the control.  
   pe.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
      this.Size));  
}  
  
```  
  
 위의 예제는 매우 간단한 그래픽 표현을 사용하여 컨트롤을 렌더링하는 방법을 설명합니다.  이 예제에서는 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출하고, 그리는 데 사용할 <xref:System.Drawing.Pen> 개체를 만든 다음 마지막으로 컨트롤의 <xref:System.Windows.Forms.Control.Location%2A> 및 <xref:System.Windows.Forms.Control.Size%2A>에 의해 결정되는 사각형 안에 타원을 그립니다.  대부분의 렌더링 코드는 이것보다 좀 더 복잡하지만 이 예제를 통해 <xref:System.Windows.Forms.PaintEventArgs> 개체에 포함된 <xref:System.Drawing.Graphics> 개체의 사용 방법을 알 수 있습니다.  <xref:System.Windows.Forms.UserControl> 또는 <xref:System.Windows.Forms.Button>과 같이 기존의 그래픽 표현이 있는 클래스에서 상속하면서 이 표현을 렌더링에 포함하지 않으려면 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출하지 않아야 합니다.  
  
 컨트롤의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드에 있는 코드는 컨트롤이 처음 그려질 때와 컨트롤이 새로 고쳐질 때마다 실행됩니다.  크기가 변경될 때마다 컨트롤이 다시 그려지도록 하려면 컨트롤의 생성자에 다음 줄을 추가하십시오.  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
  
```  
  
> [!NOTE]
>  사각형이 아닌 컨트롤을 구현하려면 <xref:System.Windows.Forms.Control.Region%2A?displayProperty=fullName> 속성을 사용합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.Region%2A>   
 <xref:System.Windows.Forms.ControlStyles>   
 <xref:System.Drawing.Graphics>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Windows.Forms.PaintEventArgs>   
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [구성 요소 컨트롤](../../../../docs/framework/winforms/controls/constituent-controls.md)   
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)