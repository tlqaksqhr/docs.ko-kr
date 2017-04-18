---
title: "방법: 정방형 3차원 곡선 만들기 | Microsoft Docs"
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
  - "베지어 곡선, 만들기"
  - "그래픽[WPF], 정방형 베지어 곡선"
  - "정방형 베지어 곡선, 만들기"
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 정방형 3차원 곡선 만들기
이 예제에서는 정방형 3차원 곡선을 만드는 방법을 보여 줍니다.  정방형 3차원 곡선을 만들려면 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> 및 <xref:System.Windows.Media.QuadraticBezierSegment> 클래스를 사용합니다.  
  
## 예제  
 다음 예제에서는 \(10,100\) 지점에서 \(300,100\) 지점까지 정방형 3차원 곡선을 그립니다.  이 곡선의 제어점은 \(200,200\)입니다.  
  
 \[xaml\]  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 특성 구문을 사용하여 경로를 나타낼 수 있습니다.  
  
 [!code-xml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 \[xaml\]  
  
 실제로 이 특성 구문은 <xref:System.Windows.Media.PathGeometry>의 단순화된 버전인 <xref:System.Windows.Media.StreamGeometry>를 만듭니다.  자세한 내용은 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지를 참조하십시오.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 개체 요소 구문을 사용하여 정방형 3차원 곡선을 그릴 수도 있습니다.  다음은 앞의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 예제와 동일합니다.  
  
 [!code-xml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 이 예제는 큰 샘플의 일부입니다. 전체 샘플을 보려면 [Geometries 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하십시오.  
  
## 참고 항목  
 [타원형 원호 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)   
 [입방형 3차원 곡선 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)