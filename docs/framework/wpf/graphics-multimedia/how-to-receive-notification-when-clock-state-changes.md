---
title: "방법: 알림을 받을 때 클록 &#39; s 상태 변경"
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
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 396e2c51894ad5ed11f8953bceb1bd36899cfc62
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a><span data-ttu-id="1bf19-102">방법: 알림을 받을 때 클록 &#39; s 상태 변경</span><span class="sxs-lookup"><span data-stu-id="1bf19-102">How to: Receive Notification When a Clock&#39;s State Changes</span></span>
<span data-ttu-id="1bf19-103">클록의 <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> 이벤트가 발생할 때 해당 <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> 클록 시작 되거나 중지 될 때와 같은 유효 하지 않게 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bf19-103">A clock's <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> event occurs when its <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> becomes invalid, such as when the clock starts or stops.</span></span> <span data-ttu-id="1bf19-104">사용 하 여 직접이 이벤트에 등록할 수는 <xref:System.Windows.Media.Animation.Clock>, 하거나 사용 하 여 등록할 수 있습니다는 <xref:System.Windows.Media.Animation.Timeline>합니다.</span><span class="sxs-lookup"><span data-stu-id="1bf19-104">You can register for this event with directly using a <xref:System.Windows.Media.Animation.Clock>, or you can register using a <xref:System.Windows.Media.Animation.Timeline>.</span></span>  
  
 <span data-ttu-id="1bf19-105">다음 예제에서는 <xref:System.Windows.Media.Animation.Storyboard> 와 두 개의 <xref:System.Windows.Media.Animation.DoubleAnimation> 개체는 두 개의 사각형의 너비에 애니메이션을 적용 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1bf19-105">In the following example, a <xref:System.Windows.Media.Animation.Storyboard> and two <xref:System.Windows.Media.Animation.DoubleAnimation> objects are used to animate the width of two rectangles.</span></span> <span data-ttu-id="1bf19-106"><xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> 이벤트는 클록 상태 변경 내용을 수신 대기 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bf19-106">The <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event is used to listen for clock state changes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bf19-107">예</span><span class="sxs-lookup"><span data-stu-id="1bf19-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 <span data-ttu-id="1bf19-108">다음 그림과 부모 타임 라인으로 다양 한 상태 애니메이션 입력 (*스토리 보드*) 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bf19-108">The following illustration shows the different states the animations enter as the parent timeline (*Storyboard*) progresses.</span></span>  
  
 <span data-ttu-id="1bf19-109">![두 개의 애니메이션이 있는 Storyboard에 대 한 상태 클록](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span><span class="sxs-lookup"><span data-stu-id="1bf19-109">![Clock states for a Storyboard with two animations](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")</span></span>  
  
 <span data-ttu-id="1bf19-110">다음 표에서 시간을 *Animation1*의 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> 이벤트 발생:</span><span class="sxs-lookup"><span data-stu-id="1bf19-110">The following table shows the times at which *Animation1*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||  
|-|-|-|-|-|-|-|  
|<span data-ttu-id="1bf19-111">시간 (초)</span><span class="sxs-lookup"><span data-stu-id="1bf19-111">Time (Seconds)</span></span>|<span data-ttu-id="1bf19-112">1</span><span class="sxs-lookup"><span data-stu-id="1bf19-112">1</span></span>|<span data-ttu-id="1bf19-113">10</span><span class="sxs-lookup"><span data-stu-id="1bf19-113">10</span></span>|<span data-ttu-id="1bf19-114">19</span><span class="sxs-lookup"><span data-stu-id="1bf19-114">19</span></span>|<span data-ttu-id="1bf19-115">21</span><span class="sxs-lookup"><span data-stu-id="1bf19-115">21</span></span>|<span data-ttu-id="1bf19-116">30</span><span class="sxs-lookup"><span data-stu-id="1bf19-116">30</span></span>|<span data-ttu-id="1bf19-117">39</span><span class="sxs-lookup"><span data-stu-id="1bf19-117">39</span></span>|  
|<span data-ttu-id="1bf19-118">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="1bf19-118">State</span></span>|<span data-ttu-id="1bf19-119">활성</span><span class="sxs-lookup"><span data-stu-id="1bf19-119">Active</span></span>|<span data-ttu-id="1bf19-120">활성</span><span class="sxs-lookup"><span data-stu-id="1bf19-120">Active</span></span>|<span data-ttu-id="1bf19-121">중지됨</span><span class="sxs-lookup"><span data-stu-id="1bf19-121">Stopped</span></span>|<span data-ttu-id="1bf19-122">활성</span><span class="sxs-lookup"><span data-stu-id="1bf19-122">Active</span></span>|<span data-ttu-id="1bf19-123">활성</span><span class="sxs-lookup"><span data-stu-id="1bf19-123">Active</span></span>|<span data-ttu-id="1bf19-124">중지됨</span><span class="sxs-lookup"><span data-stu-id="1bf19-124">Stopped</span></span>|  
  
 <span data-ttu-id="1bf19-125">다음 표에서 시간을 *Animation2*의 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> 이벤트 발생:</span><span class="sxs-lookup"><span data-stu-id="1bf19-125">The following table shows the times at which *Animation2*'s <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires:</span></span>  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="1bf19-126">시간 (초)</span><span class="sxs-lookup"><span data-stu-id="1bf19-126">Time (Seconds)</span></span>|<span data-ttu-id="1bf19-127">1</span><span class="sxs-lookup"><span data-stu-id="1bf19-127">1</span></span>|<span data-ttu-id="1bf19-128">10</span><span class="sxs-lookup"><span data-stu-id="1bf19-128">9</span></span>|<span data-ttu-id="1bf19-129">11</span><span class="sxs-lookup"><span data-stu-id="1bf19-129">11</span></span>|<span data-ttu-id="1bf19-130">19</span><span class="sxs-lookup"><span data-stu-id="1bf19-130">19</span></span>|<span data-ttu-id="1bf19-131">21</span><span class="sxs-lookup"><span data-stu-id="1bf19-131">21</span></span>|<span data-ttu-id="1bf19-132">29</span><span class="sxs-lookup"><span data-stu-id="1bf19-132">29</span></span>|<span data-ttu-id="1bf19-133">31</span><span class="sxs-lookup"><span data-stu-id="1bf19-133">31</span></span>|<span data-ttu-id="1bf19-134">39</span><span class="sxs-lookup"><span data-stu-id="1bf19-134">39</span></span>|  
|<span data-ttu-id="1bf19-135">시스템 상태</span><span class="sxs-lookup"><span data-stu-id="1bf19-135">State</span></span>|<span data-ttu-id="1bf19-136">활성</span><span class="sxs-lookup"><span data-stu-id="1bf19-136">Active</span></span>|<span data-ttu-id="1bf19-137">채우기</span><span class="sxs-lookup"><span data-stu-id="1bf19-137">Filling</span></span>|<span data-ttu-id="1bf19-138">활성</span><span class="sxs-lookup"><span data-stu-id="1bf19-138">Active</span></span>|<span data-ttu-id="1bf19-139">중지됨</span><span class="sxs-lookup"><span data-stu-id="1bf19-139">Stopped</span></span>|<span data-ttu-id="1bf19-140">활성</span><span class="sxs-lookup"><span data-stu-id="1bf19-140">Active</span></span>|<span data-ttu-id="1bf19-141">채우기</span><span class="sxs-lookup"><span data-stu-id="1bf19-141">Filling</span></span>|<span data-ttu-id="1bf19-142">활성</span><span class="sxs-lookup"><span data-stu-id="1bf19-142">Active</span></span>|<span data-ttu-id="1bf19-143">중지됨</span><span class="sxs-lookup"><span data-stu-id="1bf19-143">Stopped</span></span>|  
  
 <span data-ttu-id="1bf19-144">다음에 유의 *Animation1*의 <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> 상태로 유지 되는 경우에이 이벤트가 10 초 후에 발생 <xref:System.Windows.Media.Animation.ClockState.Active>합니다.</span><span class="sxs-lookup"><span data-stu-id="1bf19-144">Notice that *Animation1*'s  <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> event fires at 10 seconds, even though its state remains <xref:System.Windows.Media.Animation.ClockState.Active>.</span></span> <span data-ttu-id="1bf19-145">10 초 후에 상태가 변경에서 변경 하기 때문에 <xref:System.Windows.Media.Animation.ClockState.Active> 를 <xref:System.Windows.Media.Animation.ClockState.Filling> 다시 <xref:System.Windows.Media.Animation.ClockState.Active> 동일한 눈금에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="1bf19-145">That's because its state changed at 10 seconds, but it changed from <xref:System.Windows.Media.Animation.ClockState.Active> to <xref:System.Windows.Media.Animation.ClockState.Filling> and then back to <xref:System.Windows.Media.Animation.ClockState.Active> in the same tick.</span></span>
