---
title: "방법: 도구 설명 배치"
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
- ToolTip control [WPF], positioning
- positioning ToolTip controls [WPF]
ms.assetid: cddf3757-9e5f-4ce3-a6eb-44489cf3804a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0e8345b74cf9269bca21e1e5698de974109c2aee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-a-tooltip"></a><span data-ttu-id="90579-102">방법: 도구 설명 배치</span><span class="sxs-lookup"><span data-stu-id="90579-102">How to: Position a ToolTip</span></span>
<span data-ttu-id="90579-103">이 예제에서는 화면에 도구 설명의 위치를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90579-103">This example shows how to specify the position of a tooltip on the screen.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90579-104">예제</span><span class="sxs-lookup"><span data-stu-id="90579-104">Example</span></span>  
 <span data-ttu-id="90579-105">도구 설명 모두에서 정의 하는 5 개의 속성 집합이 사용 하 여 배치할 수 있습니다는 <xref:System.Windows.Controls.ToolTip> 및 <xref:System.Windows.Controls.ToolTipService> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="90579-105">You can position a tooltip by using a set of five properties that are defined in both the <xref:System.Windows.Controls.ToolTip> and <xref:System.Windows.Controls.ToolTipService> classes.</span></span> <span data-ttu-id="90579-106">다음 표에서 이러한 두 속성 집합의 5 개 보여주며, 클래스에 따라 참조 설명서의 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="90579-106">The following table shows these two sets of five properties and provides links to their reference documentation according to class.</span></span>  
  
### <a name="corresponding-tooltip-properties-according-to-class"></a><span data-ttu-id="90579-107">클래스에 따라 해당 하는 도구 설명 속성</span><span class="sxs-lookup"><span data-stu-id="90579-107">Corresponding tooltip properties according to class</span></span>  
  
|<span data-ttu-id="90579-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType>클래스 속성</span><span class="sxs-lookup"><span data-stu-id="90579-108"><xref:System.Windows.Controls.ToolTip?displayProperty=nameWithType> class properties</span></span>|<span data-ttu-id="90579-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType>클래스 속성</span><span class="sxs-lookup"><span data-stu-id="90579-109"><xref:System.Windows.Controls.ToolTipService?displayProperty=nameWithType> class properties</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Windows.Controls.ToolTip.Placement%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.Placement%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementTarget%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementTarget%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.PlacementRectangle%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.PlacementRectangle%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.HorizontalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.HorizontalOffset%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Controls.ToolTip.VerticalOffset%2A?displayProperty=nameWithType>|<xref:System.Windows.Controls.ToolTipService.VerticalOffset%2A?displayProperty=nameWithType>|  
  
 <span data-ttu-id="90579-110">사용 하 여 도구 설명의 내용을 정의 하는 경우는 <xref:System.Windows.Controls.ToolTip> 개체 클래스의 속성을 사용할 수 있지만 <xref:System.Windows.Controls.ToolTipService> 속성 보다 우선 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="90579-110">If you define the contents of a tooltip by using a <xref:System.Windows.Controls.ToolTip> object, you can use the properties of either class; however, the <xref:System.Windows.Controls.ToolTipService> properties take precedence.</span></span> <span data-ttu-id="90579-111">사용 하 여는 <xref:System.Windows.Controls.ToolTipService> 로 정의 되어 있지 않은 도구 설명에 대 한 속성 <xref:System.Windows.Controls.ToolTip> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="90579-111">Use the <xref:System.Windows.Controls.ToolTipService> properties for tooltips that are not defined as <xref:System.Windows.Controls.ToolTip> objects.</span></span>  
  
 <span data-ttu-id="90579-112">다음 그림은 이러한 속성을 사용 하 여 도구 설명을 배치 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="90579-112">The following illustrations show how to position a tooltip by using these properties.</span></span> <span data-ttu-id="90579-113">하지만, [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 이러한 그림의 예제에서 정의한 속성을 설정 하는 방법을 보여 줍니다는 <xref:System.Windows.Controls.ToolTip> 클래스의 해당 속성은 <xref:System.Windows.Controls.ToolTipService> 클래스 같은 레이아웃 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="90579-113">Although, the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples in these illustrations show how to set the properties that are defined by the <xref:System.Windows.Controls.ToolTip> class, the corresponding properties of the <xref:System.Windows.Controls.ToolTipService> class follow the same layout rules.</span></span> <span data-ttu-id="90579-114">배치 속성에 대 한 가능한 값에 대 한 자세한 내용은 참조 [팝업 배치 동작](../../../../docs/framework/wpf/controls/popup-placement-behavior.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="90579-114">For more information about the possible values for the Placement property, see [Popup Placement Behavior](../../../../docs/framework/wpf/controls/popup-placement-behavior.md).</span></span>  
  
 <span data-ttu-id="90579-115">![ToolTip 배치](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span><span class="sxs-lookup"><span data-stu-id="90579-115">![ToolTip placement](../../../../docs/framework/wpf/controls/media/tooltipplacement.png "ToolTipPlacement")</span></span>  
<span data-ttu-id="90579-116">배치 속성을 사용 하 여 ToolTip 배치</span><span class="sxs-lookup"><span data-stu-id="90579-116">ToolTip placement by using the Placement property</span></span>  
  
 <span data-ttu-id="90579-117">![배치 사각형을 사용 하 여 ToolTip 배치](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span><span class="sxs-lookup"><span data-stu-id="90579-117">![Placing a ToolTip by using a placement rectangle](../../../../docs/framework/wpf/controls/media/tooltipplacementrectangle.png "ToolTipPlacementRectangle")</span></span>  
<span data-ttu-id="90579-118">배치 및 PlacementRectangle 속성을 사용 하 여 ToolTip 배치</span><span class="sxs-lookup"><span data-stu-id="90579-118">ToolTip placement by using the Placement and PlacementRectangle properties</span></span>  
  
 <span data-ttu-id="90579-119">![ToolTip 배치 다이어그램](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span><span class="sxs-lookup"><span data-stu-id="90579-119">![ToolTip placement diagram](../../../../docs/framework/wpf/controls/media/tooltipplacementprhv.png "ToolTipPlacementPRHV")</span></span>  
<span data-ttu-id="90579-120">Placement, PlacementRectangle, 및 오프셋 속성을 사용 하 여 ToolTip 배치</span><span class="sxs-lookup"><span data-stu-id="90579-120">ToolTip placement by using the Placement, PlacementRectangle, and Offset properties</span></span>  
  
 <span data-ttu-id="90579-121">사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.ToolTip> 내용이 도구 설명의 위치를 지정 하는 속성을 <xref:System.Windows.Controls.ToolTip> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="90579-121">The following example shows how to use the <xref:System.Windows.Controls.ToolTip> properties to specify the position of a tooltip whose content is a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#tooltip)]  
  
 [!code-csharp[ToolTipService#ToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#tooltipcode)]
 [!code-vb[ToolTipService#ToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#tooltipcode)]  
  
 <span data-ttu-id="90579-122">사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.ToolTipService> 내용이 없는 도구 설명의 위치를 지정 하는 속성은 <xref:System.Windows.Controls.ToolTip> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="90579-122">The following example shows how to use the <xref:System.Windows.Controls.ToolTipService> properties to specify the position of a tooltip whose content is not a <xref:System.Windows.Controls.ToolTip> object.</span></span>  
  
 [!code-xaml[ToolTipService#NoToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml#notooltip)]  
  
 [!code-csharp[ToolTipService#NoToolTipCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolTipService/CSharp/Pane1.xaml.cs#notooltipcode)]
 [!code-vb[ToolTipService#NoToolTipCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ToolTipService/visualbasic/pane1.xaml.vb#notooltipcode)]  
  
## <a name="see-also"></a><span data-ttu-id="90579-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90579-123">See Also</span></span>  
 <xref:System.Windows.Controls.ToolTip>  
 <xref:System.Windows.Controls.ToolTipService>  
 [<span data-ttu-id="90579-124">방법 항목</span><span class="sxs-lookup"><span data-stu-id="90579-124">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/tooltip-how-to-topics.md)  
 [<span data-ttu-id="90579-125">도구 설명 개요</span><span class="sxs-lookup"><span data-stu-id="90579-125">ToolTip Overview</span></span>](../../../../docs/framework/wpf/controls/tooltip-overview.md)  
 [<span data-ttu-id="90579-126">ContextMenuService 및 ToolTipService 사용</span><span class="sxs-lookup"><span data-stu-id="90579-126">Use the ContextMenuService and ToolTipService</span></span>](http://msdn.microsoft.com/en-us/809b0e9c-d612-4cda-b8af-1a698c68f4d1)
