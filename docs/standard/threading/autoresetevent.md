---
title: "AutoResetEvent | Microsoft Docs"
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
  - "threading [.NET Framework], AutoResetEvent class"
  - "AutoResetEvent class"
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# AutoResetEvent
<xref:System.Threading.AutoResetEvent> 클래스는 대기 스레드 하나를 해제한 뒤 신호를 받으면 자동으로 재설정되는 로컬 대기 핸들 이벤트를 나타냅니다.  이 클래스는 기본 클래스인 <xref:System.Threading.EventWaitHandle>의 특별한 경우를 나타냅니다.  자동 재설정 이벤트의 사용과 기능에 대해서는 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 개념 문서를 참조하십시오.  
  
 <xref:System.Threading.AutoResetEvent> 개체는 단일 대기 스레드가 해제된 후 시스템에 의해 자동으로 non\-signaled 상태로 재설정됩니다.  대기 중인 스레드가 없으면 이벤트 개체는 signaled 상태로 계속 남아 있습니다.  <xref:System.Threading.AutoResetEvent>는 Win32 `CreateEvent` 호출에 해당하며 `bManualReset` 인수를 `false`로 지정합니다.  
  
 <xref:System.Threading.AutoResetEvent>를 사용하는 예제는 [모니터](../Topic/Monitors.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Monitor>   
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Wait Handles](../Topic/Wait%20Handles.md)