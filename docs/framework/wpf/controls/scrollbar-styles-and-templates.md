---
title: ScrollBar 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 926fc3373bb40eb12462dcead278d458cefad7cf
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="0d48e-102">ScrollBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0d48e-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="0d48e-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.Primitives.ScrollBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="0d48e-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0d48e-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d48e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="0d48e-106">스크롤 막대 부분</span><span class="sxs-lookup"><span data-stu-id="0d48e-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="0d48e-107">다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.Primitives.ScrollBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="0d48e-108">파트</span><span class="sxs-lookup"><span data-stu-id="0d48e-108">Part</span></span>|<span data-ttu-id="0d48e-109">형식</span><span class="sxs-lookup"><span data-stu-id="0d48e-109">Type</span></span>|<span data-ttu-id="0d48e-110">설명</span><span class="sxs-lookup"><span data-stu-id="0d48e-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0d48e-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="0d48e-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="0d48e-112">위치를 나타내는 요소에 대 한 컨테이너는 <xref:System.Windows.Controls.Primitives.ScrollBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="0d48e-113">스크롤 막대 상태</span><span class="sxs-lookup"><span data-stu-id="0d48e-113">ScrollBar States</span></span>  
 <span data-ttu-id="0d48e-114">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.Primitives.ScrollBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="0d48e-115">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="0d48e-115">VisualState Name</span></span>|<span data-ttu-id="0d48e-116">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="0d48e-116">VisualStateGroup Name</span></span>|<span data-ttu-id="0d48e-117">설명</span><span class="sxs-lookup"><span data-stu-id="0d48e-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="0d48e-118">보통</span><span class="sxs-lookup"><span data-stu-id="0d48e-118">Normal</span></span>|<span data-ttu-id="0d48e-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0d48e-119">CommonStates</span></span>|<span data-ttu-id="0d48e-120">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-120">The default state.</span></span>|  
|<span data-ttu-id="0d48e-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0d48e-121">MouseOver</span></span>|<span data-ttu-id="0d48e-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0d48e-122">CommonStates</span></span>|<span data-ttu-id="0d48e-123">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="0d48e-124">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0d48e-124">Disabled</span></span>|<span data-ttu-id="0d48e-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0d48e-125">CommonStates</span></span>|<span data-ttu-id="0d48e-126">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-126">The control is disabled.</span></span>|  
|<span data-ttu-id="0d48e-127">유효</span><span class="sxs-lookup"><span data-stu-id="0d48e-127">Valid</span></span>|<span data-ttu-id="0d48e-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0d48e-128">ValidationStates</span></span>|<span data-ttu-id="0d48e-129">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0d48e-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0d48e-130">InvalidFocused</span></span>|<span data-ttu-id="0d48e-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0d48e-131">ValidationStates</span></span>|<span data-ttu-id="0d48e-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0d48e-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0d48e-133">InvalidUnfocused</span></span>|<span data-ttu-id="0d48e-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0d48e-134">ValidationStates</span></span>|<span data-ttu-id="0d48e-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="0d48e-136">보려면</span><span class="sxs-lookup"><span data-stu-id="0d48e-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="0d48e-137">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Primitives.ScrollBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="0d48e-138">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d48e-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0d48e-139">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d48e-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d48e-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d48e-140">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="0d48e-141">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0d48e-141">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="0d48e-142">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0d48e-142">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="0d48e-143">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0d48e-143">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="0d48e-144">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0d48e-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
