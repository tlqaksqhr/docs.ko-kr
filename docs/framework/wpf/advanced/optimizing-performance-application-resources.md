---
title: "성능 최적화: 응용 프로그램 리소스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0a7c9920b321f15f3f01a64fbfc80693042a025
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-application-resources"></a><span data-ttu-id="dfe6e-102">성능 최적화: 응용 프로그램 리소스</span><span class="sxs-lookup"><span data-stu-id="dfe6e-102">Optimizing Performance: Application Resources</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="dfe6e-103">비슷한 형식의 요소에서 일관성 있는 모양이 나 동작을 지원할 수 있도록 응용 프로그램 리소스를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-103"> allows you to share application resources so that you can support a consistent look or behavior across similar-typed elements.</span></span> <span data-ttu-id="dfe6e-104">이 항목에서는 몇 가지 권장 사항 수 있는이 영역에 응용 프로그램의 성능을 개선 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-104">This topic provides a few recommendations in this area that can help you improve the performance of your applications.</span></span>  
  
 <span data-ttu-id="dfe6e-105">리소스에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-105">For more information on resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
## <a name="sharing-resources"></a><span data-ttu-id="dfe6e-106">리소스 공유</span><span class="sxs-lookup"><span data-stu-id="dfe6e-106">Sharing resources</span></span>  
 <span data-ttu-id="dfe6e-107">응용 프로그램 사용자 지정 컨트롤을 사용 하 여 및에 리소스를 정의 하는 경우는 <xref:System.Windows.ResourceDictionary> (또는 XAML 리소스 노드)를 정의 하는 중 하나에 포함 된 리소스 것이 좋습니다.는 <xref:System.Windows.Application> 또는 <xref:System.Windows.Window> 수준 개체에 대 한 기본 테마에 정의할 수도 사용자 지정 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-107">If your application uses custom controls and defines resources in a <xref:System.Windows.ResourceDictionary> (or XAML Resources node), it is recommended that you either define the resources at the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or define them in the default theme for the custom controls.</span></span> <span data-ttu-id="dfe6e-108">사용자 지정 컨트롤에 리소스를 정의 <xref:System.Windows.ResourceDictionary> 해당 컨트롤의 모든 인스턴스에 대 한 성능에 영향을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-108">Defining resources in a custom control's <xref:System.Windows.ResourceDictionary> imposes a performance impact for every instance of that control.</span></span> <span data-ttu-id="dfe6e-109">예를 들어 사용자 지정 컨트롤의 여러 인스턴스 및 사용자 지정 컨트롤의 리소스 정의의 일부로 정의 된 성능이 브러시 작업을 사용 하도록 설정한 경우 응용 프로그램의 작업 집합이 크게 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-109">For example, if you have performance-intensive brush operations defined as part of the resource definition of a custom control and many instances of the custom control, the application's working set will increase significantly.</span></span>  
  
 <span data-ttu-id="dfe6e-110">예를 들어, 다음 사항을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-110">To illustrate this point, consider the following.</span></span> <span data-ttu-id="dfe6e-111">사용 하는 카드 게임을 개발 하는 경우를 가정해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-111">Let's say you are developing a card game using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="dfe6e-112">대부분의 카드 게임 52 카드와 해당 52 서로 다른 면에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-112">For most card games, you need 52 cards with 52 different faces.</span></span> <span data-ttu-id="dfe6e-113">카드 사용자 지정 컨트롤을 구현 하도록 결정 하 고 카드 사용자 지정 컨트롤의 리소스에서 (각 카드 그림을 나타냄) 52 브러시를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-113">You decide to implement a card custom control and you define 52 brushes (each representing a card face) in the resources of your card custom control.</span></span> <span data-ttu-id="dfe6e-114">주 응용 프로그램에서 처음이 카드 사용자 지정 컨트롤의 52 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-114">In your main application, you initially create 52 instances of this card custom control.</span></span> <span data-ttu-id="dfe6e-115">52 인스턴스를 생성 하는 카드 사용자 지정 컨트롤의 각 인스턴스에 <xref:System.Windows.Media.Brush> 52 * 52의 합계를 제공 하는 개체를 <xref:System.Windows.Media.Brush> 응용 프로그램의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-115">Each instance of the card custom control generates 52 instances of <xref:System.Windows.Media.Brush> objects, which gives you a total of 52 * 52 <xref:System.Windows.Media.Brush> objects in your application.</span></span> <span data-ttu-id="dfe6e-116">브러시에 카드 사용자 지정 제어 리소스를 이동 하 여는 <xref:System.Windows.Application> 또는 <xref:System.Windows.Window> 개체 수준 또는 사용자 지정 컨트롤에 대 한 기본 테마 파일에서 이제 52 브러시를 공유 하는 이후 응용 프로그램의 작업 집합을 줄이려면 52의 인스턴스에서 카드 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-116">By moving the brushes out of the card custom control resources to the <xref:System.Windows.Application> or <xref:System.Windows.Window> object level, or defining them in the default theme for the custom control, you reduce the working set of the application, since you are now sharing the 52 brushes among 52 instances of the card control.</span></span>  
  
## <a name="sharing-a-brush-without-copying"></a><span data-ttu-id="dfe6e-117">브러시를 복사 하지 않고 공유</span><span class="sxs-lookup"><span data-stu-id="dfe6e-117">Sharing a Brush without Copying</span></span>  
 <span data-ttu-id="dfe6e-118">동일한 여러 요소가 있을 경우 <xref:System.Windows.Media.Brush> 개체를 리소스로 브러시를 정의한 참조에서 브러시 인라인으로 정의 하지 않고, [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-118">If you have multiple elements using the same <xref:System.Windows.Media.Brush> object, define the brush as a resource and reference it, rather than defining the brush inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].</span></span> <span data-ttu-id="dfe6e-119">이 메서드는 하나의 인스턴스를 만들어 다시 사용에서 브러시 인라인으로 정의 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 각 요소에 대 한 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-119">This method will create one instance and reuse it, whereas defining brushes inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] creates a new instance for each element.</span></span>  
  
 <span data-ttu-id="dfe6e-120">다음 태그 샘플에는 이러한 점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-120">The following markup sample illustrates this point:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a><span data-ttu-id="dfe6e-121">가능한 경우 정적 리소스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="dfe6e-121">Use Static Resources when Possible</span></span>  
 <span data-ttu-id="dfe6e-122">정적 리소스는 이미 정의 된 리소스에 대 한 참조를 조회 하 여 모든 XAML 속성 특성에 대 한 값을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-122">A static resource provides a value for any XAML property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="dfe6e-123">해당 리소스에 대 한 조회 동작 하는 것은 컴파일 타임 조회 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-123">Lookup behavior for that resource is analogous to compile-time lookup.</span></span>  
  
 <span data-ttu-id="dfe6e-124">동적 리소스 반면에 초기 컴파일하는 동안 임시 식을 만들고 때문 요청 된 리소스 값이 개체를 생성 하기 위해 실제로 필요할 때까지 리소스에 대 한 조회를 연기 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-124">A dynamic resource, on the other hand, will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="dfe6e-125">해당 리소스에 대 한 조회 동작 하면 성능에 영향을 부과 런타임에 조회를와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-125">Lookup behavior for that resource is analogous to run-time lookup, which imposes a performance impact.</span></span> <span data-ttu-id="dfe6e-126">필요한 경우에 동적 리소스를 사용 하 여 응용 프로그램에서 가능한 경우 항상 정적 리소스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-126">Use static resources whenever possible in your application, using dynamic resources only when necessary.</span></span>  
  
 <span data-ttu-id="dfe6e-127">다음 태그 샘플 두 유형의 리소스 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dfe6e-127">The following markup sample shows the use of both types of resources:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a><span data-ttu-id="dfe6e-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfe6e-128">See Also</span></span>  
 [<span data-ttu-id="dfe6e-129">WPF 응용 프로그램 성능 최적화</span><span class="sxs-lookup"><span data-stu-id="dfe6e-129">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [<span data-ttu-id="dfe6e-130">응용 프로그램 성능 계획</span><span class="sxs-lookup"><span data-stu-id="dfe6e-130">Planning for Application Performance</span></span>](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [<span data-ttu-id="dfe6e-131">하드웨어 이용</span><span class="sxs-lookup"><span data-stu-id="dfe6e-131">Taking Advantage of Hardware</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [<span data-ttu-id="dfe6e-132">레이아웃 및 디자인</span><span class="sxs-lookup"><span data-stu-id="dfe6e-132">Layout and Design</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [<span data-ttu-id="dfe6e-133">2차원 그래픽 및 이미징</span><span class="sxs-lookup"><span data-stu-id="dfe6e-133">2D Graphics and Imaging</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [<span data-ttu-id="dfe6e-134">개체 동작</span><span class="sxs-lookup"><span data-stu-id="dfe6e-134">Object Behavior</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [<span data-ttu-id="dfe6e-135">텍스트</span><span class="sxs-lookup"><span data-stu-id="dfe6e-135">Text</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [<span data-ttu-id="dfe6e-136">데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="dfe6e-136">Data Binding</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [<span data-ttu-id="dfe6e-137">기타 성능 권장 사항</span><span class="sxs-lookup"><span data-stu-id="dfe6e-137">Other Performance Recommendations</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
