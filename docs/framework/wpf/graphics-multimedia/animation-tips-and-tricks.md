---
title: "애니메이션에 대한 유용한 정보 | Microsoft Docs"
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
  - "개체에 애니메이션 적용[WPF], 문제 해결"
  - "애니메이션에 대한 유용한 정보[WPF]"
  - "애니메이션[WPF], FillBehavior 속성"
  - "애니메이션[WPF], 시스템 리소스 사용"
  - "성능 문제 해결[WPF], 애니메이션"
  - "유용한 정보[WPF], 애니메이션"
  - "문제 해결[WPF], 애니메이션"
  - "애니메이션 문제 해결[WPF]"
ms.assetid: e467796b-d5d4-45a6-a108-8c5d7ff69a0f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 애니메이션에 대한 유용한 정보
[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 애니메이션을 사용할 때 애니메이션의 성능을 향상시키고 사용자가 문제를 해결할 수 있게 하는 여러 유용한 정보가 있습니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="generalissuessection"></a>   
## 일반 문제  
  
### 스크롤 막대 또는 슬라이더의 위치에 애니메이션 효과를 주면 고정됨  
 <xref:System.Windows.Media.Animation.FillBehavior>가 <xref:System.Windows.Media.Animation.FillBehavior>\(기본값\)인 애니메이션을 사용하여 스크롤 막대 또는 슬라이더의 위치에 애니메이션 효과를 줄 경우 사용자는 더 이상 스크롤 막대나 슬라이더를 이동할 수 없습니다.  이는 애니메이션이 끝나더라도 여전히 대상 속성의 기준 값을 재정의하기 때문입니다.  애니메이션이 속성의 현재 값을 재정의하지 않게 하려면 애니메이션을 제거하거나 <xref:System.Windows.Media.Animation.FillBehavior>인 <xref:System.Windows.Media.Animation.FillBehavior>를 제공합니다.  자세한 내용과 예제는 [Storyboard를 사용하여 애니메이션 효과를 적용한 후 속성 설정](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md)을 참조하십시오.  
  
### 애니메이션의 출력에 애니메이션 효과 적용 시 효과가 없음  
 다른 애니메이션의 출력인 개체에는 애니메이션 효과를 줄 수 없습니다.  예를 들어 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>를 사용하여 <xref:System.Windows.Media.RadialGradientBrush>에서 <xref:System.Windows.Media.SolidColorBrush>로의 애니메이션 효과를 <xref:System.Windows.Shapes.Rectangle>에 <xref:System.Windows.Shapes.Shape.Fill%2A>로 줄 경우 <xref:System.Windows.Media.RadialGradientBrush> 또는 <xref:System.Windows.Media.SolidColorBrush>의 어떠한 속성에도 애니메이션 효과를 줄 수 없습니다.  
  
### 속성에 애니메이션 효과를 준 후 속성 값을 변경할 수 없음  
 경우에 따라 속성에 애니메이션 효과를 준 후 애니메이션이 끝나더라도 속성 값을 변경할 수 없는 것처럼 보일 수 있습니다.  이는 애니메이션이 끝나더라도 여전히 속성의 기준 값을 재정의하기 때문입니다.  애니메이션이 속성의 현재 값을 재정의하지 않게 하려면 애니메이션을 제거하거나 <xref:System.Windows.Media.Animation.FillBehavior>인 <xref:System.Windows.Media.Animation.FillBehavior>를 제공합니다.  자세한 내용과 예제는 [Storyboard를 사용하여 애니메이션 효과를 적용한 후 속성 설정](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-a-property-after-animating-it-with-a-storyboard.md)을 참조하십시오.  
  
### Timeline을 변경해도 효과가 없음  
 대부분의 <xref:System.Windows.Media.Animation.Timeline> 속성은 애니메이션 효과를 줄 수 있고 데이터 바인딩될 수 있지만 활성 <xref:System.Windows.Media.Animation.Timeline>의 속성 값을 변경하면 아무 효과가 없는 것처럼 보입니다.  이는 <xref:System.Windows.Media.Animation.Timeline>이 시작될 경우 타이밍 시스템이 <xref:System.Windows.Media.Animation.Timeline>의 복사본을 만들어 <xref:System.Windows.Media.Animation.Clock> 개체를 만드는 데 사용하기 때문입니다.  원본을 수정하면 시스템의 복사본에 아무 효과도 없습니다.  
  
 <xref:System.Windows.Media.Animation.Timeline>에서 변경 내용을 반영하게 하려면 해당 Clock을 다시 생성하여 이전에 만든 Clock을 대체하는 데 사용해야 합니다.  Clock은 자동으로 다시 생성되지 않습니다.  다음과 같은 방법을 통해 Timeline 변경 내용을 적용합니다.  
  
-   Timeline이 <xref:System.Windows.Media.Animation.Storyboard>이거나 여기에 속해 있는 경우 <xref:System.Windows.Media.Animation.BeginStoryboard> 또는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용하여 해당 Storyboard를 다시 적용하면 변경 내용이 반영되도록 할 수 있습니다.  그러나 이 방법을 사용하면 애니메이션도 다시 시작됩니다.  코드를 사용하는 경우에는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 메서드를 통해 Storyboard를 이전 위치로 다시 이동할 수 있습니다.  
  
-   <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하여 애니메이션을 속성에 직접 적용한 경우에는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 다시 호출하여 수정된 애니메이션을 전달합니다.  
  
-   Clock 수준에서 직접 작업을 수행하는 경우에는 새 Clock 집합을 만들어 적용한 다음 이전에 생성된 Clock 집합을 새 집합으로 대체하여 사용합니다.  
  
 Timeline 및 Clock에 대한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)를 참조하십시오.  
  
### FillBehavior.Stop이 예상대로 작동하지 않음  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.FillBehavior>으로 설정할 경우 효과가 없는 것처럼 보일 경우가 있습니다\(예: <xref:System.Windows.Media.Animation.HandoffBehavior>인 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 설정이 있기 때문에 한 애니메이션이 다른 애니메이션에 "핸드오프"될 경우\).  
  
 다음 예제에서는 <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Shapes.Rectangle> 및 <xref:System.Windows.Media.TranslateTransform>을 만듭니다.  <xref:System.Windows.Media.TranslateTransform>에 애니메이션 효과가 적용되어 <xref:System.Windows.Controls.Canvas> 주위에서 <xref:System.Windows.Shapes.Rectangle>을 이동합니다.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipAnimatedObject](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipanimatedobject)]  
  
 이 단원의 예제에서는 이전 개체를 사용하여 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성이 예상대로 작동하지 않는 여러 경우를 보여 줍니다.  
  
#### 여러 애니메이션이 있는 경우의 FillBehavior\="Stop" 및 HandoffBehavior  
 애니메이션이 두 번째 애니메이션에 의해 대체될 때 해당 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 애니메이션에서 무시하는 것처럼 보이는 경우가 있습니다.  두 개의 <xref:System.Windows.Media.Animation.Storyboard> 개체를 만든 다음 이러한 개체를 사용하여 이전 예제와 같이 동일한 <xref:System.Windows.Media.TranslateTransform>에 애니메이션 효과를 주는 다음 예제를 살펴 보십시오.  
  
 첫 번째 <xref:System.Windows.Media.Animation.Storyboard>, `B1`은 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성에 0에서 350으로 이동하는 애니메이션 효과를 적용하여 사각형을 오른쪽으로 350픽셀 이동합니다.  애니메이션이 지속 기간의 끝에 도달하여 재생을 중지할 경우 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성은 원래 값 0으로 돌아갑니다.  결과적으로 사각형은 오른쪽으로 350픽셀 이동한 다음 원래 위치로 돌아갑니다.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB1Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb1button)]  
  
 두 번째 <xref:System.Windows.Media.Animation.Storyboard>, `B2`도 동일한 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성에 애니메이션 효과를 줍니다.  이 <xref:System.Windows.Media.Animation.Storyboard>에서 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성만 설정되므로 애니메이션은 애니메이션 효과가 적용되는 속성의 현재 값을 시작 값으로 사용합니다.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardB2Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardb2button)]  
  
 첫 번째 <xref:System.Windows.Media.Animation.Storyboard>가 재생되는 동안 두 번째 단추를 클릭할 경우 다음 동작을 예상할 수 있습니다.  
  
1.  애니메이션에 <xref:System.Windows.Media.Animation.FillBehavior>인 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>가 있기 때문에 첫 번째 Storyboard가 끝나고 사각형이 원래 위치로 돌아갑니다.  
  
2.  두 번째 Storyboard는 애니메이션 효과가 적용되고 현재 위치인 0에서 500으로 이동합니다.  
  
 **그러나 이러한 예상대로 작동하지 않습니다.** 사각형은 원래 위치로 이동하지 않고 계속해서 오른쪽으로 이동합니다.  이는 두 번째 애니메이션이 첫 번째 애니메이션의 현재 값을 시작 값으로 사용하고 해당 값에서 500으로 이동하기 때문입니다.  <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.HandoffBehavior>가 사용되므로 두 번째 애니메이션이 첫 번째 애니메이션을 대체할 경우 첫 번째 애니메이션의 <xref:System.Windows.Media.Animation.FillBehavior>는 중요하지 않습니다.  
  
#### FillBehavior 및 Completed 이벤트  
 다음 예제에서는 <xref:System.Windows.Media.Animation.FillBehavior> <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>가 효과가 없는 것처럼 보이는 다른 시나리오를 보여 줍니다.  마찬가지로 이 예제에서는 Storyboard를 사용하여 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성에 0에서 350으로 이동하는 애니메이션 효과를 줍니다.  그러나 이 경우 예제는 <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트를 등록합니다.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardCButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipstoryboardcbutton)]  
  
 <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트 처리기는 동일한 속성을 현재 값에서 500으로 이동하는 애니메이션 효과를 주는 또 다른 <xref:System.Windows.Media.Animation.Storyboard>를 시작합니다.  
  
 [!code-csharp[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml.cs#fillbehaviortipstoryboardc1completedhandler)]
 [!code-vb[AnimationTipsAndTricksSample_snip#FillBehaviorTipStoryboardC1CompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/VisualBasic/FillBehaviorTip.xaml.vb#fillbehaviortipstoryboardc1completedhandler)]  
  
 다음은 두 번째 <xref:System.Windows.Media.Animation.Storyboard>를 리소스로 정의하는 태그입니다.  
  
 [!code-xml[AnimationTipsAndTricksSample_snip#FillBehaviorTipResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AnimationTipsAndTricksSample_snip/CSharp/FillBehaviorTip.xaml#fillbehaviortipresources)]  
  
 <xref:System.Windows.Media.Animation.Storyboard>를 실행할 경우 <xref:System.Windows.Media.TranslateTransform>의 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성이 0에서 350으로 이동하고 완료 후 다시 0으로 돌아가는 애니메이션 효과\(<xref:System.Windows.Media.Animation.FillBehavior>인 <xref:System.Windows.Media.Animation.FillBehavior> 설정으로 인한 효과\)를 주고 그런 다음 0에서 500으로 이동할 것으로 애니메이션 효과를 예상할 것입니다.  그러나 <xref:System.Windows.Media.TranslateTransform>은 0에서 350으로 이동한 다음 500으로 이동합니다.  
  
 이는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 이벤트를 발생시키는 순서와 속성이 무효화되지 않은 경우 속성 값이 캐시되어 다시 계산되지 않기 때문입니다.  <xref:System.Windows.Media.Animation.Timeline.Completed> 이벤트는 루트 Timeline\(첫 번째 <xref:System.Windows.Media.Animation.Storyboard>\)에 의해 트리거되었으므로 가장 먼저 처리됩니다.  이때 <xref:System.Windows.Media.TranslateTransform.X%2A> 속성은 아직 무효화되지 않았으므로 계속해서 애니메이션 효과가 주어진 값을 반환합니다.  두 번째 <xref:System.Windows.Media.Animation.Storyboard>는 캐시된 값을 시작 값으로 사용하고 애니메이션 효과 적용을 시작합니다.  
  
<a name="performancesection"></a>   
## 성능  
  
### 페이지에서 밖으로 탐색한 후에도 애니메이션이 계속 실행됨  
 실행 중인 애니메이션을 포함하는 <xref:System.Windows.Controls.Page>에서 밖으로 탐색할 경우 <xref:System.Windows.Controls.Page>에서 가비지 수집될 때까지 이러한 애니메이션이 계속 재생됩니다.  사용 중인 탐색 시스템에 따라 탐색 중이던 페이지에서 벗어나도 해당 페이지가 무기한 메모리가 남아 있으면서 해당 애니메이션으로 인해 리소스를 소비할 수 있습니다.  지속적으로 실행되는\("앰비언트"\) 애니메이션이 페이지에 포함된 경우 특히 이에 해당합니다.  
  
 이러한 이유 때문에 페이지에서 밖으로 탐색할 경우 <xref:System.Windows.FrameworkElement.Unloaded> 이벤트를 사용하여 애니메이션을 제거하는 것이 좋습니다.  
  
 애니메이션을 제거하는 여러 다른 방법이 있습니다.  다음 방법을 사용하여 <xref:System.Windows.Media.Animation.Storyboard>에 속하는 애니메이션을 제거할 수 있습니다.  
  
-   이벤트 트리거를 사용하여 시작한 <xref:System.Windows.Media.Animation.Storyboard>를 제거하려면 [How to: Remove a Storyboard](http://msdn.microsoft.com/ko-kr/7fe39531-de2f-46a0-a69f-b783d04235ee)를 참조하십시오.  
  
-   코드를 사용하여 <xref:System.Windows.Media.Animation.Storyboard>를 제거하려면 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A> 메서드를 참조하십시오.  
  
 다음 방법은 애니메이션이 시작된 방식에 상관없이 사용할 수 있습니다.  
  
-   특정 속성에서 애니메이션을 제거하려면 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 메서드를 사용합니다.  첫 번째 매개 변수로는 애니메이션을 적용할 속성을 지정하고 두 번째 매개 변수로는 `null`을 지정합니다.  그러면 속성에서 모든 애니메이션 Clock이 제거됩니다.  
  
 속성에 애니메이션 효과를 주는 다양한 방법에 대한 자세한 내용은 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)를 참조하십시오.  
  
### Compose HandoffBehavior를 사용하면 시스템 리소스가 소비됨  
 <xref:System.Windows.Media.Animation.HandoffBehavior> <xref:System.Windows.Media.Animation.HandoffBehavior>를 사용하여 <xref:System.Windows.Media.Animation.Storyboard>, <xref:System.Windows.Media.Animation.AnimationTimeline> 또는 <xref:System.Windows.Media.Animation.AnimationClock>을 속성에 적용하는 경우 이전에 해당 속성에 연결된 <xref:System.Windows.Media.Animation.Clock> 개체에서 계속 시스템 리소스를 사용하며 타이밍 시스템이 Clock을 자동으로 제거하지 않습니다.  
  
 <xref:System.Windows.Media.Animation.HandoffBehavior>를 사용하여 많은 수의 Clock을 적용하는 경우 성능 문제를 피하려면 Clock을 완성한 후 애니메이션 속성에서 구성 중인 Clock을 제거해야 합니다.  Clock을 제거하는 방법은 여러 가지가 있습니다.  
  
-   속성에서 Clock을 모두 제거하려면 애니메이션 개체의 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationClock%29> 또는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 메서드를 사용합니다.  첫 번째 매개 변수로는 애니메이션을 적용할 속성을 지정하고 두 번째 매개 변수로는 `null`을 지정합니다.  그러면 속성에서 모든 애니메이션 Clock이 제거됩니다.  
  
-   Clock 목록에서 특정 <xref:System.Windows.Media.Animation.AnimationClock>을 제거하려면 <xref:System.Windows.Media.Animation.AnimationClock>의 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성을 사용하여 <xref:System.Windows.Media.Animation.ClockController>를 검색한 다음 <xref:System.Windows.Media.Animation.ClockController>의 <xref:System.Windows.Media.Animation.ClockController.Remove%2A> 메서드를 호출합니다.  이 작업은 일반적으로 Clock에 대한 <xref:System.Windows.Media.Animation.Clock.Completed> 이벤트 처리기에서 수행됩니다.  루트 Clock만 <xref:System.Windows.Media.Animation.ClockController>로 제어할 수 있습니다. 자식 Clock의 <xref:System.Windows.Media.Animation.Clock.Controller%2A> 속성은 `null`을 반환합니다.  Clock의 실제 지속 시간이 무제한인 경우 <xref:System.Windows.Media.Animation.Clock.Completed> 이벤트는 호출되지 않습니다.  이런 경우 사용자가 <xref:System.Windows.Media.Animation.ClockController.Remove%2A>를 호출할 시기를 결정해야 합니다.  
  
 이것은 주로 수명이 긴 개체의 애니메이션에 나타나는 문제입니다.  개체에서 가비지가 수집되면 해당 Clock에서도 연결이 끊어지고 가비지가 수집됩니다.  
  
 Clock 개체에 대한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)를 참조하십시오.  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)