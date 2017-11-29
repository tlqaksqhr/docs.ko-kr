---
title: "방법: 사각형에 애니메이션 효과 주기"
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
- animation [WPF], rectangles
- rectangles [WPF], animating
ms.assetid: 572ffb95-790d-4ace-adbf-b2ea8a90e75b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 773323d5e4b92ad5fef63072e1e7405882e0f26c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-a-rectangle"></a><span data-ttu-id="2a109-102">방법: 사각형에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="2a109-102">How to: Animate a Rectangle</span></span>
<span data-ttu-id="2a109-103">이 예제에서는 사각형의 위치 및 크기 변화에 애니메이션 효과를 주는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2a109-103">This example shows how to animate changes to the size and position of a rectangle.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a109-104">예제</span><span class="sxs-lookup"><span data-stu-id="2a109-104">Example</span></span>  
 <span data-ttu-id="2a109-105">다음 예제에서 사용 하는 <xref:System.Windows.Media.Animation.RectAnimation> 애니메이션 효과를 줄 클래스는 <xref:System.Windows.Media.RectangleGeometry.Rect%2A> 속성의는 <xref:System.Windows.Media.RectangleGeometry>, 크기 및 사각형의 위치 변경 애니메이션 효과 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a109-105">The following example uses an instance of the <xref:System.Windows.Media.Animation.RectAnimation> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>, which animates changes to the size and position of the rectangle.</span></span>  
  
 [!code-csharp[BasicAnimations_snip#RectAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/RectAnimationExample.cs#rectanimationwholepage)]
 [!code-vb[BasicAnimations_snip#RectAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/RectAnimationExample.vb#rectanimationwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2a109-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a109-106">See Also</span></span>  
 <xref:System.Windows.Media.Animation.RectAnimation>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.RectangleGeometry>  
 [<span data-ttu-id="2a109-107">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="2a109-107">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="2a109-108">그래픽 및 멀티미디어</span><span class="sxs-lookup"><span data-stu-id="2a109-108">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
 [<span data-ttu-id="2a109-109">방법 항목</span><span class="sxs-lookup"><span data-stu-id="2a109-109">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)  
 [<span data-ttu-id="2a109-110">애니메이션 및 타이밍</span><span class="sxs-lookup"><span data-stu-id="2a109-110">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="2a109-111">방법 항목</span><span class="sxs-lookup"><span data-stu-id="2a109-111">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
