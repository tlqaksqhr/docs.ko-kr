---
title: "방법: 스타일에 애니메이션 효과 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], properties [WPF], within styles
- styles [WPF], animating properties within
ms.assetid: 6a791f3d-6b1f-4972-a2f9-35880bcfd954
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2aabe24b77a9016b5b8119646c80ea84eb73acb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-in-a-style"></a><span data-ttu-id="7aee2-102">방법: 스타일에 애니메이션 효과 적용</span><span class="sxs-lookup"><span data-stu-id="7aee2-102">How to: Animate in a Style</span></span>
<span data-ttu-id="7aee2-103">이 예에서는 스타일 내에서 속성에 애니메이션을 적용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-103">This example shows how to animate properties within a style.</span></span> <span data-ttu-id="7aee2-104">애니메이션 스타일 적용을 스타일이 정의 된 프레임 워크 요소만 직접 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-104">When animating within a style, only the framework element for which the style is defined can be targeted directly.</span></span> <span data-ttu-id="7aee2-105">Freezable 개체를 대상으로 하면 해야 "dot 다운" 스타일의 요소 속성에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-105">To target a freezable object, you must "dot down" from a property of the styled element.</span></span>  
  
 <span data-ttu-id="7aee2-106">다음 예제에서는 여러 개의 애니메이션 스타일 내에서 정의 되 고에 적용 한 <xref:System.Windows.Controls.Button>합니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-106">In the following example, several animations are defined within a style and applied to a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="7aee2-107">부분적으로 반투명 / 뒤에 불투명에서 사라지기 단추 위로 마우스를 이동할 때 다시, 반복적으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-107">When the user moves the mouse over the button, it fades from opaque to partially translucent and back again, repeatedly.</span></span> <span data-ttu-id="7aee2-108">단추 밖으로 마우스를 이동할 때 완전히 불투명 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-108">When the user moves the mouse off the button, it becomes completely opaque.</span></span> <span data-ttu-id="7aee2-109">단추를 클릭할 때 배경색을 흰색 다시 주황색에서 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-109">When the button is clicked, its background color changes from orange to white and back again.</span></span> <span data-ttu-id="7aee2-110">때문에 <xref:System.Windows.Media.SolidColorBrush> 그리는 데 사용 되는 단추를 직접 대상이 될 수 없습니다, 단추의에서 아래로 것으로 액세스 하는 것 <xref:System.Windows.Controls.Control.Background%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-110">Because the <xref:System.Windows.Media.SolidColorBrush> used to paint the button can't be targeted directly, it is accessed by dotting down from the button's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7aee2-111">예</span><span class="sxs-lookup"><span data-stu-id="7aee2-111">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StyleStoryboardsExample.xaml#21)]  
  
 <span data-ttu-id="7aee2-112">Note 스타일 내에서 애니메이션을 적용할 때는 수 있다는 것에 존재 하지 않는 대상 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-112">Note that when animating within a style, it's possible to target objects that don't exist.</span></span> <span data-ttu-id="7aee2-113">예를 들어, 다음을 사용 하 여 스타일은 <xref:System.Windows.Media.SolidColorBrush> 이 단추의 배경 속성을 설정 하지만 특정 지점 스타일을 재정의 하 고 단추의 배경을으로 설정 된 한 <xref:System.Windows.Media.LinearGradientBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-113">For example, suppose your style uses a <xref:System.Windows.Media.SolidColorBrush> to set a Button's background property, but at some point the style is overridden and the button's background is set with a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="7aee2-114">애니메이션 효과 적용 하는 <xref:System.Windows.Media.SolidColorBrush> ; 예외가 발생 하지 애니메이션만 자동으로 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-114">Trying to animate the <xref:System.Windows.Media.SolidColorBrush> won't throw an exception; the animation will simply fail silently.</span></span>  
  
 <span data-ttu-id="7aee2-115">스토리 보드 대상 지정 구문에 대 한 자세한 내용은 참조는 [적기](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-115">Fore more information about storyboard targeting syntax, see the [Storyboards Overview](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).</span></span> <span data-ttu-id="7aee2-116">애니메이션에 대 한 자세한 내용은 참조는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-116">For more information about animation, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="7aee2-117">스타일에 대 한 자세한 내용은 참조는 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7aee2-117">For more information about styles, see the [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>
