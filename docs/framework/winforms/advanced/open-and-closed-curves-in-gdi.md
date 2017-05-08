---
title: "GDI+의 개곡선 및 폐곡선 | Microsoft Docs"
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
  - "곡선"
  - "곡선, 그리기"
  - "곡선, 채우기"
  - "GDI+, 곡선"
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# GDI+의 개곡선 및 폐곡선
다음 그림은 개곡선 및 폐곡선을 보여 줍니다.  
  
 ![개곡선 및 폐곡선](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art24.png "Aboutgdip02\_art24")  
  
## 곡선의 관리 인터페이스  
 폐곡선에는 내부가 있기 때문에 브러시로 채울 수 있습니다.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]의 <xref:System.Drawing.Graphics> 클래스는 폐도형 및 폐곡선을 채우는 데 사용할 수 있도록 <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A> 및 <xref:System.Drawing.Graphics.FillRegion%2A> 메서드를 제공합니다.  이러한 메서드 중 하나를 호출할 경우에는 항상 <xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush> 또는 <xref:System.Drawing.Drawing2D.PathGradientBrush> 같은 특정 브러시 유형 중 하나를 인수로 전달해야 합니다.  
  
 <xref:System.Drawing.Graphics.FillPie%2A> 메서드는 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드와 함께 사용됩니다.  <xref:System.Drawing.Graphics.DrawArc%2A> 메서드가 타원의 윤곽선 부분을 그리는 것처럼 <xref:System.Drawing.Graphics.FillPie%2A> 메서드는 타원의 내부를 채웁니다.  다음 예제에서는 원호를 그리고 그에 대응하는 타원의 내부를 채웁니다.  
  
 [!code-csharp[LinesCurvesAndShapes#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 다음 그림은 원호 및 채워진 원형을 보여 줍니다.  
  
 ![개곡선 및 폐곡선](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art25.png "Aboutgdip02\_art25")  
  
 <xref:System.Drawing.Graphics.FillClosedCurve%2A> 메서드는 <xref:System.Drawing.Graphics.DrawClosedCurve%2A> 메서드와 함께 사용됩니다.  두 메서드는 모두 끝점을 시작점에 연결함으로써 자동으로 곡선을 닫습니다.  다음 예제에서는 \(0, 0\), \(60, 20\) 및 \(40, 50\)을 통과하는 곡선을 그립니다.  그러 다음 \(40, 50\)을 시작점인 \(0, 0\)에 연결하여 곡선을 자동으로 닫고 내부를 단색으로 채웁니다.  
  
 [!code-csharp[LinesCurvesAndShapes#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 <xref:System.Drawing.Graphics.FillPath%2A> 메서드는 경로에서 분리된 조각의 내부를 채웁니다.  경로의 한 부분이 폐곡선 또는 폐도형을 형성하지 않으면 <xref:System.Drawing.Graphics.FillPath%2A> 메서드는 채우기 전에 이 경로 부분을 자동으로 닫습니다.  다음 예제에서는 원호, 카디널 스플라인, 문자열 및 원형으로 구성된 경로를 그린 다음 채웁니다.  
  
 [!code-csharp[LinesCurvesAndShapes#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 다음 그림은 단색으로 채워진 부분과 그렇지 않은 부분을 갖는 경로를 보여 줍니다.  <xref:System.Drawing.Graphics.DrawPath%2A> 메서드를 통해 문자열의 텍스트 윤곽은 그렸지만 채워지지 않았습니다.  문자열 문자의 내부를 칠하는 것은 <xref:System.Drawing.Graphics.FillPath%2A> 메서드입니다.  
  
 ![경로의 문자열](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art26.png "Aboutgdip02\_art26")  
  
## 참고 항목  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Point?displayProperty=fullName>   
 [선, 곡선 및 도형](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [방법: 그리는 데 필요한 그래픽 개체 만들기](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [경로 구성 및 그리기](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)