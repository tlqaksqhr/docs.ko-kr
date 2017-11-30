---
title: "방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)"
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
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 47cafab505bcbab7008385393bbacf093e264cd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a><span data-ttu-id="f9221-102">방법: 경로를 따라 개체에 애니메이션 효과 주기(포인트 애니메이션)</span><span class="sxs-lookup"><span data-stu-id="f9221-102">How to: Animate an Object Along a Path (Point Animation)</span></span>
<span data-ttu-id="f9221-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 애니메이션 효과를 줄 개체는 <xref:System.Windows.Point> 곡선된 경로 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9221-103">This example shows how to use a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> object to animate a <xref:System.Windows.Point> along a curved path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9221-104">예제</span><span class="sxs-lookup"><span data-stu-id="f9221-104">Example</span></span>  
 <span data-ttu-id="f9221-105">다음 예제에서는 이동는 <xref:System.Windows.Media.EllipseGeometry> 에 정의 된 경로 따라는 <xref:System.Windows.Media.PathGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9221-105">The following example moves an <xref:System.Windows.Media.EllipseGeometry> along a path defined by a <xref:System.Windows.Media.PathGeometry>.</span></span> <span data-ttu-id="f9221-106">타원 기 하 도형의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성을는 <xref:System.Windows.Point> ; 애니메이션 효과 주기 있습니다 타원 기를 이동 하려면 해당 위치를 지정, 값의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9221-106">The ellipse geometry's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property, which takes a <xref:System.Windows.Point> value, specifies its position; to move the ellipse geometry, you animate its <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span> <span data-ttu-id="f9221-107">이 예제에서는 사용는 <xref:System.Windows.Media.Animation.PointAnimationUsingPath> 애니메이션 효과를 줄의 <xref:System.Windows.Media.EllipseGeometry> 개체의 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f9221-107">The example uses a <xref:System.Windows.Media.Animation.PointAnimationUsingPath> to animate the <xref:System.Windows.Media.EllipseGeometry> object's <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 <span data-ttu-id="f9221-108">전체 샘플을 참조 하십시오. [경로 애니메이션 샘플](http://go.microsoft.com/fwlink/?LinkID=160028)합니다.</span><span class="sxs-lookup"><span data-stu-id="f9221-108">For the complete sample, see [Path Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
 <span data-ttu-id="f9221-109">사용 되는 이전 샘플의 코드 버전은 <xref:System.Windows.Media.Animation.Storyboard> 애니메이션 효과를 줄의 <xref:System.Windows.Media.EllipseGeometry>하나만 애니메이션이 적용 된 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9221-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="f9221-110">A <xref:System.Windows.Media.Animation.Storyboard> 동일한 이러한 애니메이션을 제어할 수 있으므로 여러 애니메이션을 적용 하는 가장 쉬운 방법은 방식은 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="f9221-110">A <xref:System.Windows.Media.Animation.Storyboard> is often the easiest way to apply multiple animations because these animations can be controlled by the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="f9221-111">그러나 코드를 사용 하는 경우 단일 애니메이션 속성에 적용할 수 있는 더욱 손쉬운 방법을 사용 하는 것은 <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="f9221-111">However, an easier way to apply a single animation to a property when using code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="f9221-112">예제를 보려면 [Storyboard를 사용하지 않고 속성에 애니메이션 효과 주기](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f9221-112">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9221-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9221-113">See Also</span></span>  
 [<span data-ttu-id="f9221-114">경로 애니메이션 샘플</span><span class="sxs-lookup"><span data-stu-id="f9221-114">Path Animation Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=160028)  
 [<span data-ttu-id="f9221-115">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="f9221-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="f9221-116">경로 애니메이션 방법 항목</span><span class="sxs-lookup"><span data-stu-id="f9221-116">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
