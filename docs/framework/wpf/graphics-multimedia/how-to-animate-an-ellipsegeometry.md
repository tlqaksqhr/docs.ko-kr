---
title: "방법: EllipseGeometry에 애니메이션 효과 적용"
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
- animation [WPF], EllipseGeometry objects [WPF]
- EllipseGeometry objects [WPF], animating
- graphics [WPF], animation
ms.assetid: 767b9b6e-9cb7-482e-b6c2-fee7750c3995
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc9eea56d9070d33820f8e2ef1bd8eba3ec04303
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-ellipsegeometry"></a><span data-ttu-id="1de77-102">방법: EllipseGeometry에 애니메이션 효과 적용</span><span class="sxs-lookup"><span data-stu-id="1de77-102">How to: Animate an EllipseGeometry</span></span>
<span data-ttu-id="1de77-103">애니메이션 효과 적용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Geometry> 내에서 한 <xref:System.Windows.Shapes.Path> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="1de77-103">This example shows how to animate a <xref:System.Windows.Media.Geometry> within a <xref:System.Windows.Shapes.Path> element.</span></span> <span data-ttu-id="1de77-104">다음 예제에서는 <xref:System.Windows.Media.Animation.PointAnimation> 애니메이션 효과 적용 하는 데 사용 되는 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 의 <xref:System.Windows.Media.EllipseGeometry>합니다.</span><span class="sxs-lookup"><span data-stu-id="1de77-104">In the following example, a <xref:System.Windows.Media.Animation.PointAnimation> is used to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> of an <xref:System.Windows.Media.EllipseGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1de77-105">예</span><span class="sxs-lookup"><span data-stu-id="1de77-105">Example</span></span>  
 [!code-xaml[animatepath_snip_XAML#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip_XAML/CS/EllipseGeometryExample.xaml#1)]  
  
 [!code-csharp[animatepath_snip#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/animatepath_snip/CSharp/EllipseGeometryExample.cs#101)]  
  
 [!code-vb[animatepath_snip#201](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/animatepath_snip/VisualBasic/EllipseGeometryExample.vb#201)]  
  
## <a name="see-also"></a><span data-ttu-id="1de77-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1de77-106">See Also</span></span>  
 [<span data-ttu-id="1de77-107">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="1de77-107">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="1de77-108">Geometry 개요</span><span class="sxs-lookup"><span data-stu-id="1de77-108">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
