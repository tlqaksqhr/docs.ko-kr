---
title: "방법: 자식 Timeline을 사용하여 애니메이션 단순화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: daa4caac0046293e8b86a773bfffd46cf30e835b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a>방법: 자식 Timeline을 사용하여 애니메이션 단순화
자식을 사용 하 여 애니메이션을 단순화 하는 방법을 보여 주는이 예제 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체입니다. A <xref:System.Windows.Media.Animation.Storyboard> 는 유형의 <xref:System.Windows.Media.Animation.Timeline> 포함 된 타임 라인에 대 한 대상 정보를 제공 하는 합니다. 사용 하 여 한 <xref:System.Windows.Media.Animation.Storyboard> 개체 및 속성 정보를 포함 하 여 정보를 대상으로 하는 시간 표시 막대 수 있도록 합니다.  
  
 애니메이션을 시작 하려면 하나 이상의 사용 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체의 중첩 된 자식 요소로 <xref:System.Windows.Media.Animation.Storyboard>합니다. 이러한 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체 다른 애니메이션 포함 될 수 있으며 따라서 복잡 한 애니메이션의 타이밍 시퀀스를 캡슐화 할 더 수 있습니다. 애니메이션을 적용 하려는 경우 등는 <xref:System.Windows.Controls.TextBlock> 와 같은 여러 셰이프 <xref:System.Windows.Media.Animation.Storyboard>에 대 한 애니메이션을 구분할 수 있습니다는 <xref:System.Windows.Controls.TextBlock> 와 배치를 별도의 각 셰이프 <xref:System.Windows.Media.Animation.ParallelTimeline>합니다. 때문에 각 <xref:System.Windows.Media.Animation.ParallelTimeline> 자체 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 및 모든 자식 요소는 <xref:System.Windows.Media.Animation.ParallelTimeline> 이 기준으로 시작 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, 타이밍 더욱 효과적으로 캡슐화 됩니다.  
  
 다음 예제에서는 두 가지 텍스트 애니메이션 효과 줍니다 (<xref:System.Windows.Controls.TextBlock> 개체)에서 같은 <xref:System.Windows.Media.Animation.Storyboard>합니다. A <xref:System.Windows.Media.Animation.ParallelTimeline> 중 하나의 애니메이션 캡슐화는 <xref:System.Windows.Controls.TextBlock> 개체입니다.  
  
 **성능 참고 사항:** 중첩할 수 있지만 <xref:System.Windows.Media.Animation.Storyboard> 서로 timeline <xref:System.Windows.Media.Animation.ParallelTimeline>훨씬 더 적은 오버 헤드를 필요 하기 때문에 중첩에 적합 합니다. (의 <xref:System.Windows.Media.Animation.Storyboard> 클래스에서 상속 된 <xref:System.Windows.Media.Animation.ParallelTimeline> 클래스입니다.)  
  
## <a name="example"></a>예제  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Storyboard 애니메이션 간의 HandoffBehavior 지정](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
