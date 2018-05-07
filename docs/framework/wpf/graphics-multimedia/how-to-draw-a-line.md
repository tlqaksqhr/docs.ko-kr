---
title: '방법: 선 그리기'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: 1093e754912cd3ee3b8474ed7d190913079a9f9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-a-line"></a>방법: 선 그리기
이 예제를 사용 하 여 선을 그리는 방법을 보여 줍니다.는 <xref:System.Windows.Shapes.Line> 요소입니다.  
  
 줄을 그리려면 만들기는 <xref:System.Windows.Shapes.Line> 요소입니다. 사용 하 여 해당 <xref:System.Windows.Shapes.Line.X1%2A> 및 <xref:System.Windows.Shapes.Line.Y1%2A> 시작점; 설정 및 사용 하는 속성의 <xref:System.Windows.Shapes.Line.X2%2A> 및 <xref:System.Windows.Shapes.Line.Y2%2A> 끝점을 설정 하는 속성입니다. 마지막으로 설정 해당 <xref:System.Windows.Shapes.Shape.Stroke%2A> 및 <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 획 줄에 표시 되지 않으므로 합니다.  
  
 설정의 <xref:System.Windows.Shapes.Shape.Fill%2A> 선에 대 한 요소에는 줄 없는 내부에 있기 때문에 적용 되지 않습니다.  
  
 다음 예제에서는 내 세 개의 선을 그립니다는 <xref:System.Windows.Controls.Canvas> 요소입니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Shapes.Line>  
 [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)
