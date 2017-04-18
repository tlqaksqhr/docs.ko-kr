---
title: "방법: 자식 Timeline을 사용하여 애니메이션 단순화 | Microsoft Docs"
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
  - "애니메이션, 자식 Timeline을 사용하여 단순화"
  - "자식 Timeline"
  - "자식 Timeline을 사용하여 애니메이션 단순화"
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 자식 Timeline을 사용하여 애니메이션 단순화
이 예제에서는 자식 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체를 사용하여 애니메이션을 단순화하는 방법을 보여 줍니다.  <xref:System.Windows.Media.Animation.Storyboard>는 Storyboard에 포함된 Timeline에 대한 대상 정보를 제공하는 <xref:System.Windows.Media.Animation.Timeline> 형식입니다.  <xref:System.Windows.Media.Animation.Storyboard>를 사용하면 개체 및 속성 정보를 비롯한 Timeline 대상 정보를 제공할 수 있습니다.  
  
 애니메이션을 시작하려면 하나 이상의 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체를 <xref:System.Windows.Media.Animation.Storyboard>의 중첩된 자식 요소로 사용합니다.  이러한 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체는 다른 애니메이션을 포함할 수 있으므로 복잡한 애니메이션의 타이밍 시퀀스를 더욱 효율적으로 캡슐화할 수 있습니다.  예를 들어 동일한 <xref:System.Windows.Media.Animation.Storyboard>에서 <xref:System.Windows.Controls.TextBlock> 및 여러 모양에 애니메이션 효과를 주는 경우 <xref:System.Windows.Controls.TextBlock>과 모양에 대한 애니메이션을 분리하여 각각을 별도의 <xref:System.Windows.Media.Animation.ParallelTimeline>에 배치할 수 있습니다.  각 <xref:System.Windows.Media.Animation.ParallelTimeline>에는 고유한 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>이 있으며 <xref:System.Windows.Media.Animation.ParallelTimeline>의 모든 자식 요소는 이 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>에 따라 시작되므로 타이밍을 더욱 효과적으로 캡슐화할 수 있습니다.  
  
 다음 예제에서는 동일한 <xref:System.Windows.Media.Animation.Storyboard> 내에서 텍스트 조각 두 개\(<xref:System.Windows.Controls.TextBlock> 개체\)에 애니메이션 효과를 줍니다.  <xref:System.Windows.Media.Animation.ParallelTimeline>은 <xref:System.Windows.Controls.TextBlock> 개체 중 하나에 대한 애니메이션을 캡슐화합니다.  
  
 **성능 참고 사항:** <xref:System.Windows.Media.Animation.Storyboard> Timeline을 서로 중첩시킬 수 있지만 더 적은 오버헤드를 필요로 하는 <xref:System.Windows.Media.Animation.ParallelTimeline>이 중첩에 훨씬 적합합니다.  <xref:System.Windows.Media.Animation.Storyboard> 클래스는 <xref:System.Windows.Media.Animation.ParallelTimeline> 클래스에서 상속합니다.  
  
## 예제  
 [!code-xml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Storyboard 애니메이션 간의 HandoffBehavior 지정](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)