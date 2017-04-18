---
title: "속성 애니메이션 기술 개요 | Microsoft Docs"
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
  - "애니메이션, 속성, 메서드"
  - "속성, 애니메이션 적용을 위한 메서드"
ms.assetid: 74f61413-f8c0-4e75-bf04-951886426c8b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 속성 애니메이션 기술 개요
이 항목에서는 Storyboard, 로컬 애니메이션, Clock, 프레임당 애니메이션 등 속성에 애니메이션 효과를 주기 위한 다양한 방식을 설명합니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목의 내용을 이해하려면 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)에 설명되어 있는 기초적인 애니메이션 기능에 대해 잘 알고 있어야 합니다.  
  
<a name="summary"></a>   
## 애니메이션 효과를 주기 위한 여러 가지 방법  
 속성에 애니메이션 효과를 주기 위한 여러 가지 시나리오가 있기 때문에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 여러 가지 방식으로 속성에 애니메이션 효과를 줍니다.  
  
 각 방식에 대해 다음 표는 해당 방식을 스타일, 컨트롤 템플릿 또는 데이터 템플릿에서 인스턴스별로 사용할 수 있는지, 해당 방식을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 사용할 수 있는지, 해당 방식을 통해 애니메이션을 대화형으로 제어할 수 있는지를 나타냅니다.  "인스턴스별"은 애니메이션이나 Storyboard를 스타일, 컨트롤 템플릿 또는 데이터 템플릿에 적용하지 않고 개체의 인스턴스에 직접 적용하는 기술을 말합니다.  
  
|애니메이션 기술|시나리오|XAML 지원|대화형으로 제어 가능|  
|--------------|----------|-------------|-----------------|  
|Storyboard 애니메이션|인스턴스별, <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, <xref:System.Windows.DataTemplate>|예|예|  
|로컬 애니메이션|인스턴스별|아니요|아니요|  
|Clock 애니메이션|인스턴스별|아니요|예|  
|프레임별 애니메이션.|인스턴스별|아니요|N\/A|  
  
<a name="storyboard_animations"></a>   
## Storyboard 애니메이션  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 애니메이션을 정의하고 적용하거나 애니메이션을 시작한 후에 대화형으로 제어하거나 복잡한 애니메이션 트리를 만들거나 <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate> 또는 <xref:System.Windows.DataTemplate>에서 애니메이션 효과를 주려면 <xref:System.Windows.Media.Animation.Storyboard>를 사용하십시오.  개체가 <xref:System.Windows.Media.Animation.Storyboard>에 의해 애니메이션 효과를 얻으려면 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>이거나 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>를 설정하는 데 사용되어야 합니다.  자세한 내용은 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Media.Animation.Storyboard>는 포함하고 있는 애니메이션에 대한 대상 정보를 제공하는 컨테이너 <xref:System.Windows.Media.Animation.Timeline>의 특수 형식입니다.  <xref:System.Windows.Media.Animation.Storyboard>를 사용하여 애니메이션 효과를 주려면 다음의 세 단계를 수행하십시오.  
  
1.  <xref:System.Windows.Media.Animation.Storyboard> 및 하나 이상의 애니메이션을 선언합니다.  
  
2.  <xref:System.Windows.Media.Animation.Storyboard.TargetName%2A> 및 <xref:System.Windows.Media.Animation.Storyboard.TargetProperty%2A> [연결된 속성](GTMT)을 사용하여 각 애니메이션의 대상 개체 및 속성을 지정합니다.  
  
3.  \(코드 전용\) <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>에 대한 <xref:System.Windows.NameScope>를 정의합니다.  해당 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>로 애니메이션 효과를 줄 개체의 이름을 등록합니다.  
  
4.  <xref:System.Windows.Media.Animation.Storyboard>를 시작합니다.  
  
 <xref:System.Windows.Media.Animation.Storyboard>를 시작하면 애니메이션 효과를 주는 속성에 애니메이션이 적용되고 해당 속성이 시작됩니다.  두 가지 방법으로 <xref:System.Windows.Media.Animation.Storyboard>를 시작할 수 있습니다. <xref:System.Windows.Media.Animation.Storyboard> 클래스에서 제공하는 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 사용하거나 <xref:System.Windows.Media.Animation.BeginStoryboard> 작업을 사용할 수 있습니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 애니메이션 효과를 주는 유일한 방법은 <xref:System.Windows.Media.Animation.BeginStoryboard> 작업을 사용하는 것입니다. <xref:System.Windows.Media.Animation.BeginStoryboard> 작업은 <xref:System.Windows.EventTrigger>, 속성 <xref:System.Windows.Trigger> 또는 <xref:System.Windows.DataTrigger>에서 사용할 수 있습니다.  
  
 다음 표에서는 각 <xref:System.Windows.Media.Animation.Storyboard> 시작 기술이 지원되는 다양한 위치\(인스턴스별, 스타일, 컨트롤 템플릿 및 데이터 템플릿\)를 보여 줍니다.  
  
|다음을 사용하여 Storyboard 시작|인스턴스별|스타일|컨트롤 템플릿|데이터 템플릿|예제|  
|----------------------------|-----------|---------|-------------|-------------|--------|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 및 <xref:System.Windows.EventTrigger>|예|예|예|예|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 및 속성 <xref:System.Windows.Trigger>|아니요|예|예|예|[속성 값이 변경될 때 애니메이션 트리거](../../../../docs/framework/wpf/graphics-multimedia/how-to-trigger-an-animation-when-a-property-value-changes.md)|  
|<xref:System.Windows.Media.Animation.BeginStoryboard> 및 <xref:System.Windows.DataTrigger>|아니요|예|예|예|[How to: Trigger an Animation When Data Changes](http://msdn.microsoft.com/ko-kr/a736bb3a-2ae5-479a-a33a-75a27055d863)|  
|<xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드|예|아니요|아니요|아니요|[Storyboard를 사용하여 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)|  
  
 <xref:System.Windows.Media.Animation.Storyboard> 개체에 대한 자세한 내용은 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하십시오.  
  
## 로컬 애니메이션  
 로컬 애니메이션은 <xref:System.Windows.Media.Animation.Animatable> 개체의 [종속성 속성](GTMT)에 애니메이션 효과를 줄 수 있는 편리한 방법입니다.  속성에 단일 애니메이션을 적용하기를 원하며 애니메이션이 시작된 후에 애니메이션을 대화형으로 제어할 필요가 없을 때 로컬 애니메이션을 사용하십시오.  <xref:System.Windows.Media.Animation.Storyboard> 애니메이션과 달리 로컬 애니메이션은 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement>와 연관되지 않은 개체에 애니메이션 효과를 줄 수 있습니다.  이 형식의 애니메이션에 대해서는 <xref:System.Windows.NameScope>를 정의할 필요도 없습니다.  
  
 로컬 애니메이션은 코드에서만 사용될 수 있고 스타일, 컨트롤 템플릿 또는 데이터 템플릿에서 정의될 수 없습니다.  로컬 애니메이션은 시작된 이후에 대화형으로 제어할 수 없습니다.  
  
 로컬 애니메이션을 사용하여 애니메이션 효과를 주려면 다음 단계를 수행하십시오.  
  
1.  <xref:System.Windows.Media.Animation.AnimationTimeline> 개체를 만듭니다.  
  
2.  애니메이션 효과를 줄 개체의 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하여 지정한 속성에 <xref:System.Windows.Media.Animation.AnimationTimeline>을 적용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button>의 너비와 배경색에 애니메이션 효과를 주는 방법을 보여 줍니다.  
  
 [!code-cpp[animateproperty#11](../../../../samples/snippets/cpp/VS_Snippets_Wpf/animateproperty/CPP/LocalAnimationExample.cpp#11)]
 [!code-csharp[animateproperty#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animateproperty/CSharp/LocalAnimationExample.cs#11)]
 [!code-vb[animateproperty#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animateproperty/VisualBasic/LocalAnimationExample.vb#11)]  
  
## Clock 애니메이션  
 <xref:System.Windows.Media.Animation.Storyboard>를 사용하지 않고 애니메이션 효과를 주기를 원하고 복잡한 타이밍 트리를 만들거나 애니메이션이 시작된 후에 애니메이션을 대화형으로 제어하려면 <xref:System.Windows.Media.MediaPlayer.Clock%2A> 개체를 사용하십시오.  Clock 개체를 사용하여 <xref:System.Windows.Media.Animation.Animatable> 개체의 [종속성 속성](GTMT)에 애니메이션 효과를 줄 수 있습니다.  
  
 <xref:System.Windows.Media.Animation.Clock> 개체를 직접적으로 사용하여 스타일, 컨트롤 템플릿 또는 데이터 템플릿에서 애니메이션 효과를 줄 수는 없습니다.  애니메이션 및 타이밍 시스템은 실제로 <xref:System.Windows.Media.Animation.Clock> 개체를 사용하여 스타일, 컨트롤 템플릿 및 데이터 템플릿에서 애니메이션 효과를 주지만 해당 <xref:System.Windows.Media.Animation.Clock> 개체를 <xref:System.Windows.Media.Animation.Storyboard>에서 만들어야 합니다.  <xref:System.Windows.Media.Animation.Storyboard> 개체와 <xref:System.Windows.Media.Animation.Clock> 개체 간의 관계에 대한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)를 참조하십시오.  
  
 속성에 단일 <xref:System.Windows.Media.Animation.Clock>을 적용하려면 다음 단계를 수행하십시오.  
  
1.  <xref:System.Windows.Media.Animation.AnimationTimeline> 개체를 만듭니다.  
  
2.  <xref:System.Windows.Media.Animation.AnimationTimeline>의 <xref:System.Windows.Media.Animation.AnimationTimeline.CreateClock%2A> 메서드를 사용하여 <xref:System.Windows.Media.Animation.AnimationClock>을 만듭니다.  
  
3.  애니메이션 효과를 줄 개체의 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> 메서드를 사용하여 지정한 속성에 <xref:System.Windows.Media.Animation.AnimationClock>을 적용합니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.AnimationClock>을 만들어서 두 개의 비슷한 속성에 적용하는 방법을 보여 줍니다.  
  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/AnimationClockExample.cs#graphicsmmcreateanimationclockwholeclass)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMCreateAnimationClockWholeClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/animationclockexample.vb#graphicsmmcreateanimationclockwholeclass)]  
  
 타이밍 트리를 만들어서 속성에 애니메이션 효과를 주는 데 사용하려면 다음 단계를 수행하십시오.  
  
1.  <xref:System.Windows.Media.Animation.ParallelTimeline> 및 <xref:System.Windows.Media.Animation.AnimationTimeline> 개체를 사용하여 타이밍 트리를 만듭니다.  
  
2.  루트 <xref:System.Windows.Media.Animation.ParallelTimeline>의 <xref:System.Windows.Media.Animation.TimelineGroup.CreateClock%2A>을 사용하여 <xref:System.Windows.Media.Animation.ClockGroup>을 만듭니다.  
  
3.  <xref:System.Windows.Media.Animation.ClockGroup>의 <xref:System.Windows.Media.Animation.ClockGroup.Children%2A>을 반복하고 해당 자식 <xref:System.Windows.Media.Animation.Clock> 개체를 적용합니다.  각 <xref:System.Windows.Media.Animation.AnimationClock> 자식 항목에 대해 애니메이션 효과를 줄 개체의 <xref:System.Windows.Media.Animation.Animatable.ApplyAnimationClock%2A> 메서드를 사용하여 지정한 속성에 <xref:System.Windows.Media.Animation.AnimationClock>을 적용합니다.  
  
 Clock 개체에 대한 자세한 내용은 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)를 참조하십시오.  
  
## 프레임별 애니메이션: 애니메이션 및 타이밍 시스템 건너뛰기  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 시스템을 완전히 건너뛰어야 할 때 이 방식을 사용하십시오.  이 방식의 한 가지 시나리오는 물리학 애니메이션입니다. 이 애니메이션에서는 각 단계마다 마지막 개체 상호 작용 집합에 따라 개체를 다시 계산해야 합니다.  
  
 프레임별 애니메이션은 스타일, 컨트롤 템플릿 또는 데이터 템플릿 내에서 정의될 수 없습니다.  
  
 프레임별로 애니메이션 효과를 주려면 애니메이션 효과를 줄 개체가 들어 있는 개체의 <xref:System.Windows.Media.CompositionTarget.Rendering> 이벤트를 등록하십시오.  이 이벤트 처리기 메서드는 프레임당 한 번씩 호출됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 [시각적 트리](GTMT)에 있는 일관된 렌더링 데이터를 컴포지션 트리를 통해 마샬링하는 경우 이벤트 처리기 메서드가 호출됩니다.  
  
 이벤트 처리기에서 애니메이션 효과에 필요한 모든 계산을 수행하고 애니메이션 효과를 줄 개체의 속성을 해당 값으로 설정하십시오.  
  
 현재 프레임의 표시 시간을 얻기 위해 이 이벤트와 연결된 <xref:System.EventArgs>가 <xref:System.Windows.Media.RenderingEventArgs>로 캐스팅되어 현재 프레임의 렌더링 시간을 얻는 데 사용할 수 있는 <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> 속성을 제공합니다.  
  
 자세한 내용은 <xref:System.Windows.Media.CompositionTarget.Rendering> 페이지를 참조하십시오.  
  
## 참고 항목  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [종속성 속성 개요](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)