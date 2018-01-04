---
title: "방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기"
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
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baa412a889ee82c9bf20ff1d6420d8a86f339ca6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a><span data-ttu-id="840ac-102">방법: PointAnimation을 사용하여 개체 위치에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="840ac-102">How to: Animate the Position of an Object by Using PointAnimation</span></span>
<span data-ttu-id="840ac-103">사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.PointAnimation> 따라 개체를 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Shapes.Path>합니다.</span><span class="sxs-lookup"><span data-stu-id="840ac-103">This example shows how to use the <xref:System.Windows.Media.Animation.PointAnimation> class to animate an object along a <xref:System.Windows.Shapes.Path>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="840ac-104">예</span><span class="sxs-lookup"><span data-stu-id="840ac-104">Example</span></span>  
 <span data-ttu-id="840ac-105">다음 예제에서는 타원을 이동는 <xref:System.Windows.Shapes.Path> 한 지점에서 다른 화면에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="840ac-105">The following example moves an ellipse along a <xref:System.Windows.Shapes.Path> from one point on the screen to another.</span></span> <span data-ttu-id="840ac-106">이 예제에서 애니메이션 효과 적용 하의 위치는 <xref:System.Windows.Media.EllipseGeometry> 를 사용 하 여 <xref:System.Windows.Media.Animation.PointAnimation> 애니메이션 효과를 줄는 <xref:System.Windows.Media.EllipseGeometry.Center%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="840ac-106">The example animates the position of an <xref:System.Windows.Media.EllipseGeometry> by using <xref:System.Windows.Media.Animation.PointAnimation> to animate the <xref:System.Windows.Media.EllipseGeometry.Center%2A> property.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="840ac-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="840ac-107">See Also</span></span>  
 <xref:System.Windows.Media.Animation.PointAnimation>  
 <xref:System.Windows.Shapes.Path>  
 <xref:System.Windows.Media.EllipseGeometry>  
 <xref:System.Windows.Media.EllipseGeometry.Center%2A>  
 [<span data-ttu-id="840ac-108">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="840ac-108">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="840ac-109">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="840ac-109">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [<span data-ttu-id="840ac-110">방법 항목</span><span class="sxs-lookup"><span data-stu-id="840ac-110">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [<span data-ttu-id="840ac-111">애니메이션 및 타이밍</span><span class="sxs-lookup"><span data-stu-id="840ac-111">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="840ac-112">방법 항목</span><span class="sxs-lookup"><span data-stu-id="840ac-112">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
