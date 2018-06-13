---
title: Window 스타일 및 템플릿
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Window
- templates [WPF], Window
- styles [WPF], Window
- ControlTemplate [WPF], Window
- Window [WPF], styles and templates
- states [WPF], Window
ms.assetid: 2dfdf025-347b-4342-bf28-95206c273f35
ms.openlocfilehash: 4704bc7e51c10af79d39e7c6ea9013e12ec22d4c
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34456707"
---
# <a name="window-styles-and-templates"></a><span data-ttu-id="35a7b-102">Window 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="35a7b-102">Window Styles and Templates</span></span>
<span data-ttu-id="35a7b-103">이 항목에서는 스타일 및 서식 파일에 대 한 설명의 <xref:System.Windows.Window> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a7b-103">This topic describes the styles and templates for the <xref:System.Windows.Window> control.</span></span> <span data-ttu-id="35a7b-104">기본값을 수정할 수 <xref:System.Windows.Controls.ControlTemplate> 고유한 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a7b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="35a7b-105">자세한 내용은 [ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35a7b-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="window-parts"></a><span data-ttu-id="35a7b-106">창 부분</span><span class="sxs-lookup"><span data-stu-id="35a7b-106">Window Parts</span></span>  
 <span data-ttu-id="35a7b-107"><xref:System.Windows.Window> 컨트롤에는 명명된 된 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a7b-107">The <xref:System.Windows.Window> control does not have any named parts.</span></span>  
  
## <a name="window-states"></a><span data-ttu-id="35a7b-108">창 상태</span><span class="sxs-lookup"><span data-stu-id="35a7b-108">Window States</span></span>  
 <span data-ttu-id="35a7b-109">다음 표에서 시각적 상태를 나열는 <xref:System.Windows.Window> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a7b-109">The following table lists the visual states for the <xref:System.Windows.Window> control.</span></span>  
  
|<span data-ttu-id="35a7b-110">VisualState 이름</span><span class="sxs-lookup"><span data-stu-id="35a7b-110">VisualState Name</span></span>|<span data-ttu-id="35a7b-111">VisualStateGroup 이름</span><span class="sxs-lookup"><span data-stu-id="35a7b-111">VisualStateGroup Name</span></span>|<span data-ttu-id="35a7b-112">설명</span><span class="sxs-lookup"><span data-stu-id="35a7b-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="35a7b-113">유효</span><span class="sxs-lookup"><span data-stu-id="35a7b-113">Valid</span></span>|<span data-ttu-id="35a7b-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="35a7b-114">ValidationStates</span></span>|<span data-ttu-id="35a7b-115">컨트롤이 사용 하는 <xref:System.Windows.Controls.Validation> 클래스 및 <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="35a7b-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="35a7b-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="35a7b-116">InvalidFocused</span></span>|<span data-ttu-id="35a7b-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="35a7b-117">ValidationStates</span></span>|<span data-ttu-id="35a7b-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35a7b-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="35a7b-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="35a7b-119">InvalidUnfocused</span></span>|<span data-ttu-id="35a7b-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="35a7b-120">ValidationStates</span></span>|<span data-ttu-id="35a7b-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> 연결 된 속성을 `true` 가 컨트롤에 포커스가 없으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a7b-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="window-controltemplate-example"></a><span data-ttu-id="35a7b-122">창 ControlTemplate 예제</span><span class="sxs-lookup"><span data-stu-id="35a7b-122">Window ControlTemplate Example</span></span>  
 <span data-ttu-id="35a7b-123">다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Window> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a7b-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Window> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Window](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/window.xaml#window)]  
  
 <span data-ttu-id="35a7b-124"><xref:System.Windows.Controls.ControlTemplate> 다음 리소스 중 하나 이상 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="35a7b-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ResizeGrip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/resizegrip.xaml#resizegrip)]  
[!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="35a7b-125">전체 샘플을 보려면 [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating)(ControlTemplate으로 스타일 지정 샘플)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35a7b-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35a7b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35a7b-126">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="35a7b-127">Control 스타일 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="35a7b-127">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="35a7b-128">컨트롤 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="35a7b-128">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="35a7b-129">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="35a7b-129">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="35a7b-130">ControlTemplate을 만들어 기존 컨트롤의 모양 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="35a7b-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
