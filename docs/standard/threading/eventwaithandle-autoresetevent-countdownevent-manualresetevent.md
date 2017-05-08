---
title: "EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent | Microsoft Docs"
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
  - "wait handles"
  - "threading [.NET Framework], EventWaitHandle class"
  - "event wait handles [.NET Framework]"
ms.assetid: cd94fc34-ac15-427f-b723-a1240a4fab7d
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent
이벤트 대기 핸들은 서로 신호를 보내고 상대방 신호를 대기하는 방식으로 활동을 동기화할 수 있습니다.  이러한 동기화 이벤트는 Win32 대기 핸들을 기반으로 하며 신호를 받을 때 자동으로 다시 설정되는 형식과 수동으로 다시 설정되는 형식으로 구분될 수 있습니다.  
  
 이벤트 대기 핸들은 <xref:System.Threading.Monitor> 클래스와 동일한 여러 동기화 시나리오에서 유용합니다.  이벤트 대기 핸들은 일반적으로 <xref:System.Threading.Monitor.Wait%2A?displayProperty=fullName> 및 <xref:System.Threading.Monitor.Pulse%2A?displayProperty=fullName> 메서드보다 쉽게 사용할 수 있으므로 신호 전송을 보다 효과적으로 제어할 수 있습니다.  또한 명명된 이벤트 대기 핸들을 사용하면 응용 프로그램 도메인과 프로세스에 걸쳐 활동을 동기화할 수 있으며 모니터는 응용 프로그램 도메인에 대해 로컬입니다.  
  
## 단원 내용  
 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md)  
 <xref:System.Threading.EventWaitHandle> 클래스는 자동 또는 수동 재설정 이벤트를 나타내거나 로컬 이벤트 또는 명명된 시스템 이벤트를 나타낼 수 있습니다.  
  
 [AutoResetEvent](../../../docs/standard/threading/autoresetevent.md)  
 <xref:System.Threading.AutoResetEvent> 클래스는 <xref:System.Threading.EventWaitHandle>에서 파생되며 자동으로 다시 설정되는 로컬 이벤트를 나타냅니다.  
  
 [ManualResetEvent and ManualResetEventSlim](../../../docs/standard/threading/manualresetevent-and-manualreseteventslim.md)  
 <xref:System.Threading.ManualResetEvent> 클래스는 <xref:System.Threading.EventWaitHandle>에서 파생되며 수동으로 다시 설정해야 하는 로컬 이벤트를 나타냅니다.  <xref:System.Threading.ManualResetEventSlim> 클래스는 같은 프로세스 내의 이벤트에 사용할 수 있는 간단하고 더 빠른 버전입니다.  
  
 [CountdownEvent](../../../docs/standard/threading/countdownevent.md)  
 <xref:System.Threading.CountdownEvent> 클래스는 대기 핸들을 사용하는 코드에서 분기\/조인 병렬 패턴을 구현하는 간단한 방법을 제공합니다.  
  
## 관련 단원  
 [Wait Handles](../Topic/Wait%20Handles.md)  
 <xref:System.Threading.WaitHandle> 클래스는 <xref:System.Threading.EventWaitHandle>, <xref:System.Threading.Semaphore> 및 <xref:System.Threading.Mutex> 클래스의 기본 클래스입니다.  이 클래스에는 <xref:System.Threading.WaitHandle.SignalAndWait%2A> 및 <xref:System.Threading.WaitHandle.WaitAll%2A>과 같이 모든 형식의 대기 핸들 작업을 수행할 때 유용한 정적 메서드가 포함됩니다.  
  
## 참고 항목  
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)