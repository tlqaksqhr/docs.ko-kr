---
title: "방법: FrameworkElement의 크기에 애니메이션 효과 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], FrameworkElement size
- FrameworkElement [WPF], animating size of
ms.assetid: d4cd5a13-c20d-4a6f-a2ba-14f2c9ce4cef
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 17882494e48c5d692c8a774e6d77408557976c71
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-the-size-of-a-frameworkelement"></a><span data-ttu-id="58db2-102">방법: FrameworkElement의 크기에 애니메이션 효과 적용</span><span class="sxs-lookup"><span data-stu-id="58db2-102">How to: Animate the Size of a FrameworkElement</span></span>
<span data-ttu-id="58db2-103">크기를 애니메이션 효과를 주는 <xref:System.Windows.FrameworkElement>, 애니메이션을 적용할 수 있거나 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성이 나 사용 하 여 애니메이션된 <xref:System.Windows.Media.ScaleTransform>합니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-103">To animate the size of a <xref:System.Windows.FrameworkElement>, you can either animate its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties or use an animated <xref:System.Windows.Media.ScaleTransform>.</span></span>  
  
 <span data-ttu-id="58db2-104">다음 예제에서 이러한 두 방법을 사용 하 여 두 단추의 크기 애니메이션 효과 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-104">In the following example animates the size of two buttons using these two approaches.</span></span> <span data-ttu-id="58db2-105">한 개의 단추에 애니메이션을 적용 하 여 크기를 조정할 해당 <xref:System.Windows.FrameworkElement.Width%2A> 속성과 다른 애니메이션을 적용 하 여 크기가 조정 됩니다는 <xref:System.Windows.Media.ScaleTransform> 적용할 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-105">One button is resized by animating its <xref:System.Windows.FrameworkElement.Width%2A> property and another is resized by animating a <xref:System.Windows.Media.ScaleTransform> applied to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span> <span data-ttu-id="58db2-106">각 단추에는 몇 가지 텍스트가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-106">Each button contains some text.</span></span> <span data-ttu-id="58db2-107">처음에 텍스트가 표시 되는 두 단추가 모두에서 동일 하 게 되지만 두 번째 단추의 텍스트 왜곡 단추의 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-107">Initially, the text appears the same in both buttons, but as the buttons are resized, the text in the second button becomes distorted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58db2-108">예제</span><span class="sxs-lookup"><span data-stu-id="58db2-108">Example</span></span>  
 [!code-xaml[transformanimations_snip#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/AnimatingSizeExample.xaml#1)]  
  
 <span data-ttu-id="58db2-109">요소를 변형 하면 전체 요소와 해당 내용을 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-109">When you transform an element, the entire element and its contents are transformed.</span></span> <span data-ttu-id="58db2-110">첫 번째 단추의 경우 처럼 요소의 크기를 직접 변경 하는 경우 요소의 콘텐츠 크기가 조정 되지 않습니다 해당 크기 및 위치는 부모 요소의 크기에 따라 하지 않는 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-110">When you directly alter the size of an element, as in the case of the first button, the element's contents are not resized unless their size and position depend on the size of their parent element.</span></span>  
  
 <span data-ttu-id="58db2-111">애니메이션된에 변환을 적용 하 여 요소의 크기를 애니메이션 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성에 애니메이션을 보다 나은 성능을 제공 해당 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 를 직접 때문에 <xref:System.Windows.UIElement.RenderTransform%2A> 속성 레이아웃 단계를 트리거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-111">Animating the size of an element by applying an animated transform to its <xref:System.Windows.UIElement.RenderTransform%2A> property provides better performance than animated its <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> directly, because the <xref:System.Windows.UIElement.RenderTransform%2A> property does not trigger a layout pass.</span></span>  
  
 <span data-ttu-id="58db2-112">속성에 애니메이션을 적용 하는 방법에 대 한 자세한 내용은 참조는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-112">For more information about animating properties, see the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span> <span data-ttu-id="58db2-113">변환에 대 한 자세한 내용은 참조는 [변환 개요](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="58db2-113">For more information about transforms, see the [Transforms Overview](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).</span></span>
