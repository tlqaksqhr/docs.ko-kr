---
title: "ToolTip 스타일 및 템플릿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ec946e7982983519a317ee1936e8584eef63479c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="09e9b-102">ToolTip 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="09e9b-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="09e9b-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Controls.ToolTip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="09e9b-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="09e9b-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09e9b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="09e9b-106">도구 설명 부분</span><span class="sxs-lookup"><span data-stu-id="09e9b-106">ToolTip Parts</span></span>  
 <span data-ttu-id="09e9b-107"><xref:System.Windows.Controls.ToolTip> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="09e9b-108">도구 설명 상태</span><span class="sxs-lookup"><span data-stu-id="09e9b-108">ToolTip States</span></span>  
 <span data-ttu-id="09e9b-109">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Controls.ToolTip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="09e9b-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="09e9b-110">VisualState Name</span></span>|<span data-ttu-id="09e9b-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="09e9b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="09e9b-112">설명</span><span class="sxs-lookup"><span data-stu-id="09e9b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="09e9b-113">Closed</span><span class="sxs-lookup"><span data-stu-id="09e9b-113">Closed</span></span>|<span data-ttu-id="09e9b-114">OpenStates</span><span class="sxs-lookup"><span data-stu-id="09e9b-114">OpenStates</span></span>|<span data-ttu-id="09e9b-115">기본 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-115">The default state.</span></span>|  
|<span data-ttu-id="09e9b-116">열기</span><span class="sxs-lookup"><span data-stu-id="09e9b-116">Open</span></span>|<span data-ttu-id="09e9b-117">OpenStates</span><span class="sxs-lookup"><span data-stu-id="09e9b-117">OpenStates</span></span>|<span data-ttu-id="09e9b-118"><xref:System.Windows.Controls.ToolTip> 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="09e9b-119">유효</span><span class="sxs-lookup"><span data-stu-id="09e9b-119">Valid</span></span>|<span data-ttu-id="09e9b-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="09e9b-120">ValidationStates</span></span>|<span data-ttu-id="09e9b-121">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="09e9b-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="09e9b-122">InvalidFocused</span></span>|<span data-ttu-id="09e9b-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="09e9b-123">ValidationStates</span></span>|<span data-ttu-id="09e9b-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="09e9b-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="09e9b-125">InvalidUnfocused</span></span>|<span data-ttu-id="09e9b-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="09e9b-126">ValidationStates</span></span>|<span data-ttu-id="09e9b-127"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="09e9b-128">도구 설명 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="09e9b-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="09e9b-129">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.ToolTip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="09e9b-130">앞의 예제에서는 다음 리소스를 하나 이상 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="09e9b-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="09e9b-131">전체 샘플을 보려면 [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09e9b-131">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e9b-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09e9b-132">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="09e9b-133">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="09e9b-133">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="09e9b-134">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="09e9b-134">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="09e9b-135">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="09e9b-135">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="09e9b-136">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="09e9b-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
