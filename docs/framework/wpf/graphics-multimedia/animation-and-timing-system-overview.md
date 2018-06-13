---
title: 애니메이션 및 타이밍 시스템 개요
ms.date: 03/30/2017
helpviewer_keywords:
- timing system [WPF]
- animation [WPF]
ms.assetid: 172cd5a8-a333-4c81-9456-fafccc19f382
ms.openlocfilehash: bfb9a337a604fe8d86d208344d4371748e28f285
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557968"
---
# <a name="animation-and-timing-system-overview"></a>애니메이션 및 타이밍 시스템 개요
이 항목에서는 타이밍 시스템에 애니메이션을 사용 하는 방법을 설명 <xref:System.Windows.Media.Animation.Timeline>, 및 <xref:System.Windows.Media.Animation.Clock> 속성에 애니메이션을 적용 하는 클래스입니다.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목을 이해하려면 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)에 설명된 대로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션을 사용하여 속성에 애니메이션 효과를 줄 수 있어야 합니다. 종속성 속성에 익숙한 것도 도움이 됩니다. 자세한 내용은 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하세요.  
  
<a name="timelinesandclocks"></a>   
## <a name="timelines-and-clocks"></a>타임라인 및 시계  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 어떻게 설명는 <xref:System.Windows.Media.Animation.Timeline> 나타냅니다는 시간과 애니메이션의 세그먼트 유형의 <xref:System.Windows.Media.Animation.Timeline> 출력 값을 생성 하는 합니다. 자체적으로 <xref:System.Windows.Media.Animation.Timeline>, 이외의 작업도 하지 않습니다 시간 세그먼트를 설명 하는 것입니다. 타임 라인의는 <xref:System.Windows.Media.Animation.Clock> 실제 작업을 수행 하는 개체입니다. 마찬가지로, 애니메이션 하지 않는 실제로 애니메이션 효과 줄 속성: 출력 값 계산 되는 방법을, 애니메이션 클래스에 설명 하지만 <xref:System.Windows.Media.Animation.Clock> 애니메이션 속성에 적용 하는 효과 대해 만들어진 합니다.  
  
 A <xref:System.Windows.Media.Animation.Clock> 는 특수 한 유형의 개체에 대 한 타이밍 관련 런타임 상태를 유지 하는 <xref:System.Windows.Media.Animation.Timeline>합니다. 애니메이션, 타이밍 시스템에 꼭 필요한 정보의 3 비트 제공: <xref:System.Windows.Media.Animation.Clock.CurrentTime%2A>, <xref:System.Windows.Media.Animation.Clock.CurrentProgress%2A>, 및 <xref:System.Windows.Media.Animation.Clock.CurrentState%2A>합니다. A <xref:System.Windows.Media.Animation.Clock> 으로 설명 된 타이밍 동작을 사용 하 여의 현재 시간, 진행률 및 상태를 결정 해당 <xref:System.Windows.Media.Animation.Timeline>: <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A>, <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A>등입니다.  
  
 대부분의 경우에는 <xref:System.Windows.Media.Animation.Clock> 일정에 대 한 자동으로 만들어집니다. 사용 하 여 애니메이션 효과 줄 경우는 <xref:System.Windows.Media.Animation.Storyboard> 또는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 시계가 자동으로 타임 라인 및 애니메이션에 대 한 만들어지고 해당 대상된 속성에 적용 합니다. 만들 수도 있습니다는 <xref:System.Windows.Media.Animation.Clock> 를 사용 하 여 명시적으로 <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> 방식의 프로그램 <xref:System.Windows.Media.Animation.Timeline>합니다. <xref:System.Windows.Media.MediaTimeline.CreateClock%2A?displayProperty=nameWithType> 메서드에 대 한 적절 한 형식의 클록 만듭니다는 <xref:System.Windows.Media.Animation.Timeline> 호출 된 합니다. 경우는 <xref:System.Windows.Media.Animation.Timeline> 자식 타임 라인을 포함 만듭니다 <xref:System.Windows.Media.Animation.Clock> 하 개체도 있습니다. 그 결과 <xref:System.Windows.Media.Animation.Clock> 개체의 구조와 일치 하는 트리로 정렬 되는 <xref:System.Windows.Media.Animation.Timeline> 에서 생성 된 개체 트리 합니다.  
  
 다양한 유형의 타임라인에 대한 여러 유형의 시계가 있습니다. 다음 표는 <xref:System.Windows.Media.Animation.Clock> 몇 가지 다른에 해당 하는 형식을 <xref:System.Windows.Media.Animation.Timeline> 형식입니다.  
  
|타임라인 형식|시계 유형|시계 용도|  
|-------------------|----------------|-------------------|  
|애니메이션 (에서 상속 <xref:System.Windows.Media.Animation.AnimationTimeline>)|<xref:System.Windows.Media.Animation.AnimationClock>|종속성 속성에 대한 출력 값을 생성합니다.|  
|<xref:System.Windows.Media.MediaTimeline>|<xref:System.Windows.Media.MediaClock>|미디어 파일을 처리합니다.|  
|<xref:System.Windows.Media.Animation.ParallelTimeline>|<xref:System.Windows.Media.Animation.ClockGroup>|그룹화 하 고 해당 자식 제어 <xref:System.Windows.Media.Animation.Clock> 개체|  
|<xref:System.Windows.Media.Animation.Storyboard>|<xref:System.Windows.Media.Animation.ClockGroup>|그룹화 하 고 해당 자식 제어 <xref:System.Windows.Media.Animation.Clock> 개체|  
  
 적용할 수 있습니다 <xref:System.Windows.Media.Animation.AnimationClock> 호환 되는 종속성 속성을 사용 하 여 만들면 개체는 <xref:System.Windows.Media.Animation.IAnimatable.ApplyAnimationClock%2A> 메서드.  
  
 많은 수의 유사한 개체에 애니메이션을 적용 하는 등의 성능이 시나리오에서 관리 사용자 고유의 <xref:System.Windows.Media.Animation.Clock> 사용 하 여 성능 이점을 제공할 수 있습니다.  
  
<a name="timemanager"></a>   
## <a name="clocks-and-the-time-manager"></a>시계 및 시간 관리자  
 개체에 애니메이션 효과 주는 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 관리 하는 시간 관리자는는 <xref:System.Windows.Media.MediaPlayer.Clock%2A> timeline에 대해 생성 된 개체입니다. 시간 관리자는 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 개체 트리의 루트이며 해당 트리에서 시간의 흐름을 제어합니다.  시간 관리자는 각 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 대해 자동으로 만들어지며 응용 프로그램 개발자에게 표시되지 않습니다. 시간 관리자에서 매초 여러 번 "틱"이 발생하는데 초당 발생하는 실제 틱 수는 사용 가능한 시스템 리소스에 따라 다릅니다. 시간 관리자는 각각이 틱 하는 동안 모든의 상태를 계산 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> 타이밍 트리의 개체입니다.  
  
 다음 그림과 시간 관리자 간의 관계 및 <xref:System.Windows.Media.Animation.AnimationClock>, 및 애니메이션 효과 준된 종속성 속성입니다.  
  
 ![타이밍 시스템 구성 요소](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-1clock1prop.png "graphicsmm_clocks_1clock1prop")  
속성에 애니메이션 효과 주기  
  
 시간 관리자는 틱의 시간 업데이트 모든 <xref:System.Windows.Media.Animation.ClockState.Active> <xref:System.Windows.Media.Animation.Clock> 응용 프로그램에 있습니다. 경우는 <xref:System.Windows.Media.Animation.Clock> 는 <xref:System.Windows.Media.Animation.AnimationClock>를 사용 하 여는 <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> 의 메서드는 <xref:System.Windows.Media.Animation.AnimationTimeline> 에서 작성 된 현재 계산에 출력 값입니다. <xref:System.Windows.Media.Animation.AnimationClock> 제공는 <xref:System.Windows.Media.Animation.AnimationTimeline> 현재 현지 시간, 입력된 값은 일반적으로 속성의 기본 값, 및 기본 대상 값입니다. 애니메이션의 값을 검색 하는 경우 속성을 사용 하 여는 <xref:System.Windows.DependencyObject.GetValue%2A> 의 출력을 얻게 메서드 또는 해당 CLR 접근자 해당 <xref:System.Windows.Media.Animation.AnimationClock>합니다.  
  
#### <a name="clock-groups"></a>시계 그룹  
 이전 섹션 있다는 다양 한 유형의 것을 설명 <xref:System.Windows.Media.Animation.Clock> 다양 한 유형의 타임 라인에 대 한 개체입니다. 다음 그림과 시간 관리자 간의 관계는 <xref:System.Windows.Media.Animation.ClockGroup>, <xref:System.Windows.Media.Animation.AnimationClock>, 및 애니메이션 효과 준된 종속성 속성입니다. A <xref:System.Windows.Media.Animation.ClockGroup> 와 같은 다른 타임 라인을 그룹화 하는 타임 라인에 대해 만들어집니다는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 및 기타 타임 라인을 그룹화 하는 클래스입니다.  
  
 ![타이밍 시스템 구성 요소](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1clockgroup2prop.png "graphicsmm_clocks_2clock1clockgroup2prop")  
ClockGroup  
  
#### <a name="composition"></a>컴퍼지션  
 여러 시계를 단일 속성에 연결할 수 있습니다. 이 경우 각 시계에서 이전 시계의 출력 값을 기준 값으로 사용합니다. 다음 그림에 나와 세 개의 <xref:System.Windows.Media.Animation.AnimationClock> 개체에서 동일한 속성에 적용 합니다. Clock1은 애니메이션 속성의 기준 값을 해당 입력으로 사용하고 이를 사용하여 출력을 생성합니다. Clock2는 Clock1의 출력을 입력으로 받고 이를 사용하여 출력을 생성합니다. Clock3은 Clock2의 출력을 입력으로 받고 이를 사용하여 출력을 생성합니다. 여러 시계가 같은 속성에 동시에 영향을 주는 경우 컴퍼지션 체인에 있다고 합니다.  
  
 ![타이밍 시스템 구성 요소](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-clocks-2clock1prop.png "graphicsmm_clocks_2clock1prop")  
컴퍼지션 체인  
  
 입력 및 출력의 간에 관계가 생성 하지만 <xref:System.Windows.Media.Animation.AnimationClock> 개체 컴퍼지션 체인의 타이밍 미치는 영향을 받지 않습니다. <xref:System.Windows.Media.Animation.Clock> 개체 (포함 하 여 <xref:System.Windows.Media.Animation.AnimationClock> 개체)의 부모에 계층적 종속성이 있는 <xref:System.Windows.Media.Animation.Clock> 개체입니다.  
  
 같은 속성에 여러 시계를 적용 하려면 사용는 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> <xref:System.Windows.Media.Animation.HandoffBehavior> 적용 하는 경우는 <xref:System.Windows.Media.Animation.Storyboard>, 애니메이션 또는 <xref:System.Windows.Media.Animation.AnimationClock>합니다.  
  
#### <a name="ticks-and-event-consolidation"></a>틱 및 이벤트 통합  
 출력 값을 계산하는 것 외에도 시간 관리자는 틱을 발생시킬 때마다 다른 작업을 수행합니다. 각 시계의 상태를 결정하고 적절하게 이벤트를 발생시킵니다.  
  
 틱은 자주 발생하지만 틱 간에 많은 사항이 발생할 수 있습니다. 예를 들어 한 <xref:System.Windows.Media.Animation.Clock> 중지, 시작 및 다시는 쿼리에서 중지 될 수 있습니다는 <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> 값 세 번 변경 됩니다. 이론적으로 <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> 타이밍 엔진은 이벤트를 통합 하는 반면; 이벤트 눈금 하나에 여러 번 발생 시킬 수 있도록는 <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> 이벤트가 틱 당 한 번만 발생할 수 있습니다. 이 모든 타이밍 이벤트에 적용: 각 유형의 최대 하나의 이벤트가 발생 한 지정 된 <xref:System.Windows.Media.Animation.Clock> 개체입니다.  
  
 경우는 <xref:System.Windows.Media.Animation.Clock> 상태를 전환 하 고 원래 상태로 되돌리려면 틱 사이의 반환 (에서 변경 하는 등 <xref:System.Windows.Media.Animation.ClockState.Active> 를 <xref:System.Windows.Media.Animation.ClockState.Stopped> 그리고 다시 <xref:System.Windows.Media.Animation.ClockState.Active>), 연결된 된 이벤트가 계속 발생 합니다.  
  
 타이밍 이벤트에 대한 자세한 내용은 [타이밍 이벤트 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)를 참조하세요.  
  
<a name="currentvaluesbasevaluesofproperties"></a>   
## <a name="current-values-and-base-values-of-properties"></a>속성의 현재 값 및 기준 값  
 애니메이션 효과를 줄 수 있는 속성은 두 값(기준 값 및 현재 값)을 가질 수 있습니다. 해당 CLR 접근자를 사용 하 여 속성을 설정 하면 또는 <xref:System.Windows.DependencyObject.SetValue%2A> 메서드를 설정한 기준 값입니다. 속성에 애니메이션 효과를 줄 수 없는 경우 해당 기준 값과 현재 값은 동일합니다.  
  
 속성에 애니메이션을 적용할 때의 <xref:System.Windows.Media.Animation.AnimationClock> 속성의 설정 *현재* 값입니다. 해당 CLR 접근자를 통해 속성의 값을 검색 또는 <xref:System.Windows.DependencyObject.GetValue%2A> 의 출력을 반환 하는 메서드는 <xref:System.Windows.Media.Animation.AnimationClock> 때는 <xref:System.Windows.Media.Animation.AnimationClock> 은 <xref:System.Windows.Media.Animation.ClockState.Active> 또는 <xref:System.Windows.Media.Animation.ClockState.Filling>합니다. 사용 하 여 속성의 기준 값을 검색할 수 있습니다는 <xref:System.Windows.Media.Animation.IAnimatable.GetAnimationBaseValue%2A> 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [타이밍 이벤트 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-events-overview.md)  
 [타이밍 동작 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
