---
title: "방법: Timeline을 자동으로 뒤집을지 여부 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- AutoReverse property of timelines [WPF]
- Timelines [WPF], AutoReverse property
ms.assetid: 1648dd90-1bee-409a-ac69-ac729867f557
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: da1330a8513f43e7543f97838ef8e9be788af396
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-whether-a-timeline-automatically-reverses"></a><span data-ttu-id="72646-102">방법: Timeline을 자동으로 뒤집을지 여부 지정</span><span class="sxs-lookup"><span data-stu-id="72646-102">How to: Specify Whether a Timeline Automatically Reverses</span></span>
<span data-ttu-id="72646-103">타임 라인의 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성을 정방향으로 반복을 완료 한 후 반대 방향으로 재생 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72646-103">A timeline's <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property determines whether it plays in reverse after it completes a forward iteration.</span></span> <span data-ttu-id="72646-104">다음 예에서는 동일한 기간 및 대상 값을 사용 하지만 서로 다른 여러 애니메이션 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72646-104">The following example shows several animations with identical duration and target values, but with different <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> settings.</span></span> <span data-ttu-id="72646-105">설명 하기 위해 방법을 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성 서로 다른 동작 <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> 설정, 일부 애니메이션 반복으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72646-105">To demonstrate how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property behaves with different <xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> settings, some animations are set to repeat.</span></span> <span data-ttu-id="72646-106">애니메이션에 마지막 표시 된 방법을 <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> 속성은 중첩 된 타임 라인에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72646-106">The last animation shows how the <xref:System.Windows.Media.Animation.Timeline.AutoReverse%2A> property works on nested timelines.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72646-107">예</span><span class="sxs-lookup"><span data-stu-id="72646-107">Example</span></span>  
 [!code-xaml[timingbehaviors_snip#AutoReverseAndRepeatBehaviorExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/AutoReverseExample.xaml#autoreverseandrepeatbehaviorexamplewholepage)]
