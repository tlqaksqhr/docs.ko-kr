---
title: "방법: 애니메이션 반복"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RepeatBehavior property of timelines [WPF]
- repeating animating [WPF]
- Timelines RepeatBehavior property [WPF]
- animation [WPF], repeating
ms.assetid: e6f3b068-eeeb-47fd-8d40-8848c31f1e1e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03ee84463bc6ce76d209d3c9fbb0455fedd9ca1a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-repeat-an-animation"></a>방법: 애니메이션 반복
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 의 속성을 <xref:System.Windows.Media.Animation.Timeline> 애니메이션의 반복 동작을 제어 하기 위해 합니다.  
  
## <a name="example"></a>예  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성은 <xref:System.Windows.Media.Animation.Timeline> 애니메이션 단순 지속 시간을 반복 하는 횟수를 제어 합니다. 사용 하 여 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>를 지정할 수 있습니다는 <xref:System.Windows.Media.Animation.Timeline> 특정 횟수에 대 한 반복 (반복 횟수) 또는 지정된 된 기간에 대 한 합니다. 두 경우 모두 애니메이션은 요청 된 수 또는 기간을 채우기 위해 필요한 만큼 시작-끝 실행 설명 합니다.  
  
 기본적으로 타임 라인을 한 번 재생 되 고 반복 되지 않는 지 1.0의 반복 횟수를 적용 합니다. 그러나 설정 하는 경우는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성은 <xref:System.Windows.Media.Animation.Timeline> 를 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, 타임 라인 무한 반복 합니다.  
  
 사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 애니메이션의 반복 동작을 제어 하는 속성입니다. 이 예제에서는 애니메이션 효과 적용는 <xref:System.Windows.FrameworkElement.Width%2A> 다른 유형의 반복 동작을 사용 하 여 각 사각형의 5 개의 사각형의 속성입니다.  
  
 [!code-xaml[timingbehaviors_snip#RepeatBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/RepeatBehaviorExample.xaml#repeatbehaviorwholepage)]  
  
 전체 샘플을 참조 하십시오. [애니메이션 타이밍 동작 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [주기가 반복되는 동안 애니메이션 값 누적](../../../../docs/framework/wpf/graphics-multimedia/how-to-accumulate-animation-values-during-repeat-cycles.md)  
 [타임라인을 자동으로 뒤집을지 여부 지정](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [애니메이션 및 타이밍](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [애니메이션 타이밍 동작 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)
