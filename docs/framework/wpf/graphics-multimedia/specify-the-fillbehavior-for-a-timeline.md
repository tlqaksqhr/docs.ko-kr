---
title: "방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FillBehavior property for inactive timelines [WPF]
- Timelines [WPF], FillBehavior property
ms.assetid: db805f59-d513-4dac-af15-47005dae3199
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b890d121cf06dc377a3bbc1dc569d9dac7c011b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-specify-the-fillbehavior-for-a-timeline-that-has-reached-the-end-of-its-active-period"></a><span data-ttu-id="b7592-102">방법: 활성 기간이 끝난 Timeline의 FillBehavior 지정</span><span class="sxs-lookup"><span data-stu-id="b7592-102">How to: Specify the FillBehavior for a Timeline that has Reached the End of Its Active Period</span></span>
<span data-ttu-id="b7592-103">지정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 비활성에 대 한 <xref:System.Windows.Media.Animation.Timeline> 애니메이션된 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b7592-103">This example shows how to specify the <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> for the inactive <xref:System.Windows.Media.Animation.Timeline> of an animated property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7592-104">예</span><span class="sxs-lookup"><span data-stu-id="b7592-104">Example</span></span>  
 <span data-ttu-id="b7592-105"><xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 속성은 <xref:System.Windows.Media.Animation.Timeline> 되 고 있지 않습니다 때 애니메이션된 속성의 값에 수행할 작업을 결정 애니메이션 효과가 적용, 즉, 시기는 <xref:System.Windows.Media.Animation.Timeline> 만 부모 활성화 되지 않은 <xref:System.Windows.Media.Animation.Timeline> 는 활성 또는 보관 기간.</span><span class="sxs-lookup"><span data-stu-id="b7592-105">The <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> property of a <xref:System.Windows.Media.Animation.Timeline> determines what happens to the value of an animated property when it is not being animated, that is, when the <xref:System.Windows.Media.Animation.Timeline> is inactive but its parent <xref:System.Windows.Media.Animation.Timeline> is inside its active or hold period.</span></span> <span data-ttu-id="b7592-106">예를 들어 애니메이션된 속성 유지 않는다는 끝에 애니메이션을 종료 하거나 수행 후의 값은 애니메이션 시작 되기 전의 값 되돌아갑니다?</span><span class="sxs-lookup"><span data-stu-id="b7592-106">For example, does an animated property remain at its end value after the animation ends or does it revert back to the value it had before the animation started?</span></span>  
  
 <span data-ttu-id="b7592-107">다음 예제에서는 한 <xref:System.Windows.Media.Animation.DoubleAnimation> 애니메이션 효과를 줄의 <xref:System.Windows.FrameworkElement.Width%2A> 두 개의 사각형의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7592-107">The following example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.FrameworkElement.Width%2A> of two rectangles.</span></span> <span data-ttu-id="b7592-108">각 사각형을 사용 하 여 다른 <xref:System.Windows.Media.Animation.Timeline> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="b7592-108">Each rectangle uses a different <xref:System.Windows.Media.Animation.Timeline> object.</span></span>  
  
 <span data-ttu-id="b7592-109">하나의 <xref:System.Windows.Media.Animation.Timeline> 에 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 로 설정 되어 있는 <xref:System.Windows.Media.Animation.FillBehavior.Stop>, 다시 돌아가려면 해당 애니메이션이 적용 되지 않은 사각형의 너비 값으로 <xref:System.Windows.Media.Animation.Timeline> 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7592-109">One <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> that is set to <xref:System.Windows.Media.Animation.FillBehavior.Stop>, which causes the width of the rectangle to revert back to its non-animated value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span> <span data-ttu-id="b7592-110">다른 <xref:System.Windows.Media.Animation.Timeline> 에 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> 의 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, 너비의 끝을 유지 하기 위한 경우이 값은 <xref:System.Windows.Media.Animation.Timeline> 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7592-110">The other <xref:System.Windows.Media.Animation.Timeline> has a <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> of <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>, which causes the width to remain at its end value when the <xref:System.Windows.Media.Animation.Timeline> ends.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#FillBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/FillBehaviorExample.xaml#fillbehaviorwholepage)]  
  
 <span data-ttu-id="b7592-111">전체 샘플을 참조 하십시오. [애니메이션 예제 갤러리](http://go.microsoft.com/fwlink/?LinkID=159969)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7592-111">For the complete sample, see [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7592-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7592-112">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimation>  
 <xref:System.Windows.FrameworkElement.Width%2A>  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A>  
 <xref:System.Windows.Media.Animation.FillBehavior.Stop>  
 <xref:System.Windows.Media.Animation.FillBehavior.HoldEnd>  
 [<span data-ttu-id="b7592-113">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="b7592-113">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="b7592-114">애니메이션 및 타이밍</span><span class="sxs-lookup"><span data-stu-id="b7592-114">Animation and Timing</span></span>](http://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="b7592-115">방법 항목</span><span class="sxs-lookup"><span data-stu-id="b7592-115">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
