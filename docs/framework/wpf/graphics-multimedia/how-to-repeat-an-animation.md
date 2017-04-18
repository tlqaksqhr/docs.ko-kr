---
title: "방법: 애니메이션 반복 | Microsoft Docs"
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
  - "애니메이션, 반복"
  - "Timelines의 RepeatBehavior 속성"
  - "속성 반복"
  - "Timelines RepeatBehavior 속성"
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 애니메이션 반복
이 예제에서는 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 애니메이션의 반복 동작을 제어하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Media.Animation.Timeline> 컨트롤의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 애니메이션이 단순 지속 시간을 반복할 횟수를 제어합니다.  <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>를 사용하면 특정 횟수\(반복 횟수\)만큼 또는 지정한 시간 간격 동안 <xref:System.Windows.Media.Animation.Timeline>이 반복되도록 지정할 수 있습니다.  두 경우 모두 애니메이션은 요청된 횟수 또는 기간이 충족될 때까지 처음부터 끝까지 반복 실행됩니다.  
  
 기본적으로 Timeline의 반복 횟수는 1.0이며 이 경우 한 번만 재생되고 반복되지 않습니다.  하지만 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>로 설정하면 Timeline이 무한 반복됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 애니메이션의 반복 동작을 제어하는 방법을 보여 줍니다.  예제에서는 각 사각형에 서로 다른 형식의 반복 동작을 사용하여 사각형 다섯 개의 <xref:System.Windows.FrameworkElement.Width%2A> 속성에 애니메이션 효과를 줍니다.  
  
 [!code-xml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 전체 샘플을 보려면 [Animation Timing Behavior 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)을 참조하십시오.  
  
## 참고 항목  
 [주기가 반복되는 동안 애니메이션 값 누적](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)   
 [Timeline을 자동으로 뒤집을지 여부 지정](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [Animation and Timing](http://msdn.microsoft.com/ko-kr/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation Timing Behavior 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)