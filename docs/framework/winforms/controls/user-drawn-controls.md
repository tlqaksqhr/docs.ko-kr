---
title: 사용자가 그린 컨트롤
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: 26b4f062c120bf543a5e597fc8c734e8cc336bd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542199"
---
# <a name="user-drawn-controls"></a>사용자가 그린 컨트롤
.NET Framework 사용자 지정 컨트롤을 쉽게 개발 하는 기능을 제공 합니다. 코드에서 함께 바인딩된 표준 컨트롤 집합을 사용자 정의 컨트롤을 만들거나 위로 기초부터 사용자 고유의 컨트롤을 디자인할 수 있습니다. 기존 컨트롤에서 상속 되는 컨트롤을 만들고의 고유 기능에 추가 상속을 사용할 수 있습니다. 어떤 방법을 사용 하는.NET Framework를 그릴 만드는 모든 컨트롤에 대 한 사용자 지정 그래픽 인터페이스를 제공 합니다.  
  
 컨트롤의 그리기 컨트롤의 코드를 실행 하 여 수행 됩니다 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드. 단일 인수는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 한 <xref:System.Windows.Forms.PaintEventArgs> 모든 정보 및 컨트롤을 렌더링 하는 데 필요한 기능을 제공 하는 개체입니다. <xref:System.Windows.Forms.PaintEventArgs> 속성으로 컨트롤의 렌더링에 사용할 두 개의 기본 개체를 제공 합니다.  
  
-   <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 개체-에 그릴 컨트롤의 부분을 나타내는 사각형입니다. 이 수는 전체 컨트롤 또는 컨트롤을 그리는 방법에 따라 제어의 일부입니다.  
  
-   <xref:System.Drawing.Graphics> 개체-여러 그래픽 지향 개체와 컨트롤을 그리는 데 필요한 기능을 제공 하는 메서드를 캡슐화 합니다.  
  
 대 한 자세한 내용은 <xref:System.Drawing.Graphics> 개체와 사용을 참조 하는 방법 [하는 방법: 그리기에 대 한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)합니다.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트는 컨트롤을 그리거나 화면에서 새로 고칠 때마다 발생 하며 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 개체를 그리기 열리는 사각형을 나타내는입니다. 전체 컨트롤 고쳐야 하는 경우는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 는 전체 컨트롤의 크기를 나타냅니다. 그러나 컨트롤의 부분 새로 고칠 필요가,만 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 개체는 다시 그려야 하는 영역만 나타냅니다. 이러한 경우의 예는 컨트롤이 다른 컨트롤이 나 폼의 사용자 인터페이스에 의해 부분적으로 가려져 때 것입니다.  
  
 상속 된 경우는 <xref:System.Windows.Forms.Control> 재정의 해야 클래스는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드 내에서 그래픽 렌더링 코드를 제공 합니다. 사용자 정의 컨트롤 또는 상속된 된 컨트롤에 사용자 지정 그래픽 인터페이스를 제공 하려는 경우 수 또한 이렇게 하면 재정의 하 여는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드. 예는 다음과 같습니다.  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,   
         this.Size));  
   }
}  
```  
  
 앞의 예제에는 매우 간단한 그래픽 방식으로 컨트롤을 렌더링 하는 방법을 보여 줍니다. 호출 된 <xref:System.Windows.Forms.Control.OnPaint%2A> 기본 클래스의 메서드를 만듭니다는 <xref:System.Drawing.Pen> , 그리는 데 사용할 개체 및 사각형에 타원을 그립니다에 의해 결정 되는 마지막으로 <xref:System.Windows.Forms.Control.Location%2A> 및 <xref:System.Windows.Forms.Control.Size%2A> 컨트롤의 합니다. 이 예제에서는 사용 하는 대부분의 렌더링 코드 보다 좀 더 복잡 하지만 <xref:System.Drawing.Graphics> 내에 포함 된 개체는 <xref:System.Windows.Forms.PaintEventArgs> 개체입니다. 와 같은 그래픽으로 이미가지고 있는 클래스에서 상속 하는 경우에 <xref:System.Windows.Forms.UserControl> 또는 <xref:System.Windows.Forms.Button>, 표현을 렌더링에 통합 하려면, 기본 클래스를 호출 하지 않아야 하 고 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드입니다.  
  
 코드는 <xref:System.Windows.Forms.Control.OnPaint%2A> 컨트롤의 메서드를 먼저 컨트롤을 그리면 및 새로 고칠 때마다 실행 됩니다. 크기를 조정할 때마다 컨트롤을 다시 그리면 되도록 컨트롤의 생성자에 다음 줄을 추가 합니다.  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  사용 하 여 <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> 사각형이 아닌 컨트롤을 구현 하는 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Control.Region%2A>  
 <xref:System.Windows.Forms.ControlStyles>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Windows.Forms.PaintEventArgs>  
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [구성 요소 컨트롤](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 [사용자 지정 컨트롤의 종류](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
