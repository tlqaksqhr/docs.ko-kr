---
title: "Synchronizing Data for Multithreading | Microsoft Docs"
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
  - "threading [.NET Framework], synchronizing threads"
  - "managed threading"
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# Synchronizing Data for Multithreading
여러 스레드에서 단일 개체의 속성 및 메서드를 호출할 수 있는 경우 이러한 호출을 동기화하는 것이 중요합니다.  동기화하지 않으면 하나의 스레드가 다른 스레드의 작업을 방해할 수 있으며 개체가 잘못된 상태가 될 수 있습니다.  이러한 방해에서 보호될 수 있는 클래스 멤버를 스레드로부터 안전한 상태에 있다고 합니다.  
  
 공용 언어 인프라에서는 인스턴스 및 정적 멤버에 대한 액세스를 동기화하기 위한 다음 전략을 제공합니다.  
  
-   동기화된 코드 영역.  <xref:System.Threading.Monitor> 클래스나 이 클래스에 대한 컴파일러 지원을 사용하여 해당 클래스가 필요한 코드 블록만 동기화함으로써 성능을 향상시킬 수 있습니다.  
  
-   수동 동기화.  .NET Framework 클래스 라이브러리에서 제공하는 동기화 개체를 사용할 수 있습니다.  <xref:System.Threading.Monitor> 클래스에 대한 설명이 포함된 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)를 참조하십시오.  
  
-   동기화된 컨텍스트:  <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>를 사용하여 <xref:System.ContextBoundObject> 개체에 간단한 자동 동기화를 설정합니다.  
  
-   <xref:System.Collections.Concurrent?displayProperty=fullName> 네임스페이스의 컬렉션 클래스.  이러한 클래스는 동기화된 기본 제공 추가 및 제거 작업을 제공합니다.  자세한 내용은 [스레드로부터 안전한 컬렉션](../../../docs/standard/collections/thread-safe/index.md)을 참조하십시오.  
  
 공용 언어 런타임에서 제공하는 스레드 모델에서 클래스는 요구 사항에 따라 다양한 방식으로 동기화될 수 있는 여러 범주에 속합니다.  다음 표에서는 동기화 범주에 따라 필드와 메서드에 제공되는 동기화 지원 기능을 보여 줍니다.  
  
|범주|전역 필드|정적 필드|정적 메서드|인스턴스 필드|인스턴스 메서드|특정 코드 블록|  
|--------|-----------|-----------|------------|-------------|--------------|--------------|  
|동기화 없음|아니요|아니요|아니요|아니요|아니요|아니요|  
|동기화된 컨텍스트|아니요|아니요|아니요|예|예|아니요|  
|동기화된 코드 영역|아니요|아니요|표시된 경우에만|아니요|표시된 경우에만|표시된 경우에만|  
|수동 동기화|수동|수동|수동|수동|수동|수동|  
  
## 동기화 없음  
 개체의 기본값입니다.  모든 스레드는 항상 모든 메서드나 필드에 액세스할 수 있으나  한 번에 하나의 스레드만 이러한 개체에 액세스해야 합니다.  
  
## 수동 동기화  
 .NET Framework 클래스는 스레드 동기화를 위한 여러 클래스를 제공합니다.  [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)를 참조하십시오.  
  
## 동기화된 코드 영역  
 <xref:System.Threading.Monitor> 클래스나 컴파일러 키워드를 사용하여 코드 블록, 인스턴스 메서드 및 정적 메서드를 동기화할 수 있습니다.  동기화된 정적 필드는 지원되지 않습니다.  
  
 Visual Basic과 C\#에서는 특정 언어 키워드, 즉 C\#의 `lock` 문이나 Visual Basic의 `SyncLock` 문을 사용하여 코드 블록을 표시할 수 있습니다.  스레드에서는 코드를 실행할 때 해당 코드를 잠그려고 합니다.  다른 스레드에서 이미 코드를 잠근 경우에는 잠금을 사용할 수 있게 될 때까지 해당 스레드는 차단됩니다.  스레드에서 동기화된 코드 블록을 종료하면 해당 스레드에서 블록을 종료한 방법에 관계없이 잠금이 해제됩니다.  
  
> [!NOTE]
>  `lock` 및 `SyncLock` 문은 <xref:System.Threading.Monitor.Enter%2A?displayProperty=fullName>와 <xref:System.Threading.Monitor.Exit%2A?displayProperty=fullName>를 사용하여 구현되므로 동기화된 영역 내에서 이 두 메서드와 <xref:System.Threading.Monitor>의 다른 메서드를 함께 사용할 수 있습니다.  
  
 **MethodImplAttribute**와 **MethodImplOptions.Synchronized**로 메서드를 데코레이팅할 수도 있습니다. 이렇게 하면 **Monitor**나 컴파일러 키워드 중 하나를 사용하여 메서드 본문 전체를 잠그는 것과 같은 결과를 얻을 수 있습니다.  
  
 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=fullName>를 사용하여 동기화된 코드 영역 액세스 대기와 같은 차단 작업에서 스레드를 해제할 수 있습니다.  **Thread.Interrupt**는 <xref:System.Threading.Thread.Sleep%2A?displayProperty=fullName>과 같은 작업에서 스레드를 해제할 때도 사용됩니다.  
  
> [!IMPORTANT]
>  `static` 메서드\(Visual Basic의 경우 `Shared` 메서드\)를 보호하려면 형식, 즉 C\#의 `typeof(MyType)`, Visual Basic의 `GetType(MyType)` 또는 C\+\+의 `MyType::typeid`는 잠그지 않아야 합니다.  대신 전용 정적 개체를 사용합니다.  마찬가지로 인스턴스 메서드를 잠그기 위해 C\#의 `this`\(Visual Basic의 경우 `Me`\)를 사용해서는 안 됩니다.  대신 전용 개체를 사용합니다.  사용자 고유 코드가 아닌 다른 코드로 클래스나 인스턴스를 잠글 수 있으며 이 경우 교착 상태 또는 성능 문제가 발생할 수 있습니다.  
  
### 컴파일러 지원  
 Visual Basic 및 C\# 모두 개체를 잠그기 위해 <xref:System.Threading.Monitor.Enter%2A?displayProperty=fullName>와 <xref:System.Threading.Monitor.Exit%2A?displayProperty=fullName>을 사용하는 언어 키워드를 지원합니다.  Visual Basic에서는 [SyncLock](../../../ocs/visual-basic/language-reference/statements/synclock-statement.md) 문을 지원하고 C\#에서는 [lock](../Topic/lock%20Statement%20\(C%23%20Reference\).md) 문을 지원합니다.  
  
 두 경우 모두 코드 블록에서 예외가 throw되면 **lock**이나 **SyncLock**에서 설정된 잠금은 자동으로 해제됩니다.  C\#과 Visual Basic 컴파일러는 try의 시작 부분에서 **Monitor.Enter**를, **finally** 블록에서 **Monitor.Exit**을 사용하여 **try**\/**finally** 블록을 생성합니다.  **lock**이나 **SyncLock** 블록의 내부에서 예외가 throw되면 **finally** 처리기가 실행되어 정리 작업을 수행할 수 있습니다.  
  
## 동기화된 컨텍스트  
 모든 **ContextBoundObject**에서 **SynchronizationAttribute**를 사용하여 모든 인스턴스 메서드와 필드를 동기화할 수 있습니다.  같은 컨텍스트 도메인에 있는 모든 개체는 같은 잠금을 공유합니다.  여러 스레드에서 메서드와 필드에 액세스할 수 있지만 특정 시점에서는 단일 스레드만 허용됩니다.  
  
## 참고 항목  
 <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)   
 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)   
 [SyncLock Statement](../../../ocs/visual-basic/language-reference/statements/synclock-statement.md)   
 [lock 문](../Topic/lock%20Statement%20\(C%23%20Reference\).md)