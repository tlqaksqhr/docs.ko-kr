---
title: "방법: 키 프레임을 사용하여 Double에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임이 있는 Double"
  - "double, 키 프레임으로 애니메이션 적용"
  - "키 프레임, Double에 애니메이션 적용"
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 키 프레임을 사용하여 Double에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 <xref:System.Double> 형식의 속성 값에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 화면에서 사각형을 이동합니다.  이 예제에서는 <xref:System.Windows.Shapes.Rectangle>에 적용된 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성에 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 클래스를 사용하여 애니메이션 효과를 줍니다.  무제한 반복되는 이 애니메이션에서는 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  처음 3초 동안에는 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> 클래스의 인스턴스를 사용하여 시작 위치에서 위치 500까지 경로를 따라 일정한 속도로 사각형을 이동합니다.  <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>과 같은 선형 키 프레임을 사용하면 값 간에 완만한 선형 이동이 생성됩니다.  
  
2.  4초가 끝날 즈음에는 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> 클래스의 인스턴스를 사용하여 사각형을 급격하게 다음 위치로 이동합니다.  <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>과 같은 분리된 키 프레임을 사용하면 값 간에 급격한 점프가 생성됩니다.  이 예제에서는 사각형이 시작 위치에 있다가 위치 500에서 갑자기 나타납니다.  
  
3.  마지막 2초 동안은 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> 클래스의 인스턴스를 사용하여 사각형을 원래 시작 위치로 이동합니다.  <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> 같은 [스플라인](GTMT) 키 프레임은 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> 속성 값에 따라 값 간의 가변 전환을 만듭니다.  이 예제에서는 사각형이 처음에는 서서히 이동하다가 시간 세그먼트의 끝 부분으로 갈수록 빠르게 이동합니다.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  
  
 다른 애니메이션 예제와의 일관성을 위해 이 예제의 코드 버전에서는 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하여 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>를 적용합니다.  코드에 단일 애니메이션을 적용하는 경우 <xref:System.Windows.Media.Animation.Storyboard>를 사용하는 대신 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하면 더 간편합니다.  예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>   
 <xref:System.Windows.Shapes.Rectangle>   
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)