---
title: "방법: 요소 또는 브러시의 불투명도에 애니메이션 효과 적용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- opacity [WPF], animating
- animation [WPF], Opacity property
ms.assetid: 572af23b-39dd-48d1-9db5-4bca56a4b3d3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 808d29292e176af8d3af1fc0f4a02c48ee05ea35
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-animate-the-opacity-of-an-element-or-brush"></a><span data-ttu-id="44585-102">방법: 요소 또는 브러시의 불투명도에 애니메이션 효과 적용</span><span class="sxs-lookup"><span data-stu-id="44585-102">How to: Animate the Opacity of an Element or Brush</span></span>
<span data-ttu-id="44585-103">페이드 아웃 프레임 워크 요소를 하려면 애니메이션을 적용할 수 해당 <xref:System.Windows.UIElement.Opacity%2A> 속성 또는 있습니다 애니메이션을 적용할 수는 <xref:System.Windows.Media.Brush.Opacity%2A> 속성은 <xref:System.Windows.Media.Brush> (또는 브러시) 칠할 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44585-103">To make a framework element fade in and out of view, you can animate its <xref:System.Windows.UIElement.Opacity%2A> property or you can animate the <xref:System.Windows.Media.Brush.Opacity%2A> property of the <xref:System.Windows.Media.Brush> (or brushes) used to paint it.</span></span> <span data-ttu-id="44585-104">하면 불투명도 요소에 애니메이션을 적용 하 고 자식 페이드 아웃, 하지만 페이드 요소의 부분에 대 한 좀 더 선택적 될 수 있습니다 요소를 그리는 데 사용 되는 브러시에 애니메이션을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44585-104">Animating the element's opacity makes it and its children fade in and out of view, but animating the brush used to paint the element enables you to be more selective about which portion of the element fades.</span></span> <span data-ttu-id="44585-105">예를 들어 단추의 배경을 그리는 데 사용 되는 브러시 불투명도 애니메이션을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44585-105">For example, you could animate the opacity of a brush used to paint a button's background.</span></span> <span data-ttu-id="44585-106">이 단추의 배경을 완전히 불투명 한 텍스트를 그대로 유지 하면서 현재 뷰를 페이드 인 / 아웃 하 리라 예상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44585-106">This would cause the button's background to fade in and out of view, while leaving its text fully opaque.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44585-107">애니메이션의 <xref:System.Windows.Media.Brush.Opacity%2A> 의 <xref:System.Windows.Media.Brush> 애니메이션 보다 성능상 이점이 <xref:System.Windows.UIElement.Opacity%2A> 요소의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="44585-107">Animating the <xref:System.Windows.Media.Brush.Opacity%2A> of a <xref:System.Windows.Media.Brush> provides performance benefits over animating the <xref:System.Windows.UIElement.Opacity%2A> property of an element.</span></span>  
  
 <span data-ttu-id="44585-108">다음 예제에서는 두 개의 단추는 페이드 아웃 되도록 애니메이션이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44585-108">In the following example, two buttons are animated so that they fade in and out of view.</span></span> <span data-ttu-id="44585-109">첫 번째의 불투명도 <xref:System.Windows.Controls.Button> 에서 애니메이션 효과가 적용 되어 `1.0` 를 `0.0` 위에 <xref:System.Windows.Media.Animation.Timeline.Duration%2A> 5 초입니다.</span><span class="sxs-lookup"><span data-stu-id="44585-109">The Opacity of the first <xref:System.Windows.Controls.Button> is animated from `1.0` to `0.0` over a <xref:System.Windows.Media.Animation.Timeline.Duration%2A> of five seconds.</span></span> <span data-ttu-id="44585-110">두 번째 단추는 또한 애니메이션 효과가 적용 되어, 하지만 SolidColorBrush의 불투명도 그리는 데 사용 되는 <xref:System.Windows.Controls.Control.Background%2A> 전체 단추의 불투명도 하지 않고 애니메이션 효과가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44585-110">The second button is also animated, but the Opacity of the SolidColorBrush used to paint its <xref:System.Windows.Controls.Control.Background%2A> is animated rather than the opacity of the entire button.</span></span> <span data-ttu-id="44585-111">예제를 실행 하는 경우 첫 번째 단추 완전히 페이드 인 보기를 두 번째 단추의 배경을 페이드 아웃 합니다.</span><span class="sxs-lookup"><span data-stu-id="44585-111">When the example is run, the first button completely fades in and out of view, while only the background of the second button fades in and out of view.</span></span> <span data-ttu-id="44585-112">텍스트와 테두리에 완전히 불투명 한이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44585-112">Its text and border remain fully opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44585-113">예제</span><span class="sxs-lookup"><span data-stu-id="44585-113">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/OpacityAnimationExample.xaml#10)]  
  
 <span data-ttu-id="44585-114">이 예제에서 코드는 생략 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44585-114">Code has been omitted from this example.</span></span> <span data-ttu-id="44585-115">전체 샘플의 불투명도 애니메이션 효과 적용 하는 방법도 설명는 <xref:System.Windows.Media.Color> 내는 <xref:System.Windows.Media.LinearGradientBrush>합니다.</span><span class="sxs-lookup"><span data-stu-id="44585-115">The full sample also shows how to animate the opacity of a <xref:System.Windows.Media.Color> within a <xref:System.Windows.Media.LinearGradientBrush>.</span></span>  <span data-ttu-id="44585-116">전체 샘플에 대 한 참조는 [불투명도 요소 예제에 애니메이션 적용](http://go.microsoft.com/fwlink/?LinkID=159968)합니다.</span><span class="sxs-lookup"><span data-stu-id="44585-116">For the full sample, see the [Animating the Opacity of an Element Sample](http://go.microsoft.com/fwlink/?LinkID=159968).</span></span>
