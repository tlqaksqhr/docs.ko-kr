---
title: "ProgressBar 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 475607381f16d7b42f26f12809a11d5eaf4e74bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="c6cd0-102">ProgressBar 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="c6cd0-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="c6cd0-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.ProgressBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="c6cd0-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="c6cd0-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="c6cd0-106">ProgressBar 부분</span><span class="sxs-lookup"><span data-stu-id="c6cd0-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="c6cd0-107">다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.ProgressBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="c6cd0-108">파트</span><span class="sxs-lookup"><span data-stu-id="c6cd0-108">Part</span></span>|<span data-ttu-id="c6cd0-109">형식</span><span class="sxs-lookup"><span data-stu-id="c6cd0-109">Type</span></span>|<span data-ttu-id="c6cd0-110">설명</span><span class="sxs-lookup"><span data-stu-id="c6cd0-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="c6cd0-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="c6cd0-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="c6cd0-112">진행률을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="c6cd0-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="c6cd0-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="c6cd0-114">진행률 표시기의 경로 정의 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="c6cd0-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="c6cd0-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="c6cd0-116">진행률 표시줄을 장식 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="c6cd0-117">진행률 표시줄 상태</span><span class="sxs-lookup"><span data-stu-id="c6cd0-117">ProgressBar States</span></span>  
 <span data-ttu-id="c6cd0-118">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.ProgressBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="c6cd0-119">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="c6cd0-119">VisualState Name</span></span>|<span data-ttu-id="c6cd0-120">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="c6cd0-120">VisualStateGroup Name</span></span>|<span data-ttu-id="c6cd0-121">설명</span><span class="sxs-lookup"><span data-stu-id="c6cd0-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="c6cd0-122">비활성화 상태</span><span class="sxs-lookup"><span data-stu-id="c6cd0-122">Determinate</span></span>|<span data-ttu-id="c6cd0-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c6cd0-123">CommonStates</span></span>|<span data-ttu-id="c6cd0-124"><xref:System.Windows.Controls.ProgressBar>에 따라 진행률 보고는 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="c6cd0-125">비활성화 상태</span><span class="sxs-lookup"><span data-stu-id="c6cd0-125">Indeterminate</span></span>|<span data-ttu-id="c6cd0-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="c6cd0-126">CommonStates</span></span>|<span data-ttu-id="c6cd0-127"><xref:System.Windows.Controls.ProgressBar>반복을 사용 하 여 제네릭 진행률을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="c6cd0-128">유효</span><span class="sxs-lookup"><span data-stu-id="c6cd0-128">Valid</span></span>|<span data-ttu-id="c6cd0-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c6cd0-129">ValidationStates</span></span>|<span data-ttu-id="c6cd0-130">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="c6cd0-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="c6cd0-131">InvalidFocused</span></span>|<span data-ttu-id="c6cd0-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c6cd0-132">ValidationStates</span></span>|<span data-ttu-id="c6cd0-133"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="c6cd0-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="c6cd0-134">InvalidUnfocused</span></span>|<span data-ttu-id="c6cd0-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="c6cd0-135">ValidationStates</span></span>|<span data-ttu-id="c6cd0-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="c6cd0-137">ProgressBar ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="c6cd0-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="c6cd0-138">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ProgressBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="c6cd0-139">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="c6cd0-140">전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6cd0-140">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6cd0-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6cd0-141">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="c6cd0-142">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="c6cd0-142">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="c6cd0-143">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c6cd0-143">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="c6cd0-144">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="c6cd0-144">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="c6cd0-145">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c6cd0-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
