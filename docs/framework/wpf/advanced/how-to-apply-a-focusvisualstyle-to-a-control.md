---
title: "방법: 컨트롤에 FocusVisualStyle 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 41895974b7e6c128d979e362f2dcef1c68e0a5c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="a0a33-102">방법: 컨트롤에 FocusVisualStyle 적용</span><span class="sxs-lookup"><span data-stu-id="a0a33-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="a0a33-103">이 예제에서는 리소스에서 포커스 비주얼 스타일을 만들고 컨트롤에 스타일을 적용 하는 방법을 보여 줍니다. 사용 하는 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a33-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0a33-104">예</span><span class="sxs-lookup"><span data-stu-id="a0a33-104">Example</span></span>  
 <span data-ttu-id="a0a33-105">다음 예제에서는 컨트롤에 키보드에 포커스가 있을 때만 적용 되는 추가 컨트롤 구성을 만드는 스타일을 정의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a33-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="a0a33-106">사용 하 여 스타일을 정의 하 여 이렇게는 <xref:System.Windows.Controls.ControlTemplate>를 설정할 때 해당 스타일 리소스로 참조 한 다음는 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a33-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="a0a33-107">외부 테두리와 비슷한 사각형이 사각형 영역 바깥쪽에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a33-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="a0a33-108">스타일의 크기 조정에 사용 하 여을 수정 하지 않은 <xref:System.Windows.FrameworkElement.ActualHeight%2A> 및 <xref:System.Windows.FrameworkElement.ActualWidth%2A> 포커스 비주얼 스타일이 적용 되는 사각형 컨트롤의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a33-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="a0a33-109">에 대해 음수 값을 설정 하는이 예제는 <xref:System.Windows.FrameworkElement.Margin%2A> 테두리 포커스가 있는 컨트롤 밖에 약간 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a33-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="a0a33-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> 은 가산적 제공 되는 모든 컨트롤 템플릿 스타일에 명시적 스타일 또는 테마 스타일;에서 컨트롤에 대 한 기본 스타일 여전히 만들 수 있습니다를 사용 하 여는 <xref:System.Windows.Controls.ControlTemplate> 해당 스타일을 설정 하 고는 <xref:System.Windows.FrameworkElement.Style%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a33-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="a0a33-111">비주얼 스타일 테마 또는 UI를 통해 지속적으로 사용 해야 하는 포커스 포커스 각 요소에 대해 다른 하나를 사용 하는 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a33-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="a0a33-112">자세한 내용은 참조 [컨트롤과 FocusVisualStyle에 포커스에 대 한 스타일 지정](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a33-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0a33-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0a33-113">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [<span data-ttu-id="a0a33-114">스타일 지정 및 템플릿</span><span class="sxs-lookup"><span data-stu-id="a0a33-114">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="a0a33-115">컨트롤의 포커스 스타일 지정 및 FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="a0a33-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
