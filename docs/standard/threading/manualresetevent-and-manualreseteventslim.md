---
title: "ManualResetEvent and ManualResetEventSlim | Microsoft Docs"
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
  - "threading [.NET Framework], ManualResetEvent class"
  - "ManualResetEvent class, about ManualResetEvent class"
ms.assetid: 465fdcf9-ba24-4d8d-a43f-d983b7cb0cc6
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# ManualResetEvent and ManualResetEventSlim
<xref:System.Threading.ManualResetEvent?displayProperty=fullName> 클래스는 신호를 받은 후 수동으로 다시 설정되어야 하는 로컬 대기 핸들 이벤트를 나타냅니다.  이 클래스는 기본 클래스인 <xref:System.Threading.EventWaitHandle?displayProperty=fullName>의 특수한 경우를 나타냅니다.  수동 다시 설정 이벤트의 사용 및 기능에 대한 내용은 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 개념 설명서를 참조하십시오.  
  
 <xref:System.Threading.ManualResetEvent> 개체는 <xref:System.Threading.EventWaitHandle.Reset%2A?displayProperty=fullName> 메서드가 호출되기 전까지 신호를 받은 상태로 유지됩니다.  개수에 관계없이 모든 대기 스레드 또는 신호를 받은 후 이벤트를 기다리는 스레드는 개체 상태가 신호를 받은 상태인 동안 해제될 수 있습니다.  <xref:System.Threading.ManualResetEvent>는 Win32 `CreateEvent` 호출에 해당하며 `bManualReset` 인수를 `true`로 지정합니다.  
  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서, <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName>클래스를 대기 시간이 매우 짧을 것으로 예상 되 고 이벤트 프로세스 경계를 넘어서지 않을 때 성능 향상을 위해 사용할 수 있습니다.  <xref:System.Threading.ManualResetEventSlim>는 신호를 받을 이벤트를 기다리는 동안 짧은 시간 동안 고속 회전을 사용 합니다.  대기 시간이 짧으면 대기 핸들을 사용하여 기다리는 것보다 회전을 유지하는 쪽이 비용을 훨씬 더 절감할 수 있습니다.  그러나 일정 시간 내에 이벤트에 신호가 전달되지 않으면 <xref:System.Threading.ManualResetEventSlim>이 일반적인 이벤트 핸들 대기 상태로 전환됩니다.  
  
## 참고 항목  
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Wait Handles](../Topic/Wait%20Handles.md)   
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)   
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [Semaphore and SemaphoreSlim](../../../docs/standard/threading/semaphore-and-semaphoreslim.md)