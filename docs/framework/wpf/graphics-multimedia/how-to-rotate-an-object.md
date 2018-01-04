---
title: "방법: 개체 회전"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b356ef1782ec5bba4f7288644a0802f029456bbf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="f6e7f-102">방법: 개체 회전</span><span class="sxs-lookup"><span data-stu-id="f6e7f-102">How to: Rotate an Object</span></span>
<span data-ttu-id="f6e7f-103">이 예제에서는 개체를 회전하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="f6e7f-104">이 예에서는 먼저 만듭니다는 <xref:System.Windows.Media.RotateTransform> 만든 다음 해당 <xref:System.Windows.Media.RotateTransform.Angle%2A> 각도입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="f6e7f-105">다음 예제에서는 회전는 <xref:System.Windows.Shapes.Polyline> 45도 왼쪽 위 모퉁이 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6e7f-106">예</span><span class="sxs-lookup"><span data-stu-id="f6e7f-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="f6e7f-107"><xref:System.Windows.Media.RotateTransform.CenterX%2A> 및 <xref:System.Windows.Media.RotateTransform.CenterY%2A> 의 속성은 <xref:System.Windows.Media.RotateTransform> 열리는데 회전 될 지점을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="f6e7f-108">이 중심점은 변환되는 요소의 좌표 공간으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="f6e7f-109">기본적으로 회전은 변환할 개체의 왼쪽 위 구석에 해당하는 (0,0)에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="f6e7f-110">회전 하는 다음 예제는 <xref:System.Windows.Shapes.Polyline> 개체를 시계 반대 방향으로 45도 지점 (25, 50)에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="f6e7f-111">다음 그림과 적용 한 결과 <xref:System.Windows.Media.Transform> 두 개체에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="f6e7f-112">![여러 중심점을 사용한 45도 회전](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="f6e7f-112">![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="f6e7f-113">서로 다른 회전 중심에서 45도로 회전하는 두 개체</span><span class="sxs-lookup"><span data-stu-id="f6e7f-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="f6e7f-114"><xref:System.Windows.Shapes.Polyline> 은 앞의 예제에는 <xref:System.Windows.UIElement>합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="f6e7f-115">적용 하는 경우는 <xref:System.Windows.Media.Transform> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 속성의는 <xref:System.Windows.UIElement>, 사용할 수 있습니다는 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 속성의 원본을 지정 하려면 모든 <xref:System.Windows.Media.Transform> 요소에 적용 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="f6e7f-116">때문에 <xref:System.Windows.UIElement.RenderTransformOrigin%2A> 상대 좌표를 사용 하는 속성, 크기로 알 수 없는 경우에 변환을 요소의 가운데에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="f6e7f-117">자세한 정보 및 예제 참조 [변환 사용 하 여 상대 값의 원본을 지정할](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="f6e7f-118">전체 샘플을 보려면 [2차원 변환 샘플](http://go.microsoft.com/fwlink/?LinkID=158252)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6e7f-118">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6e7f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6e7f-119">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 [<span data-ttu-id="f6e7f-120">Transform 개요</span><span class="sxs-lookup"><span data-stu-id="f6e7f-120">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="f6e7f-121">방법 항목</span><span class="sxs-lookup"><span data-stu-id="f6e7f-121">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
