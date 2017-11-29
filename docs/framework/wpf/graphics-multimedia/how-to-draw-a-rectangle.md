---
title: "방법: 사각형 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], rectangles
- graphics [WPF], rectangles
- rectangles [WPF], drawing
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c163897af27c9b34c8cd87a3b197047f86d21ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-rectangle"></a>방법: 사각형 그리기
사용 하 여 사각형을 그리는 방법을 보여 주는이 예제는 <xref:System.Windows.Shapes.Rectangle> 요소입니다.  
  
 사각형을 그리려면 만들기는 <xref:System.Windows.Shapes.Rectangle> 요소를 지정 하 고 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>합니다. 사각형의 내부를 그리는 데 설정 해당 <xref:System.Windows.Shapes.Shape.Fill%2A>합니다. 사각형 윤곽선을 부여 하려면 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성입니다.  
  
 모퉁이가 둥근 사각형을 선택적 지정 <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 및 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 속성입니다. <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> 및 <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> 사각형의 모퉁이 둥글게 하는 데 사용 되는 타원의 x 축과 y 반지름 속성을 설정 합니다.  
  
 다음 예제에서는 두 개의 <xref:System.Windows.Shapes.Rectangle> 요소를 그립니다는 <xref:System.Windows.Controls.Canvas>합니다. 첫 번째 사각형에는 <xref:System.Windows.Media.Brushes.Blue%2A> 내부 합니다. 두 번째 사각형에는 <xref:System.Windows.Media.Brushes.Blue%2A> 내부는 <xref:System.Windows.Media.Brushes.Black%2A> 윤곽선 및 모서리가 둥근된 합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 이 예제에서는 한 <xref:System.Windows.Controls.Canvas> 사각형을 포함 하도록 사용할 수 있습니다 사각형 요소 (및 다른 모든 셰이프 요소) 함께 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 비 텍스트 콘텐츠를 지 원하는 합니다. 사각형은 부분에 대해 배경을 제공 하는 데 특히 유용 실제로 <xref:System.Windows.Controls.Grid> 패널입니다. 예를 들어 참조는 [테이블 개요](../../../../docs/framework/wpf/advanced/table-overview.md)합니다.  
  
 이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Shapes.Rectangle>  
 [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)  
 [테이블 개요](../../../../docs/framework/wpf/advanced/table-overview.md)
