---
title: "ListView 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ListView
- states [WPF], ListView
- ControlTemplate [WPF], ListView
- styles [WPF], ListView
- ListView [WPF], styles and templates
- templates [WPF], ListView
ms.assetid: d2387356-2171-4785-822a-7247e024b4ee
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9dc8de9fd1452b389cbba7257440fcd7175fbd7c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="listview-styles-and-templates"></a><span data-ttu-id="d153f-102">ListView 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d153f-102">ListView Styles and Templates</span></span>
<span data-ttu-id="d153f-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ListView> control.</span></span> <span data-ttu-id="d153f-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d153f-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d153f-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="listview-parts"></a><span data-ttu-id="d153f-106">ListView 부분</span><span class="sxs-lookup"><span data-stu-id="d153f-106">ListView Parts</span></span>  
 <span data-ttu-id="d153f-107"><xref:System.Windows.Controls.ListView> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-107">The <xref:System.Windows.Controls.ListView> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="d153f-108">만들 때 한 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ListView>, 서식 파일에 포함 될 수 있습니다는 <xref:System.Windows.Controls.ItemsPresenter> 내는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ListView>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="d153f-109">(의 <xref:System.Windows.Controls.ItemsPresenter> 각 항목에 표시 됩니다는 <xref:System.Windows.Controls.ListView>; <xref:System.Windows.Controls.ScrollViewer> 컨트롤 내에서 스크롤할 수)입니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ListView>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="d153f-110">경우는 <xref:System.Windows.Controls.ItemsPresenter> 의 직계 자식이 없는 <xref:System.Windows.Controls.ScrollViewer>를 지정 해야 합니다는 <xref:System.Windows.Controls.ItemsPresenter> 이름, `ItemsPresenter`합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="listview-states"></a><span data-ttu-id="d153f-111">ListView 상태</span><span class="sxs-lookup"><span data-stu-id="d153f-111">ListView States</span></span>  
 <span data-ttu-id="d153f-112">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-112">The following table lists the visual states for the <xref:System.Windows.Controls.ListView> control.</span></span>  
  
|<span data-ttu-id="d153f-113">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="d153f-113">VisualState Name</span></span>|<span data-ttu-id="d153f-114">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="d153f-114">VisualStateGroup Name</span></span>|<span data-ttu-id="d153f-115">설명</span><span class="sxs-lookup"><span data-stu-id="d153f-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d153f-116">유효</span><span class="sxs-lookup"><span data-stu-id="d153f-116">Valid</span></span>|<span data-ttu-id="d153f-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d153f-117">ValidationStates</span></span>|<span data-ttu-id="d153f-118">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d153f-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d153f-119">InvalidFocused</span></span>|<span data-ttu-id="d153f-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d153f-120">ValidationStates</span></span>|<span data-ttu-id="d153f-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d153f-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d153f-122">InvalidUnfocused</span></span>|<span data-ttu-id="d153f-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d153f-123">ValidationStates</span></span>|<span data-ttu-id="d153f-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="listviewitem-parts"></a><span data-ttu-id="d153f-125">ListViewItem 부분</span><span class="sxs-lookup"><span data-stu-id="d153f-125">ListViewItem Parts</span></span>  
 <span data-ttu-id="d153f-126"><xref:System.Windows.Controls.ListViewItem> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-126">The <xref:System.Windows.Controls.ListViewItem> control does not have any named parts.</span></span>  
  
## <a name="listviewitem-states"></a><span data-ttu-id="d153f-127">ListViewItem 상태</span><span class="sxs-lookup"><span data-stu-id="d153f-127">ListViewItem States</span></span>  
 <span data-ttu-id="d153f-128">다음 표에서에 대 한 상태를 나열는 <xref:System.Windows.Controls.ListViewItem> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-128">The following table lists the states for the <xref:System.Windows.Controls.ListViewItem> control.</span></span>  
  
|<span data-ttu-id="d153f-129">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="d153f-129">VisualState Name</span></span>|<span data-ttu-id="d153f-130">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="d153f-130">VisualStateGroup Name</span></span>|<span data-ttu-id="d153f-131">설명</span><span class="sxs-lookup"><span data-stu-id="d153f-131">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d153f-132">보통</span><span class="sxs-lookup"><span data-stu-id="d153f-132">Normal</span></span>|<span data-ttu-id="d153f-133">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d153f-133">CommonStates</span></span>|<span data-ttu-id="d153f-134">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-134">The default state.</span></span>|  
|<span data-ttu-id="d153f-135">사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d153f-135">Disabled</span></span>|<span data-ttu-id="d153f-136">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d153f-136">CommonStates</span></span>|<span data-ttu-id="d153f-137">컨트롤이 비활성화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-137">The control is disabled.</span></span>|  
|<span data-ttu-id="d153f-138">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d153f-138">MouseOver</span></span>|<span data-ttu-id="d153f-139">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d153f-139">CommonStates</span></span>|<span data-ttu-id="d153f-140">마우스 포인터가 <xref:System.Windows.Controls.ComboBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-140">The mouse pointer is over the <xref:System.Windows.Controls.ComboBox> control.</span></span>|  
|<span data-ttu-id="d153f-141">포커스 있음</span><span class="sxs-lookup"><span data-stu-id="d153f-141">Focused</span></span>|<span data-ttu-id="d153f-142">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d153f-142">FocusStates</span></span>|<span data-ttu-id="d153f-143">컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-143">The control has focus.</span></span>|  
|<span data-ttu-id="d153f-144">포커스 없음</span><span class="sxs-lookup"><span data-stu-id="d153f-144">Unfocused</span></span>|<span data-ttu-id="d153f-145">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d153f-145">FocusStates</span></span>|<span data-ttu-id="d153f-146">컨트롤에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-146">The control does not have focus.</span></span>|  
|<span data-ttu-id="d153f-147">선택함</span><span class="sxs-lookup"><span data-stu-id="d153f-147">Selected</span></span>|<span data-ttu-id="d153f-148">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="d153f-148">SelectionStates</span></span>|<span data-ttu-id="d153f-149">항목이 현재 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-149">The item is currently selected.</span></span>|  
|<span data-ttu-id="d153f-150">선택 취소</span><span class="sxs-lookup"><span data-stu-id="d153f-150">Unselected</span></span>|<span data-ttu-id="d153f-151">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="d153f-151">SelectionStates</span></span>|<span data-ttu-id="d153f-152">항목이 선택되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-152">The item is not selected.</span></span>|  
|<span data-ttu-id="d153f-153">SelectedUnfocused</span><span class="sxs-lookup"><span data-stu-id="d153f-153">SelectedUnfocused</span></span>|<span data-ttu-id="d153f-154">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="d153f-154">SelectionStates</span></span>|<span data-ttu-id="d153f-155">항목이 선택되었지만 항목에 포커스가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-155">The item is selected, but does not have focus.</span></span>|  
|<span data-ttu-id="d153f-156">유효</span><span class="sxs-lookup"><span data-stu-id="d153f-156">Valid</span></span>|<span data-ttu-id="d153f-157">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d153f-157">ValidationStates</span></span>|<span data-ttu-id="d153f-158">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-158">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d153f-159">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d153f-159">InvalidFocused</span></span>|<span data-ttu-id="d153f-160">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d153f-160">ValidationStates</span></span>|<span data-ttu-id="d153f-161"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-161">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d153f-162">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d153f-162">InvalidUnfocused</span></span>|<span data-ttu-id="d153f-163">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d153f-163">ValidationStates</span></span>|<span data-ttu-id="d153f-164"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-164">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="listview-controltemplate-examples"></a><span data-ttu-id="d153f-165">ListView ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="d153f-165">ListView ControlTemplate Examples</span></span>  
 <span data-ttu-id="d153f-166">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ListView> 컨트롤과 연결 된 해당 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-166">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ListView> control and its associated types.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ListView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listview.xaml#listview)]  
  
 <span data-ttu-id="d153f-167"><xref:System.Windows.Controls.ControlTemplate> 예제는 다음 리소스 중 하나 이상을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d153f-167">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d153f-168">전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d153f-168">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d153f-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d153f-169">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="d153f-170">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d153f-170">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="d153f-171">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d153f-171">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="d153f-172">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="d153f-172">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d153f-173">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="d153f-173">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
