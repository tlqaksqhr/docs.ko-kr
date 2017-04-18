---
title: "방법: 사각형 그리기 | Microsoft Docs"
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
  - "그리기, 사각형"
  - "그래픽[WPF], 사각형"
  - "사각형, 그리기"
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 사각형 그리기
이 예제에서는 <xref:System.Windows.Shapes.Rectangle> 요소를 사용하여 사각형을 그리는 방법을 보여 줍니다.  
  
 사각형을 그리려면 <xref:System.Windows.Shapes.Rectangle> 요소를 만든 다음 이 요소의 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>를 지정합니다.  사각형 내부를 칠하려면 <xref:System.Windows.Shapes.Shape.Fill%2A>을 설정합니다.  사각형에 윤곽선을 그리려면 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성을 사용합니다.  
  
 사각형의 모퉁이를 둥글게 처리하려면 선택적 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 및 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 속성을 지정합니다.  <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 및 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 속성은 사각형 모퉁이를 둥글게 하는 데 사용되는 타원의 x축과 y축 반경을 설정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas>에 두 개의 <xref:System.Windows.Shapes.Rectangle> 요소를 그립니다.  첫 번째 사각형에는 <xref:System.Windows.Media.Brushes.Blue%2A> 색상 내부가 적용되며  두 번째 사각형의 경우에는 <xref:System.Windows.Media.Brushes.Blue%2A> 색상 내부, <xref:System.Windows.Media.Brushes.Black%2A> 색상 윤곽선 및 둥근 모퉁이가 적용됩니다.  
  
## 예제  
 [!code-xml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 이 예제에서는 <xref:System.Windows.Controls.Canvas>에 사각형을 넣었지만 텍스트가 아닌 콘텐츠를 지원하는 모든 <xref:System.Windows.Controls.Panel> 및 <xref:System.Windows.Controls.Control>을 사각형 요소뿐만 아니라 기타 모든 도형 요소와 함께 사용할 수 있습니다.  사각형은 <xref:System.Windows.Controls.Grid> 패널의 일부에 사용되는 배경을 제공할 때 특히 유용합니다.  이에 대한 예제를 보려면 [표 개요](../../../../docs/framework/wpf/advanced/table-overview.md)를 참조하십시오.  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Shape Elements 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Shapes.Rectangle>   
 [Shape Elements 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)   
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [표 개요](../../../../docs/framework/wpf/advanced/table-overview.md)