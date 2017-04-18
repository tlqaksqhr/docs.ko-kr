---
title: "방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정 | Microsoft Docs"
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
  - "비활성 Timeline의 FillBehavior 속성"
  - "Timeline, FillBehavior 속성"
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정
이 예제에서는 애니메이션 효과가 적용된 속성의 비활성 <xref:System.Windows.Media.Animation.Timeline>에 대한 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>를 지정하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 애니메이션 효과가 적용되지 않을 때, 즉 <xref:System.Windows.Media.Animation.Timeline>은 비활성 상태지만 부모 <xref:System.Windows.Media.Animation.Timeline>는 활성 기간 또는 보관 기간에 있을 때 애니메이션 효과가 적용된 속성의 값이 어떻게 될지 결정합니다.  예를 들어 애니메이션 효과가 적용된 속성이 애니메이션이 끝난 후 끝 값으로 유지될지, 아니면 애니메이션 시작 전의 값으로 되돌아갈지를 결정합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 두 사각형의 <xref:System.Windows.FrameworkElement.Width%2A>에 애니메이션 효과를 적용합니다.  각 사각형은 서로 다른 <xref:System.Windows.Media.Animation.Timeline> 개체를 사용합니다.  
  
 한 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>는 <xref:System.Windows.Media.Animation.FillBehavior>으로 설정되어 <xref:System.Windows.Media.Animation.Timeline>이 끝날 때 사각형의 너비는 애니메이션 효과가 적용되지 않은 값으로 되돌아갑니다.  다른 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>는 <xref:System.Windows.Media.Animation.FillBehavior>이기 때문에 <xref:System.Windows.Media.Animation.Timeline>이 끝날 때 너비가 끝 값으로 유지됩니다.  
  
 [!code-xml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 전체 샘플을 보려면 [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.DoubleAnimation>   
 <xref:System.Windows.FrameworkElement.Width%2A>   
 <xref:System.Windows.Media.Animation.Timeline>   
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>   
 <xref:System.Windows.Media.Animation.FillBehavior>   
 <xref:System.Windows.Media.Animation.FillBehavior>   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Animation and Timing](http://msdn.microsoft.com/ko-kr/7d83765b-d5ae-41b1-b423-80206e1124aa)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)