---
title: "From/To/By 애니메이션 개요 | Microsoft Docs"
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
  - "애니메이션, From/To/By"
  - "From/To/By 애니메이션"
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# From/To/By 애니메이션 개요
이 항목에서는 From\/To\/By 애니메이션을 사용하여 [종속성 속성](GTMT)에 애니메이션 효과를 주는 방법을 보여 줍니다.  From\/To\/By 애니메이션은 두 값 간에 전환을 생성합니다.  
  
 이 항목에는 다음 단원이 포함되어 있습니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prereq"></a>   
## 사전 요구 사항  
 이 항목의 내용을 이해하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 애니메이션 기능에 대해 잘 알고 있어야 합니다.  애니메이션 기능에 대한 소개는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오.  
  
<a name="whatisanimation"></a>   
## From\/To\/By 애니메이션 정의  
 From\/To\/By 애니메이션은 시작 값과 끝 값 간에 전환을 생성하는 일종의 <xref:System.Windows.Media.Animation.AnimationTimeline>입니다.  전환이 완료되는 데 필요한 시간은 애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>에 따라 결정됩니다.  
  
 태그와 코드에 <xref:System.Windows.Media.Animation.Storyboard>를 사용하거나 코드에 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하여 속성에 From\/To\/By 애니메이션을 적용할 수 있습니다.  <xref:System.Windows.Media.Animation.AnimationClock>을 만들어 하나 이상의 속성에 적용하려는 경우에도 From\/To\/By 애니메이션을 사용할 수 있습니다.  애니메이션을 적용하는 다양한 방법에 대한 자세한 내용은 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)를 참조하십시오.  
  
 From\/To\/By 애니메이션에는 대상 값을 두 개까지만 지정할 수 있습니다.  애니메이션에 대상 값을 세 개 이상 지정해야 하는 경우에는 키 프레임 애니메이션을 사용하십시오.  키 프레임 애니메이션에 대한 설명은 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)를 참조하십시오.  
  
<a name="animation_types"></a>   
## From\/To\/By 애니메이션의 형식  
 애니메이션은 속성 값을 생성하므로 속성 형식에 따라 애니메이션의 형식도 달라집니다.  요소의 <xref:System.Windows.FrameworkElement.Width%2A> 속성과 같이 <xref:System.Double>을 사용하는 속성에 애니메이션 효과를 적용하려면 <xref:System.Double> 값을 생성하는 애니메이션을 사용합니다.  <xref:System.Windows.Point>를 사용하는 속성에 애니메이션 효과를 적용하려면 <xref:System.Windows.Point> 값 등을 생성하는 애니메이션을 사용합니다.  
  
 From\/To\/By 애니메이션 클래스는 <xref:System.Windows.Media.Animation> 네임스페이스에 속하며 다음 명명 규칙을 사용합니다.  
  
 *\<Type\>* `Animation`  
  
 여기서 *\<Type\>*은 클래스가 애니메이션 효과를 주는 값의 형식입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 다음 From\/To\/By 애니메이션 클래스를 제공합니다.  
  
|속성 형식|해당 From\/To\/By 애니메이션 클래스|  
|-----------|-------------------------------|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimation>|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimation>|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16Animation>|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32Animation>|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64Animation>|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimation>|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimation>|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimation>|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimation>|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimation>|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimation>|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimation>|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimation>|  
  
<a name="anim_values"></a>   
## 대상 값  
 From\/To\/By 애니메이션은 두 대상 값 간에 전환을 생성합니다.  일반적으로 시작 값\(<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 사용하여 설정\)과 끝 값\(<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 사용하여 설정\)을 지정합니다.  하지만 시작 값, 대상 값 또는 오프셋 값 중 하나만 지정할 수도 있습니다.  이 경우 애니메이션은 없는 대상 값을 애니메이션 효과가 적용되는 속성에서 가져옵니다.  아래에서는 애니메이션의 대상 값을 지정하는 여러 방법을 보여 줍니다.  
  
-   **시작 값**  
  
     애니메이션의 시작 값을 명시적으로 지정하려면 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 사용합니다.  <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 단독으로 사용하거나 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 또는 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성과 함께 사용할 수 있습니다.  <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성만 지정하는 경우 해당 값에서 애니메이션 효과가 적용되는 속성의 기준 값으로 애니메이션이 전환됩니다.  
  
-   **끝 값**  
  
     애니메이션의 끝 값을 지정하려면 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 사용합니다.  <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 단독으로 사용하는 경우 애니메이션은 애니메이션 효과가 적용되는 속성이나 동일한 속성에 적용된 다른 애니메이션의 출력에서 시작 값을 가져옵니다.  <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성과 함께 사용하여 애니메이션의 시작 값과 끝 값을 명시적으로 지정할 수 있습니다.  
  
-   **오프셋 값**  
  
     <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 사용하면 애니메이션의 명시적 시작 값 또는 끝 값 대신 오프셋을 지정할 수 있습니다.  애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성은 애니메이션 실행 기간 동안 애니메이션이 어느 정도까지 값을 변경해야 하는지를 지정합니다.  <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 단독으로 사용하거나 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성과 함께 사용할 수 있습니다.  <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성만 지정하는 경우 애니메이션이 속성의 기준 값 또는 다른 애니메이션의 출력에 해당 오프셋 값을 추가합니다.  
  
<a name="examples"></a>   
## From\/To\/By 값 사용  
 다음 단원에서는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 함께 또는 개별적으로 사용하는 방법을 설명합니다.  
  
 이 단원의 각 예제에서는 From\/To\/By 애니메이션 형식인 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하여 세로가 10 [장치 독립적 픽셀](GTMT)이고 가로가 100 [장치 독립적 픽셀](GTMT)인 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A> 속성에 애니메이션 효과를 줍니다.  
  
 예제마다 <xref:System.Windows.Media.Animation.DoubleAnimation>을 사용하고 있지만 모든 From\/To\/By 애니메이션의 From, To 및 By 속성은 동일하게 작동합니다.  각 예제에서는 <xref:System.Windows.Media.Animation.Storyboard>를 사용하지만 From\/To\/By 애니메이션을 다른 방법으로 사용할 수도 있습니다.  자세한 내용은 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)를 참조하십시오.  
  
### From\/To  
 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 값과 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 값을 함께 설정하면 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 지정된 값에서 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성에 지정된 값으로 애니메이션이 진행됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 50으로 설정하고 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 300으로 설정합니다.  그 결과 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>에 50에서 300까지 애니메이션 효과가 적용됩니다.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### To  
 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성만 설정하는 경우 애니메이션 효과가 적용되는 속성의 기준 값 또는 이전에 동일한 속성에 적용된 구성 애니메이션\(Composing Animatioin\)의 출력에서 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성에 지정된 값까지 애니메이션이 진행됩니다.  
  
 "구성 애니메이션"은 현재 애니메이션을 적용할 당시 지금까지 효과가 있는 동일한 속성에 <xref:System.Windows.Media.Animation.HandoffBehavior> 전달 동작을 사용하여 이전에 적용된 <xref:System.Windows.Media.Animation.ClockState> 또는 <xref:System.Windows.Media.Animation.ClockState> 애니메이션을 나타냅니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성만 300으로 설정합니다.  시작 값이 지정되지 않았으므로 <xref:System.Windows.Media.Animation.DoubleAnimation>은 <xref:System.Windows.FrameworkElement.Width%2A> 속성의 기준 값\(100\)을 시작 값으로 사용합니다.  <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>에는 100에서 애니메이션 대상 값인 300까지 애니메이션 효과가 적용됩니다.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### By  
 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성만 설정하는 경우 애니메이션 효과를 적용 중인 속성의 기준 값 또는 구성 애니메이션의 출력에서 이 두 값 중 하나와 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성에 지정된 값을 더한 값까지 애니메이션이 진행됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성만 300으로 설정합니다.  이 예제에서는 시작 값을 지정하지 않았으므로 <xref:System.Windows.Media.Animation.DoubleAnimation>은 <xref:System.Windows.FrameworkElement.Width%2A> 속성의 기준 값\(100\)을 시작 값으로 사용합니다.  끝 값은 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 값인 300에 시작 값인 100을 더한 400으로 결정됩니다.  그 결과 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>에 100에서 400까지 애니메이션 효과가 적용됩니다.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### From\/By  
 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 설정하는 경우 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 지정된 값에서 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성에 지정된 값을 더한 값까지 애니메이션이 진행됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 50으로 설정하고 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 300으로 설정합니다.  끝 값은 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 값인 300에 시작 값인 50을 더한 350으로 결정됩니다.  그 결과 <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>에 50에서 350까지 애니메이션 효과가 적용됩니다.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### From  
 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 값만 설정하는 경우 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 지정된 값에서 애니메이션 효과를 적용 중인 속성의 기준 값 또는 구성 애니메이션의 출력까지 애니메이션이 진행됩니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation>의 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성만 50으로 설정합니다.  끝 값이 지정되지 않았으므로 <xref:System.Windows.Media.Animation.DoubleAnimation>은 <xref:System.Windows.FrameworkElement.Width%2A> 속성의 기준 값\(100\)을 끝 값으로 사용합니다.  <xref:System.Windows.Shapes.Rectangle>의 <xref:System.Windows.FrameworkElement.Width%2A>에는 50에서 <xref:System.Windows.FrameworkElement.Width%2A> 속성의 기준 값인 100까지 애니메이션 효과가 적용됩니다.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### To\/By  
 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성과 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 모두 설정하면 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성이 무시됩니다.  
  
<a name="otheranimationtypes"></a>   
## 다른 애니메이션 형식  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 From\/To\/By 애니메이션 외에도 키 프레임 애니메이션과 경로 애니메이션이라는 다른 형식의 애니메이션도 제공합니다.  
  
-   키 프레임 애니메이션은 키 프레임을 사용하여 정의된 일련의 대상 값을 따라 애니메이션 효과를 적용합니다.  자세한 내용은 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)을 참조하십시오.  
  
-   경로 애니메이션은 <xref:System.Windows.Media.PathGeometry>에서 출력 값을 생성합니다.  자세한 내용은 [경로 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)을 참조하십시오.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용하면 고유한 형식의 사용자 지정 애니메이션도 만들 수 있습니다.  자세한 내용은 [사용자 지정 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.Timeline>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [경로 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)   
 [사용자 지정 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)   
 [From, To, and By Animation Target Values 샘플](http://go.microsoft.com/fwlink/?LinkID=159988)