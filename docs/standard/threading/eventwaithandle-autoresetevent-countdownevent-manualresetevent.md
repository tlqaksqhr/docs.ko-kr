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
# <a name="eventwaithandle-autoresetevent-countdownevent-manualresetevent"></a>EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
이벤트 대기 핸들을 통해 스레드가 서로 신호를 보내고 상대방의 신호를 대기하여 작업을 동기화할 수 있습니다. 이러한 동기화 이벤트는 Win32 대기 핸들을 기반으로 하고 신호를 보낼 때 자동으로 다시 설정되는 이벤트 및 수동으로 다시 설정되는 이벤트라는 두 가지 유형으로 나눌 수 있습니다.  
  
 이벤트 대기 핸들은 여러으로 동일한 동기화 시나리오에서 유용는 <xref:System.Threading.Monitor> 클래스입니다. 이벤트 대기 핸들은 보다 사용 하기 쉽게 종종는 <xref:System.Threading.Monitor.Wait%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Monitor.Pulse%2A?displayProperty=nameWithType> 메서드보다 더 많이 제어할 신호를 제공 합니다. 명명된 이벤트 대기 핸들은 응용 프로그램 도메인 및 프로세스에 작업을 동기화하는 데 사용할 수 있습니다. 이 때 모니터는 응용 프로그램 도메인에 대해 로컬입니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 <xref:System.Threading.EventWaitHandle> 수동 재설정 이벤트를 나타내거나 로컬 이벤트 또는 명명 된 시스템 이벤트 또는 클래스 자동을 나타낼 수 있습니다.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 <xref:System.Threading.AutoResetEvent> 클래스에서 파생 <xref:System.Threading.EventWaitHandle> 자동으로 다시 설정 하는 로컬 이벤트를 나타냅니다.  
  
 [ManualResetEvent 및 ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <xref:System.Threading.ManualResetEvent> 클래스에서 파생 <xref:System.Threading.EventWaitHandle> 수동으로 다시 설정 해야 하는 로컬 이벤트를 나타냅니다. <xref:System.Threading.ManualResetEventSlim> 클래스는 동일한 프로세스 내에서 이벤트에 대해 사용할 수 있는 간단한, 빠른 버전입니다.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 <xref:System.Threading.CountdownEvent> 클래스는 코드를 사용 하 여 대기 핸들에서 분기/조인 병렬 처리 패턴을 구현 하는 간단한 방법을 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [대기 핸들](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 <xref:System.Threading.WaitHandle> 클래스는에 대 한 기본 클래스는 <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore>, 및 <xref:System.Threading.Mutex> 클래스입니다. 와 같은 정적 메서드가 포함 <xref:System.Threading.WaitHandle.SignalAndWait%2A> 및 <xref:System.Threading.WaitHandle.WaitAll%2A> 하는 모든 유형의 대기 핸들을 작업할 때 유용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)  
 [관리되는 스레딩 기본 사항](../../../docs/standard/threading/managed-threading-basics.md)
