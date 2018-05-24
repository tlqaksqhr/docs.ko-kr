---
title: RepeatButton 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: d5edea14c1ea4184fda67e9b64887f192420b413
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="repeatbutton-syles-and-templates"></a><span data-ttu-id="0f125-102">RepeatButton 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0f125-102">RepeatButton Syles and Templates</span></span>
<span data-ttu-id="0f125-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.Primitives.RepeatButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="0f125-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0f125-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f125-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="repeatbutton-parts"></a><span data-ttu-id="0f125-106">RepeatButton 부분</span><span class="sxs-lookup"><span data-stu-id="0f125-106">RepeatButton Parts</span></span>  
 <span data-ttu-id="0f125-107"><xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>  
  
## <a name="repeatbutton-states"></a><span data-ttu-id="0f125-108">RepeatButton 상태</span><span class="sxs-lookup"><span data-stu-id="0f125-108">RepeatButton States</span></span>  
 <span data-ttu-id="0f125-109">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.Primitives.RepeatButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>  
  
|<span data-ttu-id="0f125-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="0f125-110">VisualState Name</span></span>|<span data-ttu-id="0f125-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="0f125-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0f125-112">설명</span><span class="sxs-lookup"><span data-stu-id="0f125-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0f125-113">보통</span><span class="sxs-lookup"><span data-stu-id="0f125-113">Normal</span></span>|<span data-ttu-id="0f125-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0f125-114">CommonStates</span></span>|<span data-ttu-id="0f125-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-115">The default state.</span></span>|  
|<span data-ttu-id="0f125-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0f125-116">MouseOver</span></span>|<span data-ttu-id="0f125-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0f125-117">CommonStates</span></span>|<span data-ttu-id="0f125-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="0f125-119">누름</span><span class="sxs-lookup"><span data-stu-id="0f125-119">Pressed</span></span>|<span data-ttu-id="0f125-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0f125-120">CommonStates</span></span>|<span data-ttu-id="0f125-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-121">The control is pressed.</span></span>|  
|<span data-ttu-id="0f125-122">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="0f125-122">Disabled</span></span>|<span data-ttu-id="0f125-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0f125-123">CommonStates</span></span>|<span data-ttu-id="0f125-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-124">The control is disabled.</span></span>|  
|<span data-ttu-id="0f125-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="0f125-125">Focused</span></span>|<span data-ttu-id="0f125-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0f125-126">FocusStates</span></span>|<span data-ttu-id="0f125-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-127">The control has focus.</span></span>|  
|<span data-ttu-id="0f125-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="0f125-128">Unfocused</span></span>|<span data-ttu-id="0f125-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0f125-129">FocusStates</span></span>|<span data-ttu-id="0f125-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="0f125-131">유효</span><span class="sxs-lookup"><span data-stu-id="0f125-131">Valid</span></span>|<span data-ttu-id="0f125-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0f125-132">ValidationStates</span></span>|<span data-ttu-id="0f125-133">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0f125-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0f125-134">InvalidFocused</span></span>|<span data-ttu-id="0f125-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0f125-135">ValidationStates</span></span>|<span data-ttu-id="0f125-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="0f125-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0f125-137">InvalidUnfocused</span></span>|<span data-ttu-id="0f125-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0f125-138">ValidationStates</span></span>|<span data-ttu-id="0f125-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="0f125-140">RepeatButton ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="0f125-140">RepeatButton ControlTemplate Example</span></span>  
 <span data-ttu-id="0f125-141">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Primitives.RepeatButton> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RepeatButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]  
  
 <span data-ttu-id="0f125-142">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f125-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0f125-143">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f125-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f125-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f125-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="0f125-145">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0f125-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="0f125-146">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0f125-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="0f125-147">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="0f125-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="0f125-148">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0f125-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
