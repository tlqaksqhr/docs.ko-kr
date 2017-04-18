---
title: "방법: Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어 | Microsoft Docs"
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
  - "이벤트 트리거, Storyboard 제어"
  - "스토리보드, 시작 후 제어"
  - "트리거, Storyboard 제어"
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어
이 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>를 시작한 후 제어하는 방법을 보여 줍니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 <xref:System.Windows.Media.Animation.Storyboard>를 시작하려면 애니메이션 효과를 줄 개체와 속성에 애니메이션을 배포한 다음 Storyboard를 시작하는 <xref:System.Windows.Media.Animation.BeginStoryboard>를 사용해야 합니다.  <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> 속성을 지정하여 <xref:System.Windows.Media.Animation.BeginStoryboard>에 이름을 제공하면 제어 가능한 Storyboard로 만들 수 있습니다.  그러면 Storyboard를 시작한 후 대화형으로 제어할 수 있습니다.  
  
 Storyboard를 제어하려면 <xref:System.Windows.EventTrigger> 개체와 함께 다음 Storyboard 작업을 사용합니다.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Storyboard를 일시 중지합니다.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: 일시 중지한 Storyboard를 다시 시작합니다.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Storyboard 속도를 변경합니다.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Storyboard를 해당 전체 기간\(있는 경우\)의 끝으로 진행합니다.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Storyboard를 중지합니다.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Storyboard를 제거하여 리소스를 해제합니다.  
  
## 예제  
 다음 예제에서는 제어 가능한 Storyboard 작업을 사용하여 대화형으로 Storyboard를 제어합니다.  
  
 **참고:** 코드를 사용한 Storyboard 제어 예제를 보려면 [대화형 메서드를 사용하여 이미 시작된 Storyboard 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)를 참조하십시오.  
  
 [!code-xml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 다른 예제를 보려면 [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>   
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>   
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>   
 <xref:System.Windows.Media.Animation.PauseStoryboard>   
 <xref:System.Windows.Media.Animation.StopStoryboard>   
 <xref:System.Windows.Media.Animation.SeekStoryboard>   
 [대화형 메서드를 사용하여 이미 시작된 Storyboard 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)