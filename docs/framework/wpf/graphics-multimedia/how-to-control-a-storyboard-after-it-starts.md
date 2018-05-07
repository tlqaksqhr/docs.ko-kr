---
title: '방법: 이미 시작된 Storyboard 제어'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 2407de5029007748de691a3020078b1241b02fd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>방법: 이미 시작된 Storyboard 제어
컨트롤에 코드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard> 시작 된 후입니다. 스토리 보드를 제어 하려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 <xref:System.Windows.Trigger> 및 <xref:System.Windows.TriggerAction> 개체, 예를 들어 참조 [이벤트 트리거는 스토리 보드 후 시작을 제어를 사용 하 여](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)합니다.  
  
 스토리 보드를 시작 하려면 사용 해당 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 스토리 보드의 애니메이션 속성에 애니메이션을 적용 하 고 스토리 보드 시작을 배포 합니다.  
  
 스토리 보드를 제어할 수 있도록 하려면 사용 된 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 지정 하 고 **true** 두 번째 매개 변수로 합니다. 그런 다음 일시 중지, 다시 시작할 seek, 중지, 속도, 또는 스토리 보드 속도가 저하 또는 채우기 기간으로 진행 스토리 보드의 대화형 메서드를 사용할 수 있습니다. 다음은 스토리 보드의 대화형 메서드 목록입니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: 스토리 보드를 일시 중지 됩니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: 일시 중지 된 스토리 보드를 다시 시작합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: 스토리 보드의 대화형 속도 설정합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: 키 스토리 보드 지정된 된 위치를 찾습니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: 지정된 된 위치에 스토리 보드를 찾습니다. 와 달리는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 이 작업 메서드를 다음 틱 보다 먼저 처리 됩니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: 있는 경우 채우기 기간에 스토리 보드를 이동 합니다.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: 스토리 보드를 중지합니다.  
  
 다음 예제에서를 스토리 보드를 대화형으로 제어할 스토리 보드는 여러 가지 방법은 사용 됩니다.  
  
 **참고:** 트리거를 사용 하 여 스토리 보드를 제어 합니다. 예를 보려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 참조 [한 스토리 보드 후 시작을 제어 하려면 이벤트 트리거를 사용 하 여](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>참고 항목  
 [Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
