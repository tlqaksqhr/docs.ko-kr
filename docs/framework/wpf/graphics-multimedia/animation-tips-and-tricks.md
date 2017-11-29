---
title: "애니메이션에 대한 유용한 정보"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting [WPF], animation
- animations [WPF], FillBehavior property
- troubleshooting animation [WPF]
- animating objects [WPF], troubleshooting
- animation tips and tricks [WPF]
- tips and tricks [WPF], animation
- performance troubleshooting [WPF], animation
- animations [WPF], use of system resources
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca88d95f760e44b6cdc319923215151eff4bf762
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="animation-tips-and-tricks"></a>애니메이션에 대한 유용한 정보
애니메이션을 사용할 때 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], 팁의 여러 가지 및 애니메이션을 만들 수 있는 방법을 더 잘 수행 불만 저장 합니다.  
  
<a name="generalissuessection"></a>   
## <a name="general-issues"></a>일반적인 문제  
  
### <a name="animating-the-position-of-a-scroll-bar-or-slider-freezes-it"></a>스크롤 막대 또는 슬라이더의 위치에 애니메이션 효과를 줄 경우 고정됨  
 애니메이션에 사용 하 여 슬라이더 또는 스크롤 막대의 위치에 애니메이션을 적용 하는 경우는 <xref:System.Windows.Media.Animation.FillBehavior> 의 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> (기본값) 사용자는 더 이상 할 수는 스크롤 막대 또는 슬라이더를 이동 합니다. 그 이유는 애니메이션이 종료되더라도 대상 속성의 기본값은 여전히 재정의되기 때문입니다. 속성의 현재 값이 재정의 애니메이션을 중지 하려면 제거 하거나 지정 된 <xref:System.Windows.Media.Animation.FillBehavior> 의 <xref:System.Windows.Media.Animation.FillBehavior.Stop>합니다. 자세한 내용 및 예제에 대 한 참조 [설정는 속성 후 애니메이션에 스토리](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md)합니다.  
  
### <a name="animating-the-output-of-an-animation-has-no-effect"></a>애니메이션의 출력에 애니메이션을 적용해도 효과가 없음  
 다른 애니메이션의 출력에 해당하는 개체에 애니메이션 효과를 줄 수 없습니다. 예를 들어, 사용 하는 경우는 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> 애니메이션 효과를 줄의 <xref:System.Windows.Shapes.Shape.Fill%2A> 의 <xref:System.Windows.Shapes.Rectangle> 에서 <xref:System.Windows.Media.RadialGradientBrush> 에 <xref:System.Windows.Media.SolidColorBrush>의 모든 속성에 애니메이션을 적용할 수 없습니다는 <xref:System.Windows.Media.RadialGradientBrush> 또는 <xref:System.Windows.Media.SolidColorBrush>합니다.  
  
### <a name="cant-change-the-value-of-a-property-after-animating-it"></a>애니메이션 효과를 적용한 후 속성 값을 변경할 수 없음  
 경우에 따라 애니메이션이 종료된 후에도 애니메이션 효과를 적용한 속성의 값을 변경할 수 없는 것처럼 나타납니다. 그 이유는 애니메이션이 종료되더라도 속성의 기본값은 여전히 재정의되기 때문입니다. 속성의 현재 값이 재정의 애니메이션을 중지 하려면 제거 하거나 지정 된 <xref:System.Windows.Media.Animation.FillBehavior> 의 <xref:System.Windows.Media.Animation.FillBehavior.Stop>합니다. 자세한 내용 및 예제에 대 한 참조 [설정는 속성 후 애니메이션에 스토리](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md)합니다.  
  
### <a name="changing-a-timeline-has-no-effect"></a>타임라인을 변경해도 효과가 없음  
 하지만 대부분 <xref:System.Windows.Media.Animation.Timeline> 속성은 애니메이션을 적용 하 고 데이터 바인딩될 수, 활성 속성 값을 변경 <xref:System.Windows.Media.Animation.Timeline> 화가 적용 되지 않습니다. 때문 때는 <xref:System.Windows.Media.Animation.Timeline> 은, 타이밍 시스템의 복사본을 만듭니다는 <xref:System.Windows.Media.Animation.Timeline> 만들기를 사용 하 여는 <xref:System.Windows.Media.Animation.Clock> 개체입니다. 원본을 수정해도 시스템의 복사본에는 영향을 주지 않습니다.  
  
 에 대 한 한 <xref:System.Windows.Media.Animation.Timeline> 변경 내용을 반영 합니다는 시계가 다시 생성 하 고 사용 해야 이전에 만든된 클록 교체할 수 있습니다. 클록은 자동으로 다시 생성되지 않습니다. 다음은 타임라인 변경 내용을 적용하는 몇 가지 방법입니다.  
  
-   타임 라인은 또는에 속하는 경우 한 <xref:System.Windows.Media.Animation.Storyboard>, 해당 스토리 보드를 사용 하 여 다시 적용 하 여 변경 내용을 반영 만들 수 있습니다는 <xref:System.Windows.Media.Animation.BeginStoryboard> 또는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드. 부작용으로 애니메이션까지 다시 시작됩니다. 코드에서 사용할 수는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 스토리 보드를 이동 하는 메서드를 이전 위치로 백업 합니다.  
  
-   애니메이션 사용 하 여 속성에 직접 적용 한 경우는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 호출은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 다시 수정 된 애니메이션을 전달 합니다.  
  
-   클록 수준에서 직접 작업하는 경우 새 클록 집합을 만들어 적용하고 이 클록 집합을 사용하여 이전에 생성된 클록 집합을 대체합니다.  
  
 타임 라인 및 클럭에 대 한 자세한 내용은 참조 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)합니다.  
  
### <a name="fillbehaviorstop-doesnt-work-as-expected"></a>FillBehavior.Stop이 예상대로 작동하지 않음  
 하는 설정 하는 경우는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 효과가 없으며, 예를 들어 있는 것 같지 애니메이션 "핸드 오프를 다른 있기 때문에 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 의 설정 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>합니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Shapes.Rectangle> 및 <xref:System.Windows.Media.TranslateTransform>합니다. <xref:System.Windows.Media.TranslateTransform> 이동 하려면 애니메이션는 <xref:System.Windows.Shapes.Rectangle> 주위에서 <xref:System.Windows.Controls.Canvas>합니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 이 섹션의 예 이전 개체를 사용 하 여 여러 개의 사례를 설명 하기 위해 여기서는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성에 예상 대로 동작 하지 않습니다.  
  
#### <a name="fillbehaviorstop-and-handoffbehavior-with-multiple-animations"></a>여러 애니메이션에서의 FillBehavior="Stop" 및 HandoffBehavior  
 애니메이션에서 무시 있다고 생각할 경우에 따라 해당 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 두 번째 애니메이션으로 대체 됩니다. 다음 예제에서는 두 개의 걸릴 <xref:System.Windows.Media.Animation.Storyboard> 개체를 사용 하 여 동일한 애니메이션 효과를 주는 <xref:System.Windows.Media.TranslateTransform> 앞의 예제에 표시 된 것입니다.  
  
 첫 번째 <xref:System.Windows.Media.Animation.Storyboard>, `B1`, 애니메이션 효과 적용는 <xref:System.Windows.Media.TranslateTransform.X%2A> 의 속성은 <xref:System.Windows.Media.TranslateTransform> 350 0 또는 있는 사각형 350 (픽셀)를 오른쪽으로 이동 합니다. 애니메이션이 해당 기간의 끝에 도달 하 고 재생을 중지할 때의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성을 원래 값을 0으로 되돌립니다. 결과적으로 사각형은 오른쪽으로 350픽셀만큼 이동한 다음 원래 위치로 되돌아갑니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 두 번째 <xref:System.Windows.Media.Animation.Storyboard>, `B2`, 또한 애니메이션 효과 적용 된 <xref:System.Windows.Media.TranslateTransform.X%2A> 는 동일한 속성 <xref:System.Windows.Media.TranslateTransform>합니다. 때문에는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 이 애니메이션의 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 애니메이션 효과가 적용 되는 속성의 현재 값을 사용 하 여 시작 값으로 설정 합니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 첫 번째 동안 두 번째 단추를 클릭 하면 <xref:System.Windows.Media.Animation.Storyboard> 은 재생 하 고, 다음과 같은 동작이 예상할 수 있습니다.  
  
1.  첫 번째 스토리 보드 종료 하 고 애니메이션에 있기 때문에 사각형을 다시 원래 위치로 보냅니다는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 의 <xref:System.Windows.Media.Animation.FillBehavior.Stop>합니다.  
  
2.  두 번째 Storyboard가 적용되며, 0에 해당하는 현재 위치에서 500으로 애니메이션 효과를 줍니다.  
  
 **그러나 이 작업이 수행되지 않습니다.** 대신, 사각형이 원래 위치로 돌아가지 않고 계속 오른쪽으로 이동됩니다. 그 이유는 두 번째 애니메이션이 첫 번째 애니메이션의 현재 값을 시작 값으로 사용하고 해당 값에서 500으로 애니메이션 효과를 주기 때문입니다. 때문에 두 번째 애니메이션 첫 번째를 대체 하는 경우는 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> <xref:System.Windows.Media.Animation.HandoffBehavior> 사용 되는 <xref:System.Windows.Media.Animation.FillBehavior> 첫 번째 애니메이션 중요 하지 않습니다.  
  
#### <a name="fillbehavior-and-the-completed-event"></a>FillBehavior 및 Completed 이벤트  
 다음 예에서는 다른 시나리오를 보여 줍니다.는 <xref:System.Windows.Media.Animation.FillBehavior.Stop> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 화가 적용 되지 않습니다. 다시,이 예제에서는 스토리 보드를 사용 하 여 애니메이션 효과를 주는 <xref:System.Windows.Media.TranslateTransform.X%2A> 의 속성은 <xref:System.Windows.Media.TranslateTransform> 350 0에서 합니다. 그러나이 이번 예에서는 등록 된 <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트입니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트 처리기가 다른 시작 <xref:System.Windows.Media.Animation.Storyboard> 500 현재 값에서 동일한 속성에 애니메이션 효과가 적용 합니다.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 다음은 두 번째를 정의 하는 태그 <xref:System.Windows.Media.Animation.Storyboard> 리소스로 합니다.  
  
 [!code-xaml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 실행 하는 경우는 <xref:System.Windows.Media.Animation.Storyboard>, 예상 대로 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성의는 <xref:System.Windows.Media.TranslateTransform> 350 0에서 애니메이션을 효과를 다음으로 되돌리려면 0 완료 된 후 (있기 때문에 <xref:System.Windows.Media.Animation.FillBehavior> 설정인 <xref:System.Windows.Media.Animation.FillBehavior.Stop>), 애니메이션을 적용 하십시오 0에서 500 합니다. 대신,는 <xref:System.Windows.Media.TranslateTransform> 350 및 500 0에서 애니메이션 효과 적용 합니다.  
  
 순서 때문에 이것이 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 속성이 무효화 되지 않은 경우 속성 값 캐시 되 고 없기 때문에 계산 및 이벤트를 발생 시킵니다. <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트 루트 타임 라인인에 의해 트리거 때문에 먼저 처리 됩니다 (첫 번째 <xref:System.Windows.Media.Animation.Storyboard>). 이번에 <xref:System.Windows.Media.TranslateTransform.X%2A> 아직 무효화 되지 않았으므로 때문에 여전히 속성 애니메이션된 값 반환 합니다. 두 번째 <xref:System.Windows.Media.Animation.Storyboard> 시작 값으로 캐시 된 값을 사용 하 고 애니메이션을 적용 하기 시작 합니다.  
  
<a name="performancesection"></a>   
## <a name="performance"></a>성능  
  
### <a name="animations-continue-to-run-after-navigating-away-from-a-page"></a>페이지 외부로 이동한 후에도 애니메이션이 계속 실행됨  
 멀리 이동 하는 경우는 <xref:System.Windows.Controls.Page> 재생 될 때까지 계속 해당 애니메이션을 실행 중인 애니메이션을 포함 하는 <xref:System.Windows.Controls.Page> 가비지가 수집 합니다. 사용 중인 탐색 시스템에 따라, 빠져 나간 페이지가 제한 없는 시간 동안 메모리에 남아 있으며 해당 애니메이션을 재생하느라 리소스를 계속 사용할 수 있습니다. 페이지에 계속 실행되는("주변") 애니메이션이 포함되어 있을 때 이러한 상황이 가장 두드러지게 나타납니다.  
  
 이러한 이유로 것이 좋습니다를 사용 하 여 <xref:System.Windows.FrameworkElement.Unloaded> 다른 페이지로 이동할 때 애니메이션을 제거 하는 이벤트입니다.  
  
 애니메이션을 제거하는 방법에는 여러 가지가 있습니다. 다음 기술에 속하는 애니메이션이 제거를 사용할 수는 <xref:System.Windows.Media.Animation.Storyboard>합니다.  
  
-   제거 하는 <xref:System.Windows.Media.Animation.Storyboard> 이벤트 트리거를 시작, 참조 [하는 방법: 스토리 보드 제거](http://msdn.microsoft.com/en-us/7fe39531-de2f-46a0-a69f-b783d04235ee)합니다.  
  
-   코드 제거를 사용 하는 <xref:System.Windows.Media.Animation.Storyboard>, 참조는 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> 메서드.  
  
 애니메이션이 시작된 방법에 관계없이 다음 기법을 사용할 수 있습니다.  
  
-   에서 제거 하려면 애니메이션 특정 속성을 사용 하 여는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 메서드. 첫 번째 매개 변수로 애니메이션 효과가 적용 되는 속성을 지정 하 고 `null` 를 두 번째입니다. 이렇게 하면 해당 속성에서 모든 애니메이션 클록이 제거됩니다.  
  
 속성에 애니메이션 효과를 주는 다양 한 방법에 대 한 자세한 내용은 참조 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)합니다.  
  
### <a name="using-the-compose-handoffbehavior-consumes-system-resources"></a>Compose HandoffBehavior를 사용하여 시스템 리소스 소비  
 적용 하는 경우는 <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline>, 또는 <xref:System.Windows.Media.Animation.AnimationClock> 사용 하 여 속성에는 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior>있으면 모든 <xref:System.Windows.Media.Animation.Clock> 해당 속성을 이전에 연관 된 개체가 시스템 리소스를 소비한 계속 있으며 타이밍 시스템 되지 것입니다 이러한 clock를 자동으로 제거 합니다.  
  
 많은 수의 시계를 사용 하 여 적용 하는 경우 성능 문제를 방지 하려면 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose>를 완성 한 후 속성에서 구성 중인 clock를 제거 해야 합니다. 여러 가지 방법으로 클록을 제거할 수 있습니다.  
  
-   에서 제거 하려면 모든 clock 속성을 사용 하 여는 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> 또는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 애니메이션된 된 개체의 메서드. 첫 번째 매개 변수로 애니메이션 효과가 적용 되는 속성을 지정 하 고 `null` 를 두 번째입니다. 이렇게 하면 해당 속성에서 모든 애니메이션 클록이 제거됩니다.  
  
-   특정을 제거 하려면 <xref:System.Windows.Media.Animation.AnimationClock> 클록 목록에서 사용 하 여는 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성의는 <xref:System.Windows.Media.Animation.AnimationClock> 검색 하는 <xref:System.Windows.Media.Animation.ClockController>, 호출는 <xref:System.Windows.Media.Animation.ClockController.Remove%2A> 의 메서드는 <xref:System.Windows.Media.Animation.ClockController>합니다. 이 일반적으로 수행 된 <xref:System.Windows.Media.Animation.Clock.Completed> 클록에 대 한 이벤트 처리기입니다. 유일한 루트 클록을 제어할 수 있는 참고는 <xref:System.Windows.Media.Animation.ClockController>; <xref:System.Windows.Media.Animation.Clock.Controller%2A> 자식 클록의 속성은 반환 `null`합니다. 또한는 <xref:System.Windows.Media.Animation.Clock.Completed> 이벤트 시계의 유효 기간을 무제한 인 경우 호출 되지 것입니다.  경우에 사용자가 호출 하는 경우를 결정 해야 <xref:System.Windows.Media.Animation.ClockController.Remove%2A>합니다.  
  
 이것은 주로 수명이 긴 개체에 대한 애니메이션에서 문제가 됩니다.  개체가 가비지 수집될 경우 해당 클록도 연결이 끊어지고 가비지가 수집됩니다.  
  
 클록 개체에 대 한 자세한 내용은 참조 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
