---
title: "방법: 해당 Timeline의 속도를 변경하지 않고 시계의 속도 변경"
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
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5421ed8b45c21e229d6c2682703cd9c7ee486e27
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a><span data-ttu-id="fad27-102">방법: 해당 Timeline의 속도를 변경하지 않고 시계의 속도 변경</span><span class="sxs-lookup"><span data-stu-id="fad27-102">How to: Change the Speed of a Clock Without Changing the Speed of Its Timeline</span></span>
<span data-ttu-id="fad27-103">A <xref:System.Windows.Media.Animation.ClockController> 개체의 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 속성의 속도 변경 하면는 <xref:System.Windows.Media.Animation.Clock> 변경 하지 않고는 <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> 클록의의 <xref:System.Windows.Media.Animation.Timeline>합니다.</span><span class="sxs-lookup"><span data-stu-id="fad27-103">A <xref:System.Windows.Media.Animation.ClockController> object's <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> property enables you to change the speed of a <xref:System.Windows.Media.Animation.Clock> without altering the <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> of the clock's <xref:System.Windows.Media.Animation.Timeline>.</span></span> <span data-ttu-id="fad27-104">다음 예제에서는 <xref:System.Windows.Media.Animation.ClockController> 대화형으로 수정 하는 데 사용 되는 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 클록의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fad27-104">In the following example, a <xref:System.Windows.Media.Animation.ClockController> is used to interactively modify the <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> of a clock.</span></span> <span data-ttu-id="fad27-105"><xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> 이벤트와 클록의 <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> 속성은 클록의 현재 글로벌 속도 표시 하는 데 사용 됩니다 대화형 때마다 <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fad27-105">The <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> event and the clock's <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> property are used to display the clock's current global speed each time its interactive <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> is changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fad27-106">예</span><span class="sxs-lookup"><span data-stu-id="fad27-106">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
