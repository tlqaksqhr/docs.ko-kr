---
title: "방법: 키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임이 있는 테두리 두께"
  - "테두리 두께, 키 프레임으로 애니메이션 적용"
  - "키 프레임, 테두리 두께에 애니메이션 적용"
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 키 프레임을 사용하여 테두리 두께에 애니메이션 효과 주기
이 예제에서는 <xref:System.Windows.Controls.Border>의 <xref:System.Windows.Controls.Control.BorderThickness%2A> 속성에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Controls.Border>의 <xref:System.Windows.Controls.Control.BorderThickness%2A> 속성에 애니메이션 효과를 줍니다.  이 애니메이션에서는 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  처음 0.5초 동안에는 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> 클래스의 인스턴스를 사용하여 테두리 두께를 점차적으로 늘립니다.  이 예제에서는 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>을 사용하여 값 간에 점차적인 선형 증가 효과를 만듭니다.  
  
2.  다음 0.5초가 끝날 즈음에는 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> 클래스의 인스턴스를 사용하여 테두리 두께를 급격하게 늘립니다.  <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>에서 파생된 것과 같은 불연속 키 프레임에서는 값 간에 급격한 점프 효과를 만듭니다. 즉, 애니메이션이 급격하게 움직입니다.  
  
3.  마지막 2초 동안 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> 클래스의 인스턴스를 사용하여 테두리의 두께를 줄입니다.  <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>에서 파생된 것과 같은 [스플라인](GTMT) 키 프레임은 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> 속성 값에 따라 값 사이의 가변 전환을 만듭니다.  이 키 프레임의 경우 애니메이션이 처음에는 서서히 시작되다가 시간 세그먼트의 끝 부분으로 갈수록 빠르게 진행됩니다.  
  
 [!code-xml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)   
 [BorderThickness 값에 애니메이션 효과 주기](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)