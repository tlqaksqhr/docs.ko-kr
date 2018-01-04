---
title: "ToolBar 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ToolBar
- ToolBar control [WPF]
ms.assetid: a8edb32c-118d-4f31-b6e6-8899082b504b
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f00597d48ff100325c1fb2884f64169164415a50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="toolbar-overview"></a><span data-ttu-id="fbbb7-102">ToolBar 개요</span><span class="sxs-lookup"><span data-stu-id="fbbb7-102">ToolBar Overview</span></span>
<span data-ttu-id="fbbb7-103"><xref:System.Windows.Controls.ToolBar>컨트롤은 명령 또는 해당 함수에서 일반적으로 관련이 있는 컨트롤의 그룹에 대 한 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-103"><xref:System.Windows.Controls.ToolBar> controls are containers for a group of commands or controls which are typically related in their function.</span></span> <span data-ttu-id="fbbb7-104">A <xref:System.Windows.Controls.ToolBar> 일반적으로 명령을 호출 하는 단추가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-104">A <xref:System.Windows.Controls.ToolBar> usually contains buttons which invoke commands.</span></span>  
  
  
<a name="ToolBarControl"></a>   
## <a name="toolbar-control"></a><span data-ttu-id="fbbb7-105">ToolBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fbbb7-105">ToolBar Control</span></span>  
 <span data-ttu-id="fbbb7-106"><xref:System.Windows.Controls.ToolBar> 컨트롤 단일 행 이나 열으로 단추 또는 다른 컨트롤의 막대와 비슷한 배열에서 해당 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-106">The <xref:System.Windows.Controls.ToolBar> control takes its name from the bar-like arrangement of buttons or other controls into a single row or column.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="fbbb7-107"><xref:System.Windows.Controls.ToolBar> 컨트롤 크기 제한 내에 맞지 않는 모든 항목을 배치 하는 오버플로 메커니즘을 제공 <xref:System.Windows.Controls.ToolBar> 특별 한 넘침 영역에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-107"> <xref:System.Windows.Controls.ToolBar> controls provide an overflow mechanism which places any items that do not fit naturally within a size-constrained <xref:System.Windows.Controls.ToolBar> into a special overflow area.</span></span> <span data-ttu-id="fbbb7-108">또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> 컨트롤은 일반적으로 사용 하는 관련 된 <xref:System.Windows.Controls.ToolBarTray> 크기 조정 및 컨트롤과 사용자가 시작한 위한 지원 뿐 아니라 특별 한 레이아웃 동작을 제공 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-108">Also, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ToolBar> controls are usually used with the related <xref:System.Windows.Controls.ToolBarTray> control, which provides special layout behavior as well as support for user-initiated sizing and arranging of toolbars.</span></span>  
  
<a name="Creating_ToolBars"></a>   
## <a name="specifying-the-position-of-toolbars-in-a-toolbartray"></a><span data-ttu-id="fbbb7-109">ToolBarTray에서 ToolBar 위치 지정</span><span class="sxs-lookup"><span data-stu-id="fbbb7-109">Specifying the Position of ToolBars in a ToolBarTray</span></span>  
 <span data-ttu-id="fbbb7-110">사용 하 여는 <xref:System.Windows.Controls.ToolBar.Band%2A> 및 <xref:System.Windows.Controls.ToolBar.BandIndex%2A> 의 위치를 지정할 속성은 <xref:System.Windows.Controls.ToolBar> 에 <xref:System.Windows.Controls.ToolBarTray>합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-110">Use the <xref:System.Windows.Controls.ToolBar.Band%2A> and <xref:System.Windows.Controls.ToolBar.BandIndex%2A> properties to position the <xref:System.Windows.Controls.ToolBar> in the <xref:System.Windows.Controls.ToolBarTray>.</span></span> <span data-ttu-id="fbbb7-111"><xref:System.Windows.Controls.ToolBar.Band%2A>위치를 나타냅니다는 <xref:System.Windows.Controls.ToolBar> 해당 부모 노드에 배치 <xref:System.Windows.Controls.ToolBarTray>합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-111"><xref:System.Windows.Controls.ToolBar.Band%2A> indicates the position in which the <xref:System.Windows.Controls.ToolBar> is placed within its parent <xref:System.Windows.Controls.ToolBarTray>.</span></span> <span data-ttu-id="fbbb7-112"><xref:System.Windows.Controls.ToolBar.BandIndex%2A>순서를 나타냅니다는 <xref:System.Windows.Controls.ToolBar> 해당 대역 내에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-112"><xref:System.Windows.Controls.ToolBar.BandIndex%2A> indicates the order in which the <xref:System.Windows.Controls.ToolBar> is placed within its band.</span></span> <span data-ttu-id="fbbb7-113">다음 예제에서는 배치 하려면이 속성을 사용 방법 <xref:System.Windows.Controls.ToolBar> 컨트롤 내부의 <xref:System.Windows.Controls.ToolBarTray>합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-113">The following example shows how use this property to place <xref:System.Windows.Controls.ToolBar> controls inside a <xref:System.Windows.Controls.ToolBarTray>.</span></span>  
  
 [!code-xaml[ToolBarExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#2)]  
  
<a name="ToolBars_with_Overflow_Items"></a>   
## <a name="toolbars-with-overflow-items"></a><span data-ttu-id="fbbb7-114">오버플로 항목이 있는 ToolBar</span><span class="sxs-lookup"><span data-stu-id="fbbb7-114">ToolBars with Overflow Items</span></span>  
 <span data-ttu-id="fbbb7-115">종종 <xref:System.Windows.Controls.ToolBar> 컨트롤에 도구 모음의 크기에 맞출 수 있는 것 보다 많은 항목이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-115">Often <xref:System.Windows.Controls.ToolBar> controls contain more items than can fit into the toolbar's size.</span></span> <span data-ttu-id="fbbb7-116">이런 경우는 <xref:System.Windows.Controls.ToolBar> 오버플로 단추를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-116">When this happens, the <xref:System.Windows.Controls.ToolBar> displays an overflow button.</span></span> <span data-ttu-id="fbbb7-117">오버플로 항목을 확인 하려면 사용자는 오버플로 단추를 클릭 하 고 항목 아래의 팝업 창에 표시 됩니다는 <xref:System.Windows.Controls.ToolBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-117">To see the overflow items, a user clicks the overflow button and the items are shown in a pop-up window below the <xref:System.Windows.Controls.ToolBar>.</span></span> <span data-ttu-id="fbbb7-118">다음 그래픽에 표시 된는 <xref:System.Windows.Controls.ToolBar> 오버플로 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-118">The following graphic shows a <xref:System.Windows.Controls.ToolBar> with overflow items.</span></span>  
  
 <span data-ttu-id="fbbb7-119">![오버플로 도구 모음](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")</span><span class="sxs-lookup"><span data-stu-id="fbbb7-119">![ToolBar with overflow](../../../../docs/framework/wpf/controls/media/toolbarwithoverflowitem.png "ToolbarWithOverflowItem")</span></span>  
<span data-ttu-id="fbbb7-120">오버플로 항목이 있는 도구 모음</span><span class="sxs-lookup"><span data-stu-id="fbbb7-120">Toolbar with Overflow Items</span></span>  
  
 <span data-ttu-id="fbbb7-121">설정 하 여 도구 모음에 있는 항목 오버플로 패널에 배치 하면 지정할 수는 <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> 연결 된 속성을 <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>, 또는 <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-121">You can specify when an item on a toolbar is placed on the overflow panel by setting the <xref:System.Windows.Controls.ToolBar.OverflowMode%2A?displayProperty=nameWithType> attached property to <xref:System.Windows.Controls.OverflowMode.Always?displayProperty=nameWithType>, <xref:System.Windows.Controls.OverflowMode.Never?displayProperty=nameWithType>, or <xref:System.Windows.Controls.OverflowMode.AsNeeded?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fbbb7-122">다음 예제에서는 도구 모음에 있는 마지막 네 개의 단추가 오버플로 패널에 항상 표시되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-122">The following example specifies that the last four buttons on the toolbar should always be on the overflow panel.</span></span>  
  
 [!code-xaml[ToolBarExample#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ToolBarExample/CS/Pane1.xaml#3)]  
  
 <span data-ttu-id="fbbb7-123"><xref:System.Windows.Controls.ToolBar> 사용 하 여 한 <xref:System.Windows.Controls.Primitives.ToolBarPanel> 및 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> 에 해당 <xref:System.Windows.Controls.ControlTemplate>합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-123">The <xref:System.Windows.Controls.ToolBar> uses a <xref:System.Windows.Controls.Primitives.ToolBarPanel> and a <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> in its <xref:System.Windows.Controls.ControlTemplate>.</span></span>  <span data-ttu-id="fbbb7-124"><xref:System.Windows.Controls.Primitives.ToolBarPanel> 도구 모음에서 항목의 레이아웃을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-124">The <xref:System.Windows.Controls.Primitives.ToolBarPanel> is responsible for the layout of the items on the toolbar.</span></span>  <span data-ttu-id="fbbb7-125"><xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> 에 맞지 않는 항목의 레이아웃에 대 한 책임이 <xref:System.Windows.Controls.ToolBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-125">The <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel> is responsible for the layout of the items that do not fit on the <xref:System.Windows.Controls.ToolBar>.</span></span> <span data-ttu-id="fbbb7-126">에 대 한 예제는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ToolBar>, 참조</span><span class="sxs-lookup"><span data-stu-id="fbbb7-126">For an example of a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, see</span></span>  
  
 <span data-ttu-id="fbbb7-127">[ToolBar 스타일 및 템플릿](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbbb7-127">[ToolBar Styles and Templates](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbbb7-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbbb7-128">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.ToolBarPanel>  
 <xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>  
 [<span data-ttu-id="fbbb7-129">ToolBar 컨트롤의 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="fbbb7-129">Style Controls on a ToolBar</span></span>](../../../../docs/framework/wpf/controls/how-to-style-controls-on-a-toolbar.md)  
 <span data-ttu-id="fbbb7-130">[WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)(WPF 컨트롤 갤러리 샘플)</span><span class="sxs-lookup"><span data-stu-id="fbbb7-130">[WPF Controls Gallery Sample](http://go.microsoft.com/fwlink/?LinkID=160053)</span></span>
