---
title: "스레딩 개체 및 기능"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], features
- managed threading
ms.assetid: 239b2e8d-581b-4ca3-992b-0e8525b9321c
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a73e5c60a661c171e9e46e6307484cf5e0e6b80
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="threading-objects-and-features"></a>스레딩 개체 및 기능
.NET Framework에서는 다중 스레드 응용 프로그램을 만들고 관리하는 데 도움이 되는 많은 개체를 제공합니다. 관리되는 스레드는 <xref:System.Threading.Thread> 클래스를 통해 표현됩니다. <xref:System.Threading.ThreadPool> 클래스는 다중 스레드 백그라운드 작업을 쉽게 만들고 관리할 수 있게 해줍니다. <xref:System.ComponentModel.BackgroundWorker> 클래스는 사용자 인터페이스와 상호 작용하는 작업에 대해 동일한 기능을 수행합니다. <xref:System.Threading.Timer> 클래스는 정해진 간격마다 백그라운드 작업을 실행합니다.  
  
 또한 .NET Framework 버전 2.0에서 도입된 <xref:System.Threading.Semaphore> 및 <xref:System.Threading.EventWaitHandle> 클래스를 포함하여 스레드 작업을 동기화하는 많은 클래스가 있습니다. 이러한 클래스의 기능은 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)에서 비교합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [관리되는 스레드 풀](../../../docs/standard/threading/the-managed-thread-pool.md)  
 직접 스레드 관리를 수행할 필요 없이 스레드에 작업을 실행하도록 요청할 수 있게 해주는 **ThreadPool** 클래스를 설명합니다.  
  
 [타이머](../../../docs/standard/threading/timers.md)  
 **Timer**를 사용하여 대리자가 지정된 시간에 호출되도록 지정하는 방법을 설명합니다.  
  
 [모니터](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 **Monitor** 클래스를 사용하여 멤버에 대한 액세스를 동기화하거나 고유한 스레드 관리 유형을 빌드하는 방법을 설명합니다.  
  
 [대기 핸들](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)  
 이벤트 대기 핸들, 뮤텍스 및 세마포에 대한 추상 기본 클래스로 여러 동기화 이벤트를 대기할 수 있게 해주는 <xref:System.Threading.WaitHandle> 클래스를 설명합니다.  
  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 신호 전송 및 신호 대기를 통해 스레드 작업을 동기화하는 데 사용되는 관리되는 이벤트 대기 핸들을 설명합니다.  
  
 [뮤텍스](../../../docs/standard/threading/mutexes.md)  
 사용 하는 방법에 설명 된 <xref:System.Threading.Mutex> 개체에 대 한 액세스를 동기화 하거나 고유한 동기화 메커니즘을 구축 합니다.  
  
 [연동 작업](../../../docs/standard/threading/interlocked-operations.md)  
 <xref:System.Threading.Interlocked> 클래스를 사용하여 값을 증가 또는 감소시키고 단일 원자성 작업에 값을 저장하는 방법을 설명합니다.  
  
 [판독기 및 작성기 잠금](../../../docs/standard/threading/reader-writer-locks.md)  
 단일 작성기/다중 판독기 의미 체계를 구현하는 잠금을 정의합니다.  
  
 [세마포 및 SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)  
 <xref:System.Threading.Semaphore> 개체 및 이 개체를 사용하여 제한된 리소스에 대한 액세스를 제어하는 방법을 설명합니다.  
  
 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)  
 관리되는 스레드 잠금 및 동기화를 위해 제공되는 .NET Framework 클래스의 기능을 비교합니다.  
  
 [장벽](../../../docs/standard/threading/barrier.md)  
 단계별 작업에서 스레드를 조정하기 위해 장벽 패턴을 구현하는 <xref:System.Threading.Barrier> 개체를 설명합니다.  
  
 [스핀 잠금](../../../docs/standard/threading/spinlock.md)  
 특정 하위 수준 시나리오에 대한 Monitor 클래스의 경량 대체 항목인 <xref:System.Threading.SpinLock>을 설명합니다.  
  
 [스핀 대기](../../../docs/standard/threading/spinwait.md)  
 커널 기반 대기를 시작하기 전에 사용 중인 회전을 수행하는 낮은 수준의 동기화 기본 형식인 <xref:System.Threading.SpinWait>를 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Threading.Thread>  
 비관리 코드에서 가져왔는지 또는 관리되는 응용 프로그램에서 만들어졌는지에 관계없이 관리되는 스레드를 나타내는 **Thread** 클래스에 대한 참조 설명서를 제공합니다.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 사용자 인터페이스 스레드에서 발생하는 이벤트를 통해 통신하여 사용자 인터페이스와 상호 작용하는 백그라운드 작업을 사용하도록 설정합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [비동기 파일 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 I/O 비동기 완료 포트가 스레드 풀을 사용하여 입출력 작업이 완료된 경우에만 처리를 요청하는 방법을 설명합니다.  
  
 [TPL(작업 병렬 라이브러리)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 이상에서 다중 스레드 프로그래밍에 권장되는 접근 방식을 설명합니다.
