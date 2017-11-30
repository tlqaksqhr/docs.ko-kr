---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69d16e8c6491b4c66ab5a5452762e73172ebbb77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="autoresetevent"></a><span data-ttu-id="a0bdc-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="a0bdc-102">AutoResetEvent</span></span>
<span data-ttu-id="a0bdc-103"><xref:System.Threading.AutoResetEvent> 대기 스레드 하나를 해제 한 후 신호를 받을 때 자동으로 다시 설정 하는 로컬 대기 핸들 이벤트 클래스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a0bdc-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="a0bdc-104">이 클래스는 기본 클래스의 특수 한 경우를 나타냅니다. <xref:System.Threading.EventWaitHandle>합니다.</span><span class="sxs-lookup"><span data-stu-id="a0bdc-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="a0bdc-105">자동 재설정 이벤트의 사용 및 기능은 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 개념 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0bdc-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="a0bdc-106"><xref:System.Threading.AutoResetEvent> 개체는 자동으로 다시 설정에 신호 시스템에서 대기 중인 단일 스레드가 해제 된 후입니다.</span><span class="sxs-lookup"><span data-stu-id="a0bdc-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="a0bdc-107">대기 스레드가 없으면 이벤트 개체의 상태는 신호를 받은 것으로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0bdc-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="a0bdc-108"><xref:System.Threading.AutoResetEvent>해당 하는 Win32 `CreateEvent` 지정 함으로써 호출 `false` 에 대 한는 `bManualReset` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="a0bdc-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="a0bdc-109">사용 하는 예제에 대 한 <xref:System.Threading.AutoResetEvent>, 참조 [모니터](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0bdc-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0bdc-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0bdc-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="a0bdc-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="a0bdc-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="a0bdc-112">스레딩</span><span class="sxs-lookup"><span data-stu-id="a0bdc-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="a0bdc-113">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="a0bdc-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="a0bdc-114">대기 핸들</span><span class="sxs-lookup"><span data-stu-id="a0bdc-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
