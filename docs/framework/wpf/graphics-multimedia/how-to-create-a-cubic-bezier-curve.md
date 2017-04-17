---
title: "방법: 입방형 3차원 곡선 만들기 | Microsoft Docs"
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
  - "베지어 곡선, 입방형"
  - "만들기, 입방형 3차원 곡선"
  - "입방형 3차원 곡선"
  - "곡선, 입방형 3차원"
  - "그래픽, 입방형 3차원 곡선"
ms.assetid: 450a3a77-7c57-48b0-a008-0f6051add980
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 입방형 3차원 곡선 만들기
이 예제에서는 입방형 3차원 곡선을 만드는 방법을 보여 줍니다.  입방형 3차원 곡선을 만들려면 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> 및 <xref:System.Windows.Media.BezierSegment> 클래스를 사용합니다.  결과 기하 도형을 표시하려면 <xref:System.Windows.Shapes.Path> 요소를 단독으로 사용하거나 <xref:System.Windows.Media.GeometryDrawing> 또는 <xref:System.Windows.Media.DrawingContext>와 함께 사용합니다.  다음 예제에서는 \(10,100\) 지점에서 \(300,100\) 지점까지 입방형 3차원 곡선을 그립니다.  이 곡선의 제어점은 \(100, 0\) 및 \(200, 200\)입니다.  
  
## 예제  
 \[xaml\]  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 약식 태그 구문을 사용하여 경로를 나타낼 수 있습니다.  
  
 [!code-xml[GeometrySample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#53)]  
  
 \[xaml\]  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 개체 태그를 사용하여 입방형 3차원 곡선을 그릴 수도 있습니다.  다음은 앞의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제와 동일합니다.  
  
 [!code-xml[GeometrySample#33](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#33)]  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Geometries 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하십시오.  
  
## 참고 항목  
 [타원형 원호 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)   
 [PathGeometry에 LineSegment 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-linesegment-in-a-pathgeometry.md)   
 [Create a Cubic Bezier Curve](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)   
 [정방형 3차원 곡선 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)