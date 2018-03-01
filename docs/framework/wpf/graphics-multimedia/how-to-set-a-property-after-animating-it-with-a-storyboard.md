---
title: "방법: Storyboard를 사용하여 애니메이션 효과를 적용한 후 속성 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], changing property values after
ms.assetid: 79466556-4dbf-40bd-9c1e-a77613b07077
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3ffc534549f5b114a07f09326be72c1968d178a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-property-after-animating-it-with-a-storyboard"></a><span data-ttu-id="cdd7d-102">방법: Storyboard를 사용하여 애니메이션 효과를 적용한 후 속성 설정</span><span class="sxs-lookup"><span data-stu-id="cdd7d-102">How to: Set a Property After Animating It with a Storyboard</span></span>
<span data-ttu-id="cdd7d-103">일부 경우 애니메이션이 적용 된 후에 속성의 값을 변경할 수 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-103">In some cases, it might appear that you can't change the value of a property after it has been animated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdd7d-104">예</span><span class="sxs-lookup"><span data-stu-id="cdd7d-104">Example</span></span>  
 <span data-ttu-id="cdd7d-105">다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션의 색을 적용 하는 데 사용 되는 <xref:System.Windows.Media.SolidColorBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> is used to animate the color of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="cdd7d-106">스토리 보드는 단추를 클릭할 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-106">The storyboard is triggered when the button is clicked.</span></span> <span data-ttu-id="cdd7d-107"><xref:System.Windows.Media.Animation.Timeline.Completed> 는 프로그램이 알림을 받을 수 있도록 이벤트를 처리 때는 <xref:System.Windows.Media.Animation.ColorAnimation> 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-107">The <xref:System.Windows.Media.Animation.Timeline.Completed> event is handled so that the program is notified when the <xref:System.Windows.Media.Animation.ColorAnimation> completes.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton1Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton1declaration)]  
  
## <a name="example"></a><span data-ttu-id="cdd7d-108">예</span><span class="sxs-lookup"><span data-stu-id="cdd7d-108">Example</span></span>  
 <span data-ttu-id="cdd7d-109">이후에 <xref:System.Windows.Media.Animation.ColorAnimation> 완료 되 면 브러시의 색을 파란색을 변경 하려면 프로그램 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-109">After the <xref:System.Windows.Media.Animation.ColorAnimation> completes, the program attempts to change the brush's color to blue.</span></span>  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton1handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton1Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton1handler)]  
  
 <span data-ttu-id="cdd7d-110">이전 코드가 어떤 작업을 보이지 않으면: 번째 노란색, 브러시 남아 제공한는 <xref:System.Windows.Media.Animation.ColorAnimation> 작업도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-110">The previous code doesn't appear to do anything: the brush remains yellow, which is the value supplied by the <xref:System.Windows.Media.Animation.ColorAnimation> that animated the brush.</span></span> <span data-ttu-id="cdd7d-111">기본 속성 값 (기본값)은 실제로 파란색으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-111">The underlying property value (the base value) is actually changed to blue.</span></span> <span data-ttu-id="cdd7d-112">그러나 유효 또는 현재, 값은 노란색 때문에 <xref:System.Windows.Media.Animation.ColorAnimation> 여전히 기준 값을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-112">However, the effective, or current, value remains yellow because the <xref:System.Windows.Media.Animation.ColorAnimation> is still overriding the base value.</span></span> <span data-ttu-id="cdd7d-113">유효한 값을 다시 되도록 기준 값을 원하는 경우 속성에 영향을 주지 애니메이션을 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-113">If you want the base value to become the effective value again, you must stop the animation from influencing the property.</span></span> <span data-ttu-id="cdd7d-114">스토리 보드 애니메이션이 작업을 수행 하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-114">There are three ways to do this with storyboard animations:</span></span>  
  
-   <span data-ttu-id="cdd7d-115">애니메이션의 설정 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성을<xref:System.Windows.Media.Animation.FillBehavior.Stop></span><span class="sxs-lookup"><span data-stu-id="cdd7d-115">Set the animation's <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property to <xref:System.Windows.Media.Animation.FillBehavior.Stop></span></span>  
  
-   <span data-ttu-id="cdd7d-116">전체 스토리 보드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-116">Remove the entire Storyboard.</span></span>  
  
-   <span data-ttu-id="cdd7d-117">각 속성에서 애니메이션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-117">Remove the animation from the individual property.</span></span>  
  
## <a name="set-the-animations-fillbehavior-property-to-stop"></a><span data-ttu-id="cdd7d-118">Stop으로 애니메이션의 FillBehavior 속성 설정</span><span class="sxs-lookup"><span data-stu-id="cdd7d-118">Set the animation's FillBehavior property to Stop</span></span>  
 <span data-ttu-id="cdd7d-119">설정 하 여 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 를 <xref:System.Windows.Media.Animation.FillBehavior.Stop>을 활성 기간의 끝에 도달한 후 대상 속성에 영향을 주는 중지 된 애니메이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-119">By setting <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, you tell the animation to stop affecting its target property after it reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton2Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton2declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton2handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton2Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton2handler)]  
  
## <a name="remove-the-entire-storyboard"></a><span data-ttu-id="cdd7d-120">전체 스토리 보드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-120">Remove the entire storyboard</span></span>  
 <span data-ttu-id="cdd7d-121">사용 하 여 한 <xref:System.Windows.Media.Animation.RemoveStoryboard> 트리거 또는 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> 메서드를 스토리 보드 애니메이션의 대상 속성에 영향을 중지 하 게 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-121">By using a <xref:System.Windows.Media.Animation.RemoveStoryboard> trigger or the <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType> method, you tell the storyboard animations to stop affecting their target properties.</span></span> <span data-ttu-id="cdd7d-122">이 접근 방식 및 설정 간의 차이 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 스토리 보드를 제거할 수 있습니다에 동안 언제 든 지는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성에만 효과가 애니메이션 활성 기간의 끝에 도달 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-122">The difference between this approach and setting the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property is that you can remove the storyboard at anytime, while the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property only has an effect when the animation reaches the end of its active period.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton3Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton3declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton3handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton3Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton3handler)]  
  
## <a name="remove-an-animation-from-an-individual-property"></a><span data-ttu-id="cdd7d-123">개별 속성에서 애니메이션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-123">Remove an animation from an individual property</span></span>  
 <span data-ttu-id="cdd7d-124">속성에 영향을 미치지 애니메이션을 중지 하는 다른 방법을 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> 애니메이션 효과가 적용 되는 개체의 메서드.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-124">Another technique to stop an animation from affecting a property is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%28System.Windows.DependencyProperty%2CSystem.Windows.Media.Animation.AnimationTimeline%29> method of the object being animated.</span></span> <span data-ttu-id="cdd7d-125">첫 번째 매개 변수로 애니메이션 효과가 적용 되는 속성을 지정 하 고 `null` 를 두 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-125">Specify the property being animated as the first parameter and `null` as the second.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#GraphicsMMButton4Declaration](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml#graphicsmmbutton4declaration)]  
  
 [!code-csharp[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AnimateThenSetPropertyExample.xaml.cs#graphicsmmbutton4handler)]
 [!code-vb[timingbehaviors_snip#GraphicsMMButton4Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/animatethensetpropertyexample.xaml.vb#graphicsmmbutton4handler)]  
  
 <span data-ttu-id="cdd7d-126">이 기술은 스토리 보드 비 애니메이션에 대 한 에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="cdd7d-126">This technique also works for non-storyboard animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdd7d-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cdd7d-127">See Also</span></span>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.Storyboard.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Media.Animation.RemoveStoryboard>  
 [<span data-ttu-id="cdd7d-128">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="cdd7d-128">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="cdd7d-129">속성 애니메이션 기술 개요</span><span class="sxs-lookup"><span data-stu-id="cdd7d-129">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)
