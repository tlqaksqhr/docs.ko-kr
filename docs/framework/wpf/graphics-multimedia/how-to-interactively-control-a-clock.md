---
title: "방법: 대화형으로 Clock 제어"
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
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: debe65ef1587171dc2f324a19da4b43e7274c438
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-interactively-control-a-clock"></a><span data-ttu-id="9ade9-102">방법: 대화형으로 Clock 제어</span><span class="sxs-lookup"><span data-stu-id="9ade9-102">How to: Interactively Control a Clock</span></span>
<span data-ttu-id="9ade9-103">A <xref:System.Windows.Media.Animation.Clock> 개체의 <xref:System.Windows.Media.Animation.ClockController> 속성을 사용 하면 대화형으로 시작, 일시 중지, 다시 시작, 검색, 시계를 해당 전체 기간 이동 및 시계를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ade9-103">A <xref:System.Windows.Media.Animation.Clock> object's <xref:System.Windows.Media.Animation.ClockController> property enables you to interactively start, pause, resume, seek, advance the clock to its fill period, and stop the clock.</span></span> <span data-ttu-id="9ade9-104">시간 트리의 루트 클록만을 대화형으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ade9-104">Only the root clock of a timing tree can be interactively controlled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ade9-105">다른 여러 가지를 대화형으로 제어 하지 않고 애니메이션을 시계와 직접 협업할 수 있습니다: 스토리 보드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ade9-105">There are other ways to interactively control animations that don't require you to work directly with clocks: you can also use Storyboards.</span></span> <span data-ttu-id="9ade9-106">스토리 보드는 태그와 코드에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ade9-106">Storyboards are supported in both markup and code.</span></span> <span data-ttu-id="9ade9-107">예를 들어 참조 [속성 스토리 보드를 사용 하 여 애니메이션을 적용](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) 또는 [애니메이션 개요](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ade9-107">For an example, see [Animate a Property by Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) or the [Animation Overview](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).</span></span>  
  
 <span data-ttu-id="9ade9-108">다음 예제에서는 여러 단추는 애니메이션 클록을 대화형으로 제어를 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ade9-108">In the following example, several buttons are used to interactively control an animation clock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ade9-109">예제</span><span class="sxs-lookup"><span data-stu-id="9ade9-109">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="9ade9-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ade9-110">See Also</span></span>  
 [<span data-ttu-id="9ade9-111">Storyboard를 사용하여 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="9ade9-111">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="9ade9-112">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="9ade9-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
