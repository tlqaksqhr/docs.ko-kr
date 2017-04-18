---
title: "방법: 키 프레임을 사용하여 크기 변경에 애니메이션 효과 주기 | Microsoft Docs"
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
  - "애니메이션, 키 프레임으로 크기 변경"
  - "키 프레임, 크기 변경에 애니메이션 적용"
  - "크기 변경, 키 프레임으로 애니메이션 적용"
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 키 프레임을 사용하여 크기 변경에 애니메이션 효과 주기
이 예제에서는 키 프레임을 사용하여 크기 변경에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> 클래스를 사용하여 <xref:System.Windows.Media.ArcSegment>의 <xref:System.Windows.Media.ArcSegment.Size%2A> 속성에 애니메이션 효과를 줍니다.  이 애니메이션에서는 다음과 같은 방식으로 세 가지 키 프레임을 사용합니다.  
  
1.  애니메이션의 처음 0.5초 동안에는 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> 클래스의 인스턴스를 사용하여 원호의 크기를 점차적으로 늘립니다.  <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>과 같은 선형 키 프레임에서는 값 간에 완만한 선형 이동을 생성합니다.  
  
2.  다음 0.5초가 끝날 즈음에는 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> 클래스의 인스턴스를 사용하여 원호의 크기를 급격하게 늘립니다.  <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>과 같은 불연속 키 프레임에서는 값 간에 급격한 점프 효과를 만듭니다. 즉, 크기가 눈에 띌 정도로 갑자기 변합니다.  
  
3.  마지막 2초 동안 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 클래스의 인스턴스를 사용하여 원호의 크기를 늘립니다.  <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> 같은 [스플라인](GTMT) 키 프레임은 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> 속성 값에 따라 값 사이의 가변 전환을 만듭니다.  이 예제에서는 원호의 크기가 처음에는 서서히 커지다가 시간 세그먼트의 끝 부분으로 갈수록 급격하게 커집니다.  
  
 [!code-xml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 전체 샘플을 보려면 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>   
 <xref:System.Windows.Media.ArcSegment.Size%2A>   
 <xref:System.Windows.Media.ArcSegment>   
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>   
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>   
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)