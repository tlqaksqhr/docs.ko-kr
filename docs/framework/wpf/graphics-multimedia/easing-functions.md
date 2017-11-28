---
title: "감속/가속 함수"
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
- applying mathematical formulas to animations [WPF]
- applying easing functions to animations [WPF]
- mathematical formulas [WPF], applying to animations
- animations [WPF], realistic movement
- easing functions [WPF]
- customizing easing functions [WPF]
- easing functions [WPF], definition
- easing functions [WPF], customizing
- animations [WPF], applying
ms.assetid: 075b9c2b-82c4-43fa-b3cd-de0b6236eb38
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 198ec8b8cb0b27e009f01f8e60a47e8086a7dbc7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="easing-functions"></a><span data-ttu-id="be26b-102">감속/가속 함수</span><span class="sxs-lookup"><span data-stu-id="be26b-102">Easing Functions</span></span>
<span data-ttu-id="be26b-103">감속/가속 함수를 사용하여 사용자 지정 수식을 애니메이션에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-103">Easing functions allow you to apply custom mathematical formulas to your animations.</span></span> <span data-ttu-id="be26b-104">예를 들어 마치 스프링 위에 있는 것처럼 개체가 사실적으로 바운스되거나 동작하도록 하고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-104">For example, you may want an object to realistically bounce or behave as though it were on a spring.</span></span> <span data-ttu-id="be26b-105">키 프레임 또는 심지어 From/To/By 애니메이션을 사용하여 이러한 효과를 대략적으로 나타낼 수 있지만 상당히 복잡한 작업이 필요하며 수식을 사용할 때보다 애니메이션이 덜 정확해집니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-105">You could use Key-Frame or even From/To/By animations to approximate these effects but it would take a significant amount of work and the animation would be less accurate than using a mathematical formula.</span></span>  
  
 <span data-ttu-id="be26b-106">상속 하 여 사용자 고유의 사용자 지정 감속/가속 함수를 만들 뿐 아니라 <xref:System.Windows.Media.Animation.EasingFunctionBase>, 런타임에서 제공 하는 몇 가지 감속/가속 함수 중 하나를 사용 하 여 일반적인 효과 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-106">Besides creating your own custom easing function by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>, you can use one of several easing functions provided by the runtime to create common effects.</span></span>  
  
-   <span data-ttu-id="be26b-107"><xref:System.Windows.Media.Animation.BackEase>: 수행 취소 애니메이션 동작 약간 표시 된 경로에 애니메이션 효과 적용 하기 전에 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-107"><xref:System.Windows.Media.Animation.BackEase>: Retracts the motion of an animation slightly before it begins to animate in the path indicated.</span></span>  
  
-   <span data-ttu-id="be26b-108"><xref:System.Windows.Media.Animation.BounceEase>: 바운스되 효과 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-108"><xref:System.Windows.Media.Animation.BounceEase>: Creates a bouncing effect.</span></span>  
  
-   <span data-ttu-id="be26b-109"><xref:System.Windows.Media.Animation.CircleEase>: 및/또는 순환 함수를 사용 하 여 감속 하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-109"><xref:System.Windows.Media.Animation.CircleEase>: Creates an animation that accelerates and/or decelerates using a circular function.</span></span>  
  
-   <span data-ttu-id="be26b-110"><xref:System.Windows.Media.Animation.CubicEase>: 및/또는 수식을 사용 하 여 감속 하는 애니메이션 만듭니다 *f*(*t*) = *t*<sup>3</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-110"><xref:System.Windows.Media.Animation.CubicEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>3</sup>.</span></span>  
  
-   <span data-ttu-id="be26b-111"><xref:System.Windows.Media.Animation.ElasticEase>: 유사한 앞뒤로 정지할 될 때까지 스프링 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-111"><xref:System.Windows.Media.Animation.ElasticEase>: Creates an animation that resembles a spring oscillating back and forth until it comes to rest.</span></span>  
  
-   <span data-ttu-id="be26b-112"><xref:System.Windows.Media.Animation.ExponentialEase>: 및/또는 지 수 수식을 사용 하 여 감속 하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-112"><xref:System.Windows.Media.Animation.ExponentialEase>: Creates an animation that accelerates and/or decelerates using an exponential formula.</span></span>  
  
-   <span data-ttu-id="be26b-113"><xref:System.Windows.Media.Animation.PowerEase>: 및/또는 수식을 사용 하 여 감속 하는 애니메이션 만듭니다 *f*(*t*) = *t*<sup>p</sup> 여기서 p는는 같음<xref:System.Windows.Media.Animation.PowerEase.Power%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-113"><xref:System.Windows.Media.Animation.PowerEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>p</sup> where p is equal to the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span>  
  
-   <span data-ttu-id="be26b-114"><xref:System.Windows.Media.Animation.QuadraticEase>: 및/또는 수식을 사용 하 여 감속 하는 애니메이션 만듭니다 *f*(*t*) = *t*<sup>2</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-114"><xref:System.Windows.Media.Animation.QuadraticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>2</sup>.</span></span>  
  
-   <span data-ttu-id="be26b-115"><xref:System.Windows.Media.Animation.QuarticEase>: 및/또는 수식을 사용 하 여 감속 하는 애니메이션 만듭니다 *f*(*t*) = *t*<sup>4</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-115"><xref:System.Windows.Media.Animation.QuarticEase>: Creates an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>4</sup>.</span></span>  
  
-   <span data-ttu-id="be26b-116"><xref:System.Windows.Media.Animation.QuinticEase>: 및/또는 수식을 사용 하 여 감속 하는 애니메이션 만들기 *f*(*t*) = *t*<sup>5</sup>합니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-116"><xref:System.Windows.Media.Animation.QuinticEase>: Create an animation that accelerates and/or decelerates using the formula *f*(*t*) = *t*<sup>5</sup>.</span></span>  
  
-   <span data-ttu-id="be26b-117"><xref:System.Windows.Media.Animation.SineEase>: 및/또는 사인 수식을 사용 하 여 감속 하는 애니메이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-117"><xref:System.Windows.Media.Animation.SineEase>: Creates an animation that accelerates and/or decelerates using a sine formula.</span></span>  
  
 <span data-ttu-id="be26b-118">다음 샘플에서 이러한 감속/가속 함수의 동작을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-118">You can explore the behavior of these easing functions with the following sample.</span></span>  
  
 [<span data-ttu-id="be26b-119">이 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="be26b-119">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=easing_functions_gallery)  
  
 <span data-ttu-id="be26b-120">감속/가속 함수를 애니메이션에 적용 하려면 사용 된 `EasingFunction` 애니메이션의 속성에 애니메이션을 적용할 감속/가속 함수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-120">To apply an easing function to an animation, use the `EasingFunction` property of the animation specify the easing function to apply to the animation.</span></span> <span data-ttu-id="be26b-121">다음 예제에서는 적용는 <xref:System.Windows.Media.Animation.BounceEase> 감속/가속 함수를 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 바운스되 효과를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-121">The following example applies a <xref:System.Windows.Media.Animation.BounceEase> easing function to a <xref:System.Windows.Media.Animation.DoubleAnimation> to create a bouncing effect.</span></span>  
  
 [<span data-ttu-id="be26b-122">이 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="be26b-122">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=BounceEase)  
  
 [!code-xaml[BounceEase_snippet#BounceEase](../../../../samples/snippets/csharp/VS_Snippets_Wpf/bounceease_snippet/CS/window1.xaml#bounceease)]  
  
 <span data-ttu-id="be26b-123">이전 예제에서는 감속/가속 함수를 From/To/By 애니메이션에 적용했습니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-123">In the previous example, the easing function was applied to a From/To/By animation.</span></span> <span data-ttu-id="be26b-124">이러한 감속/가속 함수를 키 프레임 애니메이션에 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-124">You can also apply these easing functions to Key-Frame animations.</span></span> <span data-ttu-id="be26b-125">다음 예제에서는 키 프레임과 연결된 감속/가속 함수를 사용하여 위로 수축했다가 느려진 다음 아래로 늘어난 후(떨어지는 것처럼) 바운스되었다가 정지되는 사각형의 애니메이션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-125">The following example shows how to use key frames with easing functions associated with them to create an animation of a rectangle that contracts upward, slows down, then expands downward (as though falling) and then bounces to a stop.</span></span>  
  
 [<span data-ttu-id="be26b-126">이 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="be26b-126">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=EasingFunctionDoubleKeyFrame)  
  
 [!code-xaml[EasingFunctionDoubleKeyFrame_snippet#EasingFunctionDoubleKeyFrame](../../../../samples/snippets/csharp/VS_Snippets_Wpf/easingfunctiondoublekeyframe_snippet/CS/window1.xaml#easingfunctiondoublekeyframe)]  
  
 <span data-ttu-id="be26b-127">사용할 수는 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> 속성 즉, 감속/가속 함수 동작 방식을 변경 하는 애니메이션 보간 하는 방법을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-127">You can use the <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> property to alter how the easing function behaves, that is, change how the animation interpolates.</span></span> <span data-ttu-id="be26b-128">세 가지 가능한 값을 제공할 수 있는 <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span><span class="sxs-lookup"><span data-stu-id="be26b-128">There are three possible values you can give for <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A>:</span></span>  
  
-   <span data-ttu-id="be26b-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: 보간 감속/가속 함수와 관련 된 수식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-129"><xref:System.Windows.Media.Animation.EasingMode.EaseIn>: Interpolation follows the mathematical formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="be26b-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: 보간 감속/가속 함수에 연결 된 식의 결과 뺀 값 100% 보간을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-130"><xref:System.Windows.Media.Animation.EasingMode.EaseOut>: Interpolation follows 100% interpolation minus the output of the formula associated with the easing function.</span></span>  
  
-   <span data-ttu-id="be26b-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: 보간을 사용 하 여 <xref:System.Windows.Media.Animation.EasingMode.EaseIn> 애니메이션의 첫 번째 부분에 대 한 및 <xref:System.Windows.Media.Animation.EasingMode.EaseOut> 하반기에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-131"><xref:System.Windows.Media.Animation.EasingMode.EaseInOut>: Interpolation uses <xref:System.Windows.Media.Animation.EasingMode.EaseIn> for the first half of the animation and <xref:System.Windows.Media.Animation.EasingMode.EaseOut> for the second half.</span></span>  
  
 <span data-ttu-id="be26b-132">다음 그래프의 다른 값을 보여 줍니다. <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> 여기서 *f*(*x*)에서는 및 *t* 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-132">The graphs below demonstrate the different values of <xref:System.Windows.Media.Animation.EasingFunctionBase.EasingMode%2A> where *f*(*x*) represents the animation progress and *t* represents time.</span></span>  
  
 <xref:System.Windows.Media.Animation.BackEase>  
  
 <span data-ttu-id="be26b-133">![BackEase EasingMode 그래프](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-133">![BackEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/backease-graph.png "BackEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.BounceEase>  
  
 <span data-ttu-id="be26b-134">![BounceEase EasingMode 그래프](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-134">![BounceEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/bounceease-graph.png "BounceEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CircleEase>  
  
 <span data-ttu-id="be26b-135">![CircleEase EasingMode 그래프](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-135">![CircleEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/circleease-graph.png "CircleEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.CubicEase>  
  
 <span data-ttu-id="be26b-136">![CubicEase EasingMode 그래프](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-136">![CubicEase EasingMode graphs.](../../../../docs/framework/wpf/graphics-multimedia/media/cubicease-graph.png "CubicEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ElasticEase>  
  
 <span data-ttu-id="be26b-137">![다양한 easingmode 그래프로 나타낸 ElasticEase](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-137">![ElasticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/elasticease-graph.png "ElasticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.ExponentialEase>  
  
 <span data-ttu-id="be26b-138">![다양한 easingmode 그래프로 나타낸 ExponentialEase](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-138">![ExponentialEase graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/exponentialease-graph.png "ExponentialEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.PowerEase>  
  
 <span data-ttu-id="be26b-139">![다양한 easingmode 그래프로 나타낸 QuarticEase](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-139">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuadraticEase>  
  
 <span data-ttu-id="be26b-140">![다양한 easingmode 그래프로 나타낸 QuadraticEase](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-140">![QuadraticEase with graphs of different easingmodes](../../../../docs/framework/wpf/graphics-multimedia/media/quadraticease-graph.png "QuadraticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuarticEase>  
  
 <span data-ttu-id="be26b-141">![다양한 easingmode 그래프로 나타낸 QuarticEase](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-141">![QuarticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quarticease-graph.png "QuarticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.QuinticEase>  
  
 <span data-ttu-id="be26b-142">![다양한 easingmode 그래프로 나타낸 QuinticEase](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-142">![QuinticEase with graphs of different easingmodes.](../../../../docs/framework/wpf/graphics-multimedia/media/quinticease-graph.png "QuinticEase_Graph")</span></span>  
  
 <xref:System.Windows.Media.Animation.SineEase>  
  
 <span data-ttu-id="be26b-143">![다양한 EasingMode 값의 SineEase](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span><span class="sxs-lookup"><span data-stu-id="be26b-143">![SineEase for different EasingMode values](../../../../docs/framework/wpf/graphics-multimedia/media/sineease-graph.png "SineEase_Graph")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be26b-144">사용할 수 있습니다 <xref:System.Windows.Media.Animation.PowerEase> 동일한 동작을 만들려면 <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, 및 <xref:System.Windows.Media.Animation.QuinticEase> 를 사용 하 여는 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-144">You can use <xref:System.Windows.Media.Animation.PowerEase> to create the same behavior as <xref:System.Windows.Media.Animation.CubicEase>, <xref:System.Windows.Media.Animation.QuadraticEase>, <xref:System.Windows.Media.Animation.QuarticEase>, and <xref:System.Windows.Media.Animation.QuinticEase> by using the <xref:System.Windows.Media.Animation.PowerEase.Power%2A> property.</span></span> <span data-ttu-id="be26b-145">예를 들어, 사용 하려는 경우 <xref:System.Windows.Media.Animation.PowerEase> 를 대체할 <xref:System.Windows.Media.Animation.CubicEase>, 지정는 <xref:System.Windows.Media.Animation.PowerEase.Power%2A> 값 3입니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-145">For example, if you want to use <xref:System.Windows.Media.Animation.PowerEase> to substitute for <xref:System.Windows.Media.Animation.CubicEase>, specify a <xref:System.Windows.Media.Animation.PowerEase.Power%2A> value of 3.</span></span>  
  
 <span data-ttu-id="be26b-146">실행 시간에 포함 된 감속/가속 함수를 사용 하는 것 외에도 상속 하 여 사용자 지정 감속/가속 함수를 만들 수 있습니다 <xref:System.Windows.Media.Animation.EasingFunctionBase>합니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-146">In addition to using the easing functions included in the run-time, you can create your own custom easing functions by inheriting from <xref:System.Windows.Media.Animation.EasingFunctionBase>.</span></span> <span data-ttu-id="be26b-147">다음 예제에서는 단일 사용자 지정 감속/가속 함수를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be26b-147">The following example demonstrates how to create a simple custom easing function.</span></span> <span data-ttu-id="be26b-148">감속/가속 함수를 재정의 하 여 작동 하는 방법에 대 한 고유한 수학적 논리를 추가할 수는 <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="be26b-148">You can add your own mathematical logic for how the easing function behaves by overriding the <xref:System.Windows.Media.Animation.EasingFunctionBase.EaseInCore%2A> method.</span></span>  
  
 [<span data-ttu-id="be26b-149">이 샘플 실행</span><span class="sxs-lookup"><span data-stu-id="be26b-149">Run this sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=139798&sref=CustomEasingFunction)  
  
 [!code-csharp[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/customlog10easingfunction.cs#customeasingfunction)]
 [!code-vb[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/customeasingfunction/visualbasic/customlog10easingfunction.vb#customeasingfunction)]
 [!code-xaml[CustomEasingFunction#CustomEasingFunction](../../../../samples/snippets/csharp/VS_Snippets_Wpf/customeasingfunction/csharp/window1.xaml#customeasingfunction)]
