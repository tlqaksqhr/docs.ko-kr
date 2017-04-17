---
title: "방법: Polyline 요소를 사용하여 다중선 그리기 | Microsoft Docs"
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
  - "연결된 선"
  - "그리기, 다중선"
  - "그래픽[WPF], 다중선"
  - "선, 연결됨(다중선 참조)"
  - "다중선, 그리기"
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Polyline 요소를 사용하여 다중선 그리기
이 예제에서는 <xref:System.Windows.Shapes.Polyline> 요소를 사용하여 다중선을 그리는 방법을 보여 줍니다. 다중선이란 연결된 일련의 선을 말합니다.  
  
 다중선을 그리려면 <xref:System.Windows.Shapes.Polyline> 요소를 만든 다음 요소의 <xref:System.Windows.Shapes.Polyline.Points%2A> 속성을 사용하여 도형의 꼭짓점을 지정합니다.  스트로크가 없는 선은 표시되지 않으므로 마지막 작업으로 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성을 사용하여 다중선의 윤곽을 나타냅니다.  
  
> [!NOTE]
>  <xref:System.Windows.Shapes.Polyline> 요소는 닫힌 도형이 아니므로 도형 윤곽을 의도적으로 닫더라도 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성이 아무런 영향을 주지 않습니다.  <xref:System.Windows.Shapes.Shape.Fill%2A>을 사용하여 닫힌 도형을 만들려면 <xref:System.Windows.Shapes.Polygon> 요소를 사용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas> 안에 두 개의 <xref:System.Windows.Shapes.Polyline> 요소를 그립니다.  
  
## 예제  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 점에 유효한 구문은 x, y 좌표 쌍의 공백으로 구분된 목록입니다.  
  
 [!code-xml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 이 예제에서는  <xref:System.Windows.Controls.Canvas>를 사용하여 다중선을 포함하지만 텍스트 이외의 콘텐츠를 지원하는 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control>과 함께 다중선 요소 및 다른 도형 요소를 사용할 수도 있습니다.  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Shape Elements 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Shapes.Polyline>   
 <xref:System.Windows.Shapes.Polygon>   
 <xref:System.Windows.Shapes.Shape>   
 [Shape Elements 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)   
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)