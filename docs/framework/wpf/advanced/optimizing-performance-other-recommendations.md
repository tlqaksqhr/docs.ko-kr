---
title: "성능 최적화: 기타 권장 사항"
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
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e45296befd51af5e4b03f123241efba030fd3754
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-other-recommendations"></a><span data-ttu-id="703c9-102">성능 최적화: 기타 권장 사항</span><span class="sxs-lookup"><span data-stu-id="703c9-102">Optimizing Performance: Other Recommendations</span></span>
<a name="introduction"></a> <span data-ttu-id="703c9-103">이 항목에서는 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md) 섹션의 항목 내용에 추가되는 성능 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-103">This topic provides performance recommendations in addition to the ones covered by the topics in the [Optimizing WPF Application Performance](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md) section.</span></span>  
  
 <span data-ttu-id="703c9-104">이 항목에는 다음과 같은 단원이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-104">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="703c9-105">브러시의 불투명도와 요소의 불투명도 비교</span><span class="sxs-lookup"><span data-stu-id="703c9-105">Opacity on Brushes Versus Opacity on Elements</span></span>](#Opacity)  
  
-   [<span data-ttu-id="703c9-106">개체 탐색</span><span class="sxs-lookup"><span data-stu-id="703c9-106">Navigation to Object</span></span>](#Navigation_Objects)  
  
-   [<span data-ttu-id="703c9-107">대형 3D 화면에서의 적중 횟수 테스트</span><span class="sxs-lookup"><span data-stu-id="703c9-107">Hit Testing on Large 3D Surfaces</span></span>](#Hit_Testing)  
  
-   [<span data-ttu-id="703c9-108">CompositionTarget.Rendering 이벤트</span><span class="sxs-lookup"><span data-stu-id="703c9-108">CompositionTarget.Rendering Event</span></span>](#CompositionTarget_Rendering_Event)  
  
-   [<span data-ttu-id="703c9-109">ScrollBarVisibility=Auto 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="703c9-109">Avoid Using ScrollBarVisibility=Auto</span></span>](#Avoid_Using_ScrollBarVisibility)  
  
-   [<span data-ttu-id="703c9-110">시작 시간을 줄이도록 글꼴 캐시 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="703c9-110">Configure Font Cache Service to Reduce Start-up Time</span></span>](#FontCache)  
  
<a name="Opacity"></a>   
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a><span data-ttu-id="703c9-111">브러시의 불투명도와 요소의 불투명도 비교</span><span class="sxs-lookup"><span data-stu-id="703c9-111">Opacity on Brushes Versus Opacity on Elements</span></span>  
 <span data-ttu-id="703c9-112">사용 하는 경우는 <xref:System.Windows.Media.Brush> 설정 하는 <xref:System.Windows.Shapes.Shape.Fill%2A> 또는 <xref:System.Windows.Shapes.Shape.Stroke%2A> 요소의 하는 것이 설정의 <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> 는 설정 하는 대신 값 요소의 <xref:System.Windows.UIElement.Opacity%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-112">When you use a <xref:System.Windows.Media.Brush> to set the <xref:System.Windows.Shapes.Shape.Fill%2A> or <xref:System.Windows.Shapes.Shape.Stroke%2A> of an element, it is better to set the <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> value rather than the setting the element's <xref:System.Windows.UIElement.Opacity%2A> property.</span></span> <span data-ttu-id="703c9-113">요소의 수정 <xref:System.Windows.UIElement.Opacity%2A> 속성으로 지정 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 임시 화면을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-113">Modifying an element's <xref:System.Windows.UIElement.Opacity%2A> property can cause [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to create a temporary surface.</span></span>  
  
<a name="Navigation_Objects"></a>   
## <a name="navigation-to-object"></a><span data-ttu-id="703c9-114">개체 탐색</span><span class="sxs-lookup"><span data-stu-id="703c9-114">Navigation to Object</span></span>  
 <span data-ttu-id="703c9-115"><xref:System.Windows.Navigation.NavigationWindow> 개체에서 파생 <xref:System.Windows.Window> 을 집계 하 여 주로 콘텐츠 탐색 지원을 사용 하도록 확장 <xref:System.Windows.Navigation.NavigationService> 및 저널 합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-115">The <xref:System.Windows.Navigation.NavigationWindow> object derives from <xref:System.Windows.Window> and extends it with content navigation support, primarily by aggregating <xref:System.Windows.Navigation.NavigationService> and the journal.</span></span> <span data-ttu-id="703c9-116">클라이언트 영역을 업데이트할 수 있습니다 <xref:System.Windows.Navigation.NavigationWindow> 지정 하 여 한 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 또는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-116">You can update the client area of <xref:System.Windows.Navigation.NavigationWindow> by specifying either a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] or an object.</span></span> <span data-ttu-id="703c9-117">다음 샘플에서는 이러한 두 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-117">The following sample shows both methods:</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 <span data-ttu-id="703c9-118">각 <xref:System.Windows.Navigation.NavigationWindow> 개체에 해당 창에서 사용자의 탐색 기록을 기록 하는 저널 합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-118">Each <xref:System.Windows.Navigation.NavigationWindow> object has a journal that records the user's navigation history in that window.</span></span> <span data-ttu-id="703c9-119">저널의 목적 중 하나는 사용자가 단계를 다시 수행할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-119">One of the purposes of the journal is to allow users to retrace their steps.</span></span>  
  
 <span data-ttu-id="703c9-120">[!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]를 사용하여 탐색하면 저널에서는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] 참조만 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-120">When you navigate using a [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], the journal stores only the [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] reference.</span></span> <span data-ttu-id="703c9-121">이는 페이지를 다시 방문할 때마다 동적으로 다시 구성하기 때문에 페이지가 복잡할 경우 많은 시간이 걸릴 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-121">This means that each time you revisit the page, it is dynamically reconstructed, which may be time consuming depending on the complexity of the page.</span></span> <span data-ttu-id="703c9-122">이 경우 저널 저장 비용은 낮지만 페이지를 다시 구성하는 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-122">In this case, the journal storage cost is low, but the time to reconstitute the page is potentially high.</span></span>  
  
 <span data-ttu-id="703c9-123">개체를 사용하여 탐색하면 저널에서 개체의 전체 시각적 트리를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-123">When you navigate using an object, the journal stores the entire visual tree of the object.</span></span> <span data-ttu-id="703c9-124">즉, 페이지를 다시 방문할 때마다 페이지를 다시 구성하지 않고 바로 렌더링합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-124">This means that each time you revisit the page, it renders immediately without having to be reconstructed.</span></span> <span data-ttu-id="703c9-125">이 경우 저널 저장 비용은 높지만 페이지를 다시 구성하는 시간이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-125">In this case, the journal storage cost is high, but the time to reconstitute the page is low.</span></span>  
  
 <span data-ttu-id="703c9-126">사용 하는 경우는 <xref:System.Windows.Navigation.NavigationWindow> 개체 저널링 지원 응용 프로그램의 성능에 미치는 영향에 점을 명심 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-126">When you use the <xref:System.Windows.Navigation.NavigationWindow> object, you will need to keep in mind how the journaling support impacts your application's performance.</span></span> <span data-ttu-id="703c9-127">자세한 내용은 [탐색 개요](../../../../docs/framework/wpf/app-development/navigation-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="703c9-127">For more information, see [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span>  
  
<a name="Hit_Testing"></a>   
## <a name="hit-testing-on-large-3d-surfaces"></a><span data-ttu-id="703c9-128">대형 3D 화면에서의 적중 횟수 테스트</span><span class="sxs-lookup"><span data-stu-id="703c9-128">Hit Testing on Large 3D Surfaces</span></span>  
 <span data-ttu-id="703c9-129">대형 3D 화면에서의 적중 횟수 테스트는 CPU 사용 면으로 볼 때 성능에 영향을 미치는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-129">Hit testing on large 3D surfaces is a very performance intensive operation in terms of CPU consumption.</span></span> <span data-ttu-id="703c9-130">3D 화면에 애니메이션 효과를 주는 경우 특히 더 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-130">This is especially true when the 3D surface is animating.</span></span> <span data-ttu-id="703c9-131">이러한 화면에서 적중 횟수 테스트가 필요 없는 경우에는 적중 횟수 테스트를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="703c9-131">If you do not require hit testing on these surfaces, then disable hit testing.</span></span> <span data-ttu-id="703c9-132">개체에서 파생 된 <xref:System.Windows.UIElement> 수 적중 테스트를 해제할 설정 하 여는 <xref:System.Windows.UIElement.IsHitTestVisible%2A> 속성을 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-132">Objects that are derived from <xref:System.Windows.UIElement> can disable hit testing by setting the <xref:System.Windows.UIElement.IsHitTestVisible%2A> property to `false`.</span></span>  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## <a name="compositiontargetrendering-event"></a><span data-ttu-id="703c9-133">CompositionTarget.Rendering 이벤트</span><span class="sxs-lookup"><span data-stu-id="703c9-133">CompositionTarget.Rendering Event</span></span>  
 <span data-ttu-id="703c9-134"><xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> 이벤트로 인해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에 지속적으로 애니메이션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-134">The <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> event causes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to continuously animate.</span></span> <span data-ttu-id="703c9-135">이 이벤트를 사용하는 경우 기회가 될 때마다 이 이벤트를 분리하세요.</span><span class="sxs-lookup"><span data-stu-id="703c9-135">If you use this event, detach it at every opportunity.</span></span>  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## <a name="avoid-using-scrollbarvisibilityauto"></a><span data-ttu-id="703c9-136">ScrollBarVisibility=Auto 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="703c9-136">Avoid Using ScrollBarVisibility=Auto</span></span>  
 <span data-ttu-id="703c9-137">가능 하면 항상 사용 하지 않도록는 <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> 에 대 한 값은 `HorizontalScrollBarVisibility` 및 `VerticalScrollBarVisibility` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-137">Whenever possible, avoid using the <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> value for the `HorizontalScrollBarVisibility` and `VerticalScrollBarVisibility` properties.</span></span> <span data-ttu-id="703c9-138">이러한 속성에 대해 정의 된 <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>, 및 <xref:System.Windows.Controls.TextBox> 개체 및 연결된 된 속성에 대 한 다른 이름으로 <xref:System.Windows.Controls.ListBox> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-138">These properties are defined for <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>, and <xref:System.Windows.Controls.TextBox> objects, and as an attached property for the <xref:System.Windows.Controls.ListBox> object.</span></span> <span data-ttu-id="703c9-139">대신, 설정 <xref:System.Windows.Controls.ScrollBarVisibility> 를 <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, 또는 <xref:System.Windows.Controls.ScrollBarVisibility.Visible>합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-139">Instead, set <xref:System.Windows.Controls.ScrollBarVisibility> to <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, or <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.</span></span>  
  
 <span data-ttu-id="703c9-140"><xref:System.Windows.Controls.ScrollBarVisibility.Auto> 사례에 대 한 값을 사용할 공간은 제한 하 고 필요한 경우에 스크롤 막대를 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-140">The <xref:System.Windows.Controls.ScrollBarVisibility.Auto> value is intended for cases when space is limited and scrollbars should only be displayed when necessary.</span></span> <span data-ttu-id="703c9-141">예를 들어이 하 유용할 수 있습니다 <xref:System.Windows.Controls.ScrollBarVisibility> 값과 <xref:System.Windows.Controls.ListBox> 반대인 30 개의 항목이 <xref:System.Windows.Controls.TextBox> 수백 줄의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-141">For example, it may be useful to use this <xref:System.Windows.Controls.ScrollBarVisibility> value with a <xref:System.Windows.Controls.ListBox> of 30 items as opposed to a <xref:System.Windows.Controls.TextBox> with hundreds of lines of text.</span></span>  
  
<a name="FontCache"></a>   
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a><span data-ttu-id="703c9-142">시작 시간을 줄이도록 글꼴 캐시 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="703c9-142">Configure Font Cache Service to Reduce Start-up Time</span></span>  
 <span data-ttu-id="703c9-143">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 글꼴 캐시 서비스는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램 간에 글꼴 데이터를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-143">The [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Font Cache service shares font data between [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications.</span></span> <span data-ttu-id="703c9-144">서비스가 실행되고 있지 않은 경우 처음 실행하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 이 서비스가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-144">The first [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application you run starts this service if the service is not already running.</span></span> <span data-ttu-id="703c9-145">[!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]를 사용하면 “[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 글꼴 캐시 3.0.0.0” 서비스를 “수동(기본값)”에서 “자동(지연된 시작)”으로 설정하여 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램의 초기 시작 시간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="703c9-145">If you are using [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], you can set the "[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Font Cache 3.0.0.0" service from "Manual" (the default) to "Automatic (Delayed Start)" to reduce the initial start-up time of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703c9-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="703c9-146">See Also</span></span>  
 [<span data-ttu-id="703c9-147">응용 프로그램 성능 계획</span><span class="sxs-lookup"><span data-stu-id="703c9-147">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [<span data-ttu-id="703c9-148">하드웨어 이용</span><span class="sxs-lookup"><span data-stu-id="703c9-148">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [<span data-ttu-id="703c9-149">레이아웃 및 디자인</span><span class="sxs-lookup"><span data-stu-id="703c9-149">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [<span data-ttu-id="703c9-150">2차원 그래픽 및 이미징</span><span class="sxs-lookup"><span data-stu-id="703c9-150">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="703c9-151">개체 동작</span><span class="sxs-lookup"><span data-stu-id="703c9-151">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [<span data-ttu-id="703c9-152">응용 프로그램 리소스</span><span class="sxs-lookup"><span data-stu-id="703c9-152">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [<span data-ttu-id="703c9-153">텍스트</span><span class="sxs-lookup"><span data-stu-id="703c9-153">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [<span data-ttu-id="703c9-154">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="703c9-154">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [<span data-ttu-id="703c9-155">애니메이션에 대한 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="703c9-155">Animation Tips and Tricks</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)
