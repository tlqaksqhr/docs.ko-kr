---
title: '방법: PathGeometry를 사용하여 도형 만들기'
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], creating with PathGeometry class
- graphics [WPF], shapes
ms.assetid: 49a4a8b7-e738-45be-8dac-b54a6d8f5b21
ms.openlocfilehash: 6c77844b054dd89a0c3f3cbecd0725968df9ae71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-shape-by-using-a-pathgeometry"></a>방법: PathGeometry를 사용하여 도형 만들기
사용 하 여 도형을 만드는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.PathGeometry> 클래스입니다. <xref:System.Windows.Media.PathGeometry> 개체는 하나 이상의 구성 됩니다 <xref:System.Windows.Media.PathFigure> 객체; 각 <xref:System.Windows.Media.PathFigure> 다른 "그림" 또는 셰이프를 나타냅니다. 각 <xref:System.Windows.Media.PathFigure> 은 자체 구성 된 하나 이상의 <xref:System.Windows.Media.PathSegment> 각각 또는 도형의의 연결 된 부분을 나타내는 개체입니다. 세그먼트 종류 <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.ArcSegment>, 및 <xref:System.Windows.Media.BezierSegment>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 <xref:System.Windows.Media.PathGeometry> 삼각형이 생성 합니다. <xref:System.Windows.Media.PathGeometry> 를 사용 하 여 표시 되는 <xref:System.Windows.Shapes.Path> 요소입니다.  
  
 [!code-xaml[GeometrySample#49](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#49)]  
  
 다음 그림은 이전 예제에서 만든 도형을 보여 줍니다.  
  
 ![PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-pathgeometry-triangle.gif "wcpsdk_graphicsmm_pathgeometry_triangle")  
PathGeometry를 사용 하 여 만든 삼각형  
  
 앞의 예제에는 상대적으로 간단한 도형을, 삼각형을 만드는 방법을 보여 주었습니다. A <xref:System.Windows.Media.PathGeometry> 곡선을 포함 하는 보다 복잡 한 셰이프를 만들려면 사용할 수도 있습니다. 예제를 보려면 [타원형 호를 만들](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md), [입방 형 3 차원 곡선을 만들](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md), 및 [정방형 3 차원 곡선을 만들](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)합니다.  
  
 이 예제는 더 큰 샘플에 속합니다. 전체 샘플을 보려면 [기하 도형 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.GeometryDrawing>  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [기 하 도형 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)
