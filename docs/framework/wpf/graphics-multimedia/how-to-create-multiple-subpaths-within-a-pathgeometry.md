---
title: "방법: PathGeometry 내에 다중 하위 경로 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "클래스, PathGeometry"
  - "그래픽[WPF], 하위 경로"
  - "여러 하위 경로"
  - "PathGeometry 클래스"
  - "하위 경로"
ms.assetid: 104a862c-dde2-4e62-ac87-80660dd1681c
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: PathGeometry 내에 다중 하위 경로 만들기
이 예제에서는 <xref:System.Windows.Media.PathGeometry>에 여러 하위 경로를 만드는 방법을 보여 줍니다.  여러 하위 경로를 만들려면 각 하위 경로에 대해 <xref:System.Windows.Media.PathFigure>를 만듭니다.  
  
## 예제  
 다음 예제에서는 각각 하나의 삼각형을 이루는 하위 경로 두 개를 만듭니다.  
  
 [!code-xml[GeometrySample#38](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#38)]  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Path> 및 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 특성 구문을 사용하여 여러 하위 경로를 만드는 방법을 보여 줍니다.  각 `M`은 예제에서 각각 삼각형을 그리는 두 개의 하위 경로를 만들 수 있도록 새 하위 경로를 만듭니다.  
  
 [!code-xml[GeometrySample#58](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#58)]  
  
 실제로 이 특성 구문은 <xref:System.Windows.Media.PathGeometry>의 단순화된 버전인 <xref:System.Windows.Media.StreamGeometry>를 만듭니다.  자세한 내용은 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지를 참조하십시오.  
  
## 참고 항목  
 [Geometry 개요](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)