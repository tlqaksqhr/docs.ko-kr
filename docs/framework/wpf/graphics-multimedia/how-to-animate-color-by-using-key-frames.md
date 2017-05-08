---
title: "방법: 키 프레임을 사용하여 색에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임으로 색"
  - "색, 키 프레임으로 애니메이션 적용"
  - "키 프레임, 색에 애니메이션 적용"
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 키 프레임을 사용하여 색에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A>에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Media.SolidColorBrush>의 <xref:System.Windows.Media.SolidColorBrush.Color%2A> 속성에 애니메이션 효과를 줍니다.  이 애니메이션에서는 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  처음 2초 동안에는 <xref:System.Windows.Media.Animation.LinearColorKeyFrame> 클래스의 인스턴스를 사용하여 색을 녹색에서 빨간색으로 점진적으로 변화시킵니다.  <xref:System.Windows.Media.Animation.LinearColorKeyFrame>과 같은 선형 키 프레임에서는 값 간에 부드러운 선형 전환 효과를 만듭니다.  
  
2.  다음 0.5초가 끝날 무렵에는 <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> 클래스의 인스턴스를 사용하여 색을 빨간색에서 노란색으로 급격하게 변화시킵니다.  <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame>과 같은 불연속 키 프레임에서는 값 간에 급격한 변경 효과를 만듭니다. 즉, 애니메이션의 색이 눈에 띌 정도로 갑자기 변합니다.  
  
3.  마지막 2초 동안 <xref:System.Windows.Media.Animation.SplineColorKeyFrame> 클래스의 인스턴스를 사용하여 색을 다시 변경합니다. 이번에는 노란색을 다시 녹색으로 변경합니다.  <xref:System.Windows.Media.Animation.SplineColorKeyFrame> 같은 [스플라인](GTMT) 키 프레임은 <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> 속성 값에 따라 값 사이의 가변 전환을 만듭니다.  이 예제의 경우 색 변화가 처음에는 서서히 시작되다가 시간 세그먼트의 끝 부분으로 갈수록 빠르게 진행됩니다.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>   
 <xref:System.Windows.Media.SolidColorBrush>   
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)