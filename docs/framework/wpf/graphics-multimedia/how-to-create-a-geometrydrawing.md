---
title: "방법: GeometryDrawing 만들기 | Microsoft Docs"
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
  - "클래스, GeometryDrawing"
  - "GeometryDrawing 클래스"
  - "그래픽, GeometryDrawing 클래스"
  - "렌더링 가능한 도형"
  - "도형, 렌더링 가능"
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: GeometryDrawing 만들기
이 예제에서는 <xref:System.Windows.Media.GeometryDrawing>을 만들고 표시하는 방법을 보여 줍니다.  <xref:System.Windows.Media.GeometryDrawing>을 사용하면 <xref:System.Windows.Media.Pen> 및 <xref:System.Windows.Media.Brush>를 <xref:System.Windows.Media.Geometry>와 연결하여 채우기 및 윤곽선이 있는 도형을 만들 수 있습니다.  <xref:System.Windows.Media.GeometryDrawing.Geometry%2A>는 도형의 구조를 설명하고 <xref:System.Windows.Media.GeometryDrawing.Brush%2A>는 도형의 채우기를 설명하며 <xref:System.Windows.Media.GeometryDrawing.Pen%2A>은 도형의 윤곽선을 설명합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.GeometryDrawing>을 사용하여 도형을 렌더링합니다.  도형은 <xref:System.Windows.Media.GeometryGroup> 및 두 개의 <xref:System.Windows.Media.EllipseGeometry> 개체로 설명됩니다.  도형의 내부는 <xref:System.Windows.Media.LinearGradientBrush>를 사용하여 칠하고, 윤곽은 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>을 사용하여 그립니다.  <xref:System.Windows.Media.GeometryDrawing>은 <xref:System.Windows.Media.ImageDrawing> 및 <xref:System.Windows.Controls.Image> 요소를 사용하여 표시합니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 다음 그림에서는 결과 <xref:System.Windows.Media.GeometryDrawing>을 보여 줍니다.  
  
 ![타원 두 개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
  
 보다 복잡한 그리기를 만들려면 <xref:System.Windows.Media.DrawingGroup>을 사용하여 여러 그리기 개체를 하나의 합성 그리기로 결합합니다.  
  
## 참고 항목  
 <xref:System.Windows.Media.DrawingGroup>   
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [합성 그리기 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)