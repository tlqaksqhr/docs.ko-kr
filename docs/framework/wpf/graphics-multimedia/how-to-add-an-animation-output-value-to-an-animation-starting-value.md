---
title: "방법: 애니메이션 시작 값에 애니메이션 출력 값 추가 | Microsoft Docs"
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
  - "애니메이션"
  - "IsAdditive 속성"
ms.assetid: b89a82be-b03d-481e-a8d3-cc513d09ca00
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 애니메이션 시작 값에 애니메이션 출력 값 추가
이 예제에서는 애니메이션 시작 값에 애니메이션 출력 값을 추가하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> 속성은 애니메이션의 출력 값을 애니메이션이 적용된 속성의 시작 값\(기준 값\)에 추가할지 여부를 지정합니다.  <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A> 속성은 가장 기본적인 애니메이션 및 대부분의 키 프레임 애니메이션에 사용할 수 있습니다.  자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 및 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)을 참조하십시오.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation.IsAdditive%2A?displayProperty=fullName> 속성에 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하거나 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsAdditive%2A?displayProperty=fullName> 속성에 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>를 사용하는 경우의 효과를 보여 줍니다.  
  
 [!code-xml[timingbehaviors_snip#IsAdditiveWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsAdditiveExample.xaml#isadditivewholepage)]  
  
## 참고 항목  
 [주기가 반복되는 동안 애니메이션 값 누적](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/ko-kr/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)