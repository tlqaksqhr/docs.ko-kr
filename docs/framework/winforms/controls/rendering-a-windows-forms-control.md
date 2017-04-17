---
title: "Windows Forms 컨트롤 렌더링 | Microsoft Docs"
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
  - "사용자 지정 컨트롤[Windows Forms], 그래픽 리소스"
  - "사용자 지정 컨트롤[Windows Forms], 무효화 및 그리기"
  - "사용자 지정 컨트롤[Windows Forms], 렌더링"
  - "OnPaintBackground 메서드, Windows Forms 사용자 지정 컨트롤에서 호출"
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms 컨트롤 렌더링
렌더링은 사용자의 화면에 시각적 표현을 만드는 과정을 말합니다.  Windows Forms에서는 렌더링을 위해 새로운 Windows 그래픽 라이브러리인 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]를 사용합니다.  [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]에 대한 액세스를 제공하는 관리되는 클래스는 <xref:System.Drawing?displayProperty=fullName> 네임스페이스 및 해당 하위 네임스페이스에 있습니다.  
  
 컨트롤 렌더링에는 다음 요소가 포함됩니다.  
  
-   기본 클래스 <xref:System.Windows.Forms.Control?displayProperty=fullName>에서 제공하는 그리기 기능  
  
-   [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] 그래픽 라이브러리의 필수 요소  
  
-   그리기 영역의 기하 도형  
  
-   그래픽 리소스를 해제하기 위한 절차  
  
## 컨트롤에서 제공하는 그리기 기능  
 기본 클래스 <xref:System.Windows.Forms.Control>에서는 해당 <xref:System.Windows.Forms.Control.Paint> 이벤트를 통해 그리기 기능을 제공합니다.  컨트롤에서 표시를 업데이트해야 할 때마다 <xref:System.Windows.Forms.Control.Paint> 이벤트를 발생시킵니다.  .NET Framework의 이벤트에 대한 자세한 내용은 [이벤트 처리 및 발생](../../../../docs/standard/events/index.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.Control.Paint> 이벤트의 이벤트 데이터 클래스인 <xref:System.Windows.Forms.PaintEventArgs>에는 그릴 영역을 나타내는 사각형 개체와 그래픽 개체에 대한 핸들과 같은 컨트롤을 그리는 데 필요한 데이터가 저장되어 있습니다.  이러한 개체는 다음 코드 조각에서 굵게 표시되어 있습니다.  
  
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
  
 <xref:System.Drawing.Graphics>는 이 항목 후반의 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]에 대한 설명에서 볼 수 있는 것처럼 그리기 기능을 캡슐화하는 관리되는 클래스입니다.  <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>은 <xref:System.Drawing.Rectangle> 구조체 인스턴스이며 컨트롤이 그릴 수 있는 사용 가능한 영역을 정의합니다.  이 항목 후반의 기하에 대한 설명에서 볼 수 있는 것처럼 컨트롤 개발자는 컨트롤의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성을 사용하여 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>을 계산할 수 있습니다.  
  
 컨트롤은 <xref:System.Windows.Forms.Control>에서 상속된 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의하여 렌더링 논리를 제공해야 합니다.  <xref:System.Windows.Forms.Control.OnPaint%2A>는 전달받은 <xref:System.Windows.Forms.PaintEventArgs> 인스턴스의 <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> 및 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성을 통해 그릴 그래픽 개체와 사각형에 액세스합니다.  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 기본 <xref:System.Windows.Forms.Control> 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드에서는 그리기 기능을 구현하지 않고 <xref:System.Windows.Forms.Control.Paint> 이벤트에 등록된 이벤트 대리자만 호출합니다.  <xref:System.Windows.Forms.Control.OnPaint%2A>를 재정의할 경우 대개 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출하여 등록된 대리자가 <xref:System.Windows.Forms.Control.Paint> 이벤트를 받도록 해야 합니다.  그러나 전체 화면을 그리는 컨트롤은 깜빡임이 생기기 때문에 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A>를 호출하지 않아야 합니다.  <xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트 재정의에 대한 예를 보려면 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조하십시오.  
  
> [!NOTE]
>  컨트롤에서 바로 <xref:System.Windows.Forms.Control.OnPaint%2A>를 호출하지 마십시오. 대신 <xref:System.Windows.Forms.Control>에서 상속된 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드나 <xref:System.Windows.Forms.Control.Invalidate%2A>를 호출하는 다른 메서드를 호출하십시오.  그러면 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드에서 <xref:System.Windows.Forms.Control.OnPaint%2A>를 호출합니다.  <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드가 오버로드되고, <xref:System.Windows.Forms.Control.Invalidate%2A> `e`에 제공된 인수에 따라 컨트롤에서 화면 영역의 일부 또는 전체를 다시 그립니다.  
  
 기본 <xref:System.Windows.Forms.Control> 클래스는 그리기에 유용한 다른 메서드, 즉 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드를 정의합니다.  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>는 창의 배경과 모양을 그리며 속도가 빠릅니다. 반면 <xref:System.Windows.Forms.Control.OnPaint%2A>는 세부 내용을 그리며 다시 그려야 하는 모든 영역을 다루는 하나의 <xref:System.Windows.Forms.Control.Paint> 이벤트로 개별 그리기 요청이 결합되기 때문에 속도가 느릴 수 있습니다.  예를 들어, 컨트롤에 대해 그라데이션 색의 배경을 그리려면 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>를 호출합니다.  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>는 명칭이 이벤트 같고 `OnPaint` 메서드와 동일한 인수를 사용하는 반면 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>는 진정한 이벤트 메서드가 아닙니다.  `PaintBackground` 이벤트는 없으며 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>는 이벤트 대리자를 호출하지 않습니다.  <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드를 재정의할 때는 파생 클래스 없이도 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드를 호출할 수 있습니다.  
  
## GDI\+ 기본  
 <xref:System.Drawing.Graphics> 클래스는 텍스트를 표시하는 메서드뿐만 아니라 원, 삼각형, 원호, 타원과 같은 다양한 모양을 그릴 수 있는 메서드를 제공합니다.  <xref:System.Drawing?displayProperty=fullName> 네임스페이스 및 해당 하위 네임스페이스에는 모양\(원, 사각형, 원호 등\), 색, 글꼴, 브러시 등과 같은 그래픽 요소를 캡슐화하는 클래스가 포함되어 있습니다.  [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]에 대한 자세한 내용은 [관리되는 그래픽 클래스 사용](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)을 참조하십시오.  [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]에 대한 주요 내용은 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)에도 설명되어 있습니다.  
  
## 그리기 영역의 기하 도형  
 컨트롤의 <xref:System.Windows.Forms.Control.ClientRectangle%2A> 속성은 사용자 화면에서 컨트롤을 사용할 수 있는 사각형 영역을 지정하고 <xref:System.Windows.Forms.PaintEventArgs>의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성은 실제로 그릴 영역을 지정합니다.  <xref:System.Windows.Forms.PaintEventArgs> 인스턴스를 인수로 사용하는 <xref:System.Windows.Forms.Control.Paint> 이벤트 메서드에서 그리기가 수행됩니다.  컨트롤의 표시 일부가 변경되는 경우처럼 컨트롤에서 사용 가능한 영역의 일부만 그려야 할 수도 있습니다.  이러한 경우 컨트롤 개발자는 그릴 실제 사각형을 계산하여 <xref:System.Windows.Forms.Control.Invalidate%2A>에게 전달해야 합니다.  <xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.Region>을 인수로 사용하는 <xref:System.Windows.Forms.Control.Invalidate%2A>의 오버로드된 버전에서는 이러한 인수를 사용하여 <xref:System.Windows.Forms.PaintEventArgs>의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성을 생성합니다.  
  
 다음 코드 조각에서는 `FlashTrackBar` 사용자 지정 컨트롤에서 그릴 사각형 영역을 계산하는 방법을 보여 줍니다.  `client` 변수는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성을 나타냅니다.  완전한 샘플은 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조하십시오.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## 그래픽 리소스 해제  
 그래픽 개체는 시스템 리소스를 사용하기 때문에 부담이 큽니다.  이러한 개체에는 <xref:System.Drawing.Brush?displayProperty=fullName>, <xref:System.Drawing.Pen?displayProperty=fullName> 및 기타 그래픽 클래스의 인스턴스뿐만 아니라 <xref:System.Drawing.Graphics?displayProperty=fullName> 클래스의 인스턴스도 포함되어 있습니다.  그러므로 필요할 때만 그래픽 리소스를 만들고 사용이 끝나면 바로 해제해야 합니다.  <xref:System.IDisposable> 인터페이스를 구현하는 형식을 만든 경우 사용이 끝났으면 해당 <xref:System.IDisposable.Dispose%2A> 메서드를 호출하여 리소스를 해제합니다.  
  
 다음 코드 조각에서는 `FlashTrackBar` 사용자 지정 컨트롤에서 <xref:System.Drawing.Brush> 리소스를 만들고 해제하는 방법을 보여 줍니다.  전체 소스 코드를 보려면 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조하십시오.  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## 참고 항목  
 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)