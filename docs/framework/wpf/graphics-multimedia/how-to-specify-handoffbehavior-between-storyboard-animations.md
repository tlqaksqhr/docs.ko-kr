---
title: '방법: Storyboard 애니메이션 간의 HandoffBehavior 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
ms.openlocfilehash: c4728dc1cb4eeeff55e533b8d91e4512d9cc1d94
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a>방법: Storyboard 애니메이션 간의 HandoffBehavior 지정
이 예제에는 스토리 보드 애니메이션 간의 전달 동작을 지정 하는 방법을 보여 줍니다. <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 속성 <xref:System.Windows.Media.Animation.BeginStoryboard> 지정 방법을 새 애니메이션 속성에 이미 적용 된 기존 애니메이션과 상호 작용 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 개의 단추 위로 마우스 커서를 이동 하는 때를 확대 커지고 커서를 만듭니다. 단추 위로 마우스 커서를 신속 하 게 제거 하는 경우 첫 번째 작업이 완료 되기 전에 두 번째 애니메이션이 적용 됩니다. 간의 차이 볼 수 있는 다음과 같은 두 개의 애니메이션이 겹칠 때는 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 값 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 및 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>합니다. 값이 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 애니메이션 값 간의 전환을 더 부드럽게 겹치는 애니메이션 결합 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> 새 애니메이션이 즉시 겹치는 이전를 대체 하 게 합니다.  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [애니메이션 및 타이밍](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
