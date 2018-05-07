---
title: '방법: Polyline 요소를 사용하여 다중선 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- connected lines [WPF]
- polylines [WPF], drawing
- graphics [WPF], polylines
- lines [WPF], connected (see polylines)
- drawing [WPF], polylines
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
ms.openlocfilehash: 2abfa29f7aca4bfc8c5f91e36fd974093a98a9e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-polyline-by-using-the-polyline-element"></a>방법: Polyline 요소를 사용하여 다중선 그리기
사용 하 여 일련의 연결 된 줄은 다중선 그리는 방법을 보여 주는이 예제는 <xref:System.Windows.Shapes.Polyline> 요소입니다.  
  
 다중선을 그리려면 만들기는 <xref:System.Windows.Shapes.Polyline> 요소 및 사용 하 여 해당 <xref:System.Windows.Shapes.Polyline.Points%2A> 속성을 통해 이러한 셰이프 기능을 지정 합니다. 마지막으로 사용 하 여는 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 획 줄에 표시 되지 않으므로 폴리라인에서 설명 하는 속성에 간략하게 설명 합니다.  
  
> [!NOTE]
>  때문에 <xref:System.Windows.Shapes.Polyline> 요소는 닫힌된 셰이프는 <xref:System.Windows.Shapes.Shape.Fill%2A> 도형 윤곽선을 의도적으로 종결 하는 경우에 속성에 적용 되지 않습니다. 와 닫힌된 셰이프를 만들려면는 <xref:System.Windows.Shapes.Shape.Fill%2A>를 사용 하 여 한 <xref:System.Windows.Shapes.Polygon> 요소입니다.  
  
 다음 예제에서는 두 개의 그립니다 <xref:System.Windows.Shapes.Polyline> 내부 요소는 <xref:System.Windows.Controls.Canvas>합니다.  
  
## <a name="example"></a>예제  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 지점에 대 한 유효한 구문은 공백으로 구분 된 목록 쉼표로 구분 된 x 및 y 좌표 쌍입니다.  
  
 [!code-xaml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 이 예제에서는 한 <xref:System.Windows.Controls.Canvas> 다중선을 포함 하 여 사용할 수 있습니다 폴리라인 요소 (및 다른 모든 셰이프 요소) 함께 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 비 텍스트 콘텐츠를 지 원하는 합니다.  
  
 이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Shapes.Polygon>  
 <xref:System.Windows.Shapes.Shape>  
 [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)  
 [WPF에서 Shape 및 기본 그리기 개요](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)
