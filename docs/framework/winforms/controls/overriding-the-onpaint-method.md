---
title: "OnPaint 메서드 재정의"
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
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d9012d1a31eeaf50560b6166d32ac58662c5aa4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="overriding-the-onpaint-method"></a>OnPaint 메서드 재정의
에 정의 된 이벤트를 재정의 하는 기본 단계는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 동일 하며 다음 목록에 요약 되어 있습니다.  
  
#### <a name="to-override-an-inherited-event"></a>상속된 된 이벤트를 재정의 하려면  
  
1.  보호 된 재정의 `On` *EventName* 메서드.  
  
2.  호출 된 `On` *EventName* 에서 재정의 된 기본 클래스의 메서드 `On` *EventName* 메서드를 등록 된 대리자가 이벤트를 받도록 합니다.  
  
 <xref:System.Windows.Forms.Control.Paint> 이벤트는 모든 Windows Forms 컨트롤 재정의 해야 하기 때문에 여기에서 자세히 설명 되어는 <xref:System.Windows.Forms.Control.Paint> 에서 상속 된 이벤트 <xref:System.Windows.Forms.Control>합니다. 기본 <xref:System.Windows.Forms.Control> 클래스 파생된 된 컨트롤을 그릴 수 있도록 요구 하는 방법을 알지 못합니다 및 모든 그리기 논리를 제공 하지 않습니다는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드. <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드 <xref:System.Windows.Forms.Control> 디스패치 하기만 <xref:System.Windows.Forms.Control.Paint> 등록 된 이벤트 수신기에는 이벤트입니다.  
  
 이 샘플에서 작업 한 경우 [하는 방법: 간단한 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md), 재정의 하는 예제에 알아보았습니다는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드. 다음 코드에서는 샘플에서 수행 됩니다.  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs> 클래스에 대 한 데이터가 포함 된 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다. 이것은 다음 코드에 표시 된 두 개의 속성.  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>그리려는 사각형 및 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 속성은 참조는 <xref:System.Drawing.Graphics> 개체입니다. 클래스는 <xref:System.Drawing?displayProperty=nameWithType> 네임 스페이스는 관리의 기능에 대 한 액세스를 제공 하는 클래스 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 새 Windows 그래픽 라이브러리입니다. <xref:System.Drawing.Graphics> 개체의 포인트, 문자열, 선, 타원, 타원, 및 기타 많은 도형을 그릴 수 있는 메서드가 있습니다.  
  
 컨트롤 호출 해당 <xref:System.Windows.Forms.Control.OnPaint%2A> 자신의 시각적 표시를 변경 해야 할 때마다 메서드. 이 메서드는 메서드가 다시에 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [이벤트](../../../../docs/standard/events/index.md)  
 [Windows Forms 컨트롤 렌더링](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [이벤트 정의](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
