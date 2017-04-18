---
title: "방법: 사각형 기하 도형의 모퉁이 둥글게 하기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "모퉁이, 반올림"
  - "그래픽, RectangleGeometry 개체의 모퉁이 둥글게"
  - "RectangleGeometry 클래스, 코너 둥글게"
  - "RectangleGeometry 개체의 모퉁이 둥글게"
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# 방법: 사각형 기하 도형의 모퉁이 둥글게 하기
<xref:System.Windows.Media.RectangleGeometry>의 모퉁이를 둥글게 하려면 <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> 및 <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> 속성을 0보다 큰 값으로 설정합니다.  값이 클수록 사각형의 모퉁이가 더 둥글게 됩니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> 및 <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> 설정이 서로 다른 몇 가지 <xref:System.Windows.Media.RectangleGeometry> 개체를 보여 줍니다.  <xref:System.Windows.Media.RectangleGeometry> 개체는 <xref:System.Windows.Shapes.Path> 요소를 사용하여 표시됩니다.  
  
 [!code-xml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![여러 RadiusX&#47;RadiusY 설정의 사각형](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm\_rounded")  
모퉁이가 둥근 사각형  
  
## 참고 항목  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)   
 [복합 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)   
 [PathGeometry를 사용하여 도형 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)