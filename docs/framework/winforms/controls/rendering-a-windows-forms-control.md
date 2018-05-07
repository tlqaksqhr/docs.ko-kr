---
title: Windows Forms 컨트롤 렌더링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: a2d7a02e725e3f8065b80a6b30ea21158be43ea8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="rendering-a-windows-forms-control"></a>Windows Forms 컨트롤 렌더링
렌더링은 사용자의 화면에 시각적 표시를 만드는 프로세스를 말합니다. Windows Forms를 사용 하 여 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (새 Windows 그래픽 라이브러리) 렌더링 합니다. 에 대 한 액세스를 제공 하는 관리 되는 클래스 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 에 <xref:System.Drawing?displayProperty=nameWithType> 네임 스페이스 및 그 하위 네임 스페이스입니다.  
  
 다음 요소가 컨트롤 렌더링에 포함 됩니다.  
  
-   기본 클래스에서 제공 하는 그리기 기능 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.  
  
-   필수 요소는 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 그래픽 라이브러리입니다.  
  
-   그리기 영역의 기 하 도형을 합니다.  
  
-   그래픽 리소스를 해제 하기 위한 절차입니다.  
  
## <a name="drawing-functionality-provided-by-control"></a>그리기 컨트롤에서 제공 하는 기능  
 기본 클래스 <xref:System.Windows.Forms.Control> 통해 그리기 기능을 제공 해당 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다. 컨트롤에서 발생 된 <xref:System.Windows.Forms.Control.Paint> 표시를 업데이트 해야 할 때마다 이벤트입니다. .NET Framework의 이벤트에 대 한 자세한 내용은 참조 [이벤트 처리 및 발생](../../../../docs/standard/events/index.md)합니다.  
  
 이벤트 데이터에 대 한 클래스는 <xref:System.Windows.Forms.Control.Paint> 이벤트 <xref:System.Windows.Forms.PaintEventArgs>, 컨트롤을 그리는 데 필요한 데이터를 보유-graphics 개체 및 그릴 영역을 나타내는 사각형 개체에 대 한 핸들입니다. 이러한 개체에 표시 되는 다음 코드 조각에서 굵게 표시 합니다.  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <xref:System.Drawing.Graphics> 그리기 기능을 캡슐화 하는 관리 되는 클래스에 대 한 설명에 설명 된 대로 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 이 항목의 뒷부분에 나오는 합니다. <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 의 인스턴스가 <xref:System.Drawing.Rectangle> 구조체이 고 컨트롤을 그릴 수 있는 사용 가능한 영역을 정의 합니다. 컨트롤 개발자를 계산할 수는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 를 사용 하는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 이 항목의 뒷부분에 나오는 기 하 도형에 대 한 설명에 설명 된 대로 컨트롤의 속성입니다.  
  
 재정의 하 여 컨트롤 렌더링 논리를 제공 해야는 <xref:System.Windows.Forms.Control.OnPaint%2A> 에서 상속 된 메서드 <xref:System.Windows.Forms.Control>합니다. <xref:System.Windows.Forms.Control.OnPaint%2A> 그래픽 개체 및 통해 그릴 사각형에 대 한 액세스를 가져옵니다는 <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> 및 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 의 속성은 <xref:System.Windows.Forms.PaintEventArgs> 인스턴스가 전달 합니다.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 기본 <xref:System.Windows.Forms.Control> 클래스는 그리기 기능을 구현 하지 않는 있지만에 등록 된 이벤트 대리자를 호출는 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다. 재정의 하는 경우 <xref:System.Windows.Forms.Control.OnPaint%2A>, 일반적으로 호출 해야 합니다는 <xref:System.Windows.Forms.Control.OnPaint%2A> 수신 하는 등록 된 대리자에는 기본 클래스의 메서드는 <xref:System.Windows.Forms.Control.Paint> 이벤트입니다. 하지만 전체 화면을 그리는 컨트롤의 기본 클래스를 호출 하지 않아야 <xref:System.Windows.Forms.Control.OnPaint%2A>마찬가지로 깜빡임을 소개 합니다. 재정의에 대 한 예제는 <xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트 참조는 [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.  
  
> [!NOTE]
>  호출 하지 말고 <xref:System.Windows.Forms.Control.OnPaint%2A> 직접 제어;에서 대신 호출할는 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드 (에서 상속 되며, <xref:System.Windows.Forms.Control>) 또는 일부 다른 메서드를 호출 하는 <xref:System.Windows.Forms.Control.Invalidate%2A>합니다. <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드 호출 <xref:System.Windows.Forms.Control.OnPaint%2A>합니다. <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드는 오버 로드 하 고 제공 된 인수에 따라 <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, 일부 또는 전체 화면 영역의 컨트롤을 다시 그립니다.  
  
 기본 <xref:System.Windows.Forms.Control> 그리기에 사용 되는 다른 메서드를 정의 하는 클래스-는 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 배경을 칠하는 (있고, 따라서 셰이프) 창 동안 빠른 되도록 보장 하 고 <xref:System.Windows.Forms.Control.OnPaint%2A> 세부 정보를 그리는 및 개별 그리기 요청은 하나에 결합 되므로 느릴 수 <xref:System.Windows.Forms.Control.Paint> 되어야 하는 모든 영역을 검사 하는 이벤트 다시 그려집니다. 호출 하려는 경우는 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 예를 들어, 컨트롤에 대 한 그라데이션 색 배경을 그리는 하려는 경우.  
  
 반면 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 이벤트와 비슷한 명명법 개이고으로 동일한 인수를 사용는 `OnPaint` 메서드를 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> true 이벤트 메서드가 아닙니다. 없는 `PaintBackground` 이벤트 및 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 이벤트 대리자를 호출 하지 않습니다. 재정의 하는 경우는 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드, 파생된 클래스를 호출 하는 데 필요 하지 않습니다.는 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 기본 클래스의 메서드.  
  
## <a name="gdi-basics"></a>GDI + 기본 사항  
 <xref:System.Drawing.Graphics> 클래스는 텍스트를 표시 하기 위한 메서드 뿐 아니라 원, 삼각형, 호 및 타원, 같은 다양 한 셰이프를 그리기 위한 메서드를 제공 합니다. <xref:System.Drawing?displayProperty=nameWithType> 네임 스페이스 및 그 하위 네임 스페이스 셰이프 (원, 사각형, 타원, 및 기타), 색, 글꼴, 브러시, 등과 같은 그래픽 요소를 캡슐화 하는 클래스가 포함 되어 있습니다. 에 대 한 자세한 내용은 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], 참조 [관리 되는 그래픽 클래스를 사용 하 여](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)합니다. 필수 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 에 나와 [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.  
  
## <a name="geometry-of-the-drawing-region"></a>기 하 도형 그리기 영역의  
 <xref:System.Windows.Forms.Control.ClientRectangle%2A> 사용자의 화면에 컨트롤에 사용할 수 있는 사각형 영역을 지정 하는 컨트롤의 속성 동안는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성 <xref:System.Windows.Forms.PaintEventArgs> 그리고 실제로 있는 영역을 지정 합니다. (기억 그리기가 수행 됩니다는 <xref:System.Windows.Forms.Control.Paint> 사용 이벤트 메서드를 한 <xref:System.Windows.Forms.PaintEventArgs> 인스턴스). 컨트롤의 표시 변경의 경우 작은 섹션의 경우 처럼 컨트롤에서 사용 가능한 영역의 부분만 그릴 해야 합니다. 컨트롤 개발자 이런 경우, 그리고 전달 하는 실제 사각형을 계산 해야 <xref:System.Windows.Forms.Control.Invalidate%2A>합니다. 오버 로드 된 버전의 <xref:System.Windows.Forms.Control.Invalidate%2A> 사용 하는 <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.Region> 인수를 사용 하 여 인수에 지정 된 생성의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성 <xref:System.Windows.Forms.PaintEventArgs>합니다.  
  
 다음 코드 조각 표시 방법을 `FlashTrackBar` 사용자 지정 컨트롤에 그릴 사각형 영역을 계산 합니다. `client` 변수 나타냅니다는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성입니다. 전체 샘플을 참조 하십시오. [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>그래픽 리소스를 해제  
 그래픽 개체는 시스템 리소스를 사용 하기 때문에 비용이 많이 드는입니다. 인스턴스를 포함 하는 이러한 개체는 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 클래스의 인스턴스 뿐만 아니라 <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, 및 기타 그래픽 클래스입니다. 에 필요 하 고 해제 하는 경우에 그래픽 리소스를 만드는 것이 중요 하기를 사용 하 여 작업을 마치는 곧 합니다. 구현 하는 형식을 만드는 경우는 <xref:System.IDisposable> 인터페이스를 호출 해당 <xref:System.IDisposable.Dispose%2A> 메서드 했으면 된 리소스를 해제 합니다.  
  
 다음 코드 조각 표시 방법을 `FlashTrackBar` 사용자 지정 컨트롤을 만들고 해제는 <xref:System.Drawing.Brush> 리소스입니다. 전체 소스 코드에 대 한 참조 [하는 방법: Windows Forms 컨트롤을 표시 진행률 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)합니다.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
