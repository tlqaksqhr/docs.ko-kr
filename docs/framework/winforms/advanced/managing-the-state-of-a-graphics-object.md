---
title: Graphics 개체의 상태 관리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: b81c3c8b25f13ac5791b5d2116b8536575f9ebcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525121"
---
# <a name="managing-the-state-of-a-graphics-object"></a>Graphics 개체의 상태 관리
<xref:System.Drawing.Graphics> 의 핵심 클래스는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]합니다. 아무 것도 그리지, 가져와야는 <xref:System.Drawing.Graphics> 개체 속성을 설정 하 고 해당 메서드를 호출할 <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, 등).  
  
 다음 예제에서는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다. 에 전달 되는 첫 번째 인수는 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드는 한 <xref:System.Drawing.Pen> 개체입니다.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a>그래픽 상태  
 A <xref:System.Drawing.Graphics> 개체는 그리기 메서드와 같은 제공 이상 <xref:System.Drawing.Graphics.DrawLine%2A> 및 <xref:System.Drawing.Graphics.DrawRectangle%2A>합니다. A <xref:System.Drawing.Graphics> 개체에는 또한 다음과 같은 범주로 나눌 수 있는 그래픽 상태를 유지 관리 합니다.  
  
-   품질 설정  
  
-   변형  
  
-   클립 영역  
  
### <a name="quality-settings"></a>품질 설정  
 A <xref:System.Drawing.Graphics> 개체에 나타나는 항목의 품질에 영향을 주는 몇 가지 속성이 있습니다. 예를 들어, 설정할 수는 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 앤티 앨리어싱 (있는 경우)의 텍스트에 적용 된 형식을 지정 하는 속성입니다. 품질에 영향을 주는 다른 속성은 <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, 및 <xref:System.Drawing.Graphics.InterpolationMode%2A>합니다.  
  
 다음 예제에서는 다듬기 모드가 설정 된 두 타원을 그립니다 <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> 고 다른 하나는 다듬기 모드 <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a>변형  
 A <xref:System.Drawing.Graphics> 개체를 유지 관리 하 여 그린 모든 항목에 적용 되는 두 개의 변환 (월드 및 페이지) <xref:System.Drawing.Graphics> 개체입니다. 모든 관계 변환 전역 변환에 저장할 수 있습니다. 3x3 유사 변환에는 크기 조정, 회전, 반사, 기울이기 및 변환 하는 기능이 포함 됩니다. 페이지 변환 크기를 조정 하 고 단위 (예를 들어 인치로 픽셀)를 변경 하는 데 사용할 수 있습니다. 자세한 내용은 참조 [좌표계 및 변형](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)합니다.  
  
 다음 예제에서는 설정의 월드 및 페이지 변환을 <xref:System.Drawing.Graphics> 개체입니다. 월드 변형은 30도 회전으로 설정 됩니다. 페이지 변형을 설정 하 여 두 번째 인스턴스에 전달 되는 좌표 <xref:System.Drawing.Graphics.DrawEllipse%2A> 픽셀 대신 밀리미터도 처리 됩니다. 코드에서는 두 개의 동일한 호출을는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드. 첫 번째에 세계 변형이 적용 <xref:System.Drawing.Graphics.DrawEllipse%2A> 호출과 두 가지 변환은 모두 (월드 및 페이지)는 두 번째에 적용 됩니다 <xref:System.Drawing.Graphics.DrawEllipse%2A> 호출 합니다.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);   
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 다음 그림에서는 두 타원을 보여 줍니다. 30도 회전 (클라이언트 영역의 왼쪽 위 모퉁이) 좌표계의 원점을, 타원의 중앙 대해서는 알아보지 인지 note 합니다. 또한 1의 펜 너비는 두 번째 타원에 첫 번째 타원은 및 1mm 1 픽셀 note 합니다.  
  
 ![타원](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### <a name="clipping-region"></a>클립 영역  
 A <xref:System.Drawing.Graphics> 개체를 유지 관리 하 여 그린 모든 항목에 적용 되는 클립 영역 <xref:System.Drawing.Graphics> 개체입니다. 호출 하 여 클립 영역을 설정할 수 있습니다는 <xref:System.Drawing.Graphics.SetClip%2A> 메서드.  
  
 다음 예제에서는 두 개의 사각형의 모퉁이 결합 하 여 더하기 모양의 영역을 만듭니다. 해당 지역의의 클립 영역으로 지정 된는 <xref:System.Drawing.Graphics> 개체입니다. 그런 다음 코드는 클립 영역 내부로 제한 되는 두 줄을 그립니다.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);    
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));    
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 다음 그림에는 잘린된 줄 보여 줍니다.  
  
 ![클립 영역을 제한](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [중첩된 Graphics 컨테이너 사용](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)
