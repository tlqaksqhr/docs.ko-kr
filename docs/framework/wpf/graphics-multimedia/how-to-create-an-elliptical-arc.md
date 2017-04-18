---
title: "방법: 타원형 원호 만들기 | Microsoft Docs"
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
  - "원호, 타원형"
  - "타원형 원호, 만들기"
  - "그래픽[WPF], 타원형 원호"
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 타원형 원호 만들기
이 예제에서는 타원형 원호를 그리는 방법을 보여 줍니다.  타원형 원호를 만들려면 <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> 및 <xref:System.Windows.Media.ArcSegment> 클래스를 사용합니다.  
  
## 예제  
 다음 예제에서는 \(10,100\)에서 \(200,100\)까지 타원형 원호를 그립니다.  이 원호의 <xref:System.Windows.Media.ArcSegment.Size%2A>는 장치에 관계없이 100 x 50 픽셀이고 <xref:System.Windows.Media.ArcSegment.RotationAngle%2A>은 45도이며 <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> 설정은 `true`이고 <xref:System.Windows.Media.ArcSegment.SweepDirection%2A>은 <xref:System.Windows.Media.SweepDirection>입니다.  
  
 \[xaml\]  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]에서는 특성 구문을 사용하여 경로를 나타낼 수 있습니다.  
  
 [!code-xml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 \[xaml\]  
  
 실제로 이 특성 구문은 <xref:System.Windows.Media.PathGeometry>의 단순화된 버전인 <xref:System.Windows.Media.StreamGeometry>를 만듭니다.  자세한 내용은 [경로 태그 구문](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) 페이지를 참조하십시오.  
  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 개체 태그를 명시적으로 사용하여 타원형 원호를 그릴 수도 있습니다.  다음은 앞의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그와 동일한 결과를 가져옵니다.  
  
 [!code-xml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 이 예제는 보다 큰 예제의 일부입니다.  전체 샘플을 보려면 [Geometries 샘플](http://go.microsoft.com/fwlink/?LinkID=159989)을 참조하십시오.  
  
## 참고 항목  
 [정방형 3차원 곡선 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)   
 [입방형 3차원 곡선 만들기](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)