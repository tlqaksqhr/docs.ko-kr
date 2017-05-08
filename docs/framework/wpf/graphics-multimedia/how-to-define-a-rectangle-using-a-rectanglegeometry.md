---
title: "방법: RectangleGeometry를 사용하여 사각형 정의 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "클래스, RectangleGeometry"
  - "그래픽[WPF], 사각형"
  - "RectangleGeometry 클래스"
  - "사각형, RectangleGeometry 클래스로 만들기"
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: RectangleGeometry를 사용하여 사각형 정의
이 예제에서는 <xref:System.Windows.Media.RectangleGeometry> 클래스를 사용하여 사각형을 설명하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.RectangleGeometry>를 만들고 렌더링하는 방법을 보여 줍니다.  사각형의 상대적 위치와 크기는 <xref:System.Windows.Rect> 구조체를 사용하여 정의합니다.  상대적 위치는 `50,50`으로 지정하고 높이와 너비를 모두 `25`로 지정하여 정사각형을 만듭니다.  사각형의 내부는 <xref:System.Windows.Media.Brushes.LemonChiffon%2A> 브러시를 사용하여 칠하고 사각형의 윤곽선은 두께가 `1`인 <xref:System.Windows.Media.Brushes.Black%2A> 스트로크를 사용하여 그립니다.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.png "graphicsmm\_rectangle")  
RectangleGeometry  
  
 이 예제에서는 <xref:System.Windows.Shapes.Path> 요소를 사용하여 <xref:System.Windows.Media.RectangleGeometry>를 렌더링하지만 <xref:System.Windows.Media.RectangleGeometry> 개체를 사용하는 다른 방법도 많이 있습니다.  예를 들어 <xref:System.Windows.UIElement>의 <xref:System.Windows.UIElement.Clip%2A> 또는 <xref:System.Windows.Media.GeometryDrawing>의 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A>를 지정하는 데 <xref:System.Windows.Media.RectangleGeometry>를 사용할 수 있습니다.  
  
 다른 단순한 기하 도형 클래스로는 <xref:System.Windows.Media.LineGeometry> 및 <xref:System.Windows.Media.EllipseGeometry>가 있습니다.  이러한 기하 도형 및 보다 복잡한 기하 도형은 <xref:System.Windows.Media.PathGeometry> 또는 <xref:System.Windows.Media.StreamGeometry>를 사용하여 만들 수도 있습니다.  
  
## 참고 항목  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [복합 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [PathGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)