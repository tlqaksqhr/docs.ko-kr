---
title: "Pausing and Resuming Threads | Microsoft Docs"
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
  - "resuming threads"
  - "threading [.NET Framework], pausing"
  - "pausing threads"
ms.assetid: 9fce4859-a19d-4506-b082-7dd0792688ca
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Pausing and Resuming Threads
스레드 작업을 동기화하는 가장 일반적인 방법은 스레드를 차단 및 해제하거나 개체 또는 코드 영역을 잠그는 것입니다.  이러한 잠금 및 차단 메커니즘에 대한 자세한 내용은 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)를 참조하세요.  
  
 스레드가 자동으로 중지되도록 할 수도 있습니다.  스레드가 차단 또는 중지된 경우 <xref:System.Threading.ThreadInterruptedException>을 사용하여 대기 상태에서 분리할 수 있습니다.  
  
## Thread.Sleep 메서드  
 <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName> 메서드를 호출하면 현재 스레드가 <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>에 전달하는 시간\(밀리초\) 동안 즉시 차단되어 해당 시간 조각의 나머지 부분을 다른 스레드에 양보합니다.  한 스레드가 다른 스레드에서 <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>를 호출할 수는 없습니다.  
  
 <xref:System.Threading.Timeout.Infinite?displayProperty=fullName>를 사용하여 <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>를 호출하면 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>를 호출하는 다른 스레드에 의해 중단될 때까지 또는 <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>에 의해 종료될 때까지 스레드가 중지됩니다.  
  
## 스레드 중단  
 차단된 스레드에서 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>를 호출하여 <xref:System.Threading.ThreadInterruptedException>을 발생시키면 스레드가 차단 호출에서 분리되어 대기 스레드를 중단할 수 있습니다.  스레드는 <xref:System.Threading.ThreadInterruptedException>을 catch하고 작업을 계속하는 데 필요한 동작을 수행해야 합니다.  스레드가 예외를 무시하는 경우 런타임은 예외를 catch하고 스레드를 중지합니다.  
  
> [!NOTE]
>  <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>를 호출할 때 대상 스레드가 차단되지 않는 경우 스레드는 차단될 때까지 중단되지 않습니다.  스레드가 차단되지 않으면 중단 없이 완료될 수 있습니다.  
  
 대기가 관리되는 대기인 경우 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> 및 <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName> 둘 다 스레드를 즉시 깨웁니다.  대기가 관리되지 않는 대기인 경우\(예: Win32 `WaitForSingleObject` 함수에 대한 플랫폼 호출\) 스레드가 관리 코드로 반환되거나 호출할 때까지 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName> 또는 <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>가 스레드를 제어할 수 있습니다.  관리 코드에서 동작은 다음과 같습니다.  
  
-   <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>는 대기 상태에서 스레드를 깨우고 대상 스레드에서 <xref:System.Threading.ThreadInterruptedException>이 발생하게 합니다.  
  
-   <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>는 스레드에서 <xref:System.Threading.ThreadAbortException>이 발생되게 한다는 점을 제외하고 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>와 비슷합니다.  자세한 내용은 [스레드 삭제](../../../docs/standard/threading/destroying-threads.md)를 참조하세요.  
  
## 일시 중지 및 다시 시작\(사용 되지 않음\)  
 <xref:System.Threading.Thread> 클래스에는 스레드를 일시 중지 및 다시 시작하기 위한 두 메서드 <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> 및 <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName>이 포함되어 있습니다.  그러나 이러한 메서드는 사용하지 않는 것이 좋습니다.  
  
> [!IMPORTANT]
>  .NET Framework 버전 2.0부터 <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> 및 <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> 메서드는 사용되지 않는 것으로 표시되었으며 이후 릴리스에서 제거됩니다.  
>   
>  <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> 및 <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName> 메서드는 일반적으로 응용 프로그램에 유용하지 않으며 동기화 메커니즘과 혼동해서는 안 됩니다.  <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> 및 <xref:System.Threading.Thread.Resume%2A?displayProperty=fullName>은 제어되는 스레드의 협력에 의존하지 않으므로 개입이 많아 교착 상태와 같은 심각한 응용 프로그램 문제를 발생시킬 수 있습니다\(예: 다른 스레드에 필요한 리소스를 보유하는 스레드를 일시 중단하는 경우\).  
  
 일부 응용 프로그램은 성능 향상을 위해 스레드의 우선 순위를 제어해야 합니다.  이 작업을 수행하려면 <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName> 대신 <xref:System.Threading.Thread.Priority%2A?displayProperty=fullName> 속성을 사용해야 합니다.  
  
## 참고 항목  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadInterruptedException>   
 <xref:System.Threading.ThreadAbortException>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)   
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)