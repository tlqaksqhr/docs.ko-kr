---
title: "타이밍 동작 개요 | Microsoft Docs"
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
  - "동작, 타이밍"
  - "타이밍 동작"
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 타이밍 동작 개요
이 항목에서는 애니메이션 및 기타 <xref:System.Windows.Media.Animation.Timeline> 개체의 타이밍 동작을 설명합니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목의 내용을 이해하려면 기본적인 애니메이션 기능에 대해 잘 알고 있어야 합니다.  자세한 내용은 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)을 참조하십시오.  
  
<a name="timelinetypes"></a>   
## Timeline 형식  
 <xref:System.Windows.Media.Animation.Timeline>은 시간 세그먼트를 나타냅니다.  이는 세그먼트 길이, 시작 시점, 반복 횟수, 해당 세그먼트에서의 진행 속도 등을 지정할 수 있는 속성을 제공합니다.  
  
 Timeline 클래스에서 상속된 클래스는 애니메이션 및 미디어 재생과 같은 추가 기능을 제공합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 다음 <xref:System.Windows.Media.Animation.Timeline> 형식을 제공합니다.  
  
|Timeline 형식|설명|  
|-----------------|--------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|속성에 애니메이션 효과를 주기 위한 출력 값을 생성하는 <xref:System.Windows.Media.Animation.Timeline> 개체에 대한 추상 기본 클래스입니다.|  
|<xref:System.Windows.Media.MediaTimeline>|미디어 파일에서 출력을 생성합니다.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|자식 <xref:System.Windows.Media.Animation.Timeline> 개체를 그룹화하고 제어하는 <xref:System.Windows.Media.Animation.TimelineGroup> 형식입니다.|  
|<xref:System.Windows.Media.Animation.Storyboard>|포함하고 있는 Timeline 개체에 대한 대상 정보를 제공하는 <xref:System.Windows.Media.Animation.ParallelTimeline> 형식입니다.|  
|<xref:System.Windows.Media.Animation.Timeline>|타이밍 동작을 정의하는 추상 기본 클래스입니다.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|다른 <xref:System.Windows.Media.Animation.Timeline> 개체를 포함할 수 있는 <xref:System.Windows.Media.Animation.Timeline> 개체에 대한 추상 클래스입니다.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## Timeline의 길이를 제어하는 속성  
 <xref:System.Windows.Media.Animation.Timeline>은 시간 세그먼트를 나타내며 Timeline의 길이는 다른 방법으로 설명할 수 있습니다.  다음 표에서는 Timeline의 길이를 설명하는 몇 가지 값을 정의합니다.  
  
|용어|설명|속성||||  
|--------|--------|--------|-|-|-|  
|단순 지속 시간|Timeline이 한 번 앞으로 반복하는 데 걸리는 시간입니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|단일 반복|Timeline이 한 번 앞으로 재생하는 데 걸리는 시간으로 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성이 true이면 뒤로 한 번 재생합니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|활성 기간|Timeline이 <xref:System.Windows.Media.Animation.RepeatBehavior> 속성으로 지정한 모든 반복을 완료하는 데 걸리는 시간입니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### Duration 속성  
 앞서 설명한 것처럼 Timeline은 시간 세그먼트를 나타냅니다.  이 세그먼트의 길이는 Timeline의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>에 의해 결정됩니다.  Timeline이 이 지속 시간의 끝에 도달하면 재생이 중지됩니다.  Timeline에 자식 Timeline이 있는 경우 자식 Timeline의 재생도 중지됩니다.  애니메이션의 경우 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>은 애니메이션이 해당 시작 값에서 종료 값까지 전환하는 데 걸리는 시간을 지정합니다.  Timeline의 지속 시간은 한 번 반복할 때의 지속 시간과 여러 번의 반복을 포함하는 애니메이션 전체 재생 시간을 구분하기 위해 단순 지속 시간이라고도 합니다.  제한 시간 값 또는 특수 값인 <xref:System.Windows.Duration.Automatic%2A> 또는 <xref:System.Windows.Duration.Forever%2A>를 사용하여 지속 시간을 지정할 수 있습니다.  애니메이션 지속 시간은 <xref:System.Windows.Duration.TimeSpan%2A> 값으로 적용되어야 하므로 값을 전환할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>이 5초인 <xref:System.Windows.Media.Animation.DoubleAnimation>을 보여 줍니다.  
  
  
  
 <xref:System.Windows.Media.Animation.Storyboard> 및 <xref:System.Windows.Media.Animation.ParallelTimeline>과 같은 컨테이너 Timeline의 지속 시간 기본값은 <xref:System.Windows.Duration.Automatic%2A>으로 마지막 자식의 재생이 중지되면 자동으로 종료됩니다.  다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>이 5초인 <xref:System.Windows.Media.Animation.Storyboard>를 보여 주는데, 이는 모든 자식 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체가 완료되는 데 걸리는 시간입니다.  
  
  
  
 컨테이너 Timeline의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>을 <xref:System.Windows.Duration.TimeSpan%2A> 값으로 설정함으로써 자식 <xref:System.Windows.Media.Animation.Timeline> 개체의 재생 시간보다 더 길게 또는 더 짧게 재생할 수 있습니다.  <xref:System.Windows.Media.Animation.Timeline.Duration%2A>을 컨테이너 Timeline의 자식 <xref:System.Windows.Media.Animation.Timeline> 개체의 길이보다 작은 값으로 설정하면 자식 <xref:System.Windows.Media.Animation.Timeline> 개체는 컨테이너 Timeline 재생 시 재생을 중지합니다.  다음 예제에서는 이전 예제의 <xref:System.Windows.Media.Animation.Storyboard>의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>을 3초로 설정합니다.  그 결과 대상 사각형 너비의 애니메이션 효과를 60으로 설정하면 <xref:System.Windows.Media.Animation.DoubleAnimation>은 3초 후에 진행이 중지됩니다.  
  
  
  
<a name="repeatinganimations"></a>   
### RepeatBehavior 속성  
 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 단순 지속 시간 반복 횟수를 제어합니다.  <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 Timeline 재생 횟수\(반복 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>\)를 지정하거나 재생해야 하는 총 시간\(반복 <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>\)을 지정할 수 있습니다.  두 경우 모두 애니메이션은 요청된 횟수 또는 지속 시간이 충족될 때까지 처음부터 끝까지 반복 실행됩니다.  기본적으로 Timeline에는 반복 횟수가 `1.0`으로 지정되므로 한 번만 재생되고 반복되지 않습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 반복 횟수를 지정함으로써 단순 지속 시간의 두 배의 시간 동안 <xref:System.Windows.Media.Animation.DoubleAnimation>이 재생되도록 합니다.  
  
  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 <xref:System.Windows.Media.Animation.DoubleAnimation>이 단순 지속 시간의 절반 동안 재생되도록 합니다.  
  
  
  
 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>로 설정하면 <xref:System.Windows.Media.Animation.Timeline>은 대화형으로 또는 타이밍 시스템에 의해 중지될 때까지 반복합니다.  다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 사용하여 <xref:System.Windows.Media.Animation.DoubleAnimation>이 무한 재생되도록 합니다.  
  
  
  
 다른 예제를 보려면 [애니메이션 반복](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)을 참조하십시오.  
  
<a name="autoreverseproperty"></a>   
### AutoReverse 속성  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성은 <xref:System.Windows.Media.Animation.Timeline>이 앞으로 반복이 끝나면 뒤로 재생할 것인지 여부를 지정합니다.  다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성을 `true`로 지정하고, 그 결과 0에서 100 사이에 애니메이션 효과를 적용한 다음 다시 100에서 0 사이에 애니메이션 효과를 적용합니다.  총 10초 동안 재생합니다.  
  
  
  
 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 값을 사용하여 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>를 지정하고 그 <xref:System.Windows.Media.Animation.Timeline>의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성이 `true`인 경우 단일 반복은 한 번의 앞으로 반복 다음에 한 번의 뒤로 반복이 나오도록 구성됩니다.  다음 예제에서는 이전 예제의 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>를 둘 중에 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>로 설정합니다.  그 결과 <xref:System.Windows.Media.Animation.DoubleAnimation>은 5초 동안 앞으로, 5초 동안 뒤로, 다시 5초 동안 앞으로 그리고 5초 동안 뒤로 재생되어 총 20초 동안 재생됩니다.  
  
  
  
 컨테이너 Timeline에 자식 <xref:System.Windows.Media.Animation.Timeline> 개체가 있는 경우 컨테이너 Timeline이 뒤로 재생되면 자식 개체도 뒤로 재생됩니다.  다른 예제를 보려면 [Timeline을 자동으로 뒤집을지 여부 지정](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)를 참조하십시오.  
  
<a name="timelinebegin"></a>   
## BeginTime 속성  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성을 사용하면 Timeline이 시작되는 시점을 지정할 수 있습니다.  Timeline 시작 시간은 부모 Timeline에 따라 달라집니다.  시작 시간이 0초인 경우 이는 부모가 시작되자마자 Timeline이 시작된다는 것을 의미하며, 값이 있는 경우 이는 부모 Timeline이 재생을 시작하는 시간과 자식 Timeline이 재생하는 시간 사이의 오프셋을 의미합니다.  예를 들어 시작 시간이 2초인 경우 이는 부모가 2초에 도달하는 시점에 해당 Timeline이 재생을 시작한다는 의미입니다.  기본적으로 모든 Timeline의 시작 시간은 0초입니다.  또한 Timeline의 시작 시간을 `null`로 설정하여 Timeline이 시작되지 않도록 할 수도 있습니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 [x:Null 태그 확장](../../../../docs/framework/xaml-services/x-null-markup-extension.md)을 사용하여 Null을 지정합니다.  
  
 Timeline의 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 설정으로 인해 Timeline이 반복될 때마다 시작 시간이 적용되는 것은 아닙니다.  <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>이 10초이고 <xref:System.Windows.Media.Animation.RepeatBehavior>가 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>인 애니메이션을 만드는 경우 맨 처음 애니메이션이 재생되기 전까지 10초의 지연이 발생하지만 이후 반복될 때마다 매번 그런 것은 아닙니다.  그러나 애니메이션의 부모 Time이 다시 시작되거나 반복되는 경우 10초 지연이 발생합니다.  
  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성은 Timeline 간에 시간 차이를 둘 때 유용합니다.  다음 예제에서는 두 개의 자식 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체가 있는 <xref:System.Windows.Media.Animation.Storyboard>를 만듭니다.  첫 번째 애니메이션은 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>이 5초이고, 두 번째는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>이 3초입니다.  이 예제에서는 두 번째 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>을 5초로 설정하였으므로 첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimation>이 종료된 다음에 재생을 시작합니다.  
  
  
  
<a name="fillbehaviorproperty"></a>   
## FillBehavior 속성  
 <xref:System.Windows.Media.Animation.Timeline>이 총 활성 지속 시간의 끝에 도달하면 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 중지할지 또는 마지막 값을 보유할지를 지정합니다.  <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>가 <xref:System.Windows.Media.Animation.FillBehavior>인 애니메이션은 출력 값을 "보유"합니다. 즉, 애니메이션 효과를 받는 속성이 해당 애니메이션의 마지막 값을 보유합니다.  <xref:System.Windows.Media.Animation.FillBehavior> 값은 종료 후에 애니메이션이 대상 속성에 더 이상 영향을 미치지 않도록 합니다.  
  
 다음 예제에서는 두 개의 자식 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체가 있는 <xref:System.Windows.Media.Animation.Storyboard>를 만듭니다.  두 개의 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체가 모두 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>에 0에서 100 사이에 애니메이션 효과를 적용합니다.  <xref:System.Windows.Shapes.Rectangle> 요소는 500 [장치 독립적 픽셀](GTMT)의 <xref:System.Windows.FrameworkElement.Width%2A> 값으로 애니메이션 효과를 적용하지 않습니다.  
  
-   첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 기본값인 <xref:System.Windows.Media.Animation.FillBehavior>로 설정됩니다.  그 결과 사각형의 너비는 <xref:System.Windows.Media.Animation.DoubleAnimation>이 종료된 후에 100으로 유지됩니다.  
  
-   두 번째 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 <xref:System.Windows.Media.Animation.FillBehavior>으로 설정됩니다.  그 결과 두 번째 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>는 <xref:System.Windows.Media.Animation.DoubleAnimation>이 종료된 후 500으로 되돌아갑니다.  
  
  
  
<a name="speedproperties"></a>   
## Timeline의 속도를 제어하는 속성  
 <xref:System.Windows.Media.Animation.Timeline> 클래스는 속도를 지정하는 세 가지 속성을 제공합니다.  
  
-   <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> – <xref:System.Windows.Media.Animation.Timeline>에 대한 진행 속도로 부모에 상대적인 비율을 지정합니다.  1보다 큰 값을 지정하면 <xref:System.Windows.Media.Animation.Timeline> 및 자식 <xref:System.Windows.Media.Animation.Timeline> 개체의 속도가 빨라지고 0에서 1 사이의 값을 지정하면 속도가 느려집니다.  1 값을 지정하면 <xref:System.Windows.Media.Animation.Timeline> 부모와 같은 속도로 진행됩니다.  컨테이너 Timeline의 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> 설정은 모든 자식 <xref:System.Windows.Media.Animation.Timeline> 개체에도 영향을 미칩니다.  
  
-   <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> – 가속에 소요된 Timeline <xref:System.Windows.Media.Animation.Timeline.Duration%2A>의 비율\(%\)을 지정합니다.  예제를 보려면 [애니메이션 가속 또는 감속](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md)을 참조하십시오.  
  
-   <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> \- 감속에 소요된 Timeline <xref:System.Windows.Media.Animation.Timeline.Duration%2A>의 비율\(%\)을 지정합니다.  예제를 보려면 [애니메이션 가속 또는 감속](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md)을 참조하십시오.  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [타이밍 이벤트 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)   
 [Animation Timing Behavior 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)