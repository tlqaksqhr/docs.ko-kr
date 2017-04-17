---
title: "방법: Polygon 요소를 사용하여 닫힌 도형 그리기 | Microsoft Docs"
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
  - "닫힌 도형, Polygon 요소로 그리기"
  - "그리기, Polygon 요소가 포함된 닫힌 도형"
  - "그래픽, Polygon 요소"
  - "Polygon 요소"
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: Polygon 요소를 사용하여 닫힌 도형 그리기
이 예제에서는 <xref:System.Windows.Shapes.Polygon> 요소를 사용하여 닫힌 도형을 그리는 방법을 보여 줍니다.  닫힌 도형을 그리려면 <xref:System.Windows.Shapes.Polygon> 요소를 만든 다음 요소의 <xref:System.Windows.Shapes.Polygon.Points%2A> 속성을 사용하여 도형의 꼭짓점을 지정합니다.  첫 번째 점과 마지막 점을 연결하는 선이 자동으로 그려집니다.  마지막으로 <xref:System.Windows.Shapes.Shape.Fill%2A>이나 <xref:System.Windows.Shapes.Shape.Stroke%2A>를 지정하거나 둘 모두를 지정합니다.  
  
## 예제  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서 점에 유효한 구문은 x, y 좌표 쌍의 공백으로 구분된 목록입니다.  
  
 [!code-xml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 이 예제에서는 <xref:System.Windows.Controls.Canvas>를 사용하여 다각형을 포함하지만 텍스트 이외의 콘텐츠를 지원하는 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control>과 함께 다각형 요소 및 다른 도형 요소를 사용할 수도 있습니다.  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Shape Elements 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)을 참조하십시오.