---
title: "방법: GeometryDrawing 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31417a3eeee2c1e61674c43558c2799705797c35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-geometrydrawing"></a>방법: GeometryDrawing 만들기
만들고 표시 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.GeometryDrawing>합니다. A <xref:System.Windows.Media.GeometryDrawing> 채우기 개요와 연결 하 여 셰이프를 만들 수 있습니다는 <xref:System.Windows.Media.Pen> 및 <xref:System.Windows.Media.Brush> 와 <xref:System.Windows.Media.Geometry>합니다. <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> 도형의 구조를 설명는 <xref:System.Windows.Media.GeometryDrawing.Brush%2A> 도형의 채우기 설명 및 <xref:System.Windows.Media.GeometryDrawing.Pen%2A> 도형의 윤곽선에 설명 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.Windows.Media.GeometryDrawing> 셰이프를 렌더링 합니다. 모양을 설명는 <xref:System.Windows.Media.GeometryGroup> 와 두 개의 <xref:System.Windows.Media.EllipseGeometry> 개체입니다. 도형의 내부가 그려지는와 <xref:System.Windows.Media.LinearGradientBrush> 윤곽선을 사용 하 여 그린 및는 <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>합니다. <xref:System.Windows.Media.GeometryDrawing> 를 사용 하 여 표시 되는 <xref:System.Windows.Media.ImageDrawing> 및 <xref:System.Windows.Controls.Image> 요소입니다.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 다음 그림과 결과 <xref:System.Windows.Media.GeometryDrawing>합니다.  
  
 ![개의 GeometryDrawing](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 보다 복잡 한 그리기를 만들려면 여러 그리기 개체를 사용 하 여 그리기 단일 복합 결합할 수 있습니다는 <xref:System.Windows.Media.DrawingGroup>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.DrawingGroup>  
 [Drawing 개체 개요](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [합성 그리기 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
