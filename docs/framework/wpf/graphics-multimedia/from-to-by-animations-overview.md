---
title: "-에-By 애니메이션 개요"
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
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f5eba773a290f1100fcea411919c5c16558e01ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="fromtoby-animations-overview"></a>From/To/By 애니메이션 개요
이 항목에서는 From/To/By 애니메이션을 사용하여 종속성 속성에 애니메이션 효과를 적용하는 방법을 설명합니다. From/To/By 애니메이션은 두 값 간에 변환을 생성합니다.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목을 이해 하려면에 대해 잘 알고 있어야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애니메이션 기능입니다. 애니메이션 기능에 대 한 소개를 참조 하십시오.는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>From/To/By 애니메이션이란?  
 From/하/By 애니메이션의 형식인 <xref:System.Windows.Media.Animation.AnimationTimeline> 하는 시작 값과 끝 값 사이 전환을 만듭니다. 전환을 완료 하는 데 걸리는 시간을의 크기에 따라 결정 되는 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 애니메이션의 합니다.  
  
 From/하/여 적용할 수 있습니다를 사용 하 여 속성에 애니메이션을 <xref:System.Windows.Media.Animation.Storyboard> 태그와 코드를 또는 사용 하 여는 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 코드에서 메서드. 만들려는 From/To/By 애니메이션을 사용할 수도 있습니다는 <xref:System.Windows.Media.Animation.AnimationClock> 하나 이상의 속성에 적용 합니다. 애니메이션 효과를 주기 위한 여러 다양한 방법에 대한 자세한 내용은 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)를 참조하세요.  
  
 From/To/By 애니메이션은 2개 이하의 대상 값을 가질 수 있습니다. 2개를 초과하는 대상 값을 갖는 애니메이션이 필요한 경우 키 프레임 애니메이션을 사용합니다. 키 프레임 애니메이션에 설명 되어 있음는 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>From/To/By 애니메이션 형식  
 애니메이션은 속성 값을 생성하므로 속성 형식이 다르면 애니메이션 형식도 다릅니다. 사용 하는 속성에 애니메이션 효과를 주는 <xref:System.Double>와 같은 <xref:System.Windows.FrameworkElement.Width%2A> 는 요소의 속성을 사용 하 여 생성 하는 애니메이션 <xref:System.Double> 값입니다. 사용 하는 속성에 애니메이션 효과를 주는 <xref:System.Windows.Point>를 생성 하는 애니메이션을 사용 하 여 <xref:System.Windows.Point> 값, 및 기타 등등.  
  
 From/하/By 애니메이션 클래스에 속하는 <xref:System.Windows.Media.Animation> 네임 스페이스는 다음 명명 규칙을 사용 하 여:  
  
 *\<Type>* `Animation`  
  
 여기서 *\<Type>*은 클래스가 애니메이션을 적용하는 값의 형식입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 다음 From/To/By 애니메이션 클래스를 제공합니다.  
  
|속성 형식|해당 From/To/By 애니메이션 클래스|  
|-------------------|------------------------------------------------|  
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
## <a name="target-values"></a>대상 값  
 From/To/By 애니메이션은 두 대상 값 간에 변환을 생성합니다. 시작 값을 지정 하는 것 (사용 하 여 설정는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성)과 끝 값 (사용 하 여 설정 된 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성). 그러나 시작 값, 대상 값 또는 오프셋 값만 지정할 수도 있습니다. 이러한 경우 애니메이션은 애니메이션 효과를 적용할 속성에서 누락된 대상 값을 가져옵니다. 다음 목록에서는 애니메이션의 대상 값을 지정하는 여러 가지 방법을 설명합니다.  
  
-   **시작 값**  
  
     사용 하 여는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션의 시작 값을 명시적으로 지정 하려는 경우이 속성입니다. 사용할 수는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 단독으로 또는 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 또는 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다. 지정 하는 경우는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성, 속성의 기본 값에 해당 값에서는 애니메이션 전환 합니다.  
  
-   **끝 값**  
  
     애니메이션의 끝 값을 지정 하려면 사용 하 여 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다. 사용 하는 경우는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 단독으로 애니메이션 가져옵니다 시작 값에 애니메이션을 적용 하는 속성 또는 동일한 속성에 적용 되는 다른 애니메이션의 출력에서 합니다. 사용할 수는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성과 함께 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 명시적으로 시작 및 끝 애니메이션에 대 한 값을 지정 합니다.  
  
-   **오프셋 값**  
  
     <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성 대신 명시적 시작 또는 끝 값 애니메이션에 대 한 오프셋을 지정할 수 있습니다. <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 애니메이션의 속성 지정 얼마나 애니메이션에 따라 기간 동안 값을 변경 합니다. 사용할 수는 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 단독으로 또는 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성입니다. 지정 하는 경우는 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성에 애니메이션 속성의 기준 값 또는 다른 애니메이션의 출력으로 오프셋된 값을 추가 합니다.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>From/To/By 값 사용  
 다음 섹션에서는 사용 하는 방법에 설명 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성 함께 또는 별도로 합니다.  
  
 이 예제에서는 각각 사용 섹션는 <xref:System.Windows.Media.Animation.DoubleAnimation>, From/하/By 애니메이션을 애니메이션 효과를 줄의 형식인는 <xref:System.Windows.FrameworkElement.Width%2A> 속성은 <xref:System.Windows.Shapes.Rectangle> 하는 장치 독립적 픽셀 단위로 높은 10 / 100 장치 독립적 픽셀로 합니다.  
  
 각 예에서는 사용 하지는 않지만 <xref:System.Windows.Media.Animation.DoubleAnimation>, From, To 및 모든 From/하/에서 속성에 애니메이션 동일 하 게 작동 합니다. 이러한 각 예에서 사용 하 여는 <xref:System.Windows.Media.Animation.Storyboard>, 다른 방법으로 From/하/By 애니메이션을 사용할 수 있습니다. 자세한 내용은 참조 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)합니다.  
  
### <a name="fromto"></a>시작/끝  
 설정 하는 경우는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 는 애니메이션을 적용 하 여 지정 된 값에서 값을 함께 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성으로 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 의 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation> 50 및 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성을 300입니다. 결과적으로 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Shapes.Rectangle> 50에서-300 애니메이션 효과가 적용 됩니다.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>대상  
 설정 하는 경우는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성, 애니메이션된 속성의 기준 값 또는 이전에 동일한 속성을 지정 된 값에 적용 된 구성 애니메이션의 출력에서 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.  
  
 ("구성 애니메이션" 참조 하는 <xref:System.Windows.Media.Animation.ClockState.Active> 또는 <xref:System.Windows.Media.Animation.ClockState.Filling> 이전에 사용 하 여 현재 애니메이션을 적용할 때 적용 된 상태에서 있는 동일한 속성에 적용 하는 애니메이션의 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 전달 동작 합니다.)  
  
 다음 예제에서는 설정는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 의 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation> 300으로 합니다. 지정 된 시작 값 때문에 <xref:System.Windows.Media.Animation.DoubleAnimation> 의 기준 값 (100)를 사용 하 여는 <xref:System.Windows.FrameworkElement.Width%2A> 시작 값으로 속성입니다. <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Shapes.Rectangle> 100에서 300의 애니메이션의 대상 값에 애니메이션 효과가 적용 됩니다.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>By  
 설정 하는 경우는 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 애니메이션의 속성은 애니메이션 효과 줄 속성의 기준 값 또는 지정 된 값과 값의 합계를 구할 구성 애니메이션의 출력에서 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.  
  
 다음 예제에서는 설정는 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 의 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation> 300으로 합니다. 이 예제는 시작 값을 지정 하지 않으므로 <xref:System.Windows.Media.Animation.DoubleAnimation> 의 기준 값을 사용 하 여는 <xref:System.Windows.FrameworkElement.Width%2A> 속성, 100, 시작 값으로. 추가 하 여 끝 값이 결정은 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 300 100: 400, 시작 값에 애니메이션의 값입니다. 결과적으로 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Shapes.Rectangle> 100에서 400 애니메이션 효과가 적용 됩니다.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 설정 하는 경우는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 애니메이션의 속성는 애니메이션을 적용 하 여 지정 된 값에서는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 의해 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 의 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation> 50 및 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 300입니다. 추가 하 여 끝 값이 결정은 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 애니메이션 시작 값인 50: 350를 300의 값입니다. 결과적으로 <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Shapes.Rectangle> 350 50에서 애니메이션 효과가 적용 됩니다.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>시작  
 만 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션의 값, 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성을 애니메이션 효과가 적용 되는 속성의 기준 값 구성 애니메이션의 출력입니다.  
  
 다음 예제에서는 설정는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 의 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation> 50입니다. 지정 된 끝 값 때문에 <xref:System.Windows.Media.Animation.DoubleAnimation> 의 기준 값을 사용 하 여는 <xref:System.Windows.FrameworkElement.Width%2A> 속성, 100, 끝 값으로. <xref:System.Windows.FrameworkElement.Width%2A> 의 <xref:System.Windows.Shapes.Rectangle> 50에서의 기본 값에 애니메이션 효과가 적용 되어는 <xref:System.Windows.FrameworkElement.Width%2A> 속성을 100입니다.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 모두 설정 하면는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 애니메이션의 속성은 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성은 무시 됩니다.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>기타 애니메이션 형식  
 From/하/By 애니메이션은 애니메이션의 유일한 형식이 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제공: 키 프레임 애니메이션과 경로 애니메이션도 제공 합니다.  
  
-   키 프레임 애니메이션은 키 프레임을 사용하여 설명되는 제한 없는 수의 대상 값에 따라 애니메이션을 적용합니다. 자세한 내용은 참조는 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.  
  
-   경로 애니메이션에서 출력 값을 생성 한 <xref:System.Windows.Media.PathGeometry>합니다. 자세한 내용은 참조는 [경로 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 고유한 사용자 지정 애니메이션 형식도 만들 수 있습니다. 자세한 내용은 참조는 [사용자 지정 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [경로 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)  
 [사용자 지정 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)  
 [From, To 및 By 애니메이션 대상 값 샘플](http://go.microsoft.com/fwlink/?LinkID=159988)
