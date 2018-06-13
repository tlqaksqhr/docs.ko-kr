---
title: ContextMenu 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], ContextMenu
- parts [WPF], ContextMenu
- ContextMenu [WPF], styles and templates
- styles [WPF], ContextMenu
- ControlTemplate [WPF], ContextMenu
- states [WPF], ContextMenu
ms.assetid: 342d1f17-c406-4f94-8f55-867c5f3ea511
ms.openlocfilehash: 671fb0a4f178c9e16149f6d47945670ea0e64d48
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457407"
---
# <a name="contextmenu-styles-and-templates"></a><span data-ttu-id="a38d3-102">ContextMenu 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a38d3-102">ContextMenu Styles and Templates</span></span>
<span data-ttu-id="a38d3-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.ContextMenu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ContextMenu> control.</span></span> <span data-ttu-id="a38d3-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a38d3-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a38d3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="contextmenu-parts"></a><span data-ttu-id="a38d3-106">ContextMenu 부분</span><span class="sxs-lookup"><span data-stu-id="a38d3-106">ContextMenu Parts</span></span>  
 <span data-ttu-id="a38d3-107"><xref:System.Windows.Controls.ContextMenu> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-107">The <xref:System.Windows.Controls.ContextMenu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="a38d3-108">만들 때 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ContextMenu>, 서식 파일에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ContextMenu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="a38d3-109">(의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목에 표시 됩니다는 <xref:System.Windows.Controls.ContextMenu>; <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ContextMenu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="a38d3-110">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직계 자식이 없는 <xref:System.Windows.Controls.ScrollViewer>를 지정 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름, `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="contextmenu-states"></a><span data-ttu-id="a38d3-111">ContextMenu 상태</span><span class="sxs-lookup"><span data-stu-id="a38d3-111">ContextMenu States</span></span>  
 <span data-ttu-id="a38d3-112">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.ContextMenu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-112">The following table lists the visual states for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
|<span data-ttu-id="a38d3-113">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="a38d3-113">VisualState Name</span></span>|<span data-ttu-id="a38d3-114">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="a38d3-114">VisualStateGroup Name</span></span>|<span data-ttu-id="a38d3-115">설명</span><span class="sxs-lookup"><span data-stu-id="a38d3-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a38d3-116">유효</span><span class="sxs-lookup"><span data-stu-id="a38d3-116">Valid</span></span>|<span data-ttu-id="a38d3-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a38d3-117">ValidationStates</span></span>|<span data-ttu-id="a38d3-118">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a38d3-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a38d3-119">InvalidFocused</span></span>|<span data-ttu-id="a38d3-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a38d3-120">ValidationStates</span></span>|<span data-ttu-id="a38d3-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a38d3-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a38d3-122">InvalidUnfocused</span></span>|<span data-ttu-id="a38d3-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a38d3-123">ValidationStates</span></span>|<span data-ttu-id="a38d3-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="contextmenu-controltemplate-example"></a><span data-ttu-id="a38d3-125">ContextMenu ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="a38d3-125">ContextMenu ControlTemplate Example</span></span>  
 <span data-ttu-id="a38d3-126">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ContextMenu> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-126">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ContextMenu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#contextmenu)]  
  
 <span data-ttu-id="a38d3-127"><xref:System.Windows.Controls.ControlTemplate> 다음 리소스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a38d3-127">The <xref:System.Windows.Controls.ControlTemplate> uses the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a38d3-128">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a38d3-128">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38d3-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a38d3-129">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="a38d3-130">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a38d3-130">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="a38d3-131">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a38d3-131">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="a38d3-132">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a38d3-132">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a38d3-133">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a38d3-133">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
