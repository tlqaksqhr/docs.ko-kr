---
title: "방법: 요소 배율 조정 | Microsoft Docs"
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
  - "클래스, ScaleTransform"
  - "그래픽, 요소 배율 조정"
  - "ScaleTransform 클래스"
  - "배율, 요소"
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 요소 배율 조정
이 예제에서는 <xref:System.Windows.Media.ScaleTransform>을 사용하여 요소의 배율을 조정하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성을 사용하여 지정한 배율로 요소의 크기를 조정할 수 있습니다.  예를 들어 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 값으로 1.5를 지정하면 요소 너비가 원래 너비의 150%로 늘려지고,  <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 값으로 0.5를 지정하면 요소 높이가 50%까지 줄어듭니다.  
  
 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 속성을 사용하여 배율 조정 작업의 중점을 지정할 수 있습니다.  기본적으로 <xref:System.Windows.Media.ScaleTransform>의 중점은 사각형의 왼쪽 위 모퉁이에 해당하는 지점\(0,0\)입니다.  이는 요소를 이동하고 더 크게 보이도록 만드는 효과를 내는데, <xref:System.Windows.Media.Transform>을 적용할 때는 개체가 위치한 좌표 공간이 변경되기 때문입니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.ScaleTransform>을 사용하여 가로와 세로가 각각 50인 <xref:System.Windows.Shapes.Rectangle>의 크기를 두 배로 늘립니다.  <xref:System.Windows.Media.ScaleTransform>의 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 값은 모두 0\(기본값\)입니다.  
  
## 예제  
 [!code-xml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 일반적으로 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A>는 배율을 조정하는 개체의 중점\(<xref:System.Windows.FrameworkElement.Width%2A>\/2, <xref:System.Windows.FrameworkElement.Height%2A>\/2\)으로 설정합니다.  
  
 다음 예제에서는 크기가 두 배인 다른 <xref:System.Windows.Shapes.Rectangle>을 보여 줍니다. 하지만 이 <xref:System.Windows.Media.ScaleTransform>의 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 값은 모두 25이며 이는 사각형의 중점에 해당합니다.  
  
 [!code-xml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 다음 그림에서는 두 <xref:System.Windows.Media.ScaleTransform> 작업의 차이점을 보여 줍니다.  점선은 배율 조정 전의 사각형의 크기와 위치를 보여 줍니다.  
  
 ![여러 중심점을 사용한 2x 배율 조정](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.png "wcpsdk\_graphicsmm\_scalecenter")  
ScaleX 및 ScaleY 값이 같지만 중점은 다른 두 ScaleTransform 작업  
  
 전체 샘플을 보려면 [2\-D Transforms 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.ScaleTransform>   
 [Transform 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)