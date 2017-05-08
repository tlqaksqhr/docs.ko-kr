---
title: "방법: AnimationClock을 사용하여 속성에 애니메이션 효과 적용 | Microsoft Docs"
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
  - "애니메이션, 속성, AnimationClocks로"
  - "AnimationClocks"
ms.assetid: e6542021-714c-4675-9567-04f1c7380834
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: AnimationClock을 사용하여 속성에 애니메이션 효과 적용
이 예제에서는 <xref:System.Windows.Media.Animation.Clock> 개체를 사용하여 속성에 애니메이션 효과를 적용하는 방법을 보여 줍니다.  
  
 다음과 같은 세 가지 방법으로 [종속성 속성](GTMT)에 애니메이션 효과를 적용할 수 있습니다.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline>을 만든 다음 <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 해당 속성에 연결합니다.  
  
-   개체의 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하여 대상 속성에 단일 <xref:System.Windows.Media.Animation.AnimationTimeline>을 적용합니다.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline>에서 <xref:System.Windows.Media.Animation.AnimationClock>을 만들어 속성에 적용합니다.  
  
 <xref:System.Windows.Media.Animation.Storyboard> 개체와 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하면 시계를 직접 만들어 배포하지 않고도 속성에 애니메이션 효과를 적용할 수 있습니다. 시계는 자동으로 만들어져 배포됩니다. 예제를 보려면 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) 및 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Media.Animation.AnimationClock>을 만들어서 두 개의 비슷한 속성에 적용하는 방법을 보여 줍니다.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 <xref:System.Windows.Media.Animation.Clock>이 시작된 후 이를 대화식으로 제어하는 방법을 보여 주는 예제는 [대화식으로 Clock 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-interactively-control-a-clock.md)를 참조하십시오.  
  
## 참고 항목  
 [Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)   
 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)   
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)