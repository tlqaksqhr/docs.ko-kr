---
title: "ScrollViewer 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ScrollViewer
- states [WPF], ScrollViewer
- styles [WPF], ScrollViewer
- templates [WPF], ScrollViewer
- ControlTemplate [WPF], ScrollViewer
- ScrollViewer [WPF], styles and templates
ms.assetid: dffdd822-ae69-4946-abaf-710860cd65b2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 74f8a693a143e1c6788dd79a1c1bbd1954f8cfd0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="scrollviewer-styles-and-templates"></a><span data-ttu-id="7f01e-102">ScrollViewer 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7f01e-102">ScrollViewer Styles and Templates</span></span>
<span data-ttu-id="7f01e-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span> <span data-ttu-id="7f01e-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7f01e-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f01e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollviewer-parts"></a><span data-ttu-id="7f01e-106">ScrollViewer 부분</span><span class="sxs-lookup"><span data-stu-id="7f01e-106">ScrollViewer Parts</span></span>  
 <span data-ttu-id="7f01e-107">다음 표에서 명명된 된 요소를 나열는 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-107">The following table lists the named parts for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="7f01e-108">파트</span><span class="sxs-lookup"><span data-stu-id="7f01e-108">Part</span></span>|<span data-ttu-id="7f01e-109">형식</span><span class="sxs-lookup"><span data-stu-id="7f01e-109">Type</span></span>|<span data-ttu-id="7f01e-110">설명</span><span class="sxs-lookup"><span data-stu-id="7f01e-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7f01e-111">PART_ScrollContentPresenter</span><span class="sxs-lookup"><span data-stu-id="7f01e-111">PART_ScrollContentPresenter</span></span>|<xref:System.Windows.Controls.ScrollContentPresenter>|<span data-ttu-id="7f01e-112">콘텐츠에 대 한 자리 표시자는 <xref:System.Windows.Controls.ScrollViewer>합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-112">The placeholder for content in the <xref:System.Windows.Controls.ScrollViewer>.</span></span>|  
|<span data-ttu-id="7f01e-113">PART_HorizontalScrollBar</span><span class="sxs-lookup"><span data-stu-id="7f01e-113">PART_HorizontalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="7f01e-114"><xref:System.Windows.Controls.Primitives.ScrollBar> 콘텐츠를 가로로 스크롤할 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-114">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content horizontally.</span></span>|  
|<span data-ttu-id="7f01e-115">PART_VerticalScrollBar</span><span class="sxs-lookup"><span data-stu-id="7f01e-115">PART_VerticalScrollBar</span></span>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="7f01e-116"><xref:System.Windows.Controls.Primitives.ScrollBar> 콘텐츠를 세로로 스크롤할 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-116">The <xref:System.Windows.Controls.Primitives.ScrollBar> used to scroll the content vertically.</span></span>|  
  
## <a name="scrollviewer-states"></a><span data-ttu-id="7f01e-117">ScrollViewer 상태</span><span class="sxs-lookup"><span data-stu-id="7f01e-117">ScrollViewer States</span></span>  
 <span data-ttu-id="7f01e-118">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-118">The following table lists the visual states for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
|<span data-ttu-id="7f01e-119">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="7f01e-119">VisualState Name</span></span>|<span data-ttu-id="7f01e-120">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="7f01e-120">VisualStateGroup Name</span></span>|<span data-ttu-id="7f01e-121">설명</span><span class="sxs-lookup"><span data-stu-id="7f01e-121">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7f01e-122">유효</span><span class="sxs-lookup"><span data-stu-id="7f01e-122">Valid</span></span>|<span data-ttu-id="7f01e-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7f01e-123">ValidationStates</span></span>|<span data-ttu-id="7f01e-124">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-124">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7f01e-125">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7f01e-125">InvalidFocused</span></span>|<span data-ttu-id="7f01e-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7f01e-126">ValidationStates</span></span>|<span data-ttu-id="7f01e-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7f01e-128">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7f01e-128">InvalidUnfocused</span></span>|<span data-ttu-id="7f01e-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7f01e-129">ValidationStates</span></span>|<span data-ttu-id="7f01e-130"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-130">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="scrollviewer-controltemplate-example"></a><span data-ttu-id="7f01e-131">ScrollViewer ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="7f01e-131">ScrollViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="7f01e-132">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-132">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollviewer.xaml#scrollviewer)]  
  
 <span data-ttu-id="7f01e-133">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f01e-133">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7f01e-134">전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f01e-134">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f01e-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f01e-135">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="7f01e-136">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7f01e-136">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="7f01e-137">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7f01e-137">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="7f01e-138">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="7f01e-138">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="7f01e-139">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="7f01e-139">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
