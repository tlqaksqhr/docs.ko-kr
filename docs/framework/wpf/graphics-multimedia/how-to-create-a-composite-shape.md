---
title: "방법: 복합 도형 만들기 | Microsoft Docs"
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
  - "복합 도형"
  - "그래픽, 복합 도형"
  - "도형, 복합"
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 복합 도형 만들기
이 예제에서는 <xref:System.Windows.Media.Geometry> 개체를 사용하여 복합 도형을 만들고 <xref:System.Windows.Shapes.Path> 요소를 사용하여 이를 표시하는 방법을 보여 줍니다.  다음 예제에서는 <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry> 및 <xref:System.Windows.Media.RectangleGeometry>를 <xref:System.Windows.Media.GeometryGroup>과 함께 사용하여 복합 도형을 만듭니다.  그런 다음 <xref:System.Windows.Shapes.Path> 요소를 사용하여 기하 도형을 그립니다.  
  
## 예제  
 [!code-xml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 다음 그림에서는 이전 예제에서 만든 도형을 보여 줍니다.  
  
 ![GeometryGroup을 사용하여 만든 복잡 기하 도형](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.png "wcpsdk\_graphicsmm\_compositegeometryexample1")  
복합 기하 도형  
  
 다각형 및 곡선 세그먼트가 있는 도형과 같은 더 복잡한 도형은 <xref:System.Windows.Media.PathGeometry>를 사용하여 만들 수 있습니다.  <xref:System.Windows.Media.PathGeometry>를 사용하여 도형을 만드는 방법을 보여 주는 예제는 [PathGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)를 참조하십시오.  이 예제에서는 <xref:System.Windows.Shapes.Path> 요소를 사용하여 도형을 화면에 렌더링하지만, <xref:System.Windows.Media.Geometry> 개체를 사용하여 <xref:System.Windows.Media.GeometryDrawing> 또는 <xref:System.Windows.Media.DrawingContext>의 콘텐츠를 설명할 수도 있습니다.  또한 클리핑 및 적중 테스트에도 사용할 수 있습니다.  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Geometries 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하십시오.