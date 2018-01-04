---
title: "방법: Storyboard 애니메이션 간의 HandoffBehavior 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Storyboards [WPF], handoff behavior between animations
- animation [WPF], handoff behavior between
ms.assetid: 97bd6842-929b-49d9-813e-46553ae46472
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 21d4a39b9cbd2ee563edd22818630c18658e1d6d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-handoffbehavior-between-storyboard-animations"></a><span data-ttu-id="a6915-102">방법: Storyboard 애니메이션 간의 HandoffBehavior 지정</span><span class="sxs-lookup"><span data-stu-id="a6915-102">How to: Specify HandoffBehavior Between Storyboard Animations</span></span>
<span data-ttu-id="a6915-103">이 예제에는 스토리 보드 애니메이션 간의 전달 동작을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6915-103">This example shows how to specify handoff behavior between storyboard animations.</span></span> <span data-ttu-id="a6915-104"><xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 속성 <xref:System.Windows.Media.Animation.BeginStoryboard> 지정 방법을 새 애니메이션 속성에 이미 적용 된 기존 애니메이션과 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6915-104">The <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> property of <xref:System.Windows.Media.Animation.BeginStoryboard> specifies how new animations interact with any existing ones that are already applied to a property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6915-105">예</span><span class="sxs-lookup"><span data-stu-id="a6915-105">Example</span></span>  
 <span data-ttu-id="a6915-106">다음 예제에서는 두 개의 단추 위로 마우스 커서를 이동 하는 때를 확대 커지고 커서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6915-106">The following example creates two buttons that enlarge when the mouse cursor moves over them and become smaller when the cursor moves away.</span></span> <span data-ttu-id="a6915-107">단추 위로 마우스 커서를 신속 하 게 제거 하는 경우 첫 번째 작업이 완료 되기 전에 두 번째 애니메이션이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6915-107">If you mouse over a button and then quickly remove the cursor, the second animation will be applied before the first one is finished.</span></span> <span data-ttu-id="a6915-108">간의 차이 볼 수 있는 다음과 같은 두 개의 애니메이션이 겹칠 때는 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> 값 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 및 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>합니다.</span><span class="sxs-lookup"><span data-stu-id="a6915-108">It is when two animations overlap like this that you can see the difference between the <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A> values of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> and <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace>.</span></span> <span data-ttu-id="a6915-109">값이 <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> 애니메이션 값 간의 전환을 더 부드럽게 겹치는 애니메이션 결합 <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> 새 애니메이션이 즉시 겹치는 이전를 대체 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6915-109">A value of <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> combines the overlapping animations causing a smoother transition between animations while a value of <xref:System.Windows.Media.Animation.HandoffBehavior.SnapshotAndReplace> causes the new animation to immediately replace the earlier overlapping animation.</span></span>  
  
 [!code-xaml[timingbehaviors_snip#HandoffBehaviorWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/HandoffBehaviorExample.xaml#handoffbehaviorwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a6915-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6915-110">See Also</span></span>  
 <xref:System.Windows.Media.Animation.BeginStoryboard>  
 <xref:System.Windows.Media.Animation.BeginStoryboard.HandoffBehavior%2A>  
 [<span data-ttu-id="a6915-111">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="a6915-111">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="a6915-112">애니메이션 및 타이밍</span><span class="sxs-lookup"><span data-stu-id="a6915-112">Animation and Timing</span></span>](http://msdn.microsoft.com/en-us/7d83765b-d5ae-41b1-b423-80206e1124aa)  
 [<span data-ttu-id="a6915-113">방법 항목</span><span class="sxs-lookup"><span data-stu-id="a6915-113">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
