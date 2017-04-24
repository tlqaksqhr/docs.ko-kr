---
title: "키 프레임 애니메이션 개요 | Microsoft Docs"
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
  - "애니메이션, 키 프레임"
  - "키 프레임[WPF], 키 프레임 애니메이션 정보"
  - "여러 애니메이션 대상 값"
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# 키 프레임 애니메이션 개요
이 항목에서는 키 프레임 애니메이션에 대해 소개합니다.  키 프레임 애니메이션을 사용하면 세 개 이상의 대상 값을 사용하여 애니메이션 효과를 주고 애니메이션의 보간 방법을 제어할 수 있습니다.  
  
 이 항목에는 다음 단원이 포함되어 있습니다.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [사전 요구 사항](#prerequisites)  
  
-   [키 프레임 애니메이션 사용](#keyframeanimations)  
  
-   [관련 항목](#seeAlsoToggle)  
  
<a name="prerequisites"></a>   
## 사전 요구 사항  
 이 개요를 이해하려면 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 애니메이션 및 시간 표시 막대에 대해 잘 알고 있어야 합니다.  애니메이션에 대한 소개는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)를 참조하십시오. 또한 From\/To\/By 애니메이션에 대해 익숙하면 이 내용을 이해하는 데 도움이 됩니다.  자세한 내용은 [From\/To\/By 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md)을 참조하십시오.  
  
<a name="whatisakeyframeanimation"></a>   
## 키 프레임 애니메이션  
 From\/To\/By 애니메이션처럼 키 프레임 애니메이션에서도 대상 속성 값에 애니메이션 효과를 줍니다.  해당 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 동안 대상 값 간에 전환되는 효과를 만듭니다.  그러나 From\/To\/By 애니메이션에서는 두 값 사이의 전환을 만드는 반면 단일 키 프레임 애니메이션에서는 원하는 수의 대상 값 사이에서 전환을 만듭니다.  From\/To\/By 애니메이션과 달리 키 프레임 애니메이션에는 대상 값을 설정하는 데 사용하는 From, To 또는 By 속성이 없습니다.  키 프레임 애니메이션의 대상 값은 키 프레임 개체\(이후에는 "키 프레임 애니메이션"\)를 사용하여 지정합니다.  애니메이션의 대상 값을 지정하려면 키 프레임 개체를 만들어 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> 컬렉션에 추가합니다.  애니메이션을 실행하면 애니메이션이 지정한 프레임 간에 전환됩니다.  
  
 일부 키 프레임 방법에서는 여러 대상 값을 지원하는 것뿐 아니라 여러 보간 방법도 지원합니다.  애니메이션의 보간 방법에서는 애니메이션이 한 값에서 다음 값으로 전환되는 방식을 정의합니다.  세 가지의 보간 형식으로 [discrete](GTMT), [linear](GTMT) 및 [splined](GTMT)가 있습니다.  
  
 키 프레임 애니메이션을 사용하여 애니메이션 효과를 주려면 다음 단계를 수행합니다.  
  
-   From\/To\/By 애니메이션처럼 애니메이션을 선언하고 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>을 지정합니다.  
  
-   각 대상 값에 대해 적절한 형식의 키 프레임을 만들고 해당 값 및 <xref:System.Windows.Media.Animation.KeyTime>을 설정한 다음 애니메이션의 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> 컬렉션에 추가합니다.  
  
-   From\/To\/By 애니메이션처럼 애니메이션을 속성과 연결합니다.  스토리보드를 사용하여 속성에 애니메이션을 적용하는 방법에 대한 자세한 내용은 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)를 참조하십시오.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>를 사용하여 <xref:System.Windows.Shapes.Rectangle> 요소에 애니메이션 효과를 주어 네 개의 다른 위치로 움직입니다.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->  
  
 From\/To\/By 애니메이션처럼 키 프레임 애니메이션도 태그 및 코드에서 <xref:System.Windows.Media.Animation.Storyboard>를 사용하거나 코드에서 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드를 사용하여 속성에 적용할 수 있습니다.  또한 키 프레임 애니메이션을 사용하여 <xref:System.Windows.Media.Animation.AnimationClock>을 만들고 하나 이상의 속성에 적용할 수 있습니다.  애니메이션을 적용하는 다양한 방법에 대한 자세한 내용은 [속성 애니메이션 기술 개요](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)를 참조하십시오.  
  
<a name="animation_types"></a>   
## 키 프레임 애니메이션 형식  
 애니메이션은 속성 값을 생성하므로 속성 형식에 따라 애니메이션의 형식도 달라집니다.  요소의 <xref:System.Windows.FrameworkElement.Width%2A> 속성과 같이 <xref:System.Double>을 사용하는 속성에 애니메이션 효과를 적용하려면 <xref:System.Double> 값을 생성하는 애니메이션을 사용합니다.  <xref:System.Windows.Point>를 사용하는 속성에 애니메이션 효과를 적용하려면 <xref:System.Windows.Point> 값 등을 생성하는 애니메이션을 사용합니다.  
  
 키 프레임 애니메이션 클래스는 <xref:System.Windows.Media.Animation> 네임스페이스에 속하며 다음 명명 규칙을 따릅니다.  
  
 *\<Type\>* `AnimationUsingKeyFrames`  
  
 여기서 *\<Type\>*은 클래스가 애니메이션 효과를 주는 값의 형식입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 다음과 같은 키 프레임 애니메이션 클래스를 제공합니다.  
  
|속성 형식|해당 From\/To\/By 애니메이션 클래스|지원되는 보간 방법|  
|-----------|-------------------------------|----------------|  
|<xref:System.Boolean>|<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>|불연속|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16AnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32AnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64AnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>|불연속|  
|<xref:System.Object>|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>|불연속|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.String>|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|불연속|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimationUsingKeyFrames>|불연속, 선형, 스플라인|  
  
<a name="animation_target_values"></a>   
## 대상 값\(키 프레임\) 및 키 시간  
 다른 속성 값에 애니메이션 효과를 적용하기 위해 서로 다른 형식의 키 프레임 애니메이션을 사용하는 것처럼 키 프레임 개체도 애니메이션 효과를 적용하는 값의 각 형식과 지원되는 보간 방법에 대해 서로 다른 형식을 사용합니다.  키 프레임 형식에서는 다음 명명 규칙을 따릅니다.  
  
 *\<InterpolationMethod\>\<Type\>* `KeyFrame`  
  
 여기서 *\<InterpolationMethod\>*는 키 프레임에서 사용하는 보간 방법이고 *\<Type\>*은 클래스에서 애니메이션 효과를 적용하는 값의 형식입니다.  세 가지의 보간 방법을 모두 지원하는 키 프레임 애니메이션에서는 세 가지의 키 프레임 형식을 사용할 수 있습니다.  예를 들어 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>에서는 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> 및 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>의 세 가지 키 프레임 형식을 사용할 수 있습니다.  보간 방법에 대해서는 뒷부분에 나오는 단원에서 자세히 설명합니다.  
  
 키 프레임의 주요 용도는 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 및 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>를 지정하는 것입니다.  모든 키 프레임 형식에서는 이 두 속성을 지정합니다.  
  
-   <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 속성은 해당 키 프레임의 대상 값을 지정합니다.  
  
-   <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 속성은 애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 내에서 키 프레임의 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>에 도달하는 때를 지정합니다.  
  
 키 프레임 애니메이션이 시작되면 해당 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 속성에서 정의한 순서대로 키 프레임이 반복됩니다.  
  
-   시간 0에 키 프레임이 없으면 애니메이션에서 대상 속성의 현재 값과 첫 번째 키 프레임의 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 간에 전환이 만들어지고, 그렇지 않으면 애니메이션의 출력 값이 첫 번째 키 프레임의 값이 됩니다.  
  
-   애니메이션에서 두 번째 키 프레임으로 지정한 보간 방법을 사용하여 첫 번째 및 두 번째 키 프레임의 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 간 전환을 만듭니다.  이 전환은 첫 번째 프레임의 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>에서 시작되고 두 번째 키 프레임의 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>에 도달하면 끝납니다.  
  
-   애니메이션에서 계속해서 이후의 각 키 프레임과 그 앞의 키 프레임 간을 전환합니다.  
  
-   마지막으로 키 시간이 가장 큰 키 프레임 즉, 애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>보다 작거나 같은 키 프레임의 값으로 애니메이션이 전환됩니다.  
  
 애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>이 <xref:System.Windows.Duration.Automatic%2A>이거나 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>이 마지막 키 프레임의 시간과 동일한 경우 애니메이션이 끝납니다.  그렇지 않고 애니메이션의 <xref:System.Windows.Duration>이 마지막 키 프레임의 키 시간보다 큰 경우 애니메이션이 <xref:System.Windows.Duration>의 끝에 도달할 때까지 키 프레임 값을 보유합니다.  모든 애니메이션과 마찬가지로 키 프레임 애니메이션에서도 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을 통해 활성 기간의 끝에 도달할 때 최종 값을 보유할지 여부를 확인합니다.  자세한 내용은 [타이밍 동작 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)을 참조하십시오.  
  
 다음 예제에서는 앞의 예제에서 정의한 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> 개체를 사용하여 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 및 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 속성의 작동 방식을 보여 줍니다.  
  
-   첫 번째 키 프레임은 곧바로 애니메이션의 출력 값을 0으로 설정합니다.  
  
-   두 번째 키 프레임은 0에서 350 사이에 애니메이션 효과를 적용합니다.  첫 번째 키 프레임이 끝난 후 시작되고\(시간 \= 0초\) 2초 동안 재생된 다음 시간 0:0:2에 끝납니다.  
  
-   세 번째 키 프레임은 350에서 50 사이에 애니메이션 효과를 적용합니다.  두 번째 키 프레임이 끝난 후 시작되고\(시간 \= 2초\) 5초 동안 재생된 다음 시간 0:0:7에 끝납니다.  
  
-   네 번째 키 프레임은 50에서 200 사이에 애니메이션 효과를 적용합니다.  세 번째 키 프레임이 끝난 후 시작되고\(시간 \= 7초\) 1초 동안 재생된 다음 시간 0:0:8에 끝납니다.  
  
-   애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성을 10초로 설정했으므로 애니메이션에서는 시간 0:0:10에 끝나기 전에 2초 동안 최종 값을 보유합니다.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->  
  
<a name="interpolationmethods"></a>   
## 보간 방법  
 앞의 단원에서 일부 키 프레임 애니메이션은 여러 보간 방법을 지원한다고 설명했습니다.  애니메이션의 보간은 애니메이션에서 해당 지속 시간 동안 값 사이를 전환하는 방법을 말합니다.  애니메이션에서 사용할 키 프레임 형식을 선택하면 해당 키 프레임 세그먼트에 대한 보간 방법을 정의할 수 있습니다.  보간 방법에는 세 가지 형식으로 선형, 불연속 및 스플라인이 있습니다.  
  
### 선형 보간  
 [linear interpolation](GTMT)을 사용하면 애니메이션이 세그먼트 지속 시간의 일정 비율로 진행됩니다.  예를 들어 키 프레임 세그먼트가 5초의 지속 시간 동안 0에서 10 사이를 전환하면 애니메이션에서는 지정한 시간에 다음 값을 출력합니다.  
  
|시간|출력 값|  
|--------|----------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5|9|  
|5|10|  
  
### 불연속 보간  
 [discrete interpolation](GTMT)을 사용하면 애니메이션 기능이 보간 없이 한 값에서 다음 값으로 이동합니다.  키 프레임 세그먼트가 5초의 지속 시간 동안 0에서 10 사이를 전환하면 애니메이션에서는 지정한 시간에 다음 값을 출력합니다.  
  
|시간|출력 값|  
|--------|----------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5|0|  
|5|10|  
  
 애니메이션에서는 세그먼트 지속 시간의 끝에 도달할 때까지 출력 값을 변경하지 않습니다.  
  
 [Splined interpolation](GTMT)은 좀 더 복잡합니다.  이 보간 방법에 대해서는 다음 단원에서 설명합니다.  
  
<a name="anim_spline"></a>   
### 스플라인 보간  
 스플라인 보간을 사용하면 더 실감나는 타이밍 효과를 얻을 수 있습니다.  애니메이션은 실제 세계에서 일어나는 효과를 모방하는 데 사용되는 경우가 많으므로 개발자는 개체의 가속 및 감속을 미세 조정하고 타이밍 세그먼트를 긴밀히 조작해야 할 수 있습니다.  스플라인 키 프레임을 사용하면 스프라인 보간과 함께 애니메이션 효과를 적용할 수 있습니다.  다른 키 프레임에서는 <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> 및 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>을 지정합니다.  또한 스플라인 키 프레임에서는 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>도 지정합니다.  다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>의 단일 스플라인 키 프레임을 보여 줍니다.  <xref:System.Windows.Media.Animation.KeySpline> 속성이 바로 스플라인 키 프레임을 다른 형식의 키 프레임과 구별되게 만드는 속성입니다.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->  
  
 [cubic Bezier curve](GTMT)은 시작점과 끝점, 그리고 두 개의 제어점으로 정의됩니다.  스플라인 키 프레임의 <xref:System.Windows.Media.Animation.KeySpline> 속성은 \(0,0\)에서 \(1,1\)에 이르는 베지어 곡선의 제어점 두 개를 정의합니다.  첫 번째 제어점은 베지어 곡선의 처음 절반에 대한 곡선 인수를 제어하고, 두 번째 제어점은 베지어 세그먼트의 나머지 절반에 대한 곡선 인수를 제어합니다.  결과 곡선에서는 해당 스플라인 키 프레임의 변경 속도를 보여 줍니다.  곡선이 가파를수록 키 프레임의 값이 더 빠르게 변경됩니다.  곡선의 경사가 완만할수록 키 프레임의 값이 더 느리게 변경됩니다.  
  
 <xref:System.Windows.Media.Animation.KeySpline>을 사용하면 떨어지는 물이나 튀는 공과 같은 실제 궤도를 시뮬레이션하거나 동작 애니메이션에 "점점 가까이" 및 "점점 멀리" 효과를 적용할 수 있습니다.  배경 페이드나 컨트롤 단추 다시 바인딩과 같은 사용자 상호 작용 효과의 경우 스플라인 보간을 적용하여 애니메이션의 변경 속도를 특정 방식으로 높이거나 줄일 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.KeySpline>을 0,1 1,0으로 지정하여 다음과 같은 베지어 곡선을 만듭니다.  
  
 ![3차원 곡선](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm\_keyspline\_0\_1\_1\_0")  
제어점 \(0.0, 1.0\) 및 \(1.0, 0.0\)을 사용한 키 스플라인  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->  
  
 이 키 프레임의 애니메이션 효과는 시작할 때 빠르고 느려졌다가 끝나기 전에 다시 빨라집니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.KeySpline>을 0.5,0.25 0.75,1.0으로 지정하여 다음과 같은 베지어 곡선을 만듭니다.  
  
 ![3차원 곡선](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm\_keyspline\_025\_050\_075\_10")  
제어점 \(0.25, 0.5\) 및 \(0.75, 1.0\)을 사용한 키 스플라인  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  -->  
  
 베지어 곡선의 곡률이 거의 변경되지 않으므로 이 키 프레임의 애니메이션 효과는 거의 일정한 속도로 적용되다가 끝에 이르러 약간 느려집니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>를 직사각형의 위치에 애니메이션 효과를 적용합니다.  <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>에서는 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> 개체를 사용하므로 각 키 프레임 값 사이의 전환에는 스플라인 보간이 사용됩니다.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SplinedInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SplinedInterpolationExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  -->  
  
 스플라인 보간은 이해하기 까다로울 수 있으므로 여러 설정을 실험해 보면 도움이 될 수 있습니다.  [Key Spline Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160011)에서는 키 스플라인 값을 변경하고 애니메이션에 미치는 영향을 확인할 수 있습니다.  
  
<a name="combininginterpolationmethods"></a>   
### 보간 방법 조합  
 키 프레임을 사용할 때 하나의 키 프레임 애니메이션에서 여러 보간 유형을 함께 사용할 수 있습니다.  서로 다른 보간을 사용하는 두 개의 키 프레임 애니메이션이 이어지면 두 번째 키 프레임의 보간 방법을 사용하여 첫 번째 값에서 두 번째 값으로의 전환을 만듭니다.  
  
 다음 예제에서는 선형, 스플라인 및 불연속 보간을 사용하는 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>를 만듭니다.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#ComboInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#ComboInterpolationExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#combointerpolationexample)]  -->  
  
<a name="keytimes"></a>   
## 지속 시간 및 키 시간에 대한 추가 정보  
 다른 애니메이션과 마찬가지로 키 프레임 애니메이션에는 <xref:System.Windows.Duration> 속성이 있습니다.  애니메이션의 <xref:System.Windows.Duration>을 지정하는 동시에 해당 지속 시간의 어느 만큼을 각 키 프레임에 부여할 것인지 지정해야 합니다.  이렇게 하려면 각 애니메이션 키 프레임의 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>을 지정합니다.  각 키 프레임의 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>은 해당 키 프레임이 끝나는 시간을 지정합니다.  
  
 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> 속성은 키 시간이 재생되는 길이는 지정하지 않습니다.  키 프레임이 재생되는 시간은 키 프레임이 끝나는 시간, 이전 키 프레임이 끝난 시간 및 애니메이션의 지속 시간에 따라 결정됩니다.  키 시간은 시간 값, 백분율, 특수 값\(<xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 또는 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>\) 등으로 지정할 수 있습니다.  
  
 다음 목록에서는 키 시간을 지정하는 여러 방법을 보여 줍니다.  
  
### TimeSpan 값  
 <xref:System.TimeSpan> 값을 사용하여 <xref:System.Windows.Media.Animation.KeyTime>을 지정할 수 있습니다.  이 값은 0보다 크거나 같고 애니메이션의 지속 시간보다 작거나 같아야 합니다.  다음 예제에서는 지속 시간이 10초이고 키 시간을 시간 값으로 지정한 네 개의 키 프레임이 있는 애니메이션을 보여 줍니다.  
  
-   첫 번째 키 프레임은 기준 값에서 100 사이에 처음 3초 동안 애니메이션 효과를 적용하며 시간 0:0:03에 끝납니다.  
  
-   두 번째 키 프레임은 100에서 200 사이에 애니메이션 효과를 적용합니다.  첫 번째 키 프레임이 끝난 후 시작되고\(시간 \= 3초\) 5초 동안 재생된 다음 시간 0:0:8에 끝납니다.  
  
-   세 번째 키 프레임은 200에서 500 사이에 애니메이션 효과를 적용합니다.  두 번째 키 프레임이 끝난 후 시작되고\(시간 \= 8초\) 1초 동안 재생된 다음 시간 0:0:9에 끝납니다.  
  
-   네 번째 키 프레임은 500에서 600 사이에 애니메이션 효과를 적용합니다.  세 번째 키 프레임이 끝난 후 시작되고\(시간 \= 9초\) 1초 동안 재생된 다음 시간 0:0:10에 끝납니다.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#TimeSpanKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#timespankeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#TimeSpanKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#timespankeytimeexample)]  -->  
  
### 백분율 값  
 백분율 값은 키 프레임이 애니메이션 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>의 일정 비율에 끝나도록 지정합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 백분율을 숫자로 지정하고 뒤에 `%` 기호를 붙입니다.  코드에서는 <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A> 메서드를 사용하고 이 메서드에 백분율을 나타내는 <xref:System.Double>을 전달합니다.  이 값은 0보다 크거나 같고 100%보다 작거나 같아야 합니다.  다음 예제에서는 지속 시간이 10초이고 키 시간을 백분율로 지정한 네 개의 키 프레임이 있는 애니메이션을 보여 줍니다.  
  
-   첫 번째 키 프레임은 기준 값에서 100 사이에 처음 3초 동안 애니메이션 효과를 적용하며 시간 0:0:3에 끝납니다.  
  
-   두 번째 키 프레임은 100에서 200 사이에 애니메이션 효과를 적용합니다.  첫 번째 키 프레임이 끝난 후 시작되고\(시간 \= 3초\) 5초 동안 재생된 다음 시간 0:0:8\(0.8 \* 10 \= 8\)에 끝납니다.  
  
-   세 번째 키 프레임은 200에서 500 사이에 애니메이션 효과를 적용합니다.  두 번째 키 프레임이 끝난 후 시작되고\(시간 \= 8초\) 1초 동안 재생된 다음 시간 0:0:9\(0.9 \* 10 \= 9\)에 끝납니다.  
  
-   네 번째 키 프레임은 500에서 600 사이에 애니메이션 효과를 적용합니다.  세 번째 키 프레임이 끝난 후 시작되고\(시간 \= 9초\) 1초 동안 재생된 다음 시간 0:0:10\(1 \* 10 \= 10\)에 끝납니다.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PercentageKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#percentagekeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PercentageKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#percentagekeytimeexample)]  -->  
  
### 특수 값, Uniform  
 각 키 프레임이 동일한 시간을 사용하도록 하려면 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 타이밍을 사용합니다.  
  
 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 키 시간에서는 사용 가능한 시간을 키 프레임의 수로 균일하게 나누어 각 키 프레임의 종료 시간을 지정합니다.  다음 예제에서는 지속 시간이 10초이고 키 시간을 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>으로 지정한 네 개의 키 프레임이 있는 애니메이션을 보여 줍니다.  
  
-   첫 번째 키 프레임은 기준 값에서 100 사이에 처음 2.5초 동안 애니메이션 효과를 적용하며 시간 0:0:2.5에 끝납니다.  
  
-   두 번째 키 프레임은 100에서 200 사이에 애니메이션 효과를 적용합니다.  첫 번째 키 프레임이 끝난 후 시작되고\(시간 \= 2.5초\) 약 2.5초 동안 재생된 다음 시간 0:0:5에 끝납니다.  
  
-   세 번째 키 프레임은 200에서 500 사이에 애니메이션 효과를 적용합니다.  두 번째 키 프레임이 끝난 후 시작되고\(시간 \= 5초\) 2.5초 동안 재생된 다음 시간 0:0:7.5에 끝납니다.  
  
-   네 번째 키 프레임은 500에서 600 사이에 애니메이션 효과를 적용합니다.  두 번째 키 프레임이 끝난 후 시작되고\(시간 \= 7.5초\) 2.5초 동안 재생된 다음 시간 0:0:1에 끝납니다.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#UniformKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#uniformkeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#UniformKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#uniformkeytimeexample)]  -->  
  
### 특수 값, Paced  
 일정 속도로 애니메이션 효과를 적용하려면 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 타이밍을 사용합니다.  
  
 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 키 시간에서는 사용 가능한 시간을 각 키 프레임 길이에 따라 할당하여 각 프레임의 지속 시간을 지정합니다.  그러면 애니메이션의 속도를 일정하게 유지하는 동작이 만들어집니다.  다음 예제에서는 지속 시간이 10초이고 키 시간을 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>로 지정한 네 개의 키 프레임이 있는 애니메이션을 보여 줍니다.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PacedKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#pacedkeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PacedKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#pacedkeytimeexample)]  -->  
  
 마지막 키 프레임의 키 시간이 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> 또는 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>이면 확인된 키 시간이 100%로 설정됩니다.  여러 프레임 애니메이션의 첫 번째 키 프레임이 Paced이면 확인된 키 시간이 0으로 설정됩니다.  키 프레임 컬렉션에 하나의 키 프레임만 포함되어 있고 Paced 키 프레임인 경우에는 확인된 키 시간이 100%로 설정됩니다.  
  
 하나의 키 프레임 애니메이션 내의 다른 키 프레임에서는 서로 다른 키 시간 형식을 사용할 수 있습니다.  
  
<a name="combiningkeytimes"></a>   
## 키 시간, 순서가 잘못된 키 프레임 결합  
 키 프레임을 사용할 때 동일한 애니메이션에서 여러 <xref:System.Windows.Media.Animation.KeyTime> 값 형식을 사용할 수 있습니다.  그리고 키 프레임을 재생할 순서대로 추가하는 것이 좋지만 그렇게 하지 않아도 됩니다.  애니메이션 및 타이밍 시스템에서는 순서가 잘못된 키 프레임을 해결할 수 있습니다.  키 시간이 잘못된 키 프레임은 무시됩니다.  
  
 다음 목록에서는 키 프레임 애니메이션의 키 프레임에 대한 키 시간을 확인하는 절차를 보여 줍니다.  
  
1.  <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> 값을 확인합니다.  
  
2.  애니메이션의 총 보간 시간 즉, 키 프레임 애니메이션에서 정방향 반복을 완료하는 데 걸리는 총 시간을 확인합니다.  
  
    1.  애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A>이 <xref:System.Windows.Duration.Automatic%2A> 또는 <xref:System.Windows.Duration.Forever%2A>가 아니면 총 보간 시간은 애니메이션의 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 속성 값입니다.  
  
    2.  그렇지 않으면 총 보간 시간은 키 프레임 사이에서 지정한 가장 큰 <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> 값\(있는 경우\)입니다.  
  
    3.  그 외의 경우 총 보간 시간은 1초입니다.  
  
3.  총 보간 시간 값을 사용하여 <xref:System.Windows.Media.Animation.KeyTimeType> <xref:System.Windows.Media.Animation.KeyTime> 값을 확인합니다.  
  
4.  앞의 단계에서 확인하지 않은 경우 마지막 키 프레임을 확인합니다.  마지막 키 프레임의 <xref:System.Windows.Media.Animation.KeyTime>이 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> 또는 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>이면 확인된 키 시간은 총 보간 시간과 동일합니다.  
  
     첫 번째 키 프레임의 <xref:System.Windows.Media.Animation.KeyTime>이 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>이고 이 애니메이션에 두 개 이상의 키 프레임이 있으면 해당 <xref:System.Windows.Media.Animation.KeyTime> 값이 0으로 확인됩니다. 키 프레임이 하나뿐이고 해당 <xref:System.Windows.Media.Animation.KeyTime> 값이 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>이면 앞의 단계에서 설명한 대로 이 값이 총 보간 시간으로 확인됩니다.  
  
5.  나머지 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> 값을 확인합니다. 각 값에는 사용 가능한 시간의 동일한 몫이 할당됩니다.  이 프로세스 동안 확인되지 않은 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> 값은 임시로 <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> 값으로 처리되고 임시로 확인된 시간을 가집니다.  
  
6.  근처에 있는 키 프레임 중 <xref:System.Windows.Media.Animation.KeyTime> 값이 확인된 키 프레임을 사용하여 키 시간이 지정되지 않은 키 프레임의 <xref:System.Windows.Media.Animation.KeyTime> 값을 확인합니다.  
  
7.  나머지 <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> 값을 확인합니다.  <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime>에서는 이웃 키 프레임의 <xref:System.Windows.Media.Animation.KeyTime> 값을 사용하여 확인되지 않은 시간을 결정합니다.  목표는 키 프레임의 확인된 시간 주위에서 애니메이션 속도가 일정하도록 만드는 것입니다.  
  
8.  확인된 시간\(기본 키\)의 순서 및 선언\(보조 키\)의 순서대로 키 프레임을 정렬합니다. 즉, 확인된 키 프레임 <xref:System.Windows.Media.Animation.KeyTime> 값을 기준으로 한 안정적인 정렬을 사용합니다.  
  
## 참고 항목  
 <xref:System.Windows.Media.Animation.KeyTime>   
 <xref:System.Windows.Media.Animation.KeySpline>   
 <xref:System.Windows.Media.Animation.Timeline>   
 [Key Spline Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160011)   
 [KeyFrame Animation 샘플](http://go.microsoft.com/fwlink/?LinkID=160012)   
 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Storyboard 개요](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [키 프레임 애니메이션 방법 항목](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)   
 [타이밍 동작 개요](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)