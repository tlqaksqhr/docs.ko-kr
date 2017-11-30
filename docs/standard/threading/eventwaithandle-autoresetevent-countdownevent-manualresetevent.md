---
title: EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], EventWaitHandle class
- event wait handles [.NET Framework]
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0bcb27ed9c8981665a50c129dfbd824c9612f5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a><span data-ttu-id="f321d-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="f321d-102">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>
<span data-ttu-id="f321d-103">이벤트 대기 핸들을 통해 스레드가 서로 신호를 보내고 상대방의 신호를 대기하여 작업을 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-103">Event wait handles allow threads to synchronize activities by signaling each other and by waiting on each other's signals.</span></span> <span data-ttu-id="f321d-104">이러한 동기화 이벤트는 Win32 대기 핸들을 기반으로 하고 신호를 보낼 때 자동으로 다시 설정되는 이벤트 및 수동으로 다시 설정되는 이벤트라는 두 가지 유형으로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-104">These synchronization events are based on Win32 wait handles and can be divided into two types: those that reset automatically when signaled and those that are reset manually.</span></span>  
  
 <span data-ttu-id="f321d-105">이벤트 대기 핸들은 여러으로 동일한 동기화 시나리오에서 유용는 <xref:System.Threading.Monitor> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-105">Event wait handles are useful in many of the same synchronization scenarios as the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="f321d-106">이벤트 대기 핸들은 보다 사용 하기 쉽게 종종는 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> 메서드보다 더 많이 제어할 신호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-106">Event wait handles are often easier to use than the <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> and <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> methods, and they offer more control over signaling.</span></span> <span data-ttu-id="f321d-107">명명된 이벤트 대기 핸들은 응용 프로그램 도메인 및 프로세스에 작업을 동기화하는 데 사용할 수 있습니다. 이 때 모니터는 응용 프로그램 도메인에 대해 로컬입니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-107">Named event wait handles can also be used to synchronize activities across application domains and processes, whereas monitors are local to an application domain.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f321d-108">단원 내용</span><span class="sxs-lookup"><span data-stu-id="f321d-108">In This Section</span></span>  
 [<span data-ttu-id="f321d-109">EventWaitHandle</span><span class="sxs-lookup"><span data-stu-id="f321d-109">EventWaitHandle</span></span>](../../../docs/standard/threading/eventwaithandle.md)  
 <span data-ttu-id="f321d-110"><xref:System.Threading.EventWaitHandle> 수동 재설정 이벤트를 나타내거나 로컬 이벤트 또는 명명 된 시스템 이벤트 또는 클래스 자동을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-110">The <xref:System.Threading.EventWaitHandle> class can represent either automatic or manual reset events and either local events or named system events.</span></span>  
  
 [<span data-ttu-id="f321d-111">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="f321d-111">AutoResetEvent</span></span>](../../../docs/standard/threading/autoresetevent.md)  
 <span data-ttu-id="f321d-112"><xref:System.Threading.AutoResetEvent> 클래스에서 파생 <xref:System.Threading.EventWaitHandle> 자동으로 다시 설정 하는 로컬 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-112">The <xref:System.Threading.AutoResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that resets automatically.</span></span>  
  
 [<span data-ttu-id="f321d-113">ManualResetEvent 및 ManualResetEventSlim</span><span class="sxs-lookup"><span data-stu-id="f321d-113">ManualResetEvent and ManualResetEventSlim</span></span>](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <span data-ttu-id="f321d-114"><xref:System.Threading.ManualResetEvent> 클래스에서 파생 <xref:System.Threading.EventWaitHandle> 수동으로 다시 설정 해야 하는 로컬 이벤트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-114">The <xref:System.Threading.ManualResetEvent> class derives from <xref:System.Threading.EventWaitHandle> and represents a local event that must be reset manually.</span></span> <span data-ttu-id="f321d-115"><xref:System.Threading.ManualResetEventSlim> 클래스는 동일한 프로세스 내에서 이벤트에 대해 사용할 수 있는 간단한, 빠른 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-115">The <xref:System.Threading.ManualResetEventSlim> class is a lightweight, faster version that can be used for events within the same process.</span></span>  
  
 [<span data-ttu-id="f321d-116">CountdownEvent</span><span class="sxs-lookup"><span data-stu-id="f321d-116">CountdownEvent</span></span>](../../../docs/standard/threading/countdownevent.md)  
 <span data-ttu-id="f321d-117"><xref:System.Threading.CountdownEvent> 클래스는 코드를 사용 하 여 대기 핸들에서 분기/조인 병렬 처리 패턴을 구현 하는 간단한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-117">The <xref:System.Threading.CountdownEvent> class provides a simplified way to implement fork/join parallelism patterns in code that uses wait handles.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f321d-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="f321d-118">Related Sections</span></span>  
 [<span data-ttu-id="f321d-119">대기 핸들</span><span class="sxs-lookup"><span data-stu-id="f321d-119">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <span data-ttu-id="f321d-120"><xref:System.Threading.WaitHandle> 클래스는에 대 한 기본 클래스는 <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, 및 <xref:System.Threading.Mutex> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-120">The <xref:System.Threading.WaitHandle> class is the base class for the <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, and <xref:System.Threading.Mutex> classes.</span></span> <span data-ttu-id="f321d-121">와 같은 정적 메서드가 포함 <xref:System.Threading.WaitHandle.SignalAndWait%2A> 및 <xref:System.Threading.WaitHandle.WaitAll%2A> 하는 모든 유형의 대기 핸들을 작업할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f321d-121">It contains static methods such as <xref:System.Threading.WaitHandle.SignalAndWait%2A> and <xref:System.Threading.WaitHandle.WaitAll%2A> that are useful when working with all types of wait handles.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f321d-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f321d-122">See Also</span></span>  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [<span data-ttu-id="f321d-123">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="f321d-123">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="f321d-124">관리되는 스레딩 기본 사항</span><span class="sxs-lookup"><span data-stu-id="f321d-124">Managed Threading Basics</span></span>](../../../docs/standard/threading/managed-threading-basics.md)
