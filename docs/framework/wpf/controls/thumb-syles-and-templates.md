---
title: Thumb 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: 16204820f18fed87ab769f3f59c10a35c4048d29
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="thumb-syles-and-templates"></a><span data-ttu-id="dc73c-102">Thumb 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="dc73c-102">Thumb Syles and Templates</span></span>
<span data-ttu-id="dc73c-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.Primitives.Thumb> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="dc73c-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="dc73c-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc73c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="thumb-parts"></a><span data-ttu-id="dc73c-106">Thumb 부분</span><span class="sxs-lookup"><span data-stu-id="dc73c-106">Thumb Parts</span></span>  
 <span data-ttu-id="dc73c-107"><xref:System.Windows.Controls.Primitives.Thumb> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>  
  
## <a name="thumb-states"></a><span data-ttu-id="dc73c-108">엄지 단추 상태</span><span class="sxs-lookup"><span data-stu-id="dc73c-108">Thumb States</span></span>  
 <span data-ttu-id="dc73c-109">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.Primitives.Thumb> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
|<span data-ttu-id="dc73c-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="dc73c-110">VisualState Name</span></span>|<span data-ttu-id="dc73c-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="dc73c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="dc73c-112">설명</span><span class="sxs-lookup"><span data-stu-id="dc73c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="dc73c-113">보통</span><span class="sxs-lookup"><span data-stu-id="dc73c-113">Normal</span></span>|<span data-ttu-id="dc73c-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="dc73c-114">CommonStates</span></span>|<span data-ttu-id="dc73c-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-115">The default state.</span></span>|  
|<span data-ttu-id="dc73c-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="dc73c-116">MouseOver</span></span>|<span data-ttu-id="dc73c-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="dc73c-117">CommonStates</span></span>|<span data-ttu-id="dc73c-118">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="dc73c-119">누름</span><span class="sxs-lookup"><span data-stu-id="dc73c-119">Pressed</span></span>|<span data-ttu-id="dc73c-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="dc73c-120">CommonStates</span></span>|<span data-ttu-id="dc73c-121">컨트롤을 눌렀습니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-121">The control is pressed.</span></span>|  
|<span data-ttu-id="dc73c-122">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="dc73c-122">Disabled</span></span>|<span data-ttu-id="dc73c-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="dc73c-123">CommonStates</span></span>|<span data-ttu-id="dc73c-124">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-124">The control is disabled.</span></span>|  
|<span data-ttu-id="dc73c-125">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="dc73c-125">Focused</span></span>|<span data-ttu-id="dc73c-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="dc73c-126">FocusStates</span></span>|<span data-ttu-id="dc73c-127">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-127">The control has focus.</span></span>|  
|<span data-ttu-id="dc73c-128">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="dc73c-128">Unfocused</span></span>|<span data-ttu-id="dc73c-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="dc73c-129">FocusStates</span></span>|<span data-ttu-id="dc73c-130">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="dc73c-131">유효</span><span class="sxs-lookup"><span data-stu-id="dc73c-131">Valid</span></span>|<span data-ttu-id="dc73c-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="dc73c-132">ValidationStates</span></span>|<span data-ttu-id="dc73c-133">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="dc73c-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="dc73c-134">InvalidFocused</span></span>|<span data-ttu-id="dc73c-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="dc73c-135">ValidationStates</span></span>|<span data-ttu-id="dc73c-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="dc73c-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="dc73c-137">InvalidUnfocused</span></span>|<span data-ttu-id="dc73c-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="dc73c-138">ValidationStates</span></span>|<span data-ttu-id="dc73c-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="thumb-controltemplate-example"></a><span data-ttu-id="dc73c-140">엄지 단추 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="dc73c-140">Thumb ControlTemplate Example</span></span>  
 <span data-ttu-id="dc73c-141">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.Primitives.Thumb> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]  
  
 <span data-ttu-id="dc73c-142">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="dc73c-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="dc73c-143">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc73c-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc73c-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc73c-144">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="dc73c-145">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="dc73c-145">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="dc73c-146">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="dc73c-146">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="dc73c-147">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="dc73c-147">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="dc73c-148">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="dc73c-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
