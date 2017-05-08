---
title: "방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임이 있는 RectangleGeometry 개체"
  - "키 프레임, RectangleGeometry 개체에 애니메이션 적용"
  - "RectangleGeometry 개체, 키 프레임으로 애니메이션 적용"
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 키 프레임을 사용하여 사각형에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 <xref:System.Windows.Media.RectangleGeometry>의 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 속성에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Media.RectangleGeometry>의 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 속성에 애니메이션 효과를 줍니다.  이 애니메이션에서는 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  처음 2초 동안은 <xref:System.Windows.Media.Animation.LinearRectKeyFrame> 클래스의 인스턴스를 사용하여 사각형의 위치, 너비 및 높이를 점진적으로 변화시키는 애니메이션 효과를 적용합니다.  <xref:System.Windows.Media.Animation.LinearRectKeyFrame>과 같은 선형 키 프레임에서는 값 간에 부드러운 선형 전환 효과를 만듭니다.  
  
2.  다음 0.5초가 끝날 무렵에는 <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> 클래스의 인스턴스를 사용하여 사각형의 높이를 급격하게 줄입니다.  <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame>과 같은 불연속 키 프레임에서는 값 간에 급격한 변경 효과를 만듭니다. 즉, 높이가 눈에 띌 정도로 갑자기 감소합니다.  
  
3.  마지막 2초 동안은 <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 클래스의 인스턴스를 사용하여 사각형의 크기와 위치를 다시 원래대로 변경합니다.  <xref:System.Windows.Media.Animation.SplineRectKeyFrame> 같은 [스플라인](GTMT) 키 프레임은 <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> 속성 값에 따라 값 사이의 가변 전환을 만듭니다.  이 예제의 경우 변화가 처음에는 서서히 시작되다가 시간 세그먼트의 끝 부분으로 갈수록 빠르게 진행됩니다.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.RectangleGeometry>   
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>   
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)