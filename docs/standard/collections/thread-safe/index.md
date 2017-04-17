---
title: "스레드로부터 안전한 컬렉션 | Microsoft Docs"
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
  - "스레드로부터 안전한 컬렉션, 개요"
ms.assetid: 2e7ca21f-786c-4367-96be-0cf3f3dcc6bd
caps.latest.revision: 24
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 24
---
# 스레드로부터 안전한 컬렉션
[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]에는 스레드로부터 안전하고 확장 가능한 컬렉션 클래스를 여러 개 포함하는 <xref:System.Collections.Concurrent?displayProperty=fullName> 네임스페이스가 도입되어 있습니다.  다중 스레드는 이러한 컬렉션에서 안전하고 효율적으로 항목을 추가하거나 제거할 수 있고, 이를 위해 사용자 코드에서 추가로 동기화가 필요하지는 않습니다.  새 코드를 작성할 경우 컬렉션이 다중 스레드에 동시에 쓸 때마다 동시 컬렉션 클래스를 사용합니다.  공유 컬렉션에서 읽기만 하는 경우에는 <xref:System.Collections.Generic?displayProperty=fullName> 네임스페이스의 클래스를 사용할 수 있습니다.  .NET Framework 1.1 이하의 런타임을 대상으로 지정해야 하는 경우가 아니라면 1.0 컬렉션 클래스는 사용하지 않는 것이 좋습니다.  
  
## .NET Framework 1.0 및 2.0 컬렉션에서 스레드 동기화  
 .NET Framework 1.0에서 도입된 컬렉션은 <xref:System.Collections?displayProperty=fullName> 네임스페이스에 있습니다.  이러한 컬렉션은 널리 사용되는 <xref:System.Collections.ArrayList> 및 <xref:System.Collections.Hashtable>을 포함하며, `Synchronized` 속성을 통해 스레드 보안을 제공합니다. 이 속성은 컬렉션을 둘러싸는 스레드로부터 안전한 래퍼를 반환합니다.  이 래퍼는 추가 또는 제거 작업이 수행될 때마다 전체 컬렉션을 잠가 작동합니다.  따라서 컬렉션에 액세스하려는 각 스레드는 잠금을 얻기 위해 차례를 기다려야 합니다.  이는 확장될 수 없으며 대규모 컬렉션의 경우 성능이 크게 저하될 수도 있습니다.  또한 디자인은 경합 상태로부터 완벽히 보호되지 않습니다.  자세한 내용은 MSDN 웹 사이트에서 [제네릭 컬렉션에서의 동기화](http://go.microsoft.com/fwlink/?LinkID=161130) 을 참조하십시오.  
  
 .NET Framework 2.0에서 도입된 컬렉션 클래스는 <xref:System.Collections.Generic?displayProperty=fullName> 네임스페이스에 있습니다.  이러한 클래스에는 <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602> 등이 있으며,  .NET Framework 1.0 클래스에 비해 향상된 형식 안전성 및 성능을 제공합니다.  그러나 .NET Framework 2.0 컬렉션 클래스는 스레드 동기화를 전혀 제공하지 않으므로 다중 스레드에서 항목이 동시에 추가 또는 삭제될 경우 사용자 코드에서 모든 동기화를 제공해야 합니다.  
  
 .NET Framework 2.0 컬렉션 클래스의 형식 안전성을 제공할 뿐 아니라 [!INCLUDE[net_v10_short](../../../../includes/net-v10-short-md.md)] 컬렉션에 비해 보다 효율적이고 완벽한 스레드 보안을 제공하는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]의 동시 컬렉션 클래스를 사용하는 것이 좋습니다.  
  
## 미세 잠금 메커니즘 및 잠금이 필요 없는 메커니즘  
 동시 컬렉션 형식 중 일부는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]에서 새로 도입된 <xref:System.Threading.SpinLock>, <xref:System.Threading.SpinWait>, <xref:System.Threading.SemaphoreSlim> 및 <xref:System.Threading.CountdownEvent> 같은 간단한 동기화 메커니즘을 사용합니다.  이러한 동기화 형식에서는 스레드를 진정한 대기 상태로 전환하기 이전의 짧은 시간 동안 *바쁘게 돌아가는 회전*이 일반적으로 사용됩니다.  대기 시간이 매우 짧을 것으로 예상될 경우 회전에는 부담이 큰 커널 전환을 포함하는 대기에 비해 훨씬 적은 계산 과정이 필요합니다.  따라서 회전을 사용하는 컬렉션 클래스의 경우 이러한 효율성 덕분에 다중 스레드가 매우 높은 속도로 항목을 추가 및 제거할 수 있습니다.  경계 vs. 차단에 대한 자세한 내용은 [SpinLock](../../../../docs/standard/threading/spinlock.md) 및 [SpinWait](../../../../docs/standard/threading/spinwait.md) 를 참조하십시오.  
  
 <xref:System.Collections.Concurrent.ConcurrentQueue%601> 및 <xref:System.Collections.Concurrent.ConcurrentStack%601> 클래스에서는 잠금을 전혀 사용하지 않습니다.  대신 <xref:System.Threading.Interlocked> 작업을 사용하여 스레드 보안을 달성합니다.  
  
> [!NOTE]
>  동시 컬렉션 클래스는 <xref:System.Collections.ICollection>을 지원하므로 <xref:System.Collections.ICollection.IsSynchronized%2A> 및 <xref:System.Collections.ICollection.SyncRoot%2A> 속성이 서로 관련 없는 경우에도 이러한 속성의 구현을 제공합니다.  `IsSynchronized`는 항상 `false`를 반환하고 `SyncRoot`는 항상 `null`\(Visual Basic의 경우 `Nothing`\)입니다.  
  
 다음 표에서는 <xref:System.Collections.Concurrent?displayProperty=fullName> 네임스페이스에 있는 컬렉션 형식을 보여 줍니다.  
  
|형식|설명|  
|--------|--------|  
|<xref:System.Collections.Concurrent.BlockingCollection%601>|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601>을 구현하는 모든 형식에 대해 경계 및 차단 기능을 제공합니다.  자세한 내용은 [BlockingCollection 개요](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)을 참조하십시오.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602>|키\-값 쌍을 포함하는 사전을 스레드로부터 안전하게 구현합니다.|  
|<xref:System.Collections.Concurrent.ConcurrentQueue%601>|FIFO\(선입선출\) 큐를 스레드로부터 안전하게 구현합니다.|  
|<xref:System.Collections.Concurrent.ConcurrentStack%601>|LIFO\(후입선출\) 스택을 스레드로부터 안전하게 구현합니다.|  
|<xref:System.Collections.Concurrent.ConcurrentBag%601>|정렬되지 않은 요소 컬렉션을 스레드로부터 안전하게 구현합니다.|  
|<xref:System.Collections.Concurrent.IProducerConsumerCollection%601>|`BlockingCollection`에서 사용되기 위해 형식이 구현해야 하는 인터페이스입니다.|  
  
## 관련 항목  
  
|제목|설명|  
|--------|--------|  
|[BlockingCollection 개요](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md)|<xref:System.Collections.Concurrent.BlockingCollection%601> 형식에서 제공되는 기능을 설명합니다.|  
|[방법: ConcurrentDictionary에서 항목 추가 및 제거](../../../../docs/standard/collections/thread-safe/how-to-add-and-remove-items.md)|<xref:System.Collections.Concurrent.ConcurrentDictionary%602>에서 요소를 추가 및 제거하는 방법을 설명합니다.|  
|[방법: BlockingCollection에서 개별적으로 항목 추가 및 가져오기](../../../../docs/standard/collections/thread-safe/how-to-add-and-take-items.md)|읽기 전용 열거자를 사용하지 않고 차단 컬렉션에서 항목을 추가 및 검색하는 방법을 설명합니다.|  
|[방법: 컬렉션에 경계 및 차단 기능 추가](../../../../docs/standard/collections/thread-safe/how-to-add-bounding-and-blocking.md)|컬렉션 클래스를 <xref:System.Collections.Concurrent.IProducerConsumerCollection%601> 컬렉션에 대한 내부 저장 메커니즘으로 사용하는 방법을 설명합니다.|  
|[방법: ForEach를 사용하여 BlockingCollection의 항목 제거](../../../../docs/standard/collections/thread-safe/how-to-use-foreach-to-remove.md)|`foreach`\(Visual Basic의 경우 `For Each`\)를 사용하여 차단 컬렉션에서 모든 항목을 제거하는 방법을 설명합니다.|  
|[방법: 파이프라인에서 차단 수집 배열 사용](../../../../docs/standard/collections/thread-safe/how-to-use-arrays-of-blockingcollections.md)|차단 컬렉션 여러 개를 동시에 사용하여 파이프라인을 구현하는 방법을 설명합니다.|  
|[방법: ConcurrentBag을 사용하여 개체 풀 만들기](../../../../docs/standard/collections/thread-safe/how-to-create-an-object-pool.md)|CurrentBag을 사용하여 연속적으로 새 개체를 만드는 대신 개체를 다시 사용할 수 있는 시나리오에서 성능을 향상시키는 방법을 보여 줍니다.|  
  
## 참고 항목  
 <xref:System.Collections.Concurrent?displayProperty=fullName>