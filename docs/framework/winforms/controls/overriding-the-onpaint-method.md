---
title: "OnPaint 메서드 재정의 | Microsoft Docs"
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
  - "OnPaint 메서드, Windows Forms 사용자 지정 컨트롤에서 재정의"
  - "Paint 이벤트, Windows Forms 사용자 지정 컨트롤에서 처리"
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# OnPaint 메서드 재정의
[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에 정의된 이벤트를 재정의하는 기본 단계는 동일하며 다음 목록에 요약되어 있습니다.  
  
#### 상속된 이벤트를 재정의하려면  
  
1.  보호된 `On`*EventName* 메서드를 재정의합니다.  
  
2.  재정의된 `On`*EventName* 메서드에서 기본 클래스의 `On`*EventName* 메서드를 호출하여 등록된 대리자가 이벤트를 받도록 합니다.  
  
 모든 Windows Forms 컨트롤은 자신이 <xref:System.Windows.Forms.Control>에서 상속한 <xref:System.Windows.Forms.Control.Paint> 이벤트를 재정의해야 하기 때문에 여기서 <xref:System.Windows.Forms.Control.Paint> 이벤트를 자세히 설명합니다.  기본 <xref:System.Windows.Forms.Control> 클래스에는 파생 컨트롤을 만드는 방법에 대한 정보가 없으며 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드에 아무런 그리기 논리도 제공되지 않습니다.  <xref:System.Windows.Forms.Control>의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 등록된 이벤트 수신자에게 <xref:System.Windows.Forms.Control.Paint> 이벤트를 디스패치하기만 합니다.  
  
 [방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)의 샘플을 작업한 경우 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하는 예제를 보았을 것입니다.  다음 코드 부분은 이 샘플에서 가져온 것입니다.  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class   
```  
  
```csharp  
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 <xref:System.Windows.Forms.PaintEventArgs> 클래스에는 <xref:System.Windows.Forms.Control.Paint> 이벤트의 데이터가 들어 있습니다.  아래 코드에 표시된 것처럼, 이 클래스에는 두 개의 속성이 있습니다.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property   
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>은 그리려는 사각형이며 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 속성은 <xref:System.Drawing.Graphics> 개체를 참조합니다.  <xref:System.Drawing?displayProperty=fullName> 네임스페이스의 클래스는 새로운 Windows 그래픽 라이브러리인 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]의 기능에 액세스하는 관리되는 클래스입니다.  <xref:System.Drawing.Graphics> 개체에는 점, 문자열, 선, 원호, 타원 및 기타 모양을 그릴 수 있는 메서드가 있습니다.  
  
 컨트롤은 자신의 시각적 표시를 변경해야 할 때마다 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출합니다.  그 다음 이 메서드는 <xref:System.Windows.Forms.Control.Paint> 이벤트를 발생시킵니다.  
  
## 참고 항목  
 [이벤트](../../../../docs/standard/events/index.md)   
 [Windows Forms 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)   
 [이벤트 정의](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)