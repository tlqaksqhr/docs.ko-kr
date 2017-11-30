---
title: "ManualResetEvent 및 ManualResetEventSlim"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], ManualResetEvent class
- ManualResetEvent class, about ManualResetEvent class
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f663dd17b063f77e2f9ce6bd4bbd0f8859ba4116
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="manualresetevent-and-manualreseteventslim"></a><span data-ttu-id="ef0a3-102">ManualResetEvent 및 ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="ef0a3-102">ManualResetEvent and ManualResetEventSlim</span></span>
<span data-ttu-id="ef0a3-103"><xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> 신호를 보낸 후 수동으로 재설정 해야 하는 로컬 대기 핸들 이벤트 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-103">The <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> class represents a local wait handle event that must be reset manually after it is signaled.</span></span> <span data-ttu-id="ef0a3-104">이 클래스는 기본 클래스의 특수 한 경우를 나타냅니다. <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ef0a3-105">수동 재설정 이벤트의 사용 및 기능은 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 개념 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of manual reset events.</span></span>  
  
 <span data-ttu-id="ef0a3-106">A <xref:System.Threading.ManualResetEvent> 개체 유지 될 때까지 신호를 받은 해당 <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-106">A <xref:System.Threading.ManualResetEvent> object remains signaled until its <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="ef0a3-107">대기 스레드 또는 신호를 받은 후 이벤트를 기다리는 스레드 수는 제한 없이 개체의 상태가 신호를 받는 동안 해제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-107">Any number of waiting threads, or threads that wait on the event after it has been signaled, can be released while the object's state is signaled.</span></span> <span data-ttu-id="ef0a3-108"><xref:System.Threading.ManualResetEvent>해당 하는 Win32 `CreateEvent` 지정 함으로써 호출 `true` 에 대 한는 `bManualReset` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-108"><xref:System.Threading.ManualResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `true` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="ef0a3-109">에 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]를 사용할 수 있습니다는 <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> 시점과 이벤트 프로세스 경계를 교차 하지 않으며 대기 시간이 매우 짧은 것으로 예상 되는 성능 향상을 위해 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-109">In the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use the <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType> class for better performance when wait times are expected to be very short, and when the event does not cross a process boundary.</span></span> <span data-ttu-id="ef0a3-110"><xref:System.Threading.ManualResetEventSlim>에서는 이벤트에 신호가 전달되기를 기다리는 짧은 시간 동안 고속 회전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-110"><xref:System.Threading.ManualResetEventSlim> uses busy spinning for a short time while it waits for the event to become signaled.</span></span> <span data-ttu-id="ef0a3-111">대기 시간이 짧은 경우 대기 핸들을 사용하여 기다리는 것보다 회전하는 것이 비용이 적게 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-111">When wait times are short, spinning can be much less expensive than waiting by using wait handles.</span></span> <span data-ttu-id="ef0a3-112">그러나 특정 기간 내 이벤트 신호 되지 않는 경우, <xref:System.Threading.ManualResetEventSlim> 일반적인 이벤트 핸들 대기도 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="ef0a3-112">However, if the event does not become signaled within a certain period of time, <xref:System.Threading.ManualResetEventSlim> resorts to a regular event handle wait.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef0a3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef0a3-113">See Also</span></span>  
 [<span data-ttu-id="ef0a3-114">스레딩</span><span class="sxs-lookup"><span data-stu-id="ef0a3-114">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="ef0a3-115">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="ef0a3-115">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="ef0a3-116">대기 핸들</span><span class="sxs-lookup"><span data-stu-id="ef0a3-116">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 [<span data-ttu-id="ef0a3-117">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="ef0a3-117">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 [<span data-ttu-id="ef0a3-118">스핀 대기</span><span class="sxs-lookup"><span data-stu-id="ef0a3-118">SpinWait</span></span>](../../../docs/standard/threading/spinwait.md)  
 [<span data-ttu-id="ef0a3-119">세마포 및 SemaphoreSlim</span><span class="sxs-lookup"><span data-stu-id="ef0a3-119">Semaphore and SemaphoreSlim</span></span>](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)
