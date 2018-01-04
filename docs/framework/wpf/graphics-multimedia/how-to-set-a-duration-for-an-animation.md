---
title: "방법: 애니메이션의 지속 시간 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], duration
- Timelines [WPF], description
- duration of animations [WPF]
ms.assetid: 155034ef-7d00-4416-a73c-b1713992d2eb
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e8d15a1b8432b3dae5bee73396bdec9fc9d50f0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-a-duration-for-an-animation"></a><span data-ttu-id="31b81-102">방법: 애니메이션의 지속 시간 설정</span><span class="sxs-lookup"><span data-stu-id="31b81-102">How to: Set a Duration for an Animation</span></span>
<span data-ttu-id="31b81-103">A <xref:System.Windows.Media.Animation.Timeline> 시간을 세그먼트와 해당 세그먼트의 길이 따라 사용자가 타임 라인의 나타냅니다 <xref:System.Windows.Duration>합니다.</span><span class="sxs-lookup"><span data-stu-id="31b81-103">A <xref:System.Windows.Media.Animation.Timeline> represents a segment of time and the length of that segment is determined by the timeline's <xref:System.Windows.Duration>.</span></span> <span data-ttu-id="31b81-104">경우는 <xref:System.Windows.Media.Animation.Timeline> 끝에 도달한 기간의 해당 재생이 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b81-104">When a <xref:System.Windows.Media.Animation.Timeline> reaches the end of its duration, it stops playing.</span></span> <span data-ttu-id="31b81-105">경우는 <xref:System.Windows.Media.Animation.Timeline> 자식 타임 라인에도 재생을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b81-105">If the <xref:System.Windows.Media.Animation.Timeline> has child timelines, they stop playing as well.</span></span> <span data-ttu-id="31b81-106">애니메이션의 경우는 <xref:System.Windows.Duration> 애니메이션의 소요 시간 전환의 시작 값 끝 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b81-106">In the case of an animation, the <xref:System.Windows.Duration> specifies how long the animation takes to transition from its starting value to its ending value.</span></span>  
  
 <span data-ttu-id="31b81-107">지정할 수는 <xref:System.Windows.Duration> 제한 된 특정 시간 또는 특수 한 값을 가진 <xref:System.Windows.Duration.Automatic%2A> 또는 <xref:System.Windows.Duration.Forever%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="31b81-107">You can specify a <xref:System.Windows.Duration> with a specific, finite time or the special values <xref:System.Windows.Duration.Automatic%2A> or <xref:System.Windows.Duration.Forever%2A>.</span></span> <span data-ttu-id="31b81-108">애니메이션 항상 정의 된, 유한 길이 있어야 하기 때문에 애니메이션의 지속 시간 값을 항상 이어야 합니다-애니메이션 시간은 대상 값을 인식 하지 못하기 그렇지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="31b81-108">An animation's duration must always be a time value, because an animation must always have a defined, finite length—otherwise, the animation would not know how to transition between its target values.</span></span> <span data-ttu-id="31b81-109">컨테이너 타임 라인 (<xref:System.Windows.Media.Animation.TimelineGroup> 개체), 같은 <xref:System.Windows.Media.Animation.Storyboard> 및 <xref:System.Windows.Media.Animation.ParallelTimeline>의 지속 시간 기본값 <xref:System.Windows.Duration.Automatic%2A>, 즉, 마지막 자식 해당 재생이 중지 되 면 자동으로 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b81-109">Container timelines (<xref:System.Windows.Media.Animation.TimelineGroup> objects), such as <xref:System.Windows.Media.Animation.Storyboard> and <xref:System.Windows.Media.Animation.ParallelTimeline>, have a default duration of <xref:System.Windows.Duration.Automatic%2A>, which means they automatically end when their last child stops playing.</span></span>  
  
 <span data-ttu-id="31b81-110">다음 예제에서는, 너비, 높이 및 채우기 색에는 <xref:System.Windows.Shapes.Rectangle> 애니메이션 효과가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b81-110">In the following example, the width, height and fill color of a <xref:System.Windows.Shapes.Rectangle> is animated.</span></span> <span data-ttu-id="31b81-111">애니메이션의 인지 된 속도 제어 하 고 재정의 컨테이너 타임 라인의 기간으로 자식 타임 라인의 기간을 포함 하 여 애니메이션 효과 애니메이션 및 컨테이너 타임 라인 기간이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b81-111">Durations are set on animation and container timelines resulting in animation effects including controlling the perceived speed of an animation and overriding the duration of child timelines with the duration of a container timeline.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31b81-112">예</span><span class="sxs-lookup"><span data-stu-id="31b81-112">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#DurationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/DurationExample.xaml#durationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="31b81-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31b81-113">See Also</span></span>  
 <xref:System.Windows.Duration>  
 [<span data-ttu-id="31b81-114">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="31b81-114">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
