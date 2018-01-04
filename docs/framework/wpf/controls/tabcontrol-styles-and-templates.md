---
title: "TabControl 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ControlTemplate [WPF], TabControl
- TabControl [WPF], styles and templates [WPF]
- parts [WPF], TabControl
- styles [WPF], TabControl
- states [WPF], TabControl
- templates [WPF], TabControl
ms.assetid: f6b19a30-f10e-4fa1-96ce-f17a54092ab6
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 22d1e4dbd8e7a3ca6ec9f0c91e5e59be2f683455
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="tabcontrol-styles-and-templates"></a><span data-ttu-id="5455c-102">TabControl 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="5455c-102">TabControl Styles and Templates</span></span>
<span data-ttu-id="5455c-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.TabControl> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.TabControl> control.</span></span> <span data-ttu-id="5455c-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="5455c-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5455c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tabcontrol-parts"></a><span data-ttu-id="5455c-106">TabControl 부분</span><span class="sxs-lookup"><span data-stu-id="5455c-106">TabControl Parts</span></span>  
 <span data-ttu-id="5455c-107">다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.TabControl> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-107">The following table lists the named parts for the <xref:System.Windows.Controls.TabControl> control.</span></span>  
  
|<span data-ttu-id="5455c-108">파트</span><span class="sxs-lookup"><span data-stu-id="5455c-108">Part</span></span>|<span data-ttu-id="5455c-109">형식</span><span class="sxs-lookup"><span data-stu-id="5455c-109">Type</span></span>|<span data-ttu-id="5455c-110">설명</span><span class="sxs-lookup"><span data-stu-id="5455c-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="5455c-111">PART_SelectedContentHost</span><span class="sxs-lookup"><span data-stu-id="5455c-111">PART_SelectedContentHost</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="5455c-112">현재 선택 된 내용을 표시 하는 개체 <xref:System.Windows.Controls.TabItem>합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-112">The object that shows the content of the currently selected <xref:System.Windows.Controls.TabItem>.</span></span>|  
  
 <span data-ttu-id="5455c-113">만들 때 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.TabControl>, 서식 파일에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-113">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.TabControl>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="5455c-114">(의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목에 표시 됩니다는 <xref:System.Windows.Controls.TabControl>; <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-114">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.TabControl>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="5455c-115">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직계 자식이 없는 <xref:System.Windows.Controls.ScrollViewer>를 지정 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름, `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-115">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="tabcontrol-states"></a><span data-ttu-id="5455c-116">TabControl 상태</span><span class="sxs-lookup"><span data-stu-id="5455c-116">TabControl States</span></span>  
 <span data-ttu-id="5455c-117">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.TabControl> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-117">The following table lists the visual states for the <xref:System.Windows.Controls.TabControl> control.</span></span>  
  
|<span data-ttu-id="5455c-118">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="5455c-118">VisualState Name</span></span>|<span data-ttu-id="5455c-119">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="5455c-119">VisualStateGroup Name</span></span>|<span data-ttu-id="5455c-120">설명</span><span class="sxs-lookup"><span data-stu-id="5455c-120">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="5455c-121">보통</span><span class="sxs-lookup"><span data-stu-id="5455c-121">Normal</span></span>|<span data-ttu-id="5455c-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5455c-122">CommonStates</span></span>|<span data-ttu-id="5455c-123">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-123">The default state.</span></span>|  
|<span data-ttu-id="5455c-124">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5455c-124">Disabled</span></span>|<span data-ttu-id="5455c-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5455c-125">CommonStates</span></span>|<span data-ttu-id="5455c-126">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-126">The control is disabled.</span></span>|  
|<span data-ttu-id="5455c-127">유효</span><span class="sxs-lookup"><span data-stu-id="5455c-127">Valid</span></span>|<span data-ttu-id="5455c-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5455c-128">ValidationStates</span></span>|<span data-ttu-id="5455c-129">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5455c-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5455c-130">InvalidFocused</span></span>|<span data-ttu-id="5455c-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5455c-131">ValidationStates</span></span>|<span data-ttu-id="5455c-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5455c-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5455c-133">InvalidUnfocused</span></span>|<span data-ttu-id="5455c-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5455c-134">ValidationStates</span></span>|<span data-ttu-id="5455c-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tabitem-parts"></a><span data-ttu-id="5455c-136">TabItem 부분</span><span class="sxs-lookup"><span data-stu-id="5455c-136">TabItem Parts</span></span>  
 <span data-ttu-id="5455c-137"><xref:System.Windows.Controls.TabItem> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-137">The <xref:System.Windows.Controls.TabItem> control does not have any named parts.</span></span>  
  
## <a name="tabitem-states"></a><span data-ttu-id="5455c-138">TabItem 상태</span><span class="sxs-lookup"><span data-stu-id="5455c-138">TabItem States</span></span>  
 <span data-ttu-id="5455c-139">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.TabItem> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-139">The following table lists the visual states for the <xref:System.Windows.Controls.TabItem> control.</span></span>  
  
|<span data-ttu-id="5455c-140">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="5455c-140">VisualState Name</span></span>|<span data-ttu-id="5455c-141">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="5455c-141">VisualStateGroup Name</span></span>|<span data-ttu-id="5455c-142">설명</span><span class="sxs-lookup"><span data-stu-id="5455c-142">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="5455c-143">보통</span><span class="sxs-lookup"><span data-stu-id="5455c-143">Normal</span></span>|<span data-ttu-id="5455c-144">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5455c-144">CommonStates</span></span>|<span data-ttu-id="5455c-145">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-145">The default state.</span></span>|  
|<span data-ttu-id="5455c-146">MouseOver</span><span class="sxs-lookup"><span data-stu-id="5455c-146">MouseOver</span></span>|<span data-ttu-id="5455c-147">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5455c-147">CommonStates</span></span>|<span data-ttu-id="5455c-148">마우스 포인터가 컨트롤 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-148">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="5455c-149">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="5455c-149">Disabled</span></span>|<span data-ttu-id="5455c-150">CommonStates</span><span class="sxs-lookup"><span data-stu-id="5455c-150">CommonStates</span></span>|<span data-ttu-id="5455c-151">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-151">The control is disabled.</span></span>|  
|<span data-ttu-id="5455c-152">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="5455c-152">Focused</span></span>|<span data-ttu-id="5455c-153">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5455c-153">FocusStates</span></span>|<span data-ttu-id="5455c-154">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-154">The control has focus.</span></span>|  
|<span data-ttu-id="5455c-155">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="5455c-155">Unfocused</span></span>|<span data-ttu-id="5455c-156">FocusStates</span><span class="sxs-lookup"><span data-stu-id="5455c-156">FocusStates</span></span>|<span data-ttu-id="5455c-157">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-157">The control does not have focus.</span></span>|  
|<span data-ttu-id="5455c-158">선택함</span><span class="sxs-lookup"><span data-stu-id="5455c-158">Selected</span></span>|<span data-ttu-id="5455c-159">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="5455c-159">SelectionStates</span></span>|<span data-ttu-id="5455c-160">컨트롤을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-160">The control is selected.</span></span>|  
|<span data-ttu-id="5455c-161">선택 취소</span><span class="sxs-lookup"><span data-stu-id="5455c-161">Unselected</span></span>|<span data-ttu-id="5455c-162">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="5455c-162">SelectionStates</span></span>|<span data-ttu-id="5455c-163">컨트롤을 선택 하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-163">The control is not selected.</span></span>|  
|<span data-ttu-id="5455c-164">유효</span><span class="sxs-lookup"><span data-stu-id="5455c-164">Valid</span></span>|<span data-ttu-id="5455c-165">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5455c-165">ValidationStates</span></span>|<span data-ttu-id="5455c-166">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-166">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="5455c-167">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="5455c-167">InvalidFocused</span></span>|<span data-ttu-id="5455c-168">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5455c-168">ValidationStates</span></span>|<span data-ttu-id="5455c-169"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-169">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="5455c-170">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="5455c-170">InvalidUnfocused</span></span>|<span data-ttu-id="5455c-171">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="5455c-171">ValidationStates</span></span>|<span data-ttu-id="5455c-172"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-172">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tabcontrol-controltemplate-example"></a><span data-ttu-id="5455c-173">TabControl ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="5455c-173">TabControl ControlTemplate Example</span></span>  
 <span data-ttu-id="5455c-174">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.TabControl> 및 <xref:System.Windows.Controls.TabItem> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-174">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.TabControl> and <xref:System.Windows.Controls.TabItem> controls.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#TabControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tabcontrol.xaml#tabcontrol)]  
  
 <span data-ttu-id="5455c-175">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5455c-175">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="5455c-176">전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5455c-176">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5455c-177">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5455c-177">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="5455c-178">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="5455c-178">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="5455c-179">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5455c-179">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="5455c-180">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="5455c-180">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="5455c-181">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="5455c-181">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
