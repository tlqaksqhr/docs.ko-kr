---
title: "Mutexes | Microsoft Docs"
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
  - "threading [.NET Framework], Mutex class"
  - "Mutex class, about Mutex class"
  - "threading [.NET Framework], cross-process synchronization"
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Mutexes
<xref:System.Threading.Mutex> 개체를 사용하여 리소스에 대한 단독 액세스를 제공할 수 있습니다.  <xref:System.Threading.Mutex> 클래스는 <xref:System.Threading.Monitor> 클래스보다 더 많은 시스템 리소스를 사용하지만 응용 프로그램 도메인 경계를 넘어 마샬링할 수 있고 여러 대기와 함께 사용할 수 있으며 다른 프로세스의 스레드를 동기화하는 데 사용할 수 있습니다.  관리 동기화 메커니즘에 대한 비교 정보는 [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md)를 참조하십시오.  
  
 코드 예제를 보려면 <xref:System.Threading.Mutex.%23ctor%2A> 생성자에 대한 참조 문서를 참조하십시오.  
  
## 뮤텍스 사용  
 스레드는 뮤텍스의 <xref:System.Threading.WaitHandle.WaitOne%2A> 메서드를 호출하여 소유권을 요청합니다.  뮤텍스가 사용 가능할 때까지 또는 선택적인 시간 제한 간격이 경과할 때까지 호출이 차단됩니다.  뮤텍스를 소유하는 스레드가 없으면 뮤텍스는 신호를 받는 상태입니다.  
  
 스레드는 자신의 <xref:System.Threading.Mutex.ReleaseMutex%2A> 메서드를 호출하여 뮤텍스를 해제합니다.  뮤텍스에는 스레드 선호도가 있습니다. 즉, 뮤텍스는 자신을 소유한 스레드에 의해서만 해제될 수 있습니다.  스레드가 자신이 소유하지 않은 뮤텍스를 해제하는 경우 스레드에서 <xref:System.ApplicationException>이 throw됩니다.  
  
 <xref:System.Threading.Mutex> 클래스가 <xref:System.Threading.WaitHandle>에서 파생되기 때문에 <xref:System.Threading.WaitHandle>의 정적 <xref:System.Threading.WaitHandle.WaitAll%2A> 또는 <xref:System.Threading.WaitHandle.WaitAny%2A> 메서드를 호출하여 다른 대기 핸들과 함께 <xref:System.Threading.Mutex>의 소유권을 요청할 수도 있습니다.  
  
 <xref:System.Threading.Mutex>를 소유하는 스레드는 뮤텍스의 실행을 차단하지 않고 반복되는 대기 요청 호출에 동일한 <xref:System.Threading.Mutex>를 지정할 수 있습니다. 그러나 뮤텍스의 소유권을 해제하는 횟수만큼 스레드에서 <xref:System.Threading.Mutex>를 해제해야 합니다.  
  
## 중단된 뮤텍스  
 스레드가 <xref:System.Threading.Mutex>를 해제하지 않고 종료하는 경우 뮤텍스가 중단되었다고 합니다.  뮤텍스가 보호하고 있는 리소스가 일관성이 없는 상태로 남을 수도 있으므로 이는 심각한 프로그래밍 오류를 나타내는 경우가 많습니다.  .NET Framework 버전 2.0에서 <xref:System.Threading.AbandonedMutexException>은 뮤텍스를 얻은, 다음 스레드에서 throw됩니다.  
  
> [!NOTE]
>  .NET Framework 버전 1.0 및 1.1에서 중단된 <xref:System.Threading.Mutex>는 신호를 받는 상태로 설정되고 다음 대기 스레드가 소유권을 얻습니다.  대기하는 스레드가 없는 경우 <xref:System.Threading.Mutex>는 신호를 받는 상태로 남습니다.  예외가 throw되지 않습니다.  
  
 시스템 수준 뮤텍스가 중단된 경우 Windows 작업 관리자 등을 사용하여 응용 프로그램이 갑자기 종료되었을 수 있습니다.  
  
## 로컬 및 시스템 뮤텍스  
 뮤텍스는 로컬 뮤텍스와 명명된 시스템 뮤텍스 등 두 가지 종류가 있습니다.  이름을 사용하는 생성자를 통해 <xref:System.Threading.Mutex> 개체를 만들면 해당 이름의 운영 체제 개체와 연결됩니다.  명명된 시스템 뮤텍스는 운영 체제에서 볼 수 있으며 프로세스 작업을 동기화하는 데 사용할 수 있습니다.  동일하게 명명된 시스템 뮤텍스를 나타내는 여러 개의 <xref:System.Threading.Mutex> 개체를 만들 수 있고, <xref:System.Threading.Mutex.OpenExisting%2A> 메서드를 사용하여 기존의 명명된 시스템 뮤텍스를 열 수도 있습니다.  
  
 로컬 뮤텍스는 프로세스 안에만 존재하며  프로세스의 로컬 <xref:System.Threading.Mutex> 개체에 대한 참조가 있는 스레드에서 사용될 수 있습니다.  각 <xref:System.Threading.Mutex> 개체는 별도의 로컬 뮤텍스입니다.  
  
### 시스템 뮤텍스에 대한 액세스 제어 보안  
 .NET Framework 버전 2.0에서는 명명된 시스템 개체에 대한 Windows 액세스 제어 보안을 쿼리하고 설정하는 기능을 제공합니다.  시스템 개체는 전역에서 사용되고 따라서 사용자의 코드 외에 다른 코드에 의해 잠길 수 있으므로 시스템 뮤텍스는 만들 때부터 보호하는 것이 좋습니다.  
  
 뮤텍스의 액세스 제어 보안에 대한 자세한 내용은 <xref:System.Security.AccessControl.MutexSecurity> 및 <xref:System.Security.AccessControl.MutexAccessRule> 클래스, <xref:System.Security.AccessControl.MutexRights> 열거형, <xref:System.Threading.Mutex> 클래스의 <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A> 및 <xref:System.Threading.Mutex.OpenExisting%2A> 메서드, <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29> 생성자를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Threading.Mutex>   
 <xref:System.Threading.Mutex.%23ctor%2A>   
 <xref:System.Security.AccessControl.MutexSecurity>   
 <xref:System.Security.AccessControl.MutexAccessRule>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Monitor](../Topic/Monitors.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)