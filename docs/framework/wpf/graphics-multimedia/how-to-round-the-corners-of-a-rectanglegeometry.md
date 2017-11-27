---
title: "방법: 사각형 기하 도형의 모퉁이 둥글게 하기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cd857f7ce886095bcbe92ae57c350ce83bb5c7d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a>방법: 사각형 기하 도형의 모퉁이 둥글게 하기
모퉁이 둥글게 하는 <xref:System.Windows.Media.RectangleGeometry>설정, 해당 <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> 및 <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> 속성을 0 보다 큰 값입니다. 이 값이 클수록 더 둥글게 사각형의 모퉁이입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 몇 가지 <xref:System.Windows.Media.RectangleGeometry> 서로 다른 개체 <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> 및 <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> 설정 합니다. <xref:System.Windows.Media.RectangleGeometry> 개체를 사용 하 여 표시 <xref:System.Windows.Shapes.Path> 요소입니다.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![여러 RadiusX &#47;의 사각형 RadiusY 설정](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")  
모퉁이가 둥근 사각형  
  
## <a name="see-also"></a>참고 항목  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [복합 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [PathGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
