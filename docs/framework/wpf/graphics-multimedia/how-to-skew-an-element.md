---
title: "방법: 요소 기울이기 | Microsoft Docs"
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
  - "클래스, SkewTransform"
  - "그래픽, 요소 기울이기"
  - "요소 기울이기"
  - "SkewTransform 클래스"
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 요소 기울이기
이 예제에서는 <xref:System.Windows.Media.SkewTransform>을 사용하여 요소를 기울이는 방법을 보여 줍니다.  개체 기울이기라고도 하는 [기울이기](GTMT)는 균일하지 않은 방식으로 좌표 공간을 늘리는 변환입니다.  <xref:System.Windows.Media.SkewTransform>은 일반적으로 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] 개체에 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 깊이를 시뮬레이션하는 데 사용합니다.  
  
 <xref:System.Windows.Media.SkewTransform.CenterX%2A> 및 <xref:System.Windows.Media.SkewTransform.CenterY%2A> 속성을 사용하여 <xref:System.Windows.Media.SkewTransform>의 중점을 지정합니다.  
  
 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 및 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 속성을 사용하여 x, y축의 기울기 각도를 지정하여 이 축에 따라 현재 좌표계를 기울입니다.  
  
 <xref:System.Windows.Media.SkewTransform.AngleX%2A>는 원래 좌표계를 기준으로 x축의 값을 기울이므로 기울이기 변환의 결과를 예측할 수 있습니다.  따라서 <xref:System.Windows.Media.SkewTransform.AngleX%2A>가 30도이면 y축은 원점을 통과하면서 30도 회전하고 x축 값은 해당 원점을 기준으로 30도 기울어집니다.  마찬가지로, <xref:System.Windows.Media.SkewTransform.AngleY%2A>가 30도이면 도형의 y축 값이 원점을 기준으로 30도 기울어집니다.  좌표계를 x축이나 y축으로 30도 이동하는 경우에는 이와 다른 결과가 발생합니다.  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle>을 중점 \(0,0\)으로부터 가로로 45도 기울입니다.  
  
## 예제  
 [!code-xml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle>을 중점 \(25,25\)로부터 가로로 45도 기울입니다.  
  
 [!code-xml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 다음 예제에서는 <xref:System.Windows.Shapes.Rectangle>을 중점 \(25,25\)로부터 세로로 45도 기울입니다.  
  
 [!code-xml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 다음 그림에서는 이 예제에 사용된 다양한 기울이기를 보여 줍니다.  
  
 ![SkewTransform 예제](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.png "img\_wcpsdk\_graphicsmm\_skewtransformexample")  
세 가지 SkewTransform의 예  
  
 전체 샘플을 보려면 [2\-D Transforms 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.SkewTransform>   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)