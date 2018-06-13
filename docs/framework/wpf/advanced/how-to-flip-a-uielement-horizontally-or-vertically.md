---
title: '방법: UIElement를 좌우 또는 상하 대칭 이동'
ms.date: 03/30/2017
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
ms.openlocfilehash: 89dcf668f1fe361480dabdab227a35ea40c344a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544397"
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="5230d-102">방법: UIElement를 좌우 또는 상하 대칭 이동</span><span class="sxs-lookup"><span data-stu-id="5230d-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="5230d-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ScaleTransform> 대칭는 <xref:System.Windows.UIElement> 가로 또는 세로로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="5230d-104">이 예제에서는 <xref:System.Windows.Controls.Button> 컨트롤 (의 형식을 <xref:System.Windows.UIElement>) 적용 하 여 대칭 이동는 <xref:System.Windows.Media.ScaleTransform> 를 해당 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5230d-105">예제</span><span class="sxs-lookup"><span data-stu-id="5230d-105">Example</span></span>  
 <span data-ttu-id="5230d-106">다음 그림에는 대칭 이동 하려면 단추 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="5230d-107">![변형이 없는 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="5230d-107">![A button with no transform](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="5230d-108">UIElement 대칭 이동</span><span class="sxs-lookup"><span data-stu-id="5230d-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="5230d-109">다음 단추를 생성 하는 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="5230d-110">예제</span><span class="sxs-lookup"><span data-stu-id="5230d-110">Example</span></span>  
 <span data-ttu-id="5230d-111">단추를 가로로 대칭 이동 하려면 만듭니다는 <xref:System.Windows.Media.ScaleTransform> 설정 하 고 해당 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 속성을-1입니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="5230d-112">적용 된 <xref:System.Windows.Media.ScaleTransform> 단추의에 <xref:System.Windows.UIElement.RenderTransform%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="5230d-113">![단추에 대 한 가로 대칭 이동 된 &#40;0, 0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="5230d-113">![A button flipped horizontally about &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="5230d-114">ScaleTransform을 적용 한 후 단추</span><span class="sxs-lookup"><span data-stu-id="5230d-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="5230d-115">예제</span><span class="sxs-lookup"><span data-stu-id="5230d-115">Example</span></span>  
 <span data-ttu-id="5230d-116">앞의 그림에서 볼 수 있습니다, 단추 대칭 되는 이동 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="5230d-117">단추 왼쪽된 위 모서리에서 대칭 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="5230d-118">적용 하려는 위치에 있는 단추를 대칭 이동 된 <xref:System.Windows.Media.ScaleTransform> 센터에 모퉁이가 아니라 합니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="5230d-119">쉽게 적용할 수는 <xref:System.Windows.Media.ScaleTransform> 센터 단추의 설정 하는 단추에 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성을 0.5, 0.5입니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="5230d-120">![가운데를 중심으로 가로 대칭 이동 된 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="5230d-120">![A button flipped horizontally about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="5230d-121">0.5, RenderTransformOrigin 되는 단추 0.5</span><span class="sxs-lookup"><span data-stu-id="5230d-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="5230d-122">예제</span><span class="sxs-lookup"><span data-stu-id="5230d-122">Example</span></span>  
 <span data-ttu-id="5230d-123">단추를 세로로 대칭 이동 하려면 설정는 <xref:System.Windows.Media.ScaleTransform> 개체의 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 속성 대신 해당 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="5230d-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="5230d-124">![가운데를 중심으로 세로 대칭 이동 된 단추](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="5230d-124">![A button flipped vertically about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="5230d-125">세로로 대칭 이동 된 단추</span><span class="sxs-lookup"><span data-stu-id="5230d-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5230d-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5230d-126">See Also</span></span>  
 [<span data-ttu-id="5230d-127">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="5230d-127">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
