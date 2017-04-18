---
title: "Data Structures for Parallel Programming | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "data structures, multi-threading"
ms.assetid: bdc82f2f-4754-45a1-a81e-fe2e9c30cef9
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Data Structures for Parallel Programming
.NET Framework 버전 4에서는 여러 개의 동시 컬렉션 클래스, 간단한 동기화 기본 형식 및 초기화 지연을 위한 형식을 비롯하여 병렬 프로그래밍에 유용한 몇 가지 새로운 형식이 추가되었습니다.  이러한 형식은 작업 병렬 라이브러리 및 PLINQ 등의 다중 스레드 응용 프로그램과 함께 사용할 수 있습니다.  
  
## 동시 컬렉션 클래스  
 <xref:System.Collections.Concurrent?displayProperty=fullName> 네임스페이스의 컬렉션 클래스는 가능하면 잠금을 피하고 잠금이 필요할 경우에는 미세 잠금을 사용하는 스레드로부터 안전한 추가 및 제거 작업을 제공합니다.  .NET Framework 버전 1.0 및 2.0에서 도입되었던 컬렉션과 달리 동시 컬렉션 클래스에서는 항목에 액세스할 때 잠금을 가져오는 사용자 코드를 사용할 필요가 없습니다.  여러 스레드에서 컬렉션의 항목을 추가 및 제거하는 경우에 동시 컬렉션 클래스를 사용하면 사용자 구현 잠금을 사용하는 <xref:System.Collections.ArrayList?displayProperty=fullName> 및 <xref:System.Collections.Generic.List%601?displayProperty=fullName> 등의 형식을 사용할 때보다 성능을 상당히 향상시킬 수 있습니다.  
  
 다음 표에서는 새로 추가된 동시 컬렉션 클래스를 보여 줍니다.  
  
|형식|설명|  
|--------|--------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName>을 구현하는 스레드로부터 안전한 컬렉션에 대한 차단 및 경계 기능을 제공합니다.  공급자 스레드는 사용 가능한 슬롯이 없거나 컬렉션이 가득 찬 경우에 차단되고,  소비자 스레드는 컬렉션이 비어 있는 경우에 차단됩니다.  이 형식은 소비자와 공급자에 의한 비차단 액세스도 지원합니다.  <xref:System.Collections.Concurrent.BlockingCollection%601>을 기본 클래스나 백업 저장소로 사용하여 <xref:System.Collections.Generic.IEnumerable%601>을 지원하는 컬렉션 클래스에 대한 차단 및 경계 기능을 제공할 수 있습니다.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>|확장 가능한 추가 및 가져오기 작업을 제공하는 스레드로부터 안전한 모음 구현입니다.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>|확장 가능한 동시 사전 형식입니다.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>|확장 가능한 동시 FIFO 큐입니다.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName>|확장 가능한 동시 LIFO 스택입니다.|  
  
 자세한 내용은 [스레드로부터 안전한 컬렉션](../../../docs/standard/collections/thread-safe/index.md)을 참조하십시오.  
  
## 동기화 기본 형식  
 <xref:System.Threading?displayProperty=fullName> 네임스페이스의 새로운 동기화 기본 형식을 통해 레거시 다중 스레딩 코드에 사용되는 부담이 큰 잠금 메커니즘을 피할 수 있고 이를 통해 세부적인 동시성과 더 빠른 성능을 얻을 수 있습니다.  새 형식 중 <xref:System.Threading.Barrier?displayProperty=fullName> 및 <xref:System.Threading.CountdownEvent?displayProperty=fullName>와 같은 일부 형식은 이전 버전의 .NET Framework에는 없던 완전히 새로운 형식입니다.  
  
 다음 표에서는 새로운 동기화 형식을 보여 줍니다.  
  
|형식|설명|  
|--------|--------|  
|<xref:System.Threading.Barrier?displayProperty=fullName>|각 작업에서 해당 작업이 장벽에 도달했음을 알린 다음 일부 또는 모든 작업이 도착할 때까지 차단될 수 있는 지점을 제공하여 여러 스레드가 한 알고리즘에서 병렬로 작동할 수 있게 해 줍니다.  자세한 내용은 [Barrier](../../../docs/standard/threading/barrier.md)을 참조하십시오.|  
|<xref:System.Threading.CountdownEvent?displayProperty=fullName>|쉬운 집결 메커니즘을 제공하여 분기\/조인 시나리오를 단순화합니다.  자세한 내용은 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)을 참조하십시오.|  
|<xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>|<xref:System.Threading.ManualResetEvent?displayProperty=fullName>와 비슷한 동기화 기본 형식입니다.  <xref:System.Threading.ManualResetEventSlim>은 이보다 더 단순하지만 프로세스 내 통신에만 사용할 수 있습니다.  자세한 내용은 [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)을 참조하십시오.|  
|<xref:System.Threading.SemaphoreSlim?displayProperty=fullName>|리소스 또는 리소스 풀에 동시에 액세스할 수 있는 스레드 수를 제한하는 동기화 기본 형식입니다.  자세한 내용은 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)을 참조하십시오.|  
|<xref:System.Threading.SpinLock?displayProperty=fullName>|잠금을 획득하려고 하는 스레드가 퀀텀을 생성하기 전에 일정 시간 동안 루프, 즉 *스핀*에서 대기하도록 하는 상호 제외 잠금 기본 형식입니다.  잠금 대기 시간이 짧아야 하는 경우 <xref:System.Threading.SpinLock>은 다른 형태의 잠금보다 뛰어난 성능을 제공합니다.  자세한 내용은 [SpinLock](../../../docs/standard/threading/spinlock.md)을 참조하십시오.|  
|<xref:System.Threading.SpinWait?displayProperty=fullName>|지정된 시간 동안 스핀하다가 스핀 횟수가 초과되면 스레드를 대기 상태로 전환하는 작고 단순한 형식입니다.  자세한 내용은 [SpinWait](../../../docs/standard/threading/spinwait.md)을 참조하십시오.|  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [How to: Use SpinLock for Low\-Level Synchronization](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)  
  
-   [How to: Synchronize Concurrent Operations with a Barrier](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md).  
  
## 초기화 지연 클래스  
 초기화 지연을 사용하면 필요할 때까지 개체의 메모리가 할당되지 않습니다.  초기화 지연 기능은 개체 할당을 프로그램의 수명 기간 전체에 균일하게 분산시켜 성능을 향상시킬 수 있습니다.  <xref:System.Lazy%601> 형식을 래핑하여 모든 사용자 지정 형식에 대해 초기화 지연을 사용할 수 있습니다.  
  
 다음 표에서는 초기화 지연 형식을 보여 줍니다.  
  
|형식|설명|  
|--------|--------|  
|<xref:System.Lazy%601?displayProperty=fullName>|단순하고 스레드로부터 안전한 초기화 지연 기능을 제공합니다.|  
|<xref:System.Threading.ThreadLocal%601?displayProperty=fullName>|스레드별로 초기화 지연된 값을 제공하여 각 스레드에서 초기화 함수를 나중에 호출하도록 합니다.|  
|<xref:System.Threading.LazyInitializer?displayProperty=fullName>|전용의 초기화 지연 인스턴스를 할당할 필요가 없도록 하는 정적 메서드를 제공합니다.  대신 이러한 메서드는 참조를 사용하여 대상에 액세스할 때 대상이 초기화되었는지 확인합니다.|  
  
 자세한 내용은 [초기화 지연](../../../docs/framework/performance/lazy-initialization.md)을 참조하십시오.  
  
## 집계 예외  
 <xref:System.AggregateException?displayProperty=fullName> 형식을 사용하여 개별 스레드에서 동시에 throw된 여러 예외를 캡처하고 이를 조인하는 스레드에 단일 예외로 반환할 수 있습니다.  <xref:System.Threading.Tasks.Task?displayProperty=fullName> 및 <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> 형식과 PLINQ에는 이를 주 목적으로 하는 <xref:System.AggregateException>이 사용됩니다.  자세한 내용은 [NIB: How to: Handle Exceptions Thrown by Tasks](http://msdn.microsoft.com/ko-kr/d6c47ec8-9de9-4880-beb3-ff19ae51565d) 및 [How to: Handle Exceptions in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 <xref:System.Threading?displayProperty=fullName>   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)