---
title: "타이밍 이벤트 개요"
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
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79669bdc4b5f9cfb8bdac92efa07e932cc14ac57
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="timing-events-overview"></a>타이밍 이벤트 개요
이 항목에서는에서 사용할 수 있는 5 개의 타이밍 이벤트를 사용 하는 방법을 설명 <xref:System.Windows.Media.Animation.Timeline> 및 <xref:System.Windows.Media.Animation.Clock> 개체입니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목을 이해하려면 애니메이션을 만들고 사용하는 방법을 이해해야 합니다. 애니메이션을 시작 하려면 참조는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.  
  
 여러 가지 방법으로 속성에 애니메이션 효과를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **스토리 보드 개체를 사용 하 여** (태그 및 코드): 사용할 수 있습니다 <xref:System.Windows.Media.Animation.Storyboard> 개체를 정렬 하 고 하나 이상의 개체에 애니메이션을 배포 합니다. 예를 들어 참조 [속성 스토리 보드를 사용 하 여 애니메이션을 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)합니다.  
  
-   **로컬 애니메이션을 사용 하 여** (코드): 적용할 수 있습니다 <xref:System.Windows.Media.Animation.AnimationTimeline> 애니메이션 효과 주는 속성에 직접 개체입니다. 예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.  
  
-   **클록 사용**(코드만): 클록 생성을 명시적으로 관리하고 애니메이션 클록을 직접 배포할 수 있습니다.  예를 들어 참조 [속성은 AnimationClock를 사용 하 여 애니메이션을 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md)합니다.  
  
 이 개요의 예제를 사용 하는 태그와 코드에서 사용할 수 있습니다, 때문에 <xref:System.Windows.Media.Animation.Storyboard> 개체입니다. 그러나 설명된 개념을 속성에 애니메이션 효과를 주는 다른 방법에도 적용할 수 있습니다.  
  
### <a name="what-is-a-clock"></a>클록이란?  
 타임라인 자체는 실제로 시간 세그먼트를 설명하는 것 이외의 어떤 작업도 수행하지 않습니다. 타임 라인의는 <xref:System.Windows.Media.Animation.Clock> 실제 작업을 수행 하는 개체: 시간 표시 막대에 대 한 타이밍 관련 런타임 상태를 유지 관리 합니다. Storyboard를 사용할 때와 같이 대부분의 경우에 타임라인에 대해 자동으로 클록이 생성됩니다. 만들 수도 있습니다는 <xref:System.Windows.Media.Animation.Clock> 를 사용 하 여 명시적으로 <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> 메서드. 에 대 한 자세한 내용은 <xref:System.Windows.Media.Animation.Clock> 개체 참조는 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)합니다.  
  
## <a name="why-use-events"></a>이벤트를 사용하는 이유  
 하나(마지막 틱에 맞춰진 검색)를 제외한 모든 대화형 타이밍 작업은 비동기적입니다. 실행될 시기를 정확히 알 방법은 없습니다. 타이밍 작업에 의존하는 다른 코드가 있을 때는 문제가 될 수입니다. 사각형에 애니메이션 효과를 적용한 타임라인을 중지하려고 한다고 가정해 보겠습니다. 이 타임라인이 중지된 후에 사각형의 색을 변경합니다.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 앞의 예제에서 두 번째 코드 줄은 Storyboard가 중지되기 전에 실행될 수 있습니다. 중지는 비동기 작업이기 때문입니다. 타임라인이나 클록에 중지하도록 지시하면 타이밍 엔진의 다음 틱까지는 처리되지 않는 일종의 “중지 요청”이 만들어집니다.  
  
 타임라인이 완료된 후에 명령을 실행하려면 타이밍 이벤트를 사용합니다. 다음 예제에서 이벤트 처리기는 Storyboard가 재생을 중지한 후에 사각형의 색을 변경하는 데 사용됩니다.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 자세한 예제를 참조 하십시오. [수신 알림 때 정도 클록의 상태 변경을](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md)합니다.  
  
## <a name="public-events"></a>Public 이벤트  
 <xref:System.Windows.Media.Animation.Timeline> 및 <xref:System.Windows.Media.Animation.Clock> 클래스는 모두 5 개의 타이밍 이벤트를 제공 합니다. 다음 표에는 이러한 이벤트와 해당 이벤트를 트리거하는 조건이 나와 있습니다.  
  
|이벤트(event)|트리거하는 대화형 작업|기타 트리거|  
|-----------|--------------------------------------|--------------------|  
|**Completed**|건너뛰어서 채우기|클록이 완료됩니다.|  
|**CurrentGlobalSpeedInvalidated**|일시 중지, 다시 시작, 검색, 속도 비율 설정, 건너뛰어서 채우기, 중지|클록이 거꾸로 진행되거나, 가속되거나, 시작되거나, 중지됩니다.|  
|**CurrentStateInvalidated**|시작, 건너뛰어서 채우기, 중지|클록이 시작되거나, 중지되거나, 채워집니다.|  
|**CurrentTimeInvalidated**|시작, 검색, 건너뛰어서 채우기, 중지|클록이 진행됩니다.|  
|**RemoveRequested**|제거||  
  
## <a name="ticking-and-event-consolidation"></a>틱 및 이벤트 통합  
 개체에 애니메이션 효과 주는 경우 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 타이밍 엔진 애니메이션을 관리 하입니다. 타이밍 엔진은 시간의 진행을 추적하고 각 애니메이션의 상태를 계산합니다. 1초 안에 이러한 많은 계산 패스가 진행됩니다. 이러한 계산 패스를 "틱"이라고 합니다.  
  
 틱은 자주 발생하지만 틱 간에 많은 사항이 발생할 수 있습니다. 예를 들어 타임라인이 중지되었다가 시작된 후 다시 중지될 수 있습니다. 이 경우 현재 상태는 3번 변경됩니다. 이론적으로 단일 틱에서 이벤트가 여러 번 발생할 수 있지만 타이밍 엔진은 이벤트를 통합하므로 각 이벤트는 틱마다 한 번만 발생할 수 있습니다.  
  
## <a name="registering-for-events"></a>이벤트 등록  
 타이밍 이벤트를 등록하는 방법에는 두 가지가 있습니다. 하나는 타임라인에 등록하는 것이고 다른 하나는 타임라인에서 생성된 클록에 등록하는 것입니다. 이벤트를 클록에 직접 등록하는 과정은 매우 간단합니다. 단, 반드시 코드에서만 수행할 수 있다는 단점이 있습니다. 태그 또는 코드에서 타임라인에 이벤트를 등록할 수 있습니다. 다음 섹션에서는 타임라인에 클록 이벤트를 등록하는 방법을 설명합니다.  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>타임라인에 클록 이벤트 등록  
 하지만 timeline의 <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, 및 <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> 이벤트와 이벤트 처리기를 실제로 연결 하는 이러한 이벤트에 대해 등록 된 타임 라인과 연결 된 것으로 표시는 <xref:System.Windows.Media.Animation.Clock> 타임 라인에 대해 만들어집니다.  
  
 에 대해 등록 하는 <xref:System.Windows.Media.Animation.Timeline.Completed> 타임 라인에서 이벤트, 예를 들어 하면 실제로 이야기 시스템에 대 한 등록을 <xref:System.Windows.Media.Animation.Clock.Completed> 이벤트 시계의 각 만들어진 시간 표시 막대에 대 한 합니다. 이전에이 이벤트에 대 한 등록 해야 코드에서는 <xref:System.Windows.Media.Animation.Clock> 이 타임 라인;에 대해 만들어집니다 알림을 받을 수 없습니다, 합니다. 자동으로 이런 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; 파서가 이전 이벤트에 대 한 자동으로 등록는 <xref:System.Windows.Media.Animation.Clock> 만들어집니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [타이밍 동작 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
