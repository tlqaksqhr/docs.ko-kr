---
title: "방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b890d121cf06dc377a3bbc1dc569d9dac7c011b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a>방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정
지정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 비활성에 대 한 <xref:System.Windows.Media.Animation.Timeline> 애니메이션된 속성입니다.  
  
## <a name="example"></a>예  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 <xref:System.Windows.Media.Animation.Timeline> 되 고 있지 않습니다 때 애니메이션된 속성의 값에 수행할 작업을 결정 애니메이션 효과가 적용, 즉, 시기는 <xref:System.Windows.Media.Animation.Timeline> 만 부모 활성화 되지 않은 <xref:System.Windows.Media.Animation.Timeline> 는 활성 또는 보관 기간. 예를 들어 애니메이션된 속성 유지 않는다는 끝에 애니메이션을 종료 하거나 수행 후의 값은 애니메이션 시작 되기 전의 값 되돌아갑니다?  
  
 다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 애니메이션 효과를 줄의 <xref:System.Windows.FrameworkElement.Width%2A> 두 개의 사각형의 합니다. 각 사각형을 사용 하 여 다른 <xref:System.Windows.Media.Animation.Timeline> 개체입니다.  
  
 하나의 <xref:System.Windows.Media.Animation.Timeline> 에 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 로 설정 되어 있는 <xref:System.Windows.Media.Animation.FillBehavior.Stop>, 다시 돌아가려면 해당 애니메이션이 적용 되지 않은 사각형의 너비 값으로 <xref:System.Windows.Media.Animation.Timeline> 종료 합니다. 다른 <xref:System.Windows.Media.Animation.Timeline> 에 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 의 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, 너비의 끝을 유지 하기 위한 경우이 값은 <xref:System.Windows.Media.Animation.Timeline> 종료 합니다.  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 전체 샘플을 참조 하십시오. [애니메이션 예제 갤러리](http://go.microsoft.com/fwlink/?LinkID=159969)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [애니메이션 및 타이밍](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
