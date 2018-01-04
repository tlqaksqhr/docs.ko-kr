---
title: "방법: 요소 기울이기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9da10e4eb6cf045c6c4936b76f847f21ea1495e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="d43d6-102">방법: 요소 기울이기</span><span class="sxs-lookup"><span data-stu-id="d43d6-102">How to: Skew an Element</span></span>
<span data-ttu-id="d43d6-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.SkewTransform> 요소 중심 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="d43d6-104">전단이라고도 하는 기울이기는 일관되지 않은 방식으로 좌표 공간을 늘리는 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="d43d6-105">일반적인 용도 중 하나는 <xref:System.Windows.Media.SkewTransform> 시뮬레이션 하는 데는 [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] 깊이 [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] depth in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objects.</span></span>  
  
 <span data-ttu-id="d43d6-106">사용 하 여는 <xref:System.Windows.Media.SkewTransform.CenterX%2A> 및 <xref:System.Windows.Media.SkewTransform.CenterY%2A> 중심을 지정 하는 속성의 지점는 <xref:System.Windows.Media.SkewTransform>합니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="d43d6-107">사용 하 여는 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 및 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 속성 x 축 및 y 축 기울기 각도 지정 하 고이 축에 따라 현재 좌표계를 왜곡 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="d43d6-108">기울이기 변환 효과 예측 하려면 다음을 고려해 야 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 원래 좌표계를 기준으로 x 축 값을 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="d43d6-109">따라서 프로그램 <xref:System.Windows.Media.SkewTransform.AngleX%2A> 가 30 인 y 축 원점 통과 30도 회전 하 고 x 축으로 해당 원본에서 30도 값 오차입니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="d43d6-110">마찬가지로, 한 <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30의 원점부터 30도 도형의 y 값을 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="d43d6-111">이것은 좌표 시스템을 x 또는 y축으로 30도만큼 변환(이동)하는 것과 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="d43d6-112">다음 예제에서는 45도 가로로 기울입니다는 <xref:System.Windows.Shapes.Rectangle> (0, 0)의 중심점부터 합니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d43d6-113">예</span><span class="sxs-lookup"><span data-stu-id="d43d6-113">Example</span></span>  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="d43d6-114">다음 예제에서는 45도 가로로 기울입니다는 <xref:System.Windows.Shapes.Rectangle> (25, 25 로부터) 중심점부터 합니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="d43d6-115">다음 예제에서는 45도 세로 기울입니다는 <xref:System.Windows.Shapes.Rectangle> (25, 25 로부터) 중심점부터 합니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="d43d6-116">다음 그림에서는 이 예제에서 사용되는 다양한 기울이기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d43d6-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="d43d6-117">![SkewTransform 예제](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="d43d6-117">![SkewTransform examples](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="d43d6-118">세 개의 SkewTransform 예제 그림</span><span class="sxs-lookup"><span data-stu-id="d43d6-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="d43d6-119">전체 샘플을 보려면 [2차원 변환 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d43d6-119">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d43d6-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d43d6-120">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [<span data-ttu-id="d43d6-121">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="d43d6-121">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="d43d6-122">방법 항목</span><span class="sxs-lookup"><span data-stu-id="d43d6-122">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
