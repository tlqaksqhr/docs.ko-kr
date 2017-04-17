---
title: "GDI+의 그래픽 경로 | Microsoft Docs"
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
  - "그리기, 경로"
  - "GDI+, 경로 그리기"
  - "그래픽, 경로"
  - "경로, 그리기"
ms.assetid: a5500dec-666c-41fd-9da3-2169dd89c5eb
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# GDI+의 그래픽 경로
경로는 선, 사각형 및 단순 곡선의 조합으로 이루어집니다.  [벡터 그래픽 개요](../../../../docs/framework/winforms/advanced/vector-graphics-overview.md)에서 다음과 같은 기본 빌딩 블록이 그림을 그리는 데 가장 유용하다는 사실을 설명했습니다.  
  
-   줄  
  
-   사각형  
  
-   타원  
  
-   원호  
  
-   다각형  
  
-   카디널 스플라인  
  
-   3차원 곡선 스플라인  
  
 GDI\+에서는 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체를 사용하여 이러한 빌딩 블록 시퀀스를 하나의 단위로 모을 수 있습니다.  그런 다음 <xref:System.Drawing.Graphics> 클래스의 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드를 한 번 호출하여 선, 사각형, 다각형 및 곡선의 전체 시퀀스를 그릴 수 있습니다.  다음 그림에서는 선, 원호, 3차원 곡선 스플라인 및 카디널 스플라인을 조합하여 만든 경로를 보여 줍니다.  
  
 ![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art14.png "Aboutgdip02\_art14")  
  
## 경로 사용  
 <xref:System.Drawing.Drawing2D.GraphicsPath> 클래스는 그리려는 항목의 시퀀스를 만드는 데 사용할 수 있도록 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangle%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddPolygon%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>\(카디널 스플라인용\) 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBezier%2A> 메서드를 제공합니다.  이러한 메서드는 모두 오버로드됩니다. 즉 각 메서드는 다양한 매개 변수 목록을 지원합니다.  예를 들어 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>에서 변형된 한 메서드는 네 개의 정수를 받고 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A>에서 변형된 다른 메서드는 두 개의 <xref:System.Drawing.Point> 개체를 받습니다.  
  
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddLines%2A>, <xref:System.Drawing.Drawing2D.GraphicsPath.AddRectangles%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddBeziers%2A> 등과 같이 선, 사각형 및 3차원 곡선 스플라인을 경로에 추가하는 메서드는 한 번 호출하여 경로에 몇 개의 항목을 추가하는 동반 메서드를 여러 개 갖습니다.  또한 <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddArc%2A> 메서드는 폐곡선이나 원형을 경로에 추가하는 <xref:System.Drawing.Drawing2D.GraphicsPath.AddClosedCurve%2A> 및 <xref:System.Drawing.Drawing2D.GraphicsPath.AddPie%2A> 메서드를 동반합니다.  
  
 경로를 그리려면 <xref:System.Drawing.Graphics> 개체, <xref:System.Drawing.Pen> 개체 및 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체가 필요합니다.  <xref:System.Drawing.Graphics> 개체는 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드를 제공하고 <xref:System.Drawing.Pen> 개체에는 경로를 렌더링하는 데 사용되는 선의 색과 두께 같은 특성이 저장됩니다.  <xref:System.Drawing.Drawing2D.GraphicsPath> 개체에는 경로를 구성하는 선과 곡선의 시퀀스가 저장되고  <xref:System.Drawing.Pen> 개체 및 <xref:System.Drawing.Drawing2D.GraphicsPath> 개체는 <xref:System.Drawing.Graphics.DrawPath%2A> 메서드에 인수로 전달됩니다.  다음 예제에서는 선, 타원 및 3차원 곡선 스플라인으로 구성되는 경로를 그립니다.  
  
 [!code-csharp[LinesCurvesAndShapes#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#101)]
 [!code-vb[LinesCurvesAndShapes#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#101)]  
  
 다음 그림은 경로를 보여 줍니다.  
  
 ![Path](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art15.png "Aboutgdip02\_art15")  
  
 선, 사각형 및 곡선을 경로에 추가하는 것 외에 경로를 경로에 추가할 수 있습니다.  이 기능을 사용하면 기존 경로를 여러 개 조합하여 크고 복잡한 경로를 형성할 수 있습니다.  
  
 [!code-csharp[LinesCurvesAndShapes#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#102)]
 [!code-vb[LinesCurvesAndShapes#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#102)]  
  
 경로에 추가할 기타 항목으로 문자열과 원형이 있습니다.  원형은 타원 내부의 일부분입니다.  다음 예제에서는 원호, 카디널 스플라인, 문자열 및 원형에서 경로를 만듭니다.  
  
 [!code-csharp[LinesCurvesAndShapes#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#103)]
 [!code-vb[LinesCurvesAndShapes#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#103)]  
  
 다음 그림은 경로를 보여 줍니다.  경로는 반드시 연결될 필요가 없습니다. 원호, 카디널 스플라인, 문자열 및 원형은 분리되어 있습니다.  
  
 ![경로](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art16.png "Aboutgdip02\_Art16")  
  
## 참고 항목  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 <xref:System.Drawing.Point?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [경로 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)