---
title: "사용자 지정 애니메이션 개요 | Microsoft Docs"
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
  - "애니메이션, 사용자 지정 클래스"
  - "사용자 지정 애니메이션 클래스"
  - "사용자 지정 클래스, 애니메이션"
  - "사용자 지정 키 프레임"
  - "키 프레임, 사용자 지정"
ms.assetid: 9be69d50-3384-4938-886f-08ce00e4a7a6
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 사용자 지정 애니메이션 개요
이 항목에서는 사용자 지정 키 프레임, 애니메이션 클래스를 만들거나 이를 건너뛰기 위한 프레임당 콜백을 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 시스템을 확장하는 방법과 시점에 대해 설명합니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 항목을 이해하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 제공하는 다른 애니메이션 형식에 익숙해야 합니다.  자세한 내용은 [From\/To\/By 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md), [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) 및 [경로 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)를 참조하십시오.  
  
 애니메이션 클래스는 <xref:System.Windows.Freezable> 클래스에서 상속하기 때문에 <xref:System.Windows.Freezable> 개체와 <xref:System.Windows.Freezable>에서 상속하는 방법에 익숙해야 합니다.  자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)을 참조하십시오.  
  
<a name="extendingtheanimationsystem"></a>   
## 애니메이션 시스템 확장  
 사용할 기본 제공 기능의 수준에 따라 여러 가지 방법으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 시스템을 확장할 수 있습니다.  다음은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 엔진에서의 세 가지 기본 확장성 지점입니다.  
  
-   <xref:System.Windows.Media.Animation.DoubleKeyFrame>과 같은 *\<Type\>*KeyFrame 클래스 중 하나에서 상속하여 사용자 지정 키 프레임 개체를 만듭니다.  이 방법은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 엔진의 기본 제공 기능을 대부분 사용합니다.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline>에서 상속하거나 *\<Type\>*AnimationBase 클래스 중 하나에서 상속하여 자체적인 애니메이션 클래스를 만듭니다.  
  
-   프레임당 콜백을 사용하여 프레임당 기준으로 애니메이션을 생성합니다.  이 방법은 애니메이션 및 타이밍 시스템을 완전히 건너뜁니다.  
  
 다음 표에서는 애니메이션 시스템을 확장하기 위한 몇 가지 시나리오를 설명합니다.  
  
|원하는 작업|사용할 방법|  
|------------|------------|  
|해당하는 *\<Type\>*AnimationUsingKeyFrames가 있는 형식 값 사이의 보간 사용자 지정|사용자 지정 키 프레임을 만듭니다.  자세한 내용은 [사용자 지정 키 프레임 만들기](#createacustomkeyframe) 단원을 참조하십시오.|  
|해당하는 *\<Type\>*Animation이 있는 형식 값 사이의 보간 외에 다른 항목 사용자 지정|애니메이션 효과를 지정할 형식에 해당하는 *\<Type\>*AnimationBase 클래스에서 상속하는 사용자 지정 애니메이션 클래스를 만듭니다.  자세한 내용은 [사용자 지정 애니메이션 클래스 만들기](#createcustomanimationtype) 단원을 참조하십시오.|  
|해당하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션이 없는 형식에 애니메이션 효과 지정|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>를 사용하거나 <xref:System.Windows.Media.Animation.AnimationTimeline>에서 상속하는 클래스를 만듭니다.  자세한 내용은 [사용자 지정 애니메이션 클래스 만들기](#createcustomanimationtype) 단원을 참조하십시오.|  
|값이 각 프레임에서 계산되며 마지막 개체 상호 작용 집합을 기준으로 하는 다수 개체에 애니메이션 효과 지정|프레임당 콜백을 사용합니다.  자세한 내용은 [프레임당 콜백 사용 만들기](#useperframecallback) 단원을 참조하십시오.|  
  
<a name="createacustomkeyframe"></a>   
## 사용자 지정 키 프레임 만들기  
 사용자 지정 키 프레임 클래스를 만드는 것이 애니메이션 시스템을 확장하는 가장 간단한 방법입니다.  키 프레임 애니메이션에 서로 다른 보간 방법을 사용하려고 할 때 이 방법을 사용하십시오.  [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)에 설명된 대로 키 프레임 애니메이션은 키 프레임 개체를 사용하여 해당 출력 값을 생성합니다.  각 키 프레임 개체는 세 가지 기능을 수행합니다.  
  
-   해당 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 속성을 사용하여 대상 값을 지정합니다.  
  
-   해당 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 속성을 사용하여 값에 도달해야 하는 시간을 지정합니다.  
  
-   InterpolateValueCore 메서드를 구현하여 이전 키 프레임의 값과 자체 값 사이를 보간합니다.  
  
 **구현 지침**  
  
 *\<Type\>*KeyFrame 추상 클래스에서 파생시키고 InterpolateValueCore 메서드를 구현합니다.  InterpolateValueCore 메서드는 키 프레임의 현재 값을 반환합니다.  이전 키 프레임의 값과 0에서 1 사이의 진행률 값에 해당하는 두 개의 매개 변수가 사용됩니다.  진행률 값 0은 키 프레임이 방금 시작했음을 나타내고, 값 1은 키 프레임이 방금 완료되었으며 해당 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 속성에 의해 지정된 값을 반환해야 함을 나타냅니다.  
  
 *\<Type\>*KeyFrame 클래스는 <xref:System.Windows.Freezable> 클래스에서 상속하므로 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 코어를 재정의하여 클래스의 새 인스턴스를 반환해야 합니다.  클래스에서 데이터를 저장하기 위해 [종속성 속성](GTMT)을 사용하지 않거나 생성 후 추가로 초기화 작업을 수행해야 하는 경우 추가 메서드를 재정의해야 할 수도 있습니다. 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
 사용자 지정 *\<Type\>*KeyFrame 애니메이션을 만든 후에는 해당 유형에 대한 *\<Type\>*AnimationUsingKeyFrames와 함께 사용할 수 있습니다.  
  
<a name="createacustomanimationtype"></a>   
## 사용자 지정 애니메이션 클래스 만들기  
 자체적인 애니메이션 형식을 만들면 개체에 애니메이션 효과를 주는 방법을 보다 세부적으로 제어할 수 있습니다.  자체 애니메이션 형식을 만들기 위한 두 가지 권장 방법이 있습니다. 하나는 <xref:System.Windows.Media.Animation.AnimationTimeline> 클래스에서 파생시키는 방법이며, 다른 하나는 *\<Type\>*AnimationBase 클래스에서 파생시키는 방법입니다.  *\<Type\>*Animation 또는 *\<Type\>*AnimationUsingKeyFrames 클래스에서 파생시키는 방법은 사용하지 않는 것이 좋습니다.  
  
### \<Type\>AnimationBase에서 파생  
 *\<Type\>*AnimationBase 클래스에서 파생시키는 것이 새 애니메이션 형식을 만드는 가장 간단한 방법입니다.  해당하는 *\<Type\>*AnimationBase 클래스가 이미 있는 형식에 대해 새 애니메이션을 만들 때 이 방법을 사용하십시오.  
  
 **구현 지침**  
  
 *\<Type\>*Animation 클래스에서 파생시키고 GetCurrentValueCore 메서드를 구현합니다.  GetCurrentValueCore 메서드는 애니메이션의 현재 값을 반환합니다.  세 가지 매개 변수인 제안된 시작 값, 제안된 끝 값, <xref:System.Windows.Media.Animation.AnimationClock>\(애니메이션 진행률을 확인하는 데 사용\)이 사용됩니다.  
  
 *\<Type\>*AnimationBase 클래스는 <xref:System.Windows.Freezable> 클래스에서 상속하므로 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 코어를 재정의하여 클래스의 새 인스턴스를 반환해야 합니다.  클래스에서 데이터를 저장하기 위해 [종속성 속성](GTMT)을 사용하지 않거나 생성 후 추가로 초기화 작업을 수행해야 하는 경우 추가 메서드를 재정의해야 할 수도 있습니다. 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
 자세한 내용은 애니메이션 효과를 지정할 형식의 *\<Type\>*AnimationBase 클래스에 대한 GetCurrentValueCore 메서드 설명서를 참조하십시오.  예제를 보려면 [Custom Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=159981)을 참조하십시오.  
  
 **다른 방법**  
  
 애니메이션 값이 보간되는 방법만 변경하려면 *\<Type\>*KeyFrame 클래스 중 하나에서 파생시키는 방법을 고려해 보십시오.  직접 만든 키 프레임을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 제공하는 해당 *\<Type\>*AnimationUsingKeyFrames와 함께 사용할 수 있습니다.  
  
### AnimationTimeline에서 파생  
 일치하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션이 아직 없는 형식에 대한 애니메이션을 만들거나 강력한 형식이 아닌 애니메이션을 만들 때는 <xref:System.Windows.Media.Animation.AnimationTimeline> 클래스에서 파생시키십시오.  
  
 **구현 지침**  
  
 <xref:System.Windows.Media.Animation.AnimationTimeline> 클래스에서 파생시키고 다음 멤버를 재정의합니다.  
  
-   <xref:System.Windows.Freezable.CreateInstanceCore%2A> – 새 클래스가 구체적 클래스인 경우 <xref:System.Windows.Freezable.CreateInstanceCore%2A>를 재정의하여 클래스의 새 인스턴스를 반환해야 합니다.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> – 이 메서드를 재정의하여 애니메이션의 현재 값을 반환합니다.  이 메서드는 세 개의 매개 변수, 즉 기본 원점 값, 기본 대상 값 및 <xref:System.Windows.Media.Animation.AnimationClock>을 사용합니다.  애니메이션의 현재 시간 또는 진행률을 가져오려면 <xref:System.Windows.Media.Animation.AnimationClock>을 사용합니다.  기본 원점 값과 기본 대상 값은 사용 여부를 선택할 수 있습니다.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> – 이 속성을 재정의하여 애니메이션에서 <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> 메서드로 지정되는 기본 대상 값을 사용할지 여부를 나타냅니다.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> – 이 속성을 정의하여 애니메이션에서 생성하는 출력의 <xref:System.Type>을 나타냅니다.  
  
 클래스에서 데이터를 저장하기 위해 [종속성 속성](GTMT)을 사용하지 않거나 생성 후 추가로 초기화 작업을 수행해야 하는 경우 추가 메서드를 재정의해야 할 수도 있습니다. 자세한 내용은 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)를 참조하십시오.  
  
 권장되는 패러다임\([!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션에서 사용\)은 두 상속 수준을 사용하는 것입니다.  
  
1.  <xref:System.Windows.Media.Animation.AnimationTimeline>에서 파생되는 추상 *\<Type\>*AnimationBase 클래스를 만듭니다.  이 클래스는 <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> 메서드를 재정의해야 합니다.  또한 새 추상 메서드 GetCurrentValueCore를 도입하고 <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>를 재정의하여 기본 원점 값 및 기본 대상 값 매개 변수 형식의 유효성을 검사한 다음 GetCurrentValueCore를 호출하도록 합니다.  
  
2.  새 *\<Type\>*AnimationBase 클래스에서 상속하는 또 다른 클래스를 만들고 <xref:System.Windows.Freezable.CreateInstanceCore%2A> 메서드, 도입한 GetCurrentValueCore 메서드 및 <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> 속성을 재정의합니다.  
  
 **다른 방법**  
  
 해당하는 From\/To\/By 애니메이션 또는 키 프레임 애니메이션이 없는 형식에 애니메이션 효과를 지정하려면 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>를 사용하는 것을 고려해 보십시오.  약한 형식이기 때문에 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>가 모든 값 형식에 애니메이션 효과를 지정할 수 있습니다.  이 방법의 단점은 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>가 [불연속 보간](GTMT)만 지원한다는 것입니다.  
  
<a name="useperframecallback"></a>   
## 프레임당 콜백 사용  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 시스템을 완전히 건너뛰어야 할 때 이 방법을 사용하십시오.  이 방법의 한 가지 시나리오는 물리학 애니메이션입니다. 여기에서는 각 애니메이션 단계에 있는 애니메이션 효과가 지정된 개체의 새 방향 또는 위치를 마지막 개체 상호 작용 집합을 기준으로 다시 계산해야 합니다.  
  
 **구현 지침**  
  
 이 개요에 설명된 다른 방법과 달리 프레임당 콜백을 사용하기 위해서는 사용자 지정 애니메이션이나 키 프레임 클래스를 만들 필요가 없습니다.  
  
 대신 애니메이션 효과를 지정할 개체가 들어 있는 개체의 <xref:System.Windows.Media.CompositionTarget.Rendering> 이벤트를 등록하십시오.  이 이벤트 처리기 메서드는 프레임당 한 번씩 호출됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]가 [시각적 트리](GTMT)에 있는 일관된 렌더링 데이터를 컴포지션 트리를 통해 마샬링하는 경우 이벤트 처리기 메서드가 호출됩니다.  
  
 이벤트 처리기에서 애니메이션 효과에 필요한 모든 계산을 수행하고 애니메이션 효과를 지정할 개체의 속성을 해당 값으로 설정하십시오.  
  
 현재 프레임의 표시 시간을 얻기 위해 이 이벤트와 연결된 <xref:System.EventArgs>가 <xref:System.Windows.Media.RenderingEventArgs>로 캐스팅되어 현재 프레임의 렌더링 시간을 얻는 데 사용할 수 있는 <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> 속성을 제공합니다.  
  
 자세한 내용은 <xref:System.Windows.Media.CompositionTarget.Rendering> 페이지를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.AnimationTimeline>   
 <xref:System.Windows.Media.Animation.IKeyFrame>   
 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Freezable 개체 개요](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [From\/To\/By 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md)   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [경로 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [애니메이션 및 타이밍 시스템 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Custom Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=159981)