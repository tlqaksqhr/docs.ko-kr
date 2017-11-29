---
title: "방법: From, To 및 By를 사용하여 애니메이션 제어"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aab775ab1c2f55d79da0773f81c006015c349f8b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a><span data-ttu-id="c6169-102">방법: From, To 및 By를 사용하여 애니메이션 제어</span><span class="sxs-lookup"><span data-stu-id="c6169-102">How to: Control an Animation using From, To, and By</span></span>
<span data-ttu-id="c6169-103">"From/하/By" 또는 "기본 애니메이션" 두 대상 값 사이의 전환을 만듭니다 (참조 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) 다양 한 유형의 애니메이션에 대 한 소개).</span><span class="sxs-lookup"><span data-stu-id="c6169-103">A "From/To/By" or "basic animation" creates a transition between two target values (see [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) for an introduction to different types of animations).</span></span> <span data-ttu-id="c6169-104">기본 애니메이션의 대상 값을 설정 하려면 해당 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-104">To set the target values of a basic animation, use its <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties.</span></span>  <span data-ttu-id="c6169-105">다음 표에서 요약 방법을 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성을 함께 사용할 수 있습니다. 또는 개별적으로 애니메이션의 대상 값을 확인 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-105">The following table summarizes how the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties may be used together or separately to determine an animation's target values.</span></span>  
  
|<span data-ttu-id="c6169-106">지정된 속성</span><span class="sxs-lookup"><span data-stu-id="c6169-106">Properties specified</span></span>|<span data-ttu-id="c6169-107">결과 동작</span><span class="sxs-lookup"><span data-stu-id="c6169-107">Resulting behavior</span></span>|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|<span data-ttu-id="c6169-108">에 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션 효과 줄 속성의 기준 값 또는 이전 애니메이션 속성의 구성 방식에 따라 값을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-108">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the base value of the property being animated or to a previous animation's output value, depending on how the previous animation is configured.</span></span>|  
|<span data-ttu-id="c6169-109"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A></span><span class="sxs-lookup"><span data-stu-id="c6169-109"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A></span></span>|<span data-ttu-id="c6169-110">에 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-110">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property.</span></span>|  
|<span data-ttu-id="c6169-111"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A></span><span class="sxs-lookup"><span data-stu-id="c6169-111"><xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A></span></span>|<span data-ttu-id="c6169-112">에 지정 된 값은 애니메이션이 적용 된 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 속성에 의해 지정 된 값을는 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-112">The animation progresses from the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> property to the value specified by the sum of the <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> properties.</span></span>|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|<span data-ttu-id="c6169-113">속성의 기준 값에서 진행 되는 애니메이션 또는 이전 애니메이션의 출력 값으로 지정 된 값으로는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-113">The animation progresses from the animated property's base value or a previous animation's output value to the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property.</span></span>|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|<span data-ttu-id="c6169-114">애니메이션 효과 줄 속성의 기본값은 애니메이션이 적용 또는 이전 애니메이션의 출력에 지정 된 값과 값의 합계를 구할 값은 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-114">The animation progresses from the base value of the property being animated or a previous animation's output value to the sum of that value and the value specified by the <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> property.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c6169-115">둘 다 설정 하지 않으면는 <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> 속성 및 <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> 동일한 애니메이션 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-115">Do not set both the <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> property and the <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> property on the same animation.</span></span>  
  
 <span data-ttu-id="c6169-116">다른 보간 방법을 사용하거나 둘 이상의 대상 값 사이에 애니메이션 효과를 주려면 키 프레임 애니메이션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-116">To use other interpolation methods or animate between more than two target values, use a key frame animation.</span></span> <span data-ttu-id="c6169-117">참조 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) 자세한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-117">See [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) for more information.</span></span>  
  
 <span data-ttu-id="c6169-118">단일 속성에 여러 애니메이션을 적용 하는 방법에 대 한 내용은 [키 프레임 애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-118">For information about applying multiple animations to a single property, see [Key-Frame Animations Overview](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).</span></span>  
  
 <span data-ttu-id="c6169-119">다음 예제에서는 다양 한 설정의 효과 보여 줍니다. <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, 및 <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> 애니메이션 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6169-119">The example below shows the different effects of setting <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, and <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> properties on animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6169-120">예제</span><span class="sxs-lookup"><span data-stu-id="c6169-120">Example</span></span>  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c6169-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6169-121">See Also</span></span>  
 [<span data-ttu-id="c6169-122">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="c6169-122">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="c6169-123">키 프레임 애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="c6169-123">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="c6169-124">From, To 및 By 애니메이션 대상 값 샘플</span><span class="sxs-lookup"><span data-stu-id="c6169-124">From, To, and By Animation Target Values Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159988)
