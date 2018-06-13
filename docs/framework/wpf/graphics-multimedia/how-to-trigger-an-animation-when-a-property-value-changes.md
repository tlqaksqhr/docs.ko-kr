---
title: '방법: 속성 값이 변경될 때 애니메이션 트리거'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], starting when property values change
- triggering animation [WPF]
- Storyboards [WPF], starting when property values change
ms.assetid: 12399c21-0300-4f4f-9e3a-d92d9907e5f5
ms.openlocfilehash: f127f00445a587ee097faa6bed28e124690de10e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561319"
---
# <a name="how-to-trigger-an-animation-when-a-property-value-changes"></a><span data-ttu-id="641cc-102">방법: 속성 값이 변경될 때 애니메이션 트리거</span><span class="sxs-lookup"><span data-stu-id="641cc-102">How to: Trigger an Animation When a Property Value Changes</span></span>
<span data-ttu-id="641cc-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Trigger> 시작 하는 <xref:System.Windows.Media.Animation.Storyboard> 속성 값이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="641cc-103">This example shows how to use a <xref:System.Windows.Trigger> to start a <xref:System.Windows.Media.Animation.Storyboard> when a property value changes.</span></span> <span data-ttu-id="641cc-104">사용할 수는 <xref:System.Windows.Trigger> 내는 <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, 또는 <xref:System.Windows.DataTemplate>합니다.</span><span class="sxs-lookup"><span data-stu-id="641cc-104">You can use a <xref:System.Windows.Trigger> inside a <xref:System.Windows.Style>, <xref:System.Windows.Controls.ControlTemplate>, or <xref:System.Windows.DataTemplate>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="641cc-105">예제</span><span class="sxs-lookup"><span data-stu-id="641cc-105">Example</span></span>  
 <span data-ttu-id="641cc-106">다음 예제에서는 <xref:System.Windows.Trigger> 애니메이션 효과를 줄의 <xref:System.Windows.UIElement.Opacity%2A> 의 <xref:System.Windows.Controls.Button> 때 해당 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성은 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="641cc-106">The following example uses a <xref:System.Windows.Trigger> to animate the <xref:System.Windows.UIElement.Opacity%2A> of a <xref:System.Windows.Controls.Button> when its <xref:System.Windows.UIElement.IsMouseOver%2A> property becomes `true`.</span></span>  
  
 [!code-xaml[AnimatePropertyStoryboards#PropertyTriggerExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/AnimatePropertyStoryboards/XAML/PropertyTriggerExample.xaml#propertytriggerexample)]  
  
 <span data-ttu-id="641cc-107">속성에 의해 적용 된 애니메이션이 <xref:System.Windows.Trigger> 개체 보다 더 복잡 한 방식으로 작동 <xref:System.Windows.EventTrigger> 애니메이션이 나 애니메이션 사용 하 여 시작 <xref:System.Windows.Media.Animation.Storyboard> 메서드.</span><span class="sxs-lookup"><span data-stu-id="641cc-107">Animations applied by property <xref:System.Windows.Trigger> objects behave in a more complex fashion than <xref:System.Windows.EventTrigger> animations or animations started using <xref:System.Windows.Media.Animation.Storyboard> methods.</span></span>  <span data-ttu-id="641cc-108">"핸드 오프" 애니메이션이 있는 다른 정의 <xref:System.Windows.Trigger> 개체 하지만로 작성 <xref:System.Windows.EventTrigger> 및 애니메이션 메서드 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="641cc-108">They "handoff" with animations defined by other <xref:System.Windows.Trigger> objects, but compose with <xref:System.Windows.EventTrigger> and method-triggered animations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="641cc-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="641cc-109">See Also</span></span>  
 <xref:System.Windows.Trigger>  
 [<span data-ttu-id="641cc-110">속성 애니메이션 기술 개요</span><span class="sxs-lookup"><span data-stu-id="641cc-110">Property Animation Techniques Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)  
 [<span data-ttu-id="641cc-111">Storyboard 개요</span><span class="sxs-lookup"><span data-stu-id="641cc-111">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
