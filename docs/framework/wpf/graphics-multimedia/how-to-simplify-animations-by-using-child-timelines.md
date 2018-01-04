---
title: "방법: 자식 Timeline을 사용하여 애니메이션 단순화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- simplifying animations by child timelines [WPF]
- animation [WPF], simplifying by child timelines
- child timelines [WPF]
ms.assetid: 8335d770-d13d-42bd-8dfa-63f92c0327e2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d3b8f1ca1dbf7ba5452acffc62fdf0b655c9c12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-simplify-animations-by-using-child-timelines"></a><span data-ttu-id="faa01-102">방법: 자식 Timeline을 사용하여 애니메이션 단순화</span><span class="sxs-lookup"><span data-stu-id="faa01-102">How to: Simplify Animations by Using Child Timelines</span></span>
<span data-ttu-id="faa01-103">자식을 사용 하 여 애니메이션을 단순화 하는 방법을 보여 주는이 예제 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-103">This example shows how to simplify animations by using child <xref:System.Windows.Media.Animation.ParallelTimeline> objects.</span></span> <span data-ttu-id="faa01-104">A <xref:System.Windows.Media.Animation.Storyboard> 는 유형의 <xref:System.Windows.Media.Animation.Timeline> 포함 된 타임 라인에 대 한 대상 정보를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-104">A <xref:System.Windows.Media.Animation.Storyboard> is a type of <xref:System.Windows.Media.Animation.Timeline> that provides targeting information for the timelines it contains.</span></span> <span data-ttu-id="faa01-105">사용 하 여 한 <xref:System.Windows.Media.Animation.Storyboard> 개체 및 속성 정보를 포함 하 여 정보를 대상으로 하는 시간 표시 막대 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-105">Use a <xref:System.Windows.Media.Animation.Storyboard> to provide timeline targeting information, including object and property information.</span></span>  
  
 <span data-ttu-id="faa01-106">애니메이션을 시작 하려면 하나 이상의 사용 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체의 중첩 된 자식 요소로 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-106">To begin an animation, use one or more <xref:System.Windows.Media.Animation.ParallelTimeline> objects as nested child elements of a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="faa01-107">이러한 <xref:System.Windows.Media.Animation.ParallelTimeline> 개체 다른 애니메이션 포함 될 수 있으며 따라서 복잡 한 애니메이션의 타이밍 시퀀스를 캡슐화 할 더 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-107">These <xref:System.Windows.Media.Animation.ParallelTimeline> objects can contain other animations and therefore, can better encapsulate the timing sequences in complex animations.</span></span> <span data-ttu-id="faa01-108">애니메이션을 적용 하려는 경우 등는 <xref:System.Windows.Controls.TextBlock> 와 같은 여러 셰이프 <xref:System.Windows.Media.Animation.Storyboard>에 대 한 애니메이션을 구분할 수 있습니다는 <xref:System.Windows.Controls.TextBlock> 와 배치를 별도의 각 셰이프 <xref:System.Windows.Media.Animation.ParallelTimeline>합니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-108">For example, if you are animating a <xref:System.Windows.Controls.TextBlock> and several shapes in the same <xref:System.Windows.Media.Animation.Storyboard>, you can separate the animations for the <xref:System.Windows.Controls.TextBlock> and the shapes, putting each into a separate <xref:System.Windows.Media.Animation.ParallelTimeline>.</span></span> <span data-ttu-id="faa01-109">때문에 각 <xref:System.Windows.Media.Animation.ParallelTimeline> 자체 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> 및 모든 자식 요소는 <xref:System.Windows.Media.Animation.ParallelTimeline> 이 기준으로 시작 <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, 타이밍 더욱 효과적으로 캡슐화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-109">Because each <xref:System.Windows.Media.Animation.ParallelTimeline> has its own <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> and all child elements of the <xref:System.Windows.Media.Animation.ParallelTimeline> begin relative to this <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, timing is better encapsulated.</span></span>  
  
 <span data-ttu-id="faa01-110">다음 예제에서는 두 가지 텍스트 애니메이션 효과 줍니다 (<xref:System.Windows.Controls.TextBlock> 개체)에서 같은 <xref:System.Windows.Media.Animation.Storyboard>합니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-110">The following example animates two pieces of text (<xref:System.Windows.Controls.TextBlock> objects) from within the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="faa01-111">A <xref:System.Windows.Media.Animation.ParallelTimeline> 중 하나의 애니메이션 캡슐화는 <xref:System.Windows.Controls.TextBlock> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-111">A <xref:System.Windows.Media.Animation.ParallelTimeline> encapsulates the animations of one of the <xref:System.Windows.Controls.TextBlock> objects.</span></span>  
  
 <span data-ttu-id="faa01-112">**성능 참고 사항:** 중첩할 수 있지만 <xref:System.Windows.Media.Animation.Storyboard> 서로 timeline <xref:System.Windows.Media.Animation.ParallelTimeline>훨씬 더 적은 오버 헤드를 필요 하기 때문에 중첩에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="faa01-112">**Performance Note:** Although you can nest <xref:System.Windows.Media.Animation.Storyboard> timelines inside each other, <xref:System.Windows.Media.Animation.ParallelTimeline>s are more suitable for nesting because they require less overhead.</span></span> <span data-ttu-id="faa01-113">(의 <xref:System.Windows.Media.Animation.Storyboard> 클래스에서 상속 된 <xref:System.Windows.Media.Animation.ParallelTimeline> 클래스입니다.)</span><span class="sxs-lookup"><span data-stu-id="faa01-113">(The <xref:System.Windows.Media.Animation.Storyboard> class inherits from the <xref:System.Windows.Media.Animation.ParallelTimeline> class.)</span></span>  
  
## <a name="example"></a><span data-ttu-id="faa01-114">예</span><span class="sxs-lookup"><span data-stu-id="faa01-114">Example</span></span>  
 [!code-xaml[Timelines_snip#ParallelTimelineWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Timelines_snip/CS/ParallelTimelineExample.xaml#paralleltimelinewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="faa01-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="faa01-115">See Also</span></span>  
 [<span data-ttu-id="faa01-116">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="faa01-116">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="faa01-117">Storyboard 애니메이션 간의 HandoffBehavior 지정</span><span class="sxs-lookup"><span data-stu-id="faa01-117">Specify HandoffBehavior Between Storyboard Animations</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-handoffbehavior-between-storyboard-animations.md)
