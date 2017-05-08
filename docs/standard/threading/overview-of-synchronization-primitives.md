---
title: "Overview of Synchronization Primitives | Microsoft Docs"
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
  - "synchronization, threads"
  - "threading [.NET Framework],synchronizing threads"
  - "managed threading"
ms.assetid: b782bcb8-da6a-4c6a-805f-2eb46d504309
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Overview of Synchronization Primitives
.NET Framework에서는 스레드 조작을 제어하고 경합 상태를 방지할 수 있는 동기화 기본 형식 범위를 제공합니다.  이들 기본 형식은 크게 잠금, 신호 및 연관 작업의 세 범주로 구분됩니다.  
  
 범주는 깔끔하고 분명하게 정의되지 않습니다. 일부 동기화 메커니즘에는 다음과 같은 여러 범주 특성이 있습니다. 한 번에 하나의 스레드를 해제하는 이벤트는 기능상 잠금과 같고, 잠금 해제는 신호로 간주할 수 있고, 연관 작업은 잠금을 구성하는 데 사용할 수 있습니다.  그러나 범주도 유용합니다.  
  
 스레드 동기화는 협력 작업임을 고려해야 합니다.  하나라도 스레드가 동기화 메커니즘을 건너뛰고 보호된 리소스에 직접 액세스하면 해당 동기화 메커니즘이 적용되지 않습니다.  
  
 이 개요는 다음과 같은 단원으로 구성됩니다.  
  
-   [잠금](#locking)  
  
-   [Signaling](#signaling)  
  
-   [간단한 동기화 형식](#lightweight_synchronization_types)  
  
-   [SpinWait](#spinwait)  
  
-   [연동 작업](#interlocked_operations)  
  
<a name="locking"></a>   
## 잠금  
 잠금을 통해 리소스를 한 번에 하나의 스레드 또는 지정된 수의 스레드로 제어할 수 있습니다.  잠금이 사용 중일 때 단독 잠금을 요청하는 스레드는 잠금을 사용할 수 있을 때까지 차단됩니다.  
  
### 단독 잠금  
 가장 단순한 잠금 형식은 코드 블록에 대한 액세스를 제어하는 C\# `lock` 문\(Visual Basic의 `SyncLock`\)입니다.  해당 블록을 임계 영역이라고 합니다.  `lock` 문은 <xref:System.Threading.Monitor> 클래스의 <xref:System.Threading.Monitor.Enter%2A> 및 <xref:System.Threading.Monitor.Exit%2A> 메서드를 사용하여 구현하고 `try…catch…finally`를 사용하여 잠금이 해제되었는지를 확인합니다.  
  
 일반적으로 `lock` 문을 통해 작은 코드 블록을 보호하여 메서드가 두 개 이상 스패닝되지 않게 하는 것이 <xref:System.Threading.Monitor> 클래스를 사용하는 가장 좋은 방법입니다.  강력하지만 <xref:System.Threading.Monitor> 클래스는 잠금 및 교착 상태를 분리할 수 있습니다.  
  
#### Monitor 클래스  
 <xref:System.Threading.Monitor> 클래스는 `lock` 문과 함께 사용할 수 있는 추가적인 기능을 제공합니다.  
  
-   <xref:System.Threading.Monitor.TryEnter%2A> 메서드는 차단된 스레드가 지정된 간격 후에 리소스가 포기할 때까지 대기하도록 허용합니다.  잠재적인 교차 상태를 감지하고 방지하는 데 사용할 수 있는 성공 또는 실패를 나타내는 부울 값을 반환합니다.  
  
-   <xref:System.Threading.Monitor.Wait%2A> 메서드는 임계 영역에서 스레드가 호출합니다.  이 메서드는 리소스 제어를 포기하고 리소스를 다시 사용할 수 있을 때까지 차단됩니다.  
  
-   <xref:System.Threading.Monitor.Pulse%2A> 및 <xref:System.Threading.Monitor.PulseAll%2A> 메서드는 잠금을 해제하거나 <xref:System.Threading.Monitor.Wait%2A>를 호출하여 스레드 하나 이상을 준비 큐에 넣으려고 하는 스레드를 허용하므로 잠금을 획득할 수 있습니다.  
  
 <xref:System.Threading.Monitor.Wait%2A> 메서드 오버로드에 대한 시간 제한은 스레드가 준비 큐로 이스케이프될 때까지 기다리도록 허용합니다.  
  
 잠금에 사용되는 개체가 <xref:System.MarshalByRefObject>에서 파생되면 <xref:System.Threading.Monitor> 클래스는 여러 응용 프로그램 도메인에서 잠금을 제공할 수 있습니다.  
  
 <xref:System.Threading.Monitor>에는 스레드 선호도가 있습니다.  즉, 모니터를 시작한 스레드는 <xref:System.Threading.Monitor.Exit%2A> 또는 <xref:System.Threading.Monitor.Wait%2A>를 호출하여 종료해야 합니다.  
  
 <xref:System.Threading.Monitor> 클래스는 인스턴스화할 수 없습니다.  해당 메서드는 정적\(Visual Basic의 `Shared`\)이고 인스턴스화할 수 있는 잠금 개체에서 작동합니다.  
  
 개념적인 개요를 보려면 [Monitor](../Topic/Monitors.md)를 참조하세요.  
  
#### Mutex 클래스  
 스레드는 <xref:System.Threading.WaitHandle.WaitOne%2A> 메서드의 오버로드를 호출하여 <xref:System.Threading.Mutex>를 요청합니다.  스레드가 대기를 포기할 수 있도록 시간 제한이 있는 오버로드가 제공됩니다.  <xref:System.Threading.Monitor> 클래스와 달리 뮤텍스는 로컬 또는 전역일 수 있습니다.  명명된 뮤텍스라고도 하는 전역 뮤텍스는 운영 체제 전체에 표시되고 여러 응용 프로그램 도메인 또는 프로세스에서 스레드를 동기화하는 데 사용될 수 있습니다.  로컬 뮤텍스는 <xref:System.MarshalByRefObject>에서 파생되고 응용 프로그램 도메인 경계에 걸쳐 사용할 수 있습니다.  
  
 또한 <xref:System.Threading.Mutex>는 <xref:System.Threading.WaitHandle>에서 파생됩니다. 즉, <xref:System.Threading.WaitHandle.WaitAll%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> 및 <xref:System.Threading.WaitHandle.SignalAndWait%2A> 메서드와 같은 <xref:System.Threading.WaitHandle>에서 제공된 신호 메커니즘과 함께 사용할 수 있습니다.  
  
 <xref:System.Threading.Monitor>처럼 <xref:System.Threading.Mutex>에는 스레드 선호도가 있습니다.  <xref:System.Threading.Monitor>와 달리 <xref:System.Threading.Mutex>는 인스턴스화할 수 있는 개체입니다.  
  
 개념적인 개요를 보려면 [Mutexes](../../../docs/standard/threading/mutexes.md)를 참조하세요.  
  
#### SpinLock 클래스  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 <xref:System.Threading.Monitor>에 필요한 오버헤드의 성능이 저하될 때 <xref:System.Threading.SpinLock> 클래스를 사용할 수 있습니다.  <xref:System.Threading.SpinLock>는 잠긴 임계 영역을 발견하면 잠금을 사용할 수 있을 때까지 루프에서 스핀합니다.  잠시 잠금이 유지되면 스핀을 통해 차단보다 향상된 성능을 제공할 수 있습니다.  그러나 잠금이 몇 십 회 주기 이상 유지되면 <xref:System.Threading.SpinLock>은 <xref:System.Threading.Monitor>처럼 동작하지만 더 많은 CPU 주기를 사용하므로 스레드 또는 프로세스의 성능이 저하될 수 있습니다.  
  
### 기타 잠금  
 잠금은 단독 잠금일 필요가 없습니다.  리소스에 동시에 액세스할 수 있는 스레드 수를 제한하는 것이 유용할 수 있습니다.  세마포와 판독기 및 작성기 잠금은 이런 풀링된 리소스 액세스를 제어하도록 디자인되었습니다.  
  
#### ReaderWriterLock 클래스  
 <xref:System.Threading.ReaderWriterLockSlim> 클래스는 데이터를 변경하는 스레드에 리소스에 대한 단독 액세스 권한이 있어야 하는 경우를 처리합니다.  작성기가 활성화되지 않으면 판독기가 제한 없이 리소스에 액세스할 수 있습니다\(예: <xref:System.Threading.ReaderWriterLockSlim.EnterReadLock%2A> 메서드 호출을 통해\).  스레드가 단독 액세스를 요청하면\(예: <xref:System.Threading.ReaderWriterLockSlim.EnterWriteLock%2A> 메서드 호출을 통해\) 모든 기존 판독기가 잠금을 종료하고 작성기가 잠금을 시작 및 종료할 때까지 이후 작성기 요청이 차단됩니다.  
  
 <xref:System.Threading.ReaderWriterLockSlim>에는 스레드 선호도가 있습니다.  
  
 개념적인 개요를 보려면 [Reader\-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md)을 참조하세요.  
  
#### Semaphore 클래스  
 <xref:System.Threading.Semaphore> 클래스는 지정된 수만큼 스레드가 리소스에 액세스하도록 허용합니다.  리소스를 요청하는 추가적인 스레드는 스레드가 세마포를 해제할 때까지 차단됩니다.  
  
 <xref:System.Threading.Mutex> 클래스처럼 <xref:System.Threading.Semaphore>는 <xref:System.Threading.WaitHandle>에서 파생됩니다.  <xref:System.Threading.Mutex>처럼 <xref:System.Threading.Semaphore>도 로컬 또는 전역일 수 있습니다.  응용 프로그램 도메인 경계에 걸쳐 사용할 수 있습니다.  
  
 <xref:System.Threading.Monitor>, <xref:System.Threading.Mutex> 및 <xref:System.Threading.ReaderWriterLock>과 달리 <xref:System.Threading.Semaphore>에는 스레드 선호도가 없습니다.  즉, 한 스레드가 세마포를 획득하고 다른 스레드가 세마포를 해제하는 시나리오에서 사용할 수 있습니다.  
  
 개념적인 개요를 보려면 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)를 참조하세요.  
  
 <xref:System.Threading.SemaphoreSlim?displayProperty=fullName>은 단일 프로세스 경계 내에서 동기화하기 위한 간단한 세마포입니다.  
  
 [맨 위로 이동](#top)  
  
<a name="signaling"></a>   
## Signaling  
 다른 스레드의 신호를 기다리는 가장 간단한 방법은 다른 스레드가 완료될 때까지 차단되는 <xref:System.Threading.Thread.Join%2A> 메서드를 호출하는 것입니다.  <xref:System.Threading.Thread.Join%2A>에는 차단된 스레드가 지정된 간격이 지난 후 대기에서 해제되도록 허용하는 두 가지 오버로드가 있습니다.  
  
 대기 핸들은 훨씬 다양한 대기 및 신호 기능 집합을 제공합니다.  
  
### 대기 핸들  
 대기 핸들은 <xref:System.Threading.WaitHandle> 클래스에서 파생되고 이 클래스는 <xref:System.MarshalByRefObject>에서 파생됩니다.  따라서 대기 핸들을 사용하여 응용 프로그램 도메인 경계에 걸쳐 스레드 활동을 동기화할 수 있습니다.  
  
 스레드는 인스턴스 메서드 <xref:System.Threading.WaitHandle.WaitOne%2A>를 호출하거나 정적 메서드 <xref:System.Threading.WaitHandle.WaitAll%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A> 또는 <xref:System.Threading.WaitHandle.SignalAndWait%2A>의 하나를 호출하는 방식으로 대기 핸들에서 차단됩니다.  스레드가 해제되는 방식은 호출되는 메서드 및 대기 핸들 유형에 따라 달라집니다.  
  
 개념적인 개요를 보려면 [Wait Handles](../Topic/Wait%20Handles.md)을 참조하세요.  
  
#### 이벤트 대기 핸들  
 이벤트 대기 핸들에는 <xref:System.Threading.EventWaitHandle> 클래스와 파생 클래스 <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.ManualResetEvent>가 포함됩니다.  <xref:System.Threading.EventWaitHandle.Set%2A> 메서드를 호출하거나 <xref:System.Threading.WaitHandle.SignalAndWait%2A> 메서드를 사용하여 보낸 신호를 이벤트 대기 핸들이 받으면 이벤트 대기 핸들에서 스레드가 해제됩니다.  
  
 이벤트 대기 핸들은 신호를 받을 때마다 스레드를 하나만 허용하는 턴스타일처럼 자동으로 다시 설정되거나, 신호를 받을 때까지 닫혀 있다가 누군가 닫을 때까지 열려 있는 게이트처럼 수동으로 다시 설정되어야 합니다.  이름이 나타내듯이 <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.ManualResetEvent>는 각각 전자 및 후자를 나타냅니다.  <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>은 단일 프로세스 경계 내에서 동기화하기 위한 간단한 이벤트입니다.  
  
 <xref:System.Threading.EventWaitHandle>은 이벤트 형식을 나타낼 수 있고 로컬 또는 전역일 수 있습니다.  파생 클래스 <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.ManualResetEvent>는 항상 로컬입니다.  
  
 이벤트 대기 핸들에는 스레드 선호도가 없습니다.  모든 스레드가 이벤트 대기 핸들에 신호를 보낼 수 있습니다.  
  
 개념적인 개요를 보려면 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)를 참조하세요.  
  
#### 뮤텍스 및 세마포 클래스  
 <xref:System.Threading.Mutex> 및 <xref:System.Threading.Semaphore> 클래스는 <xref:System.Threading.WaitHandle>에서 파생되므로 <xref:System.Threading.WaitHandle>의 정적 메서드와 함께 사용할 수 있습니다.  예를 들어 스레드는 <xref:System.Threading.WaitHandle.WaitAll%2A> 메서드를 사용하여 <xref:System.Threading.EventWaitHandle>이 신호를 받고 <xref:System.Threading.Mutex>가 해제되고 <xref:System.Threading.Semaphore>가 해제되는 세 가지 조건이 모두 충족될 때까지 대기할 수 있습니다.  마찬가지로 스레드는 <xref:System.Threading.WaitHandle.WaitAny%2A> 메서드를 사용하여 해당 조건의 하나가 충족될 때까지 대기할 수 있습니다.  
  
 <xref:System.Threading.Mutex> 또는 <xref:System.Threading.Semaphore>의 경우 신호를 받는다는 것은 해제됨을 의미합니다.  한쪽 형식이 <xref:System.Threading.WaitHandle.SignalAndWait%2A> 메서드의 첫 번째 인수로 사용되면 해제된 것입니다.  스레드 선호도가 있는 <xref:System.Threading.Mutex>의 경우 호출하는 스레드가 뮤텍스를 소유하고 있지 않으면 예외가 throw됩니다.  앞에서 설명한 대로 세마포에는 스레드 선호도가 없습니다.  
  
#### 장벽  
 <xref:System.Threading.Barrier> 클래스는 여러 스레드가 같은 지점에서 모두 차단되고 모든 다른 스레드가 완료될 때까지 대기하도록 여러 스레드를 순환해서 동기화하는 방법을 제공합니다.  장벽은 스레드 하나 이상이 알고리즘의 다음 단계로 진행하기 전에 다른 스레드의 결과를 필요로 할 때 유용합니다.  자세한 내용은 [Barrier](../../../docs/standard/threading/barrier.md)을 참조하세요.  
  
 [맨 위로 이동](#top)  
  
<a name="lightweight_synchronization_types"></a>   
## 간단한 동기화 형식  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터는 가능할 때마다 대기 핸들과 같은 비싼 Win32 커널 개체를 사용하지 않는 방식으로 빠른 성능을 제공하는 동기화 기본 형식을 사용할 수 있습니다.  일반적으로 대기 시간이 짧은 경우와 원래 동기화 형식이 시도되었으나 만족스럽지 않은 것으로 확인된 경우에만 이들 형식을 사용해야 합니다.  간단한 형식은 프로세스 간 통신이 필요한 시나리오에서 사용할 수 없습니다.  
  
-   <xref:System.Threading.SemaphoreSlim?displayProperty=fullName>은 <xref:System.Threading.Semaphore?displayProperty=fullName>의 간단한 버전입니다.  
  
-   <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>은 <xref:System.Threading.ManualResetEvent?displayProperty=fullName>의 간단한 버전입니다.  
  
-   <xref:System.Threading.CountdownEvent?displayProperty=fullName>는 개수가 0일 때 신호를 받게 되는 이벤트를 나타냅니다.  
  
-   <xref:System.Threading.Barrier?displayProperty=fullName>를 사용하면 여러 스레드가 마스터 스레드에 의한 제어 없이 서로 동기화될 수 있습니다.  장벽은 모든 스레드가 지정된 지점에 도달할 때까지 각 스레드가 계속하지 못하도록 차단합니다.  
  
 [맨 위로 이동](#top)  
  
<a name="spinwait"></a>   
## SpinWait  
 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터는 이벤트가 신호를 받거나 조건이 충족될 때까지 스레드가 대기해야 하지만 대기 핸들을 사용하거나 현재 스레드를 차단하여 실제 대기 시간이 필요한 대기 시간보다 적을 것으로 예상할 때 <xref:System.Threading.SpinWait?displayProperty=fullName> 구조체를 사용할 수 있습니다.  <xref:System.Threading.SpinWait>를 사용하면 대기하는 동안 스핀하고 지정된 시간 안에 조건이 충족되지 않을 경우에만 대기 또는 중지를 통해 양보하는 짧은 기간을 지정할 수 있습니다.  
  
 [맨 위로 이동](#top)  
  
<a name="interlocked_operations"></a>   
## 연동 작업  
 연동 작업은 <xref:System.Threading.Interlocked> 클래스의 정적 메서드를 통해 메모리 위치에서 수행되는 간단한 원자성 작업입니다.  해당 원자성 작업에는 비교에 따라 추가, 증가 및 감소, 교환, 조건부 교환이 포함되고 32비트 플랫폼에서 64비트 값을 읽는 작업이 포함됩니다.  
  
> [!NOTE]
>  원자성 보장은 개별 작업으로 제한됩니다. 여러 작업을 한 단위로 수행해야 하면 더 개략적인 동기화 메커니즘을 사용해야 합니다.  
  
 이들 작업은 잠금이나 신호가 아니지만 잠금 및 신호를 구성하는 데 사용할 수 있습니다.  Windows 운영 체제에 기본 제공되므로 연동 작업은 매우 빠릅니다.  
  
 연동 작업은 휘발성 메모리 보장과 함께 강력한 비차단 동시성을 보이는 응용 프로그램을 작성하는 데 사용할 수 있습니다.  그러나 연동 작업에는 정교하고 낮은 수준의 프로그래밍이 필요하므로 대부분 용도에는 간단한 잠금을 선택하는 것이 좋습니다.  
  
 개념적인 개요를 보려면 [Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md)을 참조하세요.  
  
## 참고 항목  
 [Synchronizing Data for Multithreading](../../../docs/standard/threading/synchronizing-data-for-multithreading.md)   
 [Monitor](../Topic/Monitors.md)   
 [Mutexes](../../../docs/standard/threading/mutexes.md)   
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)   
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)   
 [Wait Handles](../Topic/Wait%20Handles.md)   
 [Interlocked Operations](../../../docs/standard/threading/interlocked-operations.md)   
 [Reader\-Writer Locks](../../../docs/standard/threading/reader-writer-locks.md)   
 [Barrier](../../../docs/standard/threading/barrier.md)   
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [SpinLock](../../../docs/standard/threading/spinlock.md)