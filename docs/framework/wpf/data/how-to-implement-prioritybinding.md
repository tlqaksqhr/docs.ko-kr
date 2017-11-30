---
title: "방법: PriorityBinding 구현"
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
helpviewer_keywords: data binding [WPF], PriorityBinding class
ms.assetid: d63b65ab-b3e9-4322-9aa8-1450f8d89532
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9753462908928eaf177e100a16186826bf4828ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-prioritybinding"></a><span data-ttu-id="ea535-102">방법: PriorityBinding 구현</span><span class="sxs-lookup"><span data-stu-id="ea535-102">How to: Implement PriorityBinding</span></span>
<span data-ttu-id="ea535-103"><xref:System.Windows.Data.PriorityBinding>[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 바인딩의 목록을 지정 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-103"><xref:System.Windows.Data.PriorityBinding> in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] works by specifying a list of bindings.</span></span> <span data-ttu-id="ea535-104">바인딩 목록은 가장 낮은 우선 순위를 높은 우선 순위에서 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-104">The list of bindings is ordered from highest priority to lowest priority.</span></span> <span data-ttu-id="ea535-105">우선 순위가 높은 바인딩이 값을 반환 하는 경우 성공적으로 처리 될 때 다음는 없습니다 목록에 다른 바인딩을 처리할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-105">If the highest priority binding returns a value successfully when it is processed then there is never a need to process the other bindings in the list.</span></span> <span data-ttu-id="ea535-106">우선 순위가 높은 바인딩이 평가할 오랜 시간이 걸리는 경우 수, 다음 우선 순위가 가장 높은 값을 성공적으로 반환 하는 더 높은 우선 순위의 바인딩 값을 성공적으로 반환 될 때까지 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-106">It could be the case that the highest priority binding takes a long time to be evaluated, the next highest priority that returns a value successfully will be used until a binding of a higher priority returns a value successfully.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea535-107">예제</span><span class="sxs-lookup"><span data-stu-id="ea535-107">Example</span></span>  
 <span data-ttu-id="ea535-108">설명 하기 위해 어떻게 <xref:System.Windows.Data.PriorityBinding> 작동는 `AsyncDataSource` 다음 세 가지 속성을 가진 개체가 생성 되었음을: `FastDP`, `SlowerDP`, 및 `SlowestDP`합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-108">To demonstrate how <xref:System.Windows.Data.PriorityBinding> works, the `AsyncDataSource` object has been created with the following three properties: `FastDP`, `SlowerDP`, and `SlowestDP`.</span></span>  
  
 <span data-ttu-id="ea535-109">get 접근자 `FastDP` 의 값을 반환 된 `_fastDP` 데이터 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-109">The get accessor of `FastDP` returns the value of the `_fastDP` data member.</span></span>  
  
 <span data-ttu-id="ea535-110">get 접근자 `SlowerDP` 의 값을 반환 하기 전에 3 초 동안 대기는 `_slowerDP` 데이터 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-110">The get accessor of `SlowerDP` waits for 3 seconds before returning the value of the `_slowerDP` data member.</span></span>  
  
 <span data-ttu-id="ea535-111">get 접근자 `SlowestDP` 의 값을 반환 하기 전에 5 초 동안 대기는 `_slowestDP` 데이터 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-111">The get accessor of `SlowestDP` waits for 5 seconds before returning the value of the `_slowestDP` data member.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea535-112">이 예제는 예시용입니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-112">This example is for demonstration purposes only.</span></span> <span data-ttu-id="ea535-113">[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 지침 속성 필드 집합 보다 더 느린 대량 주문 인을 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-113">The [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] guidelines recommend against defining properties that are orders of magnitude slower than a field set would be.</span></span> <span data-ttu-id="ea535-114">자세한 내용은 참조 [NIB: 메서드와 속성 사이의 선택](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-114">For more information, see [NIB: Choosing Between Properties and Methods](http://msdn.microsoft.com/en-us/55825e8f-7e2e-448a-9505-7217cc91b1af).</span></span>  
  
 [!code-csharp[PriorityBinding#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml.cs#1)]
 [!code-vb[PriorityBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PriorityBinding/VisualBasic/AsyncDataSource.vb#1)]  
  
 <span data-ttu-id="ea535-115"><xref:System.Windows.Controls.TextBlock.Text%2A> 속성이 바인딩됩니다 위의 `AsyncDS` 를 사용 하 여 <xref:System.Windows.Data.PriorityBinding>:</span><span class="sxs-lookup"><span data-stu-id="ea535-115">The <xref:System.Windows.Controls.TextBlock.Text%2A> property binds to the above `AsyncDS` using <xref:System.Windows.Data.PriorityBinding>:</span></span>  
  
 [!code-xaml[PriorityBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PriorityBinding/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="ea535-116">바인딩 엔진에서 처리 하는 경우는 <xref:System.Windows.Data.Binding> 개체를 처음으로 시작 <xref:System.Windows.Data.Binding>에 바인딩된는 `SlowestDP` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-116">When the binding engine processes the <xref:System.Windows.Data.Binding> objects, it starts with the first <xref:System.Windows.Data.Binding>, which is bound to the `SlowestDP` property.</span></span> <span data-ttu-id="ea535-117">때이 <xref:System.Windows.Data.Binding> 은 처리를 반환 하지 않습니다 값을 성공적으로 대기 하기 5 초 동안 하므로 다음 때문에 <xref:System.Windows.Data.Binding> 요소가 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-117">When this <xref:System.Windows.Data.Binding> is processed, it does not return a value successfully because it is sleeping for 5 seconds, so the next <xref:System.Windows.Data.Binding> element is processed.</span></span> <span data-ttu-id="ea535-118">다음 <xref:System.Windows.Data.Binding> 값 반환 하지 않습니다는 성공적으로 3 초 동안 대기 하기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-118">The next <xref:System.Windows.Data.Binding> does not return a value successfully because it is sleeping for 3 seconds.</span></span> <span data-ttu-id="ea535-119">바인딩 엔진에 있는 다음 다음 이동 <xref:System.Windows.Data.Binding> 에 바인딩되는 요소는 `FastDP` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-119">The binding engine then moves onto the next <xref:System.Windows.Data.Binding> element, which is bound to the `FastDP` property.</span></span> <span data-ttu-id="ea535-120">이 <xref:System.Windows.Data.Binding> "빠른" 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-120">This <xref:System.Windows.Data.Binding> returns the value "Fast Value".</span></span> <span data-ttu-id="ea535-121"><xref:System.Windows.Controls.TextBlock> 이제 "빠른" 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-121">The <xref:System.Windows.Controls.TextBlock> now displays the value "Fast Value".</span></span>  
  
 <span data-ttu-id="ea535-122">3 초 경과 된 `SlowerDP` 속성 "느린 Value" 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-122">After 3 seconds elapses, the `SlowerDP` property returns the value "Slower Value".</span></span> <span data-ttu-id="ea535-123"><xref:System.Windows.Controls.TextBlock> "느린" 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-123">The <xref:System.Windows.Controls.TextBlock> then displays the value "Slower Value".</span></span>  
  
 <span data-ttu-id="ea535-124">5 초 동안 경과 된 `SlowestDP` 속성 "가장 느린 Value" 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-124">After 5 seconds elapses, the `SlowestDP` property returns the value "Slowest Value".</span></span> <span data-ttu-id="ea535-125">해당 바인딩을 첫 번째로 나열 되어 있으므로 가장 높은 우선 순위를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-125">That binding has the highest priority because it is listed first.</span></span> <span data-ttu-id="ea535-126"><xref:System.Windows.Controls.TextBlock> 이제 "가장 느린" 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-126">The <xref:System.Windows.Controls.TextBlock> now displays the value "Slowest Value".</span></span>  
  
 <span data-ttu-id="ea535-127">참조 <xref:System.Windows.Data.PriorityBinding> 간주 되는 바인딩에서 성공적인 반환 값에 대 한 정보에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea535-127">See <xref:System.Windows.Data.PriorityBinding> for information about what is considered a successful return value from a binding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea535-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea535-128">See Also</span></span>  
 <xref:System.Windows.Data.Binding.IsAsync%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ea535-129">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="ea535-129">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="ea535-130">방법 항목</span><span class="sxs-lookup"><span data-stu-id="ea535-130">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
