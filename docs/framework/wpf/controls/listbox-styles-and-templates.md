---
title: "ListBox 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edf8c50424a9694c4e00f5bf319d3122999bda85
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="listbox-styles-and-templates"></a><span data-ttu-id="80967-102">ListBox 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="80967-102">ListBox Styles and Templates</span></span>
<span data-ttu-id="80967-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.ListBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80967-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="80967-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="80967-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80967-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="listbox-parts"></a><span data-ttu-id="80967-106">ListBox 파트</span><span class="sxs-lookup"><span data-stu-id="80967-106">ListBox Parts</span></span>  
 <span data-ttu-id="80967-107"><xref:System.Windows.Controls.ListBox> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-107">The <xref:System.Windows.Controls.ListBox> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="80967-108">만들 때 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ListBox>, 서식 파일에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="80967-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ListBox>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="80967-109">(의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목에 표시 됩니다는 <xref:System.Windows.Controls.ListBox>; <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="80967-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ListBox>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="80967-110">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직계 자식이 없는 <xref:System.Windows.Controls.ScrollViewer>를 지정 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름, `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="80967-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="listbox-states"></a><span data-ttu-id="80967-111">ListBox 상태</span><span class="sxs-lookup"><span data-stu-id="80967-111">ListBox States</span></span>  
 <span data-ttu-id="80967-112">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.ListBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80967-112">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="80967-113">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="80967-113">VisualState Name</span></span>|<span data-ttu-id="80967-114">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="80967-114">VisualStateGroup Name</span></span>|<span data-ttu-id="80967-115">설명</span><span class="sxs-lookup"><span data-stu-id="80967-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="80967-116">유효</span><span class="sxs-lookup"><span data-stu-id="80967-116">Valid</span></span>|<span data-ttu-id="80967-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="80967-117">ValidationStates</span></span>|<span data-ttu-id="80967-118">컨트롤이 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="80967-118">The control is valid.</span></span>|  
|<span data-ttu-id="80967-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="80967-119">InvalidFocused</span></span>|<span data-ttu-id="80967-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="80967-120">ValidationStates</span></span>|<span data-ttu-id="80967-121">컨트롤이 유효하지 않고 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-121">The control is not valid and has focus.</span></span>|  
|<span data-ttu-id="80967-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="80967-122">InvalidUnfocused</span></span>|<span data-ttu-id="80967-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="80967-123">ValidationStates</span></span>|<span data-ttu-id="80967-124">컨트롤이 유효하지 않고 컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-124">The control is not valid and does not have focus.</span></span>|  
  
## <a name="listboxitem-parts"></a><span data-ttu-id="80967-125">ListBoxItem 파트</span><span class="sxs-lookup"><span data-stu-id="80967-125">ListBoxItem Parts</span></span>  
 <span data-ttu-id="80967-126"><xref:System.Windows.Controls.ListBoxItem> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-126">The <xref:System.Windows.Controls.ListBoxItem> control does not have any named parts.</span></span>  
  
## <a name="listboxitem-states"></a><span data-ttu-id="80967-127">ListBoxItem 상태</span><span class="sxs-lookup"><span data-stu-id="80967-127">ListBoxItem States</span></span>  
 <span data-ttu-id="80967-128">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.ListBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="80967-128">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="80967-129">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="80967-129">VisualState Name</span></span>|<span data-ttu-id="80967-130">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="80967-130">VisualStateGroup Name</span></span>|<span data-ttu-id="80967-131">설명</span><span class="sxs-lookup"><span data-stu-id="80967-131">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="80967-132">보통</span><span class="sxs-lookup"><span data-stu-id="80967-132">Normal</span></span>|<span data-ttu-id="80967-133">CommonStates</span><span class="sxs-lookup"><span data-stu-id="80967-133">CommonStates</span></span>|<span data-ttu-id="80967-134">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="80967-134">The default state.</span></span>|  
|<span data-ttu-id="80967-135">MouseOver</span><span class="sxs-lookup"><span data-stu-id="80967-135">MouseOver</span></span>|<span data-ttu-id="80967-136">CommonStates</span><span class="sxs-lookup"><span data-stu-id="80967-136">CommonStates</span></span>|<span data-ttu-id="80967-137">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-137">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="80967-138">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="80967-138">Disabled</span></span>|<span data-ttu-id="80967-139">CommonStates</span><span class="sxs-lookup"><span data-stu-id="80967-139">CommonStates</span></span>|<span data-ttu-id="80967-140">항목을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-140">The item is disabled.</span></span>|  
|<span data-ttu-id="80967-141">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="80967-141">Focused</span></span>|<span data-ttu-id="80967-142">FocusStates</span><span class="sxs-lookup"><span data-stu-id="80967-142">FocusStates</span></span>|<span data-ttu-id="80967-143">항목에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-143">The item has focus.</span></span>|  
|<span data-ttu-id="80967-144">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="80967-144">Unfocused</span></span>|<span data-ttu-id="80967-145">FocusStates</span><span class="sxs-lookup"><span data-stu-id="80967-145">FocusStates</span></span>|<span data-ttu-id="80967-146">항목에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-146">The item does not have focus.</span></span>|  
|<span data-ttu-id="80967-147">선택 취소</span><span class="sxs-lookup"><span data-stu-id="80967-147">Unselected</span></span>|<span data-ttu-id="80967-148">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="80967-148">SelectionStates</span></span>|<span data-ttu-id="80967-149">항목이 선택되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-149">The item is not selected.</span></span>|  
|<span data-ttu-id="80967-150">선택함</span><span class="sxs-lookup"><span data-stu-id="80967-150">Selected</span></span>|<span data-ttu-id="80967-151">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="80967-151">SelectionStates</span></span>|<span data-ttu-id="80967-152">항목이 선택된 currentlyplate입니다.</span><span class="sxs-lookup"><span data-stu-id="80967-152">The item is currentlyplate selected.</span></span>|  
|<span data-ttu-id="80967-153">SelectedUnfocused</span><span class="sxs-lookup"><span data-stu-id="80967-153">SelectedUnfocused</span></span>|<span data-ttu-id="80967-154">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="80967-154">SelectionStates</span></span>|<span data-ttu-id="80967-155">항목이 선택되었지만 항목에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-155">The item is selected, but does not have focus.</span></span>|  
|<span data-ttu-id="80967-156">유효</span><span class="sxs-lookup"><span data-stu-id="80967-156">Valid</span></span>|<span data-ttu-id="80967-157">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="80967-157">ValidationStates</span></span>|<span data-ttu-id="80967-158">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="80967-158">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="80967-159">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="80967-159">InvalidFocused</span></span>|<span data-ttu-id="80967-160">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="80967-160">ValidationStates</span></span>|<span data-ttu-id="80967-161"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80967-161">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="80967-162">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="80967-162">InvalidUnfocused</span></span>|<span data-ttu-id="80967-163">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="80967-163">ValidationStates</span></span>|<span data-ttu-id="80967-164"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="80967-164">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="listbox-controltemplate-example"></a><span data-ttu-id="80967-165">ListBox ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="80967-165">ListBox ControlTemplate Example</span></span>  
 <span data-ttu-id="80967-166">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ListBox> 및 <xref:System.Windows.Controls.ListBoxItem> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="80967-166">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ListBox> and <xref:System.Windows.Controls.ListBoxItem> controls.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 <span data-ttu-id="80967-167">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="80967-167">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="80967-168">전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="80967-168">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80967-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80967-169">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="80967-170">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="80967-170">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="80967-171">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="80967-171">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="80967-172">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="80967-172">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="80967-173">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="80967-173">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
