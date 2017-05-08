---
title: "방법: PathGeometry를 사용하여 도형 만들기 | Microsoft Docs"
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
  - "클래스, PathGeometry"
  - "그래픽[WPF], 도형"
  - "PathGeometry 클래스"
  - "도형, PathGeometry 클래스로 만들기"
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: PathGeometry를 사용하여 도형 만들기
이 예제에서는 <xref:System.Windows.Media.PathGeometry> 클래스를 사용하여 도형을 만드는 방법을 보여 줍니다.  <xref:System.Windows.Media.PathGeometry> 개체는 하나 이상의 <xref:System.Windows.Media.PathFigure> 개체로 구성되며 각 <xref:System.Windows.Media.PathFigure>는 다른 "모양"이나 도형을 나타냅니다.  각각의 <xref:System.Windows.Media.PathFigure>는 모양 또는 도형의 연결된 각 부분을 나타내는 하나 이상의 <xref:System.Windows.Media.PathSegment> 개체로 구성됩니다.  세그먼트 형식에는 <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment> 및 <xref:System.Windows.Media.BezierSegment>가 포함됩니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.PathGeometry>를 사용하여 삼각형을 만듭니다.  <xref:System.Windows.Shapes.Path> 요소를 사용하여 <xref:System.Windows.Media.PathGeometry>를 표시합니다.  
  
 [!code-xml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 다음 그림에서는 이전 예제에서 만든 도형을 보여 줍니다.  
  
 ![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.png "wcpsdk\_graphicsmm\_pathgeometry\_triangle")  
PathGeometry로 만든 삼각형  
  
 앞의 예제에서는 상대적으로 간단한 도형인 삼각형을 만드는 방법을 보여 주었습니다.  또한 <xref:System.Windows.Media.PathGeometry>를 사용하여 원호와 곡선을 비롯한 보다 복잡한 도형을 만들 수 있습니다.  자세한 내용은 [타원형 원호 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [입방형 3차원 곡선 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md) 및 [정방형 3차원 곡선 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)를 참조하십시오.  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Geometries 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Shapes.Path>   
 <xref:System.Windows.Media.GeometryDrawing>   
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [Geometries 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)