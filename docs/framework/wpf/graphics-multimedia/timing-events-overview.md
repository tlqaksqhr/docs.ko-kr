---
title: "타이밍 이벤트 개요 | Microsoft Docs"
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
  - "Clock 클래스"
  - "클래스, 시계"
  - "Timeline"
  - "타이밍 이벤트"
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 타이밍 이벤트 개요
이 항목에서 사용할 수 있는&5; 개의 타이밍 이벤트를 사용 하는 방법에 설명 <xref:System.Windows.Media.Animation.Timeline> 및 <xref:System.Windows.Media.Animation.Clock> 개체입니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목을 이해 하려면 만들고 애니메이션을 사용 하는 방법을 이해 해야 합니다. 애니메이션을 시작 하려면 참조는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.  
  
 여러 가지 방법으로 속성에 애니메이션 효과를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **스토리 보드 개체를 사용 하 여** (태그 및 코드): 사용할 수 있습니다 <xref:System.Windows.Media.Animation.Storyboard> 개체를 정렬 하 고 하나 이상의 개체에 애니메이션을 배포 합니다. 예를 들어 참조 [스토리 보드를 사용 하 여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)합니다.  
  
-   **로컬 애니메이션을 사용 하 여** (코드): 적용할 수 있습니다 <xref:System.Windows.Media.Animation.AnimationTimeline> 애니메이션을 적용 하는 속성에 직접 개체입니다. 예를 들어 참조 [속성 없이 사용 하는 스토리 보드에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)합니다.  
  
-   **시계를 사용 하 여** (코드): 명시적으로 시계 생성을 관리 하 고 애니메이션 clock 직접 배포할 수 있습니다.  예를 들어 참조 [AnimationClock을 사용 하 여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md)합니다.  
  
 이 개요의 예제를 사용 하는 태그와 코드에 사용할 수 있습니다, 있으므로 <xref:System.Windows.Media.Animation.Storyboard> 개체입니다. 그러나 다른 속성에 애니메이션 적용 방법에 설명 된 개념을 적용할 수 있습니다.  
  
### <a name="what-is-a-clock"></a>Clock 무엇입니까?  
 타임 라인을 자체적으로 실제로 아무런 동작이 수행 되지 이외의 다른 시간 세그먼트에 설명 합니다. 타임 라인의는 <xref:System.Windows.Media.Animation.Clock> 실제 작업을 수행 하는 개체: 시간 표시 막대에 대 한 타이밍 관련 런타임 상태를 유지 관리 합니다. 같은 경우 storyboard를 사용 하 여 대부분의 경우 클록이 자동으로 만들어지며 일정에 대 한 만들 수도 있습니다는 <xref:System.Windows.Media.Animation.Clock> 를 사용 하 여 명시적으로 <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> 메서드. 에 대 한 자세한 내용은 <xref:System.Windows.Media.Animation.Clock> 개체 참조는 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)합니다.  
  
## <a name="why-use-events"></a>이벤트를 사용 하는 이유는?  
 제외한 나머지 (마지막 틱에 정렬 된 검색), 모든 대화형 타이밍 작업은 비동기적입니다. 정확 하 게 실행 되는 시점을 알 수 있는 방법은 없습니다. 타이밍 작업이 종속 된 다른 코드가 있는 경우 문제가 될 수입니다. 사각형에 애니메이션 효과 타임 라인을 중지 하려는 것을 가정 합니다. 타임 라인 중지 된 후 사각형의 색을 변경 합니다.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 앞의 예제 코드의 두 번째 줄은 스토리 보드가 중단 하기 전에 실행할 수 있습니다. 중지 하는 비동기 작업 때문입니다. 시간 표시 막대 또는 시계를 중지 하 라는 요청을 만듭니다 "stop" 일종의 타이밍 엔진의 다음 틱 될 때까지 처리 되지 않는.  
  
 타이밍 이벤트를 사용 하는 타임 라인 완료 된 후 명령을 실행 합니다. 다음 예제에서는 이벤트 처리기는 스토리 보드 재생이 중지 되 면 사각형의 색을 변경 하려면 사용 됩니다.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 자세한 예제를 참조 하십시오. [수신 알림을 때는 시계의 상태가 변경](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md)합니다.  
  
## <a name="public-events"></a>Public 이벤트  
 <xref:System.Windows.Media.Animation.Timeline> 및 <xref:System.Windows.Media.Animation.Clock> 클래스는 모두&5; 개의 타이밍 이벤트를 제공 합니다. 다음 표에서 이러한 이벤트와 해당 트리거하는 조건을 나열 합니다.  
  
|이벤트|트리거 대화형 작업|다른 트리거|  
|-----------|--------------------------------------|--------------------|  
|**완료**|채우는 건너뛰기|클록을 완료합니다.|  
|**CurrentGlobalSpeedInvalidated**|일시 중지, 다시 시작, 검색, 속도 비율 설정, 건너뜁니다 채우기, 중지|시계를 반대로 바꿉니다, 그리고 가속화, 시작 하거나 중지 합니다.|  
|**CurrentStateInvalidated**|시작, 건너 뛰어 채우기, 중지|시작, 중지, 또는 채우기는 시계.|  
|**CurrentTimeInvalidated**|시작, 이동, 건너뜁니다 채우기, 중지|클록 진행 됩니다.|  
|**RemoveRequested**|제거||  
  
## <a name="ticking-and-event-consolidation"></a>틱 및 이벤트 통합  
 개체에 애니메이션 효과 주기 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], 애니메이션을 관리 하는 타이밍 엔진입니다. 타이밍 엔진은 시간의 진행을 추적 하 고 각 애니메이션의 상태를 계산 합니다. 이러한 많은 평가가 통과를 초당에서 있게 해줍니다. 이러한 평가 통과 "틱입니다." 라고 합니다.  
  
 틱이 자주 발생 하는 동안 많은 결과가 틱 간에 발생 하는 것이 같습니다. 예를 들어 타임 라인 수 중지, 시작, 하 고 다시 중지는 경우 현재 상태의 변경 되기&3; 번입니다. 이론적으로 이벤트에서에서 발생할 수 여러 번 단일 틱입니다. 그러나 타이밍 엔진은 틱 당 각 이벤트를 한 번만 발생 수 있도록 이벤트를 통합 합니다.  
  
## <a name="registering-for-events"></a>이벤트 등록  
 타이밍 이벤트에 등록 하는 방법은 두 가지가: 시간 표시 막대 또는 타임 라인에서 만든 시계를 등록할 수 있습니다. 코드에서 있어야만 완료할 수 있지만 시계와 직접 이벤트에 대 한 등록 하는 것은 매우 간단 합니다. 태그 또는 코드에서 일정을 사용 하 여 이벤트를 등록할 수 있습니다. 다음 섹션에는 일정으로 시계 이벤트에 등록 하는 방법을 설명 합니다.  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>시간 표시 막대를 사용 하 여 클록 이벤트 등록  
 하지만 timeline의 <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, 및 <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> 이벤트와 이벤트 처리기를 실제로 연결 하는 이러한 이벤트에 대해 등록 타임 라인와 연결 되도록 표시는 <xref:System.Windows.Media.Animation.Clock> 타임 라인에 대해 생성 합니다.  
  
 등록할 때는 <xref:System.Windows.Media.Animation.Timeline.Completed> 타임 라인에서 이벤트를 예를 들어 실제로 시키는 시스템에 등록 하는 <xref:System.Windows.Media.Animation.Clock.Completed> 각 클럭의 만들어지는 타임 라인에 대 한 이벤트입니다. 이 이벤트 전에 등록 해야 코드에서는 <xref:System.Windows.Media.Animation.Clock> 이 타임 라인;에 대해 만들어집니다 알림을 받을 수 없습니다, 그러지 않으면. 이 자동으로 발생 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; 파서는 이전 이벤트에 대 한 자동으로 등록 된 <xref:System.Windows.Media.Animation.Clock> 만들어집니다.  
  
## <a name="see-also"></a>참고 항목  
 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [타이밍 동작 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)