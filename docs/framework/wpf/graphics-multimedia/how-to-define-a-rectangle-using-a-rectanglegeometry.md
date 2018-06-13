---
title: '방법: RectangleGeometry를 사용하여 사각형 정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rectangles
- rectangles [WPF], creating with RectangleGeometry class
ms.assetid: e40b8a8e-54b8-416b-a9f2-be6dca9fdf0b
ms.openlocfilehash: 5d2ec6aec1eea8528ea6b43f72f4820b8bc19a37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560425"
---
# <a name="how-to-define-a-rectangle-using-a-rectanglegeometry"></a>방법: RectangleGeometry를 사용하여 사각형 정의
이 예제에 사용 하는 방법에 설명 된 <xref:System.Windows.Media.RectangleGeometry> 사각형을 설명 하는 클래스입니다.  
  
## <a name="example"></a>예제  
 만들고 렌더링 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.RectangleGeometry>합니다.  정의 된 상대적 위치와 사각형의 크기는 <xref:System.Windows.Rect> 구조입니다. 상대적 위치는 `50,50` 고 높이 너비를 모두 `25` 는 정사각형을 만듭니다. 사각형의 내부로 그려집니다는 <xref:System.Windows.Media.Brushes.LemonChiffon%2A> 로 브러시 및 윤곽선을 그리는 <xref:System.Windows.Media.Brushes.Black%2A> 스트로크 두께를 `1`합니다.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmrectanglegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmrectanglegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMRectangleGeometryExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmrectanglegeometryexample)]  
  
 ![RectangleGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rectangle.gif "graphicsmm_rectangle")  
RectangleGeometry  
  
 이 예에서는 사용 되지만 <xref:System.Windows.Shapes.Path> 요소를 렌더링 하는 <xref:System.Windows.Media.RectangleGeometry>, 여러 가지 다른 방법으로 사용 하도록 <xref:System.Windows.Media.RectangleGeometry> 개체입니다. 예를 들어 한 <xref:System.Windows.Media.RectangleGeometry> 는 지정 하는 데 사용할 수는 <xref:System.Windows.UIElement.Clip%2A> 의 <xref:System.Windows.UIElement> 또는 <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 의 <xref:System.Windows.Media.GeometryDrawing>합니다.  
  
 다른 간단한 기 하 도형 클래스 포함 <xref:System.Windows.Media.LineGeometry> 및 <xref:System.Windows.Media.EllipseGeometry>합니다. 이 기 하이 도형 뿐만 아니라 더 복잡 한 프로젝트로 만들 수도 있습니다를 사용 하는 <xref:System.Windows.Media.PathGeometry> 또는 <xref:System.Windows.Media.StreamGeometry>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [복합 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [PathGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
