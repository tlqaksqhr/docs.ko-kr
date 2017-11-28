---
title: "성능 최적화: 레이아웃 및 디자인"
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
- layout [WPF], optimizing performance
- design considerations [WPF]
- layout pass [WPF]
ms.assetid: 005f4cda-a849-448b-916b-38d14d9a96fe
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 13763e0487314fdbe7ab6fcb8b7b8711715e7a6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="optimizing-performance-layout-and-design"></a><span data-ttu-id="ab043-102">성능 최적화: 레이아웃 및 디자인</span><span class="sxs-lookup"><span data-stu-id="ab043-102">Optimizing Performance: Layout and Design</span></span>
<span data-ttu-id="ab043-103">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 디자인 작업은 레이아웃 계산과 개체 참조의 유효성 검사 과정에서 불필요한 오버헤드를 초래하여 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-103">The design of your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application can impact its performance by creating unnecessary overhead in calculating layout and validating object references.</span></span> <span data-ttu-id="ab043-104">또한 개체 생성 작업은 특히 런타임에 응용 프로그램의 성능 특성에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-104">The construction of objects, particularly at run time, can affect the performance characteristics of your application.</span></span>  
  
 <span data-ttu-id="ab043-105">이 항목에서는 이러한 영역에서 성능과 관련된 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-105">This topic provides performance recommendations in these areas.</span></span>  
  
## <a name="layout"></a><span data-ttu-id="ab043-106">레이아웃</span><span class="sxs-lookup"><span data-stu-id="ab043-106">Layout</span></span>  
 <span data-ttu-id="ab043-107">측정 및의 멤버 정렬의 프로세스를 설명 하는 "레이아웃 단계" 라는 용어는 <xref:System.Windows.Controls.Panel>-파생 다음 화면에 그리는 및 자식의 개체의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-107">The term "layout pass" describes the process of measuring and arranging the members of a <xref:System.Windows.Controls.Panel>-derived object's collection of children, and then drawing them onscreen.</span></span> <span data-ttu-id="ab043-108">레이아웃 단계는 많은 계산이 요구되는 프로세스이며 컬렉션의 자식 수가 많을수록 더 많은 계산이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-108">The layout pass is a mathematically-intensive process—the larger the number of children in the collection, the greater the number of calculations required.</span></span> <span data-ttu-id="ab043-109">예를 들어 자식 때마다 <xref:System.Windows.UIElement> 컬렉션에 개체 변경의 위치, 레이아웃 시스템에서 새로운 패스를 트리거될 수에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-109">For example, each time a child <xref:System.Windows.UIElement> object in the collection changes its position, it has the potential to trigger a new pass by the layout system.</span></span> <span data-ttu-id="ab043-110">개체 특성과 레이아웃 동작 간의 긴밀한 관계로 인해 레이아웃 시스템을 호출할 수 있는 이벤트의 형식을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-110">Because of the close relationship between object characteristics and layout behavior, it's important to understand the type of events that can invoke the layout system.</span></span> <span data-ttu-id="ab043-111">레이아웃 단계의 불필요한 호출을 되도록 많이 줄이면 응용 프로그램의 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-111">Your application will perform better by reducing as much as possible any unnecessary invocations of the layout pass.</span></span>  
  
 <span data-ttu-id="ab043-112">레이아웃 시스템은 컬렉션의 각 자식 멤버에 대해 두 개의 단계인 측정 단계 및 정렬 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-112">The layout system completes two passes for each child member in a collection: a measure pass, and an arrange pass.</span></span> <span data-ttu-id="ab043-113">각 자식 개체의 재정의 된 구현에 제공 된 <xref:System.Windows.UIElement.Measure%2A> 및 <xref:System.Windows.UIElement.Arrange%2A> 자체 특정 레이아웃 동작을 제공 하기 위해 메서드.</span><span class="sxs-lookup"><span data-stu-id="ab043-113">Each child object provides its own overridden implementation of the <xref:System.Windows.UIElement.Measure%2A> and <xref:System.Windows.UIElement.Arrange%2A> methods in order to provide its own specific layout behavior.</span></span> <span data-ttu-id="ab043-114">가장 간단한 레이아웃은 화면에서 크기 조정, 배치 및 그리기를 수행할 요소가 되는 재귀 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-114">At its simplest, layout is a recursive system that leads to an element being sized, positioned, and drawn onscreen.</span></span>  
  
-   <span data-ttu-id="ab043-115">자식 <xref:System.Windows.UIElement> 먼저 핵심 속성이 측정 하 여 개체 레이아웃 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-115">A child <xref:System.Windows.UIElement> object begins the layout process by first having its core properties measured.</span></span>  
  
-   <span data-ttu-id="ab043-116">개체의 <xref:System.Windows.FrameworkElement> 크기와 같은 관련 된 속성을 <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, 및 <xref:System.Windows.FrameworkElement.Margin%2A>, 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-116">The object's <xref:System.Windows.FrameworkElement> properties that are related to size, such as <xref:System.Windows.FrameworkElement.Width%2A>, <xref:System.Windows.FrameworkElement.Height%2A>, and <xref:System.Windows.FrameworkElement.Margin%2A>, are evaluated.</span></span>  
  
-   <span data-ttu-id="ab043-117"><xref:System.Windows.Controls.Panel>-와 같은 특정 논리가 적용 되며는 <xref:System.Windows.Controls.DockPanel.Dock%2A> 속성의는 <xref:System.Windows.Controls.DockPanel>, 또는 <xref:System.Windows.Controls.StackPanel.Orientation%2A> 의 속성은 <xref:System.Windows.Controls.StackPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-117"><xref:System.Windows.Controls.Panel>-specific logic is applied, such as the <xref:System.Windows.Controls.DockPanel.Dock%2A> property of the <xref:System.Windows.Controls.DockPanel>, or the <xref:System.Windows.Controls.StackPanel.Orientation%2A> property of the <xref:System.Windows.Controls.StackPanel>.</span></span>  
  
-   <span data-ttu-id="ab043-118">모든 자식 개체가 측정된 후 콘텐츠가 정렬 또는 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-118">Content is arranged, or positioned, after all child objects have been measured.</span></span>  
  
-   <span data-ttu-id="ab043-119">자식 개체의 컬렉션이 화면에 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-119">The collection of child objects is drawn to the screen.</span></span>  
  
 <span data-ttu-id="ab043-120">다음 작업 중 하나가 발생할 경우 레이아웃 단계 프로세스가 다시 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-120">The layout pass process is invoked again if any of the following actions occur:</span></span>  
  
-   <span data-ttu-id="ab043-121">자식 개체가 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-121">A child object is added to the collection.</span></span>  
  
-   <span data-ttu-id="ab043-122">A <xref:System.Windows.FrameworkElement.LayoutTransform%2A> 자식 개체에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-122">A <xref:System.Windows.FrameworkElement.LayoutTransform%2A> is applied to the child object.</span></span>  
  
-   <span data-ttu-id="ab043-123"><xref:System.Windows.UIElement.UpdateLayout%2A> 자식 개체에 대 한 메서드 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-123">The <xref:System.Windows.UIElement.UpdateLayout%2A> method is called for the child object.</span></span>  
  
-   <span data-ttu-id="ab043-124">측정 또는 정렬 단계에 영향을 주는 메타데이터로 표시된 종속성 속성의 값에 변경이 발생할 경우</span><span class="sxs-lookup"><span data-stu-id="ab043-124">When a change occurs to the value of a dependency property that is marked with metadata affecting the measure or arrange passes.</span></span>  
  
### <a name="use-the-most-efficient-panel-where-possible"></a><span data-ttu-id="ab043-125">가능한 경우 가장 효율적인 패널 사용</span><span class="sxs-lookup"><span data-stu-id="ab043-125">Use the Most Efficient Panel where Possible</span></span>  
 <span data-ttu-id="ab043-126">레이아웃 프로세스의 복잡성은 레이아웃 동작에 따라 직접는 <xref:System.Windows.Controls.Panel>-사용 하는 요소를 파생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-126">The complexity of the layout process is directly based on the layout behavior of the <xref:System.Windows.Controls.Panel>-derived elements you use.</span></span> <span data-ttu-id="ab043-127">예를 들어는 <xref:System.Windows.Controls.Grid> 또는 <xref:System.Windows.Controls.StackPanel> 보다 훨씬 더 많은 기능을 제공 하는 컨트롤을 <xref:System.Windows.Controls.Canvas> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-127">For example, a <xref:System.Windows.Controls.Grid> or <xref:System.Windows.Controls.StackPanel> control provides much more functionality than a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="ab043-128">기능이 많이 제공될수록 성능 비용이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-128">The price for this greater increase in functionality is a greater increase in performance costs.</span></span> <span data-ttu-id="ab043-129">그러나는 기능이 필요 하지 않은 경우 하 한 <xref:System.Windows.Controls.Grid> 컨트롤에서 제공와 같은 보다 저렴 한 비용 대안을 사용 해야는 <xref:System.Windows.Controls.Canvas> 또는 사용자 지정 패널입니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-129">However, if you do not require the functionality that a <xref:System.Windows.Controls.Grid> control provides, you should use the less costly alternatives, such as a <xref:System.Windows.Controls.Canvas> or a custom panel.</span></span>  
  
 <span data-ttu-id="ab043-130">자세한 내용은 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab043-130">For more information, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span>  
  
### <a name="update-rather-than-replace-a-rendertransform"></a><span data-ttu-id="ab043-131">RenderTransform을 대체하는 대신 업데이트</span><span class="sxs-lookup"><span data-stu-id="ab043-131">Update Rather than Replace a RenderTransform</span></span>  
 <span data-ttu-id="ab043-132">업데이트할 수 있습니다는 <xref:System.Windows.Media.Transform> 의 값으로 대체 하는 대신는 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-132">You may be able to update a <xref:System.Windows.Media.Transform> rather than replacing it as the value of a <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="ab043-133">애니메이션과 관련된 시나리오가 특히 이러한 경우에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-133">This is particularly true in scenarios that involve animation.</span></span> <span data-ttu-id="ab043-134">기존 업데이트 하 여 <xref:System.Windows.Media.Transform>, 불필요 한 레이아웃 계산이 시작 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-134">By updating an existing <xref:System.Windows.Media.Transform>, you avoid initiating an unnecessary layout calculation.</span></span>  
  
### <a name="build-your-tree-top-down"></a><span data-ttu-id="ab043-135">하향식 트리 빌드</span><span class="sxs-lookup"><span data-stu-id="ab043-135">Build Your Tree Top-Down</span></span>  
 <span data-ttu-id="ab043-136">논리적 트리에서 노드가 추가 또는 제거될 경우 노드의 부모 및 모든 자식에서 속성 무효화가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-136">When a node is added or removed from the logical tree, property invalidations are raised on the node's parent and all its children.</span></span> <span data-ttu-id="ab043-137">결과적으로 이미 유효성이 검사된 노드에서 불필요한 무효화의 비용을 방지하려면 항상 하향식 생성 패턴을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-137">As a result, a top-down construction pattern should always be followed to avoid the cost of unnecessary invalidations on nodes that have already been validated.</span></span> <span data-ttu-id="ab043-138">다음 표에서 하향식 및 상향식의 트리를 단일 150 수준의 트리를 작성할 실행 속도 차이 보여 줍니다. <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Controls.DockPanel> 각 수준에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-138">The following table shows the difference in execution speed between building a tree top-down versus bottom-up, where the tree is 150 levels deep with a single <xref:System.Windows.Controls.TextBlock> and <xref:System.Windows.Controls.DockPanel> at each level.</span></span>  
  
|<span data-ttu-id="ab043-139">**작업**</span><span class="sxs-lookup"><span data-stu-id="ab043-139">**Action**</span></span>|<span data-ttu-id="ab043-140">**트리 빌드(ms)**</span><span class="sxs-lookup"><span data-stu-id="ab043-140">**Tree building (in ms)**</span></span>|<span data-ttu-id="ab043-141">**렌더링—트리 빌드 포함(ms)**</span><span class="sxs-lookup"><span data-stu-id="ab043-141">**Render—includes tree building (in ms)**</span></span>|  
|----------------|---------------------------------|-------------------------------------------------|  
|<span data-ttu-id="ab043-142">상향식</span><span class="sxs-lookup"><span data-stu-id="ab043-142">Bottom-up</span></span>|<span data-ttu-id="ab043-143">366</span><span class="sxs-lookup"><span data-stu-id="ab043-143">366</span></span>|<span data-ttu-id="ab043-144">454</span><span class="sxs-lookup"><span data-stu-id="ab043-144">454</span></span>|  
|<span data-ttu-id="ab043-145">하향식</span><span class="sxs-lookup"><span data-stu-id="ab043-145">Top-down</span></span>|<span data-ttu-id="ab043-146">11</span><span class="sxs-lookup"><span data-stu-id="ab043-146">11</span></span>|<span data-ttu-id="ab043-147">96</span><span class="sxs-lookup"><span data-stu-id="ab043-147">96</span></span>|  
  
 <span data-ttu-id="ab043-148">다음 코드 예제에서는 하향식 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab043-148">The following code example demonstrates how to create a tree top down.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet1)]
 [!code-vb[Performance#PerformanceSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet1)]  
  
 <span data-ttu-id="ab043-149">논리적 트리에 대한 자세한 내용은 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab043-149">For more information on the logical tree, see [Trees in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab043-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab043-150">See Also</span></span>  
 [<span data-ttu-id="ab043-151">WPF 응용 프로그램 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="ab043-151">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [<span data-ttu-id="ab043-152">응용 프로그램 성능 계획</span><span class="sxs-lookup"><span data-stu-id="ab043-152">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [<span data-ttu-id="ab043-153">하드웨어 이용</span><span class="sxs-lookup"><span data-stu-id="ab043-153">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [<span data-ttu-id="ab043-154">2차원 그래픽 및 이미징</span><span class="sxs-lookup"><span data-stu-id="ab043-154">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="ab043-155">개체 동작</span><span class="sxs-lookup"><span data-stu-id="ab043-155">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [<span data-ttu-id="ab043-156">응용 프로그램 리소스</span><span class="sxs-lookup"><span data-stu-id="ab043-156">Application Resources</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [<span data-ttu-id="ab043-157">Text</span><span class="sxs-lookup"><span data-stu-id="ab043-157">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [<span data-ttu-id="ab043-158">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="ab043-158">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [<span data-ttu-id="ab043-159">기타 성능 권장 사항</span><span class="sxs-lookup"><span data-stu-id="ab043-159">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)  
 [<span data-ttu-id="ab043-160">레이아웃</span><span class="sxs-lookup"><span data-stu-id="ab043-160">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)
