---
title: "방법: 이미 시작된 Storyboard 제어"
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
helpviewer_keywords: Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 051ac6fea73b207fb5ef4d6293c5e996552f1281
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="2b50e-102">방법: 이미 시작된 Storyboard 제어</span><span class="sxs-lookup"><span data-stu-id="2b50e-102">How to: Control a Storyboard After It Starts</span></span>
<span data-ttu-id="2b50e-103">컨트롤에 코드를 사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Media.Animation.Storyboard> 시작 된 후입니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-103">This example shows how to use code to control a <xref:System.Windows.Media.Animation.Storyboard> after it has started.</span></span> <span data-ttu-id="2b50e-104">스토리 보드를 제어 하려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 사용 하 여 <xref:System.Windows.Trigger> 및 <xref:System.Windows.TriggerAction> 개체, 예를 들어 참조 [이벤트 트리거는 스토리 보드 후 시작을 제어를 사용 하 여](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-104">To control a storyboard in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Trigger> and <xref:System.Windows.TriggerAction> objects; for an example, see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 <span data-ttu-id="2b50e-105">스토리 보드를 시작 하려면 사용 해당 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 스토리 보드의 애니메이션 속성에 애니메이션을 적용 하 고 스토리 보드 시작을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-105">To start a storyboard, you use its <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method, which distributes the storyboard's animations to the properties they animate and starts the storyboard.</span></span>  
  
 <span data-ttu-id="2b50e-106">스토리 보드를 제어할 수 있도록 하려면 사용 된 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 지정 하 고 **true** 두 번째 매개 변수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-106">To make a storyboard controllable, you use the <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method and specify **true** as the second parameter.</span></span> <span data-ttu-id="2b50e-107">그런 다음 일시 중지, 다시 시작할 seek, 중지, 속도, 또는 스토리 보드 속도가 저하 또는 채우기 기간으로 진행 스토리 보드의 대화형 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-107">You can then use the storyboard's interactive methods to pause, resume, seek, stop, speed up, or slow down the storyboard, or advance it to its fill period.</span></span> <span data-ttu-id="2b50e-108">다음은 스토리 보드의 대화형 메서드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-108">The following is a list of the storyboard's interactive methods:</span></span>  
  
-   <span data-ttu-id="2b50e-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: 스토리 보드를 일시 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-109"><xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="2b50e-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: 일시 중지 된 스토리 보드를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-110"><xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="2b50e-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: 스토리 보드의 대화형 속도 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-111"><xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Sets the storyboard's interactive speed.</span></span>  
  
-   <span data-ttu-id="2b50e-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: 키 스토리 보드 지정된 된 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-112"><xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Seeks the storyboard the specified location.</span></span>  
  
-   <span data-ttu-id="2b50e-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: 지정된 된 위치에 스토리 보드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-113"><xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Seeks the storyboard to the specified location.</span></span> <span data-ttu-id="2b50e-114">와 달리는 <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> 이 작업 메서드를 다음 틱 보다 먼저 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-114">Unlike the <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> method, this operation is processed before the next tick.</span></span>  
  
-   <span data-ttu-id="2b50e-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: 있는 경우 채우기 기간에 스토리 보드를 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-115"><xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Advances the storyboard to its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="2b50e-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: 스토리 보드를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-116"><xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Stops the storyboard.</span></span>  
  
 <span data-ttu-id="2b50e-117">다음 예제에서를 스토리 보드를 대화형으로 제어할 스토리 보드는 여러 가지 방법은 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-117">In the following example, several storyboard methods are used to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="2b50e-118">**참고:** 트리거를 사용 하 여 스토리 보드를 제어 합니다. 예를 보려면 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 참조 [한 스토리 보드 후 시작을 제어 하려면 이벤트 트리거를 사용 하 여](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2b50e-118">**Note:** To see an example of controlling a storyboard using triggers with [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], see [Use Event Triggers to Control a Storyboard After It Starts](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b50e-119">예</span><span class="sxs-lookup"><span data-stu-id="2b50e-119">Example</span></span>  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="2b50e-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b50e-120">See Also</span></span>  
 [<span data-ttu-id="2b50e-121">Storyboard를 시작한 후 이벤트 트리거를 사용하여 제어</span><span class="sxs-lookup"><span data-stu-id="2b50e-121">Use Event Triggers to Control a Storyboard After It Starts</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
