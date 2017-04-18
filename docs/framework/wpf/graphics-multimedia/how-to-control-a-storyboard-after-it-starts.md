---
title: "방법: 이미 시작된 Storyboard 제어 | Microsoft Docs"
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
  - "스토리보드, 시작 후 제어"
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 이미 시작된 Storyboard 제어
이 예제에서는 이미 시작된 <xref:System.Windows.Media.Animation.Storyboard>를 코드를 사용하여 제어하는 방법을 보여 줍니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 <xref:System.Windows.Trigger> 및 <xref:System.Windows.TriggerAction> 개체를 사용하여 Storyboard를 제어합니다. 예제를 보려면 [Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)를 참조하십시오.  
  
 Storyboard를 시작하려면 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용합니다. 이 메서드는 애니메이션 효과를 적용할 속성에 Storyboard의 애니메이션을 배포한 다음 Storyboard를 시작합니다.  
  
 Storyboard를 제어 가능하게 하려면 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용하고 두 번째 매개 변수를 **true**로 지정합니다.  그런 후 Storyboard의 대화형 메서드를 사용하여 Storyboard를 일시 중지, 다시 시작, 이동, 중지, 빠르게 재생 또는 느리게 재생하거나, 전체 기간의 끝으로 진행할 수 있습니다.  다음은 Storyboard의 대화형 메서드 목록입니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Storyboard를 일시 중지합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: 일시 중지한 Storyboard를 다시 시작합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Storyboard의 속도를 대화형으로 설정합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Storyboard의 지정한 위치로 이동합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Storyboard의 지정한 위치로 이동합니다.  <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 메서드와 달리 이 작업은 다음 틱 전에서만 처리됩니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Storyboard를 해당 전체 기간\(있는 경우\)의 끝으로 진행합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Storyboard를 중지합니다.  
  
 다음 예제에서는 몇 가지 Storyboard 메서드를 사용하여 대화형으로 Storyboard를 제어합니다.  
  
 **참고:**  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 트리거로 Storyboard를 제어하는 예제를 보려면 [Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)를 참조하십시오.  
  
## 예제  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## 참고 항목  
 [Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)