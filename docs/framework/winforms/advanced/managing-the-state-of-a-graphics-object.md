---
title: "Graphics 개체의 상태 관리 | Microsoft Docs"
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
  - "그래픽, 클리핑"
  - "그래픽, 상태 관리"
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Graphics 개체의 상태 관리
<xref:System.Drawing.Graphics> 클래스는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]의 핵심입니다.  원하는 요소를 그리려면 <xref:System.Drawing.Graphics> 개체를 가져와 속성을 설정하고 <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A> 등과 같은 메서드를 호출합니다.  
  
 다음 예제에서는 <xref:System.Drawing.Graphics> 개체의 <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드를 호출합니다.  <xref:System.Drawing.Graphics.DrawRectangle%2A> 메서드에 전달되는 첫 번째 인수는 <xref:System.Drawing.Pen> 개체입니다.  
  
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
  
## Graphics 상태  
 <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Graphics.DrawLine%2A>과 <xref:System.Drawing.Graphics.DrawRectangle%2A> 같은 그리기 메서드를 제공합니다.  그 뿐만 아니라 <xref:System.Drawing.Graphics> 개체는 다음과 같은 범주로 구분되는 그래픽 상태를 유지 관리합니다.  
  
-   품질 설정  
  
-   변환  
  
-   클리핑 영역  
  
### 품질 설정  
 <xref:System.Drawing.Graphics> 개체에는 그리는 항목의 품질에 영향을 주는 몇 가지 속성이 있습니다.  예를 들면 <xref:System.Drawing.Graphics.TextRenderingHint%2A> 속성을 설정하여 텍스트에 적용되는 앤티 앨리어싱\(있을 경우\)의 종류를 지정할 수 있습니다.  이 외에도 <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A> 및 <xref:System.Drawing.Graphics.InterpolationMode%2A> 같은 속성이 품질에 영향을 줍니다.  
  
 다음 예제에서는 다듬기 모드 속성을 각각 <xref:System.Drawing.Drawing2D.SmoothingMode>와 <xref:System.Drawing.Drawing2D.SmoothingMode>로 설정한 타원 두 개를 그립니다.  
  
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
  
### 변환  
 <xref:System.Drawing.Graphics> 개체는 해당 <xref:System.Drawing.Graphics> 개체에서 그리는 모든 항목에 적용되는 전역 변환과 페이지 변환을 유지 관리합니다.  상관 변환은 전역 변환에 저장할 수 있습니다.  상관 변환으로는 배율 조정, 회전, 반사, 기울이기, 이동 등이 있습니다.  페이지 변환은 픽셀을 인치로 바꾸는 등의 단위 변환이나 배율 조정을 위해 사용할 수 있습니다.  자세한 내용은 [좌표계 및 변환](../../../../docs/framework/winforms/advanced/coordinate-systems-and-transformations.md)을 참조하십시오.  
  
 다음 예제에서는 <xref:System.Drawing.Graphics> 개체의 전역 변환과 페이지 변환을 설정합니다.  전역 변환은 30도 회전으로 설정되어 있습니다.  페이지 변환은 두 번째 <xref:System.Drawing.Graphics.DrawEllipse%2A>에 전달되는 좌표를 픽셀 대신 밀리미터로 처리하도록 설정되어 있습니다.  이 코드는 <xref:System.Drawing.Graphics.DrawEllipse%2A> 메서드를 동일한 방법으로 두 번 호출합니다.  첫 번째 <xref:System.Drawing.Graphics.DrawEllipse%2A> 호출에는 전역 변환이 적용되고 두 번째 <xref:System.Drawing.Graphics.DrawEllipse%2A> 호출에는 전역 변환과 페이지 변환이 모두 적용됩니다.  
  
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
  
 아래 그림에 두 개의 타원이 나와 있습니다.  여기서 30도 회전은 타원의 중앙이 아니라 좌표계의 원점\(클라이언트 영역의 왼쪽 위 모퉁이\)을 기준으로 합니다.  또한, 펜 굵기는 똑같이 1이지만 첫 번째 타원은 1픽셀 굵기로 그려지고 두 번째 타원은 1밀리미터 굵기로 그려집니다.  
  
 ![타원](../../../../docs/framework/winforms/advanced/media/csgraphicsascon1.png "csgraphicsascon1")  
  
### 클리핑 영역  
 <xref:System.Drawing.Graphics> 개체는 해당 <xref:System.Drawing.Graphics> 개체에서 그리는 모든 항목에 적용되는 클리핑 영역을 유지 관리합니다.  <xref:System.Drawing.Graphics.SetClip%2A> 메서드를 호출하여 클리핑 영역을 설정할 수 있습니다.  
  
 아래 예제에서는 두 개의 사각형을 결합하여 더하기 기호 모양의 영역을 만듭니다.  이 영역은 <xref:System.Drawing.Graphics> 개체의 클리핑 영역으로 지정됩니다.  그런 다음 코드에서는 클리핑 영역 내부로 제한되는 두 개의 선을 그립니다.  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](../../../../amples/snippets/visualbasic/VS_Snippets_Wpf/ToolBarOrient_snip/visualbasic/toolbargraphics/new.bmp Rectangle(50, 0, 50, 150))  
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
  
 아래 그림에 클리핑된 선이 나와 있습니다.  
  
 ![제한된 클립 영역](../../../../docs/framework/winforms/advanced/media/graphicsascon2.png "graphicsascon2")  
  
## 참고 항목  
 [Windows Forms의 그래픽 및 그리기](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [중첩된 Graphics 컨테이너 사용](../../../../docs/framework/winforms/advanced/using-nested-graphics-containers.md)