---
title: '방법: Polygon 요소를 사용하여 닫힌 도형 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 4105139e159783cf0197f4e56c82001835077cbf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559464"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>방법: Polygon 요소를 사용하여 닫힌 도형 그리기
사용 하 여 닫힌된 셰이프를 그리는 방법을 보여 주는이 예제는 <xref:System.Windows.Shapes.Polygon> 요소입니다. 폐쇄형된 도형 그리기를 만들는 <xref:System.Windows.Shapes.Polygon> 요소 및 사용 하 여 해당 <xref:System.Windows.Shapes.Polygon.Points%2A> 속성을 통해 도형의 꼭지점을 지정 합니다. 선이 그려집니다 자동으로 첫 번째 및 마지막 점을 연결 하는 없습니다. 마지막으로 지정 된 <xref:System.Windows.Shapes.Shape.Fill%2A>, 즉 <xref:System.Windows.Shapes.Shape.Stroke%2A>, 또는 둘 다 합니다.  
  
## <a name="example"></a>예제  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], 지점에 대 한 유효한 구문은 공백으로 구분 된 목록 쉼표로 구분 된 x 및 y 좌표 쌍입니다.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 이 예제에서는 사용 하지는 않지만 <xref:System.Windows.Controls.Canvas> 다각형을 포함 하는 데 다각형 요소 (및 다른 모든 셰이프 요소) 함께 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 비 텍스트 콘텐츠를 지 원하는 합니다.  
  
 이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.
