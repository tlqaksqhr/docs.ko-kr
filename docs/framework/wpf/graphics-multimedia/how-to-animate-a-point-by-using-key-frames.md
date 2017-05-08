---
title: "방법: 키 프레임을 사용하여 포인트에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임으로 점"
  - "키 프레임, 점에 애니메이션 적용"
  - "점, 키 프레임으로 애니메이션 적용"
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 키 프레임을 사용하여 포인트에 애니메이션 효과 주기
이 예제에서는 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Point>에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 삼각형 경로를 따라 타원을 이동합니다.  예제에서는 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Media.EllipseGeometry>의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성에 애니메이션 효과를 줍니다.  이 애니메이션에서는 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  처음 0.5초 동안에는 <xref:System.Windows.Media.Animation.LinearPointKeyFrame> 클래스의 인스턴스를 사용하여 시작 위치부터 일정한 속도로 경로를 따라 타원을 이동합니다.  <xref:System.Windows.Media.Animation.LinearPointKeyFrame>과 같은 선형 키 프레임은 값 사이에 부드러운 선형 보간을 생성합니다.  
  
2.  다음 0.5초가 끝날 무렵에는 <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> 클래스의 인스턴스를 사용하여 경로를 따라 타원을 급격하게 다음 위치로 이동합니다.  <xref:System.Windows.Media.Animation.DiscretePointKeyFrame>과 같은 불연속 키 프레임을 사용하면 값 간에 급격한 점프가 생성됩니다.  
  
3.  마지막 2초 동안은 <xref:System.Windows.Media.Animation.SplinePointKeyFrame> 클래스의 인스턴스를 사용하여 타원을 원래 시작 위치로 이동합니다.  <xref:System.Windows.Media.Animation.SplinePointKeyFrame> 같은 [스플라인](GTMT) 키 프레임은 <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> 속성 값에 따라 값 사이의 가변 전환을 만듭니다.  이 예제의 경우 애니메이션이 처음에는 서서히 시작되다가 시간 세그먼트의 끝 부분으로 갈수록 빠르게 진행됩니다.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  
  
 다른 애니메이션 예제와의 일관성을 위해 이 예제의 코드 버전에서는 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용하여 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>를 적용합니다.  하지만 코드에 단일 애니메이션을 적용하는 경우 <xref:System.Windows.Media.Animation.Storyboard>를 사용하는 대신 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하면 더 간편합니다.  예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=fullName>   
 <xref:System.Windows.Media.EllipseGeometry>   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)