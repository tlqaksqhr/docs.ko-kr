---
title: 타이밍 동작 개요
ms.date: 03/30/2017
helpviewer_keywords:
- timing behaviors [WPF]
- behaviors [WPF], timing
ms.assetid: 5b714d46-bd46-48b8-b467-b4be89ba3091
ms.openlocfilehash: 31a6b7d3b92e886d9c90fc39d69f31cf72b99666
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566326"
---
# <a name="timing-behaviors-overview"></a>타이밍 동작 개요
이 항목에서는 애니메이션 및 기타의 타이밍 동작을 설명 <xref:System.Windows.Media.Animation.Timeline> 개체입니다.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 기본 애니메이션 기능을 잘 알고 있어야 입니다. 자세한 내용은 참조는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.  
  
<a name="timelinetypes"></a>   
## <a name="timeline-types"></a>타임라인 형식  
 A <xref:System.Windows.Media.Animation.Timeline> 시간을 세그먼트를 나타냅니다. 해당 세그먼트의 길이, 시작 시기, 반복 횟수, 해당 세그먼트에서 진행되는 속도 등을 지정할 수 있는 속성이 제공됩니다.  
  
 타임라인 클래스에서 상속하는 클래스는 애니메이션 및 미디어 재생 등의 추가 기능을 제공합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다음과 같은 장점이 <xref:System.Windows.Media.Animation.Timeline> 형식입니다.  
  
|타임라인 형식|설명|  
|-------------------|-----------------|  
|<xref:System.Windows.Media.Animation.AnimationTimeline>|추상 기본 클래스에 대 한 <xref:System.Windows.Media.Animation.Timeline> 애니메이션 속성에 대 한 출력 값을 생성 하는 개체입니다.|  
|<xref:System.Windows.Media.MediaTimeline>|미디어 파일에서 출력을 생성합니다.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|유형의 <xref:System.Windows.Media.Animation.TimelineGroup> 그룹 및 컨트롤 자식 <xref:System.Windows.Media.Animation.Timeline> 개체입니다.|  
|<xref:System.Windows.Media.Animation.Storyboard>|유형의 <xref:System.Windows.Media.Animation.ParallelTimeline> 포함 하는 시간 표시 막대 개체에 대 한 대상 정보를 제공 하는 합니다.|  
|<xref:System.Windows.Media.Animation.Timeline>|타이밍 동작을 정의하는 추상 기본 클래스입니다.|  
|<xref:System.Windows.Media.Animation.TimelineGroup>|추상 클래스에 대 한 <xref:System.Windows.Media.Animation.Timeline> 다른 포함할 수 있는 개체 <xref:System.Windows.Media.Animation.Timeline> 개체입니다.|  
  
<a name="propertiesthatcontroltimelinelength"></a>   
## <a name="properties-that-control-the-length-of-a-timeline"></a>타임라인의 길이를 제어하는 속성  
 A <xref:System.Windows.Media.Animation.Timeline> 나타내는 시간을 세그먼트와 타임 라인의 길이 서로 다른 방식에서으로 설명할 수 있습니다. 다음 표에서는 타임라인의 길이를 설명하기 위한 몇 가지 용어를 정의합니다.  
  
|용어|설명|속성||||  
|----------|-----------------|----------------|-|-|-|  
|단순 지속 시간|타임라인이 단일 정방향 반복을 수행하는 데 걸리는 시간입니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>||||  
|1회 반복|일정을 하는 경우 한 앞으로 재생 하는 데 걸리는 시간의 길이 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성이 true 이면 한 번만 이전 버전과 재생 합니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>||||  
|활성 기간|일정으로 지정 된 모든 반복을 완료 하는 데 걸리는 시간의 길이 <xref:System.Windows.Media.Animation.RepeatBehavior> 속성입니다.|<xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>, <xref:System.Windows.Media.Animation.RepeatBehavior>||||  
  
<a name="duration"></a>   
### <a name="the-duration-property"></a>Duration 속성  
 앞서 설명한 것처럼 타임라인은 시간 세그먼트를 나타냅니다. 이 세그먼트의 길이 타임 라인의 따라 사용자가 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>합니다. 타임라인이 기간 끝에 도달하면 재생을 중지합니다. 타임라인에 자식 타임라인이 있어도 재생을 중지합니다. 애니메이션의 경우는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 애니메이션의 소요 시간 전환의 시작 값 끝 값을 지정 합니다. 시간 표시 막대의 라고도 해당 *단순 지속 기간 동안*, 단일 반복의 기간 및 애니메이션 반복을 포함 하 여 재생 시간을 총 길이 구분 하기 위해 합니다. 제한 시간 값 또는 특수 한 값을 사용 하는 기간을 지정할 수 있습니다 <xref:System.Windows.Duration.Automatic%2A> 또는 <xref:System.Windows.Duration.Forever%2A>합니다. 애니메이션의 지속 시간을 해결 해야는 <xref:System.Windows.Duration.TimeSpan%2A> 값 이므로 값을 전환할 수 있습니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 와 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 초입니다.  
  
 [!code-xaml[animation_ovws_snippet#AnimationWith5SecondDurationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#animationwith5seconddurationinline)]  
  
 컨테이너 타임 라인와 같은 <xref:System.Windows.Media.Animation.Storyboard> 및 <xref:System.Windows.Media.Animation.ParallelTimeline>의 지속 시간 기본값 <xref:System.Windows.Duration.Automatic%2A>, 즉, 마지막 자식 해당 재생이 중지 되 면 자동으로 종료 합니다. 다음 예제에서는 한 <xref:System.Windows.Media.Animation.Storyboard> 인 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 초 마다 모든 자식에 걸리는 시간의 길이를 확인 <xref:System.Windows.Media.Animation.DoubleAnimation> 완료 하는 개체입니다.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelineexampleinline)]  
  
 설정 하 여는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 하는 컨테이너 타임 라인의 한 <xref:System.Windows.Duration.TimeSpan%2A> 자식 보다 길거나 짧은 재생을 강제 수 값을 <xref:System.Windows.Media.Animation.Timeline> 개체의 재생 합니다. 설정 하는 경우는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 컨테이너 타임 라인의 자식의 길이 보다 작은 값으로 <xref:System.Windows.Media.Animation.Timeline> 개체, 자식 <xref:System.Windows.Media.Animation.Timeline> 개체 컨테이너 타임 라인을 수행 하는 경우 재생을 중지 합니다. 다음 예에서는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 의 <xref:System.Windows.Media.Animation.Storyboard> 3 초를 앞의 예제에서 합니다. 결과적으로, 첫 번째 <xref:System.Windows.Media.Animation.DoubleAnimation> 60 대상 사각형의 너비에 때 애니메이션이 적용 3 초 후에 진행이 중지 됩니다.  
  
 [!code-xaml[animation_ovws_snippet#ContainerTimelineWithShorterDurationExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#containertimelinewithshorterdurationexampleinline)]  
  
<a name="repeatinganimations"></a>   
### <a name="the-repeatbehavior-property"></a>RepeatBehavior 속성  
 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성은 <xref:System.Windows.Media.Animation.Timeline> 단순 지속 시간을 반복 하는 횟수를 제어 합니다. 사용 하는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 timeline 재생 횟수를 지정할 수 있습니다 (반복 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A>) 또는 재생 해야 하는 총 기간 (반복 <xref:System.Windows.Media.Animation.RepeatBehavior.Duration%2A>). 두 경우 모두 애니메이션은 요청된 횟수 또는 기간을 채우는 데 필요한만큼 시작-끝 실행을 반복합니다. 기본적으로 타임 라인의 반복 횟수를가지고 `1.0`, 즉 한 번 재생 되 고 반복 전혀 실행 되지 않습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 반복 횟수를 지정 하 여 두 번 단순 지속 시간 동안 재생 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior2xExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior2xexampleinline)]  
  
 사용 하 여 다음 예제는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을는 <xref:System.Windows.Media.Animation.DoubleAnimation> 절반 단순 지속 시간 동안 재생 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehavior05xExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehavior05xexampleinline)]  
  
 설정 하는 경우는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성은 <xref:System.Windows.Media.Animation.Timeline> 를 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, <xref:System.Windows.Media.Animation.Timeline> 대화형 또는 타이밍 시스템에 의해 중지 될 때까지 반복 합니다. 다음 예제에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 속성을는 <xref:System.Windows.Media.Animation.DoubleAnimation> 무한 재생 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBRepeatBehaviorForeverExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbrepeatbehaviorforeverexampleinline)]  
  
 추가 예제를 참조 하십시오. [애니메이션 반복](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)합니다.  
  
<a name="autoreverseproperty"></a>   
### <a name="the-autoreverse-property"></a>AutoReverse 속성  
 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성 지정 여부는 <xref:System.Windows.Media.Animation.Timeline> 앞으로 반복의 끝에 이전 버전과 재생 됩니다. 다음 예제에서는 설정는 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation> 를 `true`; 결과적으로, 그 다음 100이 0 인 0 ~ 100, 애니메이션 효과가 적용 합니다. 총 10초 동안 재생됩니다.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverseexampleinline)]  
  
 사용 하는 경우는 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 지정할 값은 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 의 <xref:System.Windows.Media.Animation.Timeline> 및 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성의 <xref:System.Windows.Media.Animation.Timeline> 은 `true`, 단일 반복 하나로 구성 앞으로 반복을 동반 뒤로 반복 합니다.  다음 예에서는 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 의 <xref:System.Windows.Media.Animation.DoubleAnimation> 앞의 예제에서 한 <xref:System.Windows.Media.Animation.RepeatBehavior.Count%2A> 두 합니다. 결과적으로,는 <xref:System.Windows.Media.Animation.DoubleAnimation> 20 초 동안 재생: 5 초 마다 5 초 동안 뒤로 다시 5 초 동안 전달에 대 한 앞으로 5 초 동안 뒤로 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBAutoReverseRepeatExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbautoreverserepeatexampleinline)]  
  
 컨테이너 타임 라인에 자식 <xref:System.Windows.Media.Animation.Timeline> 개체, 컨테이너 타임 라인을 수행 하는 경우를 반대로 합니다. 추가 예제를 참조 하십시오. [지정 여부는 타임 라인 자동으로 반대로 바꿉니다](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-whether-a-timeline-automatically-reverses.md)합니다.  
  
<a name="timelinebegin"></a>   
## <a name="the-begintime-property"></a>BeginTime 속성  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성을 사용 하면 타임 라인 시작 될 때 지정할 수 있습니다.  타임라인의 시작 시간은 부모 타임라인에 상대적입니다. 타임라인 0초는 부모 타임라인이 시작되자마자 해당 타임라인이 시작됨을 의미합니다. 다른 값을 지정하면 부모 타임라인이 재생을 시작하는 시간과 자식 타임라인이 재생되는 시간 사이에 오프셋이 생성됩니다. 예를 들어 시작 시간이 2초면 부모 타임라인이 2초에 도달할 때 해당 타임라인이 재생을 시작함을 의미합니다. 기본적으로 모든 타임라인의 시작 시간은 0초입니다. 타임 라인의를 설정할 수도 있습니다 시작 시간을 `null`, 시간 표시 막대를 시작할 수 없습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용 하 여 null을 지정 된 [X:null 태그 확장](../../../../docs/framework/xaml-services/x-null-markup-extension.md)합니다.  
  
 시작 시간 하지 않습니다 적용 시간 표시 막대 반복 될 때마다 해당 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 설정 합니다. 애니메이션을 만들려는 경우 한 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 10 초 및 <xref:System.Windows.Media.Animation.RepeatBehavior> 의 <xref:System.Windows.Media.Animation.RepeatBehavior.Forever%2A>, 처음으로 하지만 각 연속 반복에 대해 애니메이션이 재생 하기 전에 10 초 지연 됩니다. 그러나 애니메이션의 부모 타임라인이 다시 시작되거나 반복되면 10초의 지연이 발생할 것입니다.  
  
 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 속성은 타임 라인 시차를 적용 하는 데 유용 합니다. 다음 예제에서는 한 <xref:System.Windows.Media.Animation.Storyboard> 하는 두 명의 자식 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체입니다. 첫 번째 애니메이션은 한 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 초의 있고 두 번째는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 3 초입니다. 예제에서는 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 두 번째 <xref:System.Windows.Media.Animation.DoubleAnimation> 을 5 초로 하므로 재생을 시작은 첫 번째 이후 <xref:System.Windows.Media.Animation.DoubleAnimation> 종료 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBBeginTimeExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbbegintimeexampleinline)]  
  
<a name="fillbehaviorproperty"></a>   
## <a name="the-fillbehavior-property"></a>FillBehavior 속성  
 경우는 <xref:System.Windows.Media.Animation.Timeline> 총 해당 활성 기간의 끝에 도달는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성 중지 마지막 값을 유지 여부를 지정 합니다. 애니메이션을는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 의 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd> 애니메이션이 출력 값에 "포함": 애니메이션의 마지막 값이 유지 되는 속성입니다. 값이 <xref:System.Windows.Media.Animation.FillBehavior.Stop> 종료 된 후 대상 속성에 영향을 주는 애니메이션 중지를 발생 합니다.  
  
 다음 예제에서는 한 <xref:System.Windows.Media.Animation.Storyboard> 하는 두 명의 자식 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체입니다. 둘 다 <xref:System.Windows.Media.Animation.DoubleAnimation> 애니메이션 효과 줄 개체는 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Shapes.Rectangle> 0에서 100 사이의 합니다. <xref:System.Windows.Shapes.Rectangle> 애니메이션이 적용 되지 않은 요소에는 <xref:System.Windows.FrameworkElement.Width%2A> 500 [장치 독립적 픽셀]의 값입니다.  
  
-   <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 첫 번째 속성 <xref:System.Windows.Media.Animation.DoubleAnimation> 로 설정 된 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, 기본값입니다. 사각형의 너비 머무르 후 100 결과적으로 <xref:System.Windows.Media.Animation.DoubleAnimation> 종료 합니다.  
  
-   <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 두 번째 속성 <xref:System.Windows.Media.Animation.DoubleAnimation> 로 설정 된 <xref:System.Windows.Media.Animation.FillBehavior.Stop>합니다. 결과적으로 <xref:System.Windows.FrameworkElement.Width%2A> 두 번째 <xref:System.Windows.Shapes.Rectangle> 되돌린 후 500는 <xref:System.Windows.Media.Animation.DoubleAnimation> 종료 합니다.  
  
 [!code-xaml[animation_ovws_snippet#TBFillBehaviorExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animation_ovws_snippet/CS/TimingBehaviorsExample1.xaml#tbfillbehaviorexample)]  
  
<a name="speedproperties"></a>   
## <a name="properties-that-control-the-speed-of-a-timeline"></a>타임라인의 속도를 제어하는 속성  
 <xref:System.Windows.Media.Animation.Timeline> 클래스의 속도 지정 하기 위한 세 가지 속성을 제공 합니다.  
  
-   <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> – 비율을 지정 합니다 시간이 진행 되는 부모에 상대적인는 <xref:System.Windows.Media.Animation.Timeline>합니다. 1 보다 큰 값의 속도 높이기는 <xref:System.Windows.Media.Animation.Timeline> 와 해당 자식 <xref:System.Windows.Media.Animation.Timeline> 개체, 값 0과 1 사이의 속도가 저하 됩니다. 값이 1 이면 <xref:System.Windows.Media.Animation.Timeline> 부모와 같은 속도로 진행 합니다. <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> 는 컨테이너 타임 라인의 설정은 모든 자식 <xref:System.Windows.Media.Animation.Timeline> 개체도 있습니다.  
  
-   <xref:System.Windows.Media.Animation.Timeline.AccelerationRatio%2A> –의 백분율을 지정 합니다.는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 가 속하는 데 걸리는 시간 표시 막대의 합니다. 예를 들어 참조 [하는 방법: 가속화 애니메이션 또는 감속](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md)합니다. 
  
-   <xref:System.Windows.Media.Animation.Timeline.DecelerationRatio%2A> -의 백분율을 지정 합니다.는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 감속 소요 된 일정입니다. 예를 들어 참조 [하는 방법: 가속화 애니메이션 또는 감속](../../../../docs/framework/wpf/graphics-multimedia/how-to-accelerate-or-decelerate-an-animation.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [타이밍 이벤트 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)  
 [애니메이션 타이밍 동작 샘플](http://go.microsoft.com/fwlink/?LinkID=159970)
