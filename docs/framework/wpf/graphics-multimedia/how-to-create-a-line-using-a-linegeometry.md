---
title: "방법: LineGeometry를 사용하여 선 만들기 | Microsoft Docs"
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
  - "클래스, LineGeometry"
  - "그래픽[WPF], 선"
  - "LineGeometry 클래스"
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: LineGeometry를 사용하여 선 만들기
이 예제에서는 <xref:System.Windows.Media.LineGeometry> 클래스를 사용하여 선을 그리는 방법을 보여 줍니다.  <xref:System.Windows.Media.LineGeometry>는 시작점과 끝점으로 정의됩니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.LineGeometry>를 만들고 렌더링하는 방법을 보여 줍니다.  <xref:System.Windows.Shapes.Path> 요소는 선을 렌더링하는 데 사용됩니다.  선에는 면적이 없으므로 <xref:System.Windows.Shapes.Path> 개체의 <xref:System.Windows.Shapes.Shape.Fill%2A>을 지정하지 않고 대신 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성을 사용합니다.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![LineGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-line.png "graphicsmm\_line")  
\(10,20\)에서 \(100,130\) 사이에 그린 LineGeometry  
  
 다른 단순한 기하 도형 클래스로는 <xref:System.Windows.Media.LineGeometry> 및 <xref:System.Windows.Media.EllipseGeometry>가 있습니다.  이러한 기하 도형 및 보다 복잡한 기하 도형은 <xref:System.Windows.Media.PathGeometry> 또는 <xref:System.Windows.Media.StreamGeometry>를 사용하여 만들 수도 있습니다.  자세한 내용은 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)을 참조하십시오.  
  
## 참고 항목  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [복합 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [PathGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)