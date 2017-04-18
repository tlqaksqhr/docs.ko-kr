---
title: "방법: 주기가 반복되는 동안 애니메이션 값 누적 | Microsoft Docs"
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
  - "반복 주기에 대해 애니메이션 값 누적"
  - "애니메이션, 반복 주기에 대해 값 누적"
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 주기가 반복되는 동안 애니메이션 값 누적
이 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 속성을 사용하여 주기가 반복되는 동안 애니메이션 값을 누적하는 방법을 보여 줍니다.  
  
## 예제  
 주기가 반복되는 동안 애니메이션 기준 값을 누적하려면 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 속성을 사용합니다.  예를 들어 9회 반복되도록 애니메이션을 설정하고\(<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> \= "9x"\) 첫 번째 주기 동안에는 10\-15\(From \= 10 To \= 15\) 사이에 애니메이션 효과가 적용되도록 속성을 설정하면 첫 주기에서는 10\-15 사이에 애니메이션 효과가 적용되고, 두 번째 주기에서는 15\-20 사이, 세 번째 속성에서는 20\-25 사이에 적용되는 식으로 값이 누적되어 효과가 나타납니다.  따라서 각 애니메이션 주기는 이전 애니메이션 주기의 끝 값을 기준 값으로 사용합니다.  
  
 `IsCumulative` 속성은 가장 기본적인 애니메이션 및 대부분의 키 프레임 애니메이션에 사용할 수 있습니다.  자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 및 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)을 참조하십시오.  
  
 다음 예제에서는 사각형 네 개의 너비에 애니메이션 효과를 적용하여 이 동작을 보여 줍니다.  예를 들면 다음과 같습니다.  
  
-   <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 첫 번째 사각형에 애니메이션 효과를 주고 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 속성을 `true`로 설정합니다.  
  
-   <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 두 번째 사각형에 애니메이션 효과를 주고 <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> 속성을 기본값인 `false`로 설정합니다..  
  
-   <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>을 사용하여 세 번째 사각형에 애니메이션 효과를 주고 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 속성을 `true`로 설정합니다.  
  
-   <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>를 사용하여 마지막 사각형에 애니메이션 효과를 주고 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> 속성을 `false`로 설정합니다.  
  
 [!code-xml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## 참고 항목  
 [애니메이션 시작 값에 애니메이션 출력 값 추가](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)   
 [애니메이션 반복](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)