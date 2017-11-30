---
title: "방법: 타원 또는 원 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ellipses [WPF], drawing
- circles [WPF], drawing
- drawing circles [WPF]
- drawing ellipses [WPF]
- graphics [WPF], drawing circles
- graphics [WPF], drawing ellipses
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4da623c34b4c3b84dee0f02d631d032eb1c061d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-ellipse-or-a-circle"></a>방법: 타원 또는 원 그리기
Ellipses 및 원을 사용 하 여 그리는 방법을 보여 주는이 예제는 <xref:System.Windows.Shapes.Ellipse> 요소입니다. 타원을 그리려면 만들기는 <xref:System.Windows.Shapes.Ellipse> 요소를 지정 하 고 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A>합니다. 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.Fill%2A> 속성을 통해 지정 된 <xref:System.Windows.Media.Brush> 타원의 내부를 그리는 데 사용 되는 합니다. 사용 하 여 해당 <xref:System.Windows.Shapes.Shape.Stroke%2A> 속성을 통해 지정 된 <xref:System.Windows.Media.Brush> 타원의 윤곽선을 칠하는 데 사용 되는 합니다. <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> 속성 타원 윤곽선 두께 지정 합니다.  
  
 원을 그리려면는 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 의 <xref:System.Windows.Shapes.Ellipse> 서로 다른 요소입니다.  
  
 다음 예제에서는 네 개의 <xref:System.Windows.Shapes.Ellipse> 내의 요소는 <xref:System.Windows.Controls.Canvas>합니다.  
  
## <a name="example"></a>예제  
 [!code-xaml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 이 예제에서는 한 <xref:System.Windows.Controls.Canvas> 에 줄임표 포함 되어 있습니다 수 타원 요소 (및 다른 모든 셰이프 요소)과 함께 사용할 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.Control> 비 텍스트 콘텐츠를 지 원하는 합니다.  
  
 이 예제는 보다 큰 예제의 일부 전체 샘플을 참조 하십시오. [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Shapes.Ellipse>  
 <xref:System.Windows.Shapes.Shape>  
 [셰이프 요소 샘플](http://go.microsoft.com/fwlink/?LinkID=160037)
