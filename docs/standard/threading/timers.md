---
title: "타이머"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fca27cf5261e253c2bb3d3a10fa3db31f28a2415
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="timers"></a><span data-ttu-id="97e60-102">타이머</span><span class="sxs-lookup"><span data-stu-id="97e60-102">Timers</span></span>
<span data-ttu-id="97e60-103">타이머는 대리자가 지정된 된 시간에 호출 수를 지정할 수 있는 간단한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-103">Timers are lightweight objects that enable you to specify a delegate to be called at a specified time.</span></span> <span data-ttu-id="97e60-104">스레드 풀의 스레드 대기 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-104">A thread in the thread pool performs the wait operation.</span></span>  
  
 <span data-ttu-id="97e60-105">사용 하 여 <xref:System.Threading.Timer?displayProperty=nameWithType> 클래스는 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-105">Using the <xref:System.Threading.Timer?displayProperty=nameWithType> class is straightforward.</span></span> <span data-ttu-id="97e60-106">만들는 **타이머**전달 하는 <xref:System.Threading.TimerCallback> 대리자 콜백 메서드를 콜백, 초기 발생 시간, 및 콜백 호출 사이의 기간을 나타내는 시간에 전달 되는 상태를 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-106">You create a **Timer**, passing a <xref:System.Threading.TimerCallback> delegate to the callback method, an object representing state that will be passed to the callback, an initial raise time, and a time representing the period between callback invocations.</span></span> <span data-ttu-id="97e60-107">보류 타이머를 취소 하려면 호출는 **Timer.Dispose** 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-107">To cancel a pending timer, call the **Timer.Dispose** function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97e60-108">다른 두 개의 타이머 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-108">There are two other timer classes.</span></span> <span data-ttu-id="97e60-109"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 클래스는 컨트롤 비주얼 디자이너와 함께 작동 하 고 사용자 인터페이스에 대 한 컨텍스트에서 사용 하는 것입니다; 이벤트 사용자 인터페이스 스레드에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-109">The <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> class is a control that works with visual designers and is meant to be used in user interface contexts; it raises events on the user interface thread.</span></span> <span data-ttu-id="97e60-110"><xref:System.Timers.Timer?displayProperty=nameWithType> 클래스에서 파생 <xref:System.ComponentModel.Component>, 비주얼 디자이너와 함께 사용할 수 있으므로 이벤트를 발생 시키는 적지만에서 발생 한 <xref:System.Threading.ThreadPool> 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-110">The <xref:System.Timers.Timer?displayProperty=nameWithType> class derives from <xref:System.ComponentModel.Component>, so it can be used with visual designers; it also raises events, but it raises them on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="97e60-111"><xref:System.Threading.Timer?displayProperty=nameWithType> 클래스에서 콜백을 사용 하는 <xref:System.Threading.ThreadPool> 스레드 및 이벤트 모델을 전혀 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-111">The <xref:System.Threading.Timer?displayProperty=nameWithType> class makes callbacks on a <xref:System.Threading.ThreadPool> thread and does not use the event model at all.</span></span> <span data-ttu-id="97e60-112">또한 상태 개체를 다른 타이머 콜백 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-112">It also provides a state object to the callback method, which the other timers do not.</span></span> <span data-ttu-id="97e60-113">매우 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-113">It is extremely lightweight.</span></span>  
  
 <span data-ttu-id="97e60-114">다음 코드 예제에서는 시작 키를 누를 때까지 1 초 (1, 000 밀리초)와 틱 후 시작 되는 타이머는 **Enter** 키입니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-114">The following code example starts a timer that starts after one second (1000 milliseconds) and ticks every second until you press the **Enter** key.</span></span> <span data-ttu-id="97e60-115">변수가 타이머에 대 한 참조를 포함 하는 클래스 수준 필드로, 타이머 아닌지 가비지 수집의 대상이 계속 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-115">The variable containing the reference to the timer is a class-level field, to ensure that the timer is not subject to garbage collection while it is still running.</span></span> <span data-ttu-id="97e60-116">적극적인 가비지 수집에 대 한 자세한 내용은 참조 하십시오. <xref:System.GC.KeepAlive%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="97e60-116">For more information on aggressive garbage collection, see <xref:System.GC.KeepAlive%2A>.</span></span>  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="97e60-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97e60-117">See Also</span></span>  
 <xref:System.Threading.Timer>  
 [<span data-ttu-id="97e60-118">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="97e60-118">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
