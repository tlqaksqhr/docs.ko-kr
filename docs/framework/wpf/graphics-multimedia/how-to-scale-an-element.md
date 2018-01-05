---
title: "방법: 요소 배율 조정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling [WPF], elements
- graphics [WPF], scaling elements
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d2bff810dc9b44b25db93c8565da27acc4f0ccc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-scale-an-element"></a><span data-ttu-id="86157-102">방법: 요소 배율 조정</span><span class="sxs-lookup"><span data-stu-id="86157-102">How to: Scale an Element</span></span>
<span data-ttu-id="86157-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.ScaleTransform> 요소를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86157-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to scale an element.</span></span>  
  
 <span data-ttu-id="86157-104">사용 하 여는 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 및 <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 요소의 크기를 조정 하 여 사용자가 지정한 인수는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="86157-104">Use the <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> and <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> properties to resize the element by the factor you specify.</span></span> <span data-ttu-id="86157-105">예를 들어 한 <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> 원래 너비의 150%로 요소를 확장 하는 1.5의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="86157-105">For example, a <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> value of 1.5 stretches the element to 150 percent of its original width.</span></span> <span data-ttu-id="86157-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> 0.5의 50%가 요소의 높이 축소 합니다.</span><span class="sxs-lookup"><span data-stu-id="86157-106">A <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> value of 0.5 shrinks the height of an element by 50 percent.</span></span>  
  
 <span data-ttu-id="86157-107">사용 하 여는 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 크기 조정 작업의 가운데 있는 지점을 지정 하는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="86157-107">Use the <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> properties to specify the point that is the center of the scale operation.</span></span> <span data-ttu-id="86157-108">기본적으로는 <xref:System.Windows.Media.ScaleTransform> 사각형의 왼쪽 위 모퉁이에 해당 하는 지점 (0, 0)에 가운데 맞춤 합니다.</span><span class="sxs-lookup"><span data-stu-id="86157-108">By default, a <xref:System.Windows.Media.ScaleTransform> is centered at the point (0,0), which corresponds to the upper-left corner of the rectangle.</span></span> <span data-ttu-id="86157-109">이 인해의 요소를 이동 하 고 적용 하는 경우 때문에 더 크게 표시 되 게의 영향을 <xref:System.Windows.Media.Transform>, 해당 개체가 속한 있는 좌표 공간을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="86157-109">This has the effect of moving the element and also of making it appear larger, because when you apply a <xref:System.Windows.Media.Transform>, you change the coordinate space in which the object resides.</span></span>  
  
 <span data-ttu-id="86157-110">다음 예제에서는 한 <xref:System.Windows.Media.ScaleTransform> 50-여-50의 크기를 두 배로 <xref:System.Windows.Shapes.Rectangle>합니다.</span><span class="sxs-lookup"><span data-stu-id="86157-110">The following example uses a <xref:System.Windows.Media.ScaleTransform> to double the size of a 50-by-50 <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="86157-111"><xref:System.Windows.Media.ScaleTransform> 둘 다에 대해 0 (기본값)의 값은 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="86157-111">The <xref:System.Windows.Media.ScaleTransform> has a value of 0 (the default) for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86157-112">예</span><span class="sxs-lookup"><span data-stu-id="86157-112">Example</span></span>  
 [!code-xaml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 <span data-ttu-id="86157-113">일반적으로 설정 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A> 의 크기가 조정 되는 개체의 센터로: (<xref:System.Windows.FrameworkElement.Width%2A>/2,  <xref:System.Windows.FrameworkElement.Height%2A> /2).</span><span class="sxs-lookup"><span data-stu-id="86157-113">Typically, you set <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A> to the center of the object that is scaled: (<xref:System.Windows.FrameworkElement.Width%2A>/2, <xref:System.Windows.FrameworkElement.Height%2A>/2).</span></span>  
  
 <span data-ttu-id="86157-114">다음 예제에서는 다른 <xref:System.Windows.Shapes.Rectangle> 크기가; 두 배로 증가 하는 반면이 <xref:System.Windows.Media.ScaleTransform> 25 값 모두에 대 한이 <xref:System.Windows.Media.ScaleTransform.CenterX%2A> 및 <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, 사각형의 중앙에 해당 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="86157-114">The following example shows another <xref:System.Windows.Shapes.Rectangle> that is doubled in size; however, this <xref:System.Windows.Media.ScaleTransform> has a value of 25 for both <xref:System.Windows.Media.ScaleTransform.CenterX%2A> and <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, which corresponds to the center of the rectangle.</span></span>  
  
 [!code-xaml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 <span data-ttu-id="86157-115">다음 그림에서는 두 기능 간의 차이점을 보여 줍니다 <xref:System.Windows.Media.ScaleTransform> 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="86157-115">The following illustration shows the difference between the two <xref:System.Windows.Media.ScaleTransform> operations.</span></span> <span data-ttu-id="86157-116">점선은 크기 조정 전의 사각형 크기 및 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="86157-116">The dotted line shows the size and position of the rectangle before scaling.</span></span>  
  
 <span data-ttu-id="86157-117">![여러 중심점을 사용한 2x 배율 조정](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span><span class="sxs-lookup"><span data-stu-id="86157-117">![2x scales with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.gif "wcpsdk_graphicsmm_scalecenter")</span></span>  
<span data-ttu-id="86157-118">ScaleX 및 ScaleY 값은 같지만 중심은 다른 두 개의 ScaleTransform 작업</span><span class="sxs-lookup"><span data-stu-id="86157-118">Two ScaleTransform operations with identical ScaleX and ScaleY values but different centers</span></span>  
  
 <span data-ttu-id="86157-119">전체 샘플을 보려면 [2차원 변환 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86157-119">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86157-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86157-120">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.ScaleTransform>  
 [<span data-ttu-id="86157-121">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="86157-121">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="86157-122">방법 항목</span><span class="sxs-lookup"><span data-stu-id="86157-122">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
