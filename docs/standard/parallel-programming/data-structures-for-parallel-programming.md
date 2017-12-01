---
title: "병렬 프로그래밍을 위한 데이터 구조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data structures, multi-threading
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f35c5382455021f0a001604367e59204ce4ad93c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="data-structures-for-parallel-programming"></a>병렬 프로그래밍을 위한 데이터 구조
.NET Framework 버전 4에서는 동시 컬렉션 클래스, 간단한 동기화 기본 형식 및 초기화 지연에 대 한 형식 집합을 포함 하는 병렬 프로그래밍에 유용한 몇 가지 새로운 유형을 소개 합니다. 작업 병렬 라이브러리 및 PLINQ를 포함 하 여 모든 다중 스레드 응용 프로그램 코드와 이러한 형식을 사용할 수 있습니다.  
  
## <a name="concurrent-collection-classes"></a>동시 컬렉션 클래스  
 컬렉션에 있는 클래스는 <xref:System.Collections.Concurrent?displayProperty=nameWithType> 네임 스페이스 제공 스레드로부터 안전 하 고 추가 하 고, 가능 잠금을 방지 하는 작업을 제거 하 고, 잠금은 필요한 세분화 된 잠금을 사용 합니다. .NET Framework 버전 1.0 및 2.0에서에서 도입 된 컬렉션과 달리 동시 컬렉션 클래스는 항목에 액세스할 때에 잠금을 수행 하는 사용자 코드를 필요가 없습니다. 동시 컬렉션 클래스 성능이 크게 향상 형식에 대 등 <xref:System.Collections.ArrayList?displayProperty=nameWithType> 및 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> (사용자 구현 잠금을)으로 여러 스레드를 추가 하 고 컬렉션에서 항목을 제거할 시나리오에서 합니다.  
  
 다음 표에서 새 동시 컬렉션 클래스를 보여 줍니다.  
  
|형식|설명|  
|----------|-----------------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType>을 구현하는 스레드로부터 안전한 컬렉션에 대한 차단 및 경계 기능을 제공합니다. 생산자 스레드는 사용할 수 있는 슬롯이 없습니다. 또는 컬렉션이 전체 차단 합니다. 소비자 스레드 컬렉션이 비어 있는 경우 차단 합니다. 이 형식에는 소비자와 공급자에 비 블록 킹 액세스를 지원합니다. <xref:System.Collections.Concurrent.BlockingCollection%601>기본 클래스로 사용할 수 있고 백업 차단 하 고 지 원하는 모든 컬렉션 클래스에 대 한 경계를 제공 하는 저장소 <xref:System.Collections.Generic.IEnumerable%601>합니다.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>|확장성을 제공 하는 스레드로부터 안전한 모음 구현 추가 하 고 작업을 가져옵니다.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>|확장 가능한 동시 사전 형식입니다.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>|동시 및 확장 가능한 FIFO 큐입니다.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=nameWithType>|동시 및 확장 가능한 LIFO 스택입니다.|  
  
 자세한 내용은 [스레드로부터 안전한 컬렉션](../../../docs/standard/collections/thread-safe/index.md)을 참조하세요.  
  
## <a name="synchronization-primitives"></a>동기화 기본 형식  
 새 동기화 기본은 <xref:System.Threading?displayProperty=nameWithType> 레거시 다중 스레딩 코드에 비용이 많이 드는 잠금 메커니즘을 방지 하 여 세분화 된 동시성 및 성능을 향상 시키려면 네임 스페이스 사용 하도록 설정 합니다. 새 형식 중 일부와 같은 <xref:System.Threading.Barrier?displayProperty=nameWithType> 및 <xref:System.Threading.CountdownEvent?displayProperty=nameWithType> .NET Framework의 이전 릴리스에서 없는 버전이 있으며 합니다.  
  
 다음 표에서 새로운 동기화 형식을 나열합니다.  
  
|형식|설명|  
|----------|-----------------|  
|<xref:System.Threading.Barrier?displayProperty=nameWithType>|여러 스레드를를 각 작업 신호 도착 하 고 다음 차단할 수 일부 또는 모든 작업이 도착 될 때까지 지점을 제공 하 여 특정 알고리즘에서 병렬로에서 작업할 수 있습니다. 자세한 내용은 [Barrier](../../../docs/standard/threading/barrier.md)를 참조하세요.|  
|<xref:System.Threading.CountdownEvent?displayProperty=nameWithType>|쉽게 rendezvous 메커니즘을 제공 하 여 분기 및 조인 시나리오를 단순화 합니다. 자세한 내용은 참조 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)합니다.|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>|동기화 기본 형식을 비슷합니다 <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>합니다. <xref:System.Threading.ManualResetEventSlim>간단한 하지만 프로세스 내의 통신에만 사용할 수 있습니다. 자세한 내용은 참조 [ManualResetEvent 및 ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)합니다.|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=nameWithType>|리소스를 동시에 액세스할 수 있는 스레드 수 또는 리소스 풀을 제한 하는 동기화 기본 형식입니다. 자세한 내용은 참조 [세마포 및 SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)합니다.|  
|<xref:System.Threading.SpinLock?displayProperty=nameWithType>|스레드를 발생 시키는 상호 배제 잠금 기본 형식을 루프에서 대기 하도록 잠금을 획득 하려고 합니다. 또는 *스핀*, 퀀텀을 생성 하기 전에 일정 기간에 대 한 합니다. 잠금 대기 시간이 짧거나 되도록 필요한 시나리오에서 <xref:System.Threading.SpinLock> 뛰어난 다른 형태의 잠금 성능을 제공 합니다. 자세한 내용은 참조 [SpinLock](../../../docs/standard/threading/spinlock.md)합니다.|  
|<xref:System.Threading.SpinWait?displayProperty=nameWithType>|지정된 된 시간 동안이 고 결국으로 회전 하는 작고 단순한 형식 스핀 수를 초과 하는 스레드가 대기 상태로 전환 합니다.  자세한 내용은 참조 [SpinWait](../../../docs/standard/threading/spinwait.md)합니다.|  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [방법: 낮은 수준의 동기화에 SpinLock 사용](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [방법: 동시 작업을 장벽과 동기화](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)합니다.  
  
## <a name="lazy-initialization-classes"></a>초기화 지연 클래스  
 초기화 지연을 사용 필요할 때까지 개체에 대 한 메모리 할당 되지 않습니다. 초기화 지연 프로그램의 수명 기간 전체 개체 할당을 균등 하 게 분배 하 여 성능을 향상 시킬 수 있습니다. 모든 사용자 지정 형식에 대해 초기화 지연을 사용 하도록 설정할 형식을 래핑하여 수 <xref:System.Lazy%601>합니다.  
  
 다음 표에서 초기화 지연 형식을 보여 줍니다.  
  
|형식|설명|  
|----------|-----------------|  
|<xref:System.Lazy%601?displayProperty=nameWithType>|간단 하 고 스레드 안전 초기화 지연를 제공합니다.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType>|나중에 호출 초기화 함수가 각 스레드가 스레드 단위로에 지연 초기화 값을 제공 합니다.|  
|<xref:System.Threading.LazyInitializer?displayProperty=nameWithType>|초기화 지연 전용된 인스턴스를 할당할 필요가 없도록 하는 정적 메서드를 제공 합니다. 대신, 참조 대상이 액세스할 때 초기화 되었는지 확인 하려면 사용 합니다.|  
  
 자세한 내용은 [초기화 지연](../../../docs/framework/performance/lazy-initialization.md)을 참조하세요.  
  
## <a name="aggregate-exceptions"></a>집계 예외  
 <xref:System.AggregateException?displayProperty=nameWithType> 형식을 별도 스레드에서 동시에 throw 되 고 조인 하는 스레드는 단일 예외로 반환 하는 여러 예외 캡처를 사용할 수 있습니다. <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> 사용 하 여 형식 및 PLINQ <xref:System.AggregateException> 이 목적을 위해 광범위 하 게 합니다. 자세한 내용은 참조 [NIB: 방법: 작업에서 발생 한 예외 처리](http://msdn.microsoft.com/en-us/d6c47ec8-9de9-4880-beb3-ff19ae51565d) 및 [하는 방법: PLINQ 쿼리의 예외 처리](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 <xref:System.Threading?displayProperty=nameWithType>  
 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)
