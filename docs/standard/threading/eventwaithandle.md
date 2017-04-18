---
title: "EventWaitHandle | Microsoft Docs"
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
  - "threading [.NET Framework], EventWaitHandle class"
  - "EventWaitHandle class"
  - "event wait handles [.NET Framework]"
  - "threading [.NET Framework], cross-process synchronization"
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# EventWaitHandle
<xref:System.Threading.EventWaitHandle> 클래스를 사용하면 스레드는 신호를 보내고 신호를 기다리면서 서로 통신할 수 있습니다.  간단히 이벤트라고도 하는 이벤트 대기 핸들은 하나 이상의 대기 스레드를 해제하기 위해 신호를 받을 수 있는 대기 핸들입니다.  이벤트 대기 핸들은 신호를 받은 후에 수동 또는 자동으로 다시 설정됩니다.  <xref:System.Threading.EventWaitHandle> 클래스는 로컬 이벤트 대기 핸들\(로컬 이벤트\) 또는 명명된 시스템 이벤트 대기 핸들\(모든 프로세스에서 볼 수 있는 명명된 이벤트 또는 시스템 이벤트\)을 나타낼 수 있습니다.  
  
> [!NOTE]
>  .NET Framework에서는 이벤트 대기 핸들이 일반적으로 나타내는 의미에 비추어볼 때 이 용어가 이벤트를 나타내지는 않습니다.  관련된 대리자나 이벤트 처리기가 없기 때문입니다.  일반적으로는 이벤트 대기 핸들이 운영 체제 이벤트를 나타내며 대기 핸들에 신호를 보내는 작업이 이벤트가 발생된 대기 스레드를 나타내므로 "이벤트"라는 용어가 사용되고 있습니다.  
  
 로컬 및 명명된 이벤트 대기 핸들 모두 <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> 래퍼에 의해 보호되는 시스템 동기화 개체를 사용하여 리소스가 해제되도록 합니다.  개체 사용이 끝나면 <xref:System.Threading.WaitHandle.System%23IDisposable%23Dispose%2A> 메서드를 사용하여 리소스를 즉시 해제할 수 있습니다.  
  
## 자동으로 다시 설정되는 이벤트 대기 핸들  
 <xref:System.Threading.EventWaitHandle> 개체를 만들 때 <xref:System.Threading.EventResetMode?displayProperty=fullName>을 지정하여 자동 다시 설정 이벤트를 만듭니다.  이름에서 알 수 있는 것처럼 이 동기화 이벤트는 신호를 받으면 자동으로 다시 설정되며 그 이후에 대기 중인 단일 스레드를 해제합니다.  해당 <xref:System.Threading.EventWaitHandle.Set%2A> 메서드를 호출하여 이벤트에 신호를 보냅니다.  
  
 자동 다시 설정 이벤트는 일반적으로 한 번에 단일 스레드 리소스에 대해 배타적 액세스를 제공하기 위해 사용됩니다.  스레드는 <xref:System.Threading.WaitHandle.WaitOne%2A> 메서드를 호출하여 리소스를 요청합니다.  대기 핸들을 보류 중인 다른 스레드가 없으면 이 메서드는 `true`를 반환하며 호출 스레드가 해당 리소스를 제어하게 됩니다.  
  
> [!IMPORTANT]
>  모든 동기화 메커니즘과 마찬가지로 보호된 리소스에 액세스하기 전에 모든 코드 경로가 해당 대기 핸들을 대기하도록 해야 합니다.  스레드 동기화는 상호 협력 방식으로 진행됩니다.  
  
 대기 중인 스레드가 없을 때 자동 다시 설정 이벤트가 신호를 받으면 스레드가 대기하려고 할 때까지 신호를 받은 상태로 유지됩니다.  이 이벤트는 스레드를 해제하고 즉시 다시 설정되며 후속 스레드를 블로킹합니다.  
  
## 수동으로 다시 설정되는 이벤트 대기 핸들  
 <xref:System.Threading.EventWaitHandle> 개체를 만들 때 <xref:System.Threading.EventResetMode?displayProperty=fullName>을 지정하여 수동 다시 설정 이벤트를 만듭니다.  이름에서 알 수 있는 것처럼 이 동기화 이벤트는 신호가 오면 수동으로 다시 설정되어야 합니다.  해당 <xref:System.Threading.EventWaitHandle.Reset%2A> 메서드를 호출하여 이 이벤트를 다시 설정할 때까지 이벤트 핸들을 대기하는 스레드는 블로킹 없이 즉시 처리됩니다.  
  
 수동 다시 설정 이벤트는 동물 우리의 문처럼 작동합니다.  이벤트가 신호를 받지 못하면 우리 안에 있는 말처럼 대기 중인 스레드는 블로킹됩니다.  해당 <xref:System.Threading.EventWaitHandle.Set%2A> 메서드를 호출하여 이벤트가 신호를 받으면 대기 중인 모든 스레드는 처리 가능 상태가 됩니다.  이벤트는 해당 <xref:System.Threading.EventWaitHandle.Reset%2A> 메서드가 호출될 때까지 신호를 받은 상태로 유지됩니다.  이러한 측면에서 수동 다시 설정 이벤트는 한 스레드가 작업을 마칠 때까지 대기되어야 하는 스레드를 보류시키는 이상적인 방법입니다.  
  
 말을 우리에서 꺼낼 때처럼 해제된 스레드가 운영 체제에 의해 예약되고 다시 실행되기 시작하는 데는 다소 시간이 걸립니다.  모든 스레드의 실행이 다시 시작되기 전에 <xref:System.Threading.EventWaitHandle.Reset%2A> 메서드를 호출하면 나머지 스레드가 다시 한 번 블로킹됩니다.  다시 시작되는 스레드와 블로킹되는 스레드는 시스템 부하, 스케줄러를 대기하는 스레드 수 등과 같은 임의 요소에 따라 달라집니다.  일반적인 경우처럼 이벤트에 신호를 보내는 스레드가 신호 전송 후에 종료되어도 문제가 되지 않습니다.  모든 대기 스레드가 다시 시작된 후에 새 작업을 시작하도록 스레드가 이벤트에 신호를 보내게 하려면 모든 대기 스레드가 다시 시작될 때까지 해당 스레드를 블로킹해야 합니다.  그렇지 않으면 경쟁 상태가 발생하며 코드가 예상치 못하게 동작할 수 있습니다.  
  
## 자동 및 수동 이벤트에 공통된 기능  
 일반적으로 블로킹되지 않은 스레드가 자동 다시 설정 이벤트의 경우에는 대기 스레드 중 하나를, 수동 다시 설정 이벤트의 경우에는 모든 대기 스레드를 해제하는 <xref:System.Threading.EventWaitHandle.Set%2A> 메서드를 호출할 때까지 하나 이상의 스레드가 <xref:System.Threading.EventWaitHandle>을 블로킹합니다.  스레드는 정적 <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=fullName> 메서드를 호출하여 한 단계의 자동 작업으로 <xref:System.Threading.EventWaitHandle>에 신호를 보낸 다음 블로킹할 수 있습니다.  
  
 <xref:System.Threading.EventWaitHandle> 개체는 정적 <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> 및 <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName> 메서드와 함께 사용할 수 있습니다.  <xref:System.Threading.EventWaitHandle> 및 <xref:System.Threading.Mutex> 클래스가 둘 다 <xref:System.Threading.WaitHandle>에서 파생되므로 이러한 메서드와 두 클래스를 함께 사용할 수 있습니다.  
  
### 명명된 이벤트  
 Windows 운영 체제에서는 이벤트 대기 핸들에 이름을 지정할 수 있습니다.  명명된 이벤트는 시스템 전체에 적용됩니다.  즉, 명명된 이벤트가 일단 만들어지면 모든 프로세스의 모든 스레드에서 해당 이벤트를 볼 수 있습니다.  따라서 명명된 이벤트를 사용하여 스레드뿐만 아니라 프로세스의 작업을 동기화할 수 있습니다.  
  
 이벤트 이름을 지정하는 생성자 중 하나를 사용하여 명명된 시스템 이벤트를 나타내는 <xref:System.Threading.EventWaitHandle> 개체를 만들 수 있습니다.  
  
> [!NOTE]
>  명명된 이벤트는 시스템 전체에 적용되므로 명명된 동일한 이벤트를 나타내는 여러 개의 <xref:System.Threading.EventWaitHandle> 개체가 존재할 수 있습니다.  생성자 또는 <xref:System.Threading.EventWaitHandle.OpenExisting%2A> 메서드를 호출할 때마다 새 <xref:System.Threading.EventWaitHandle> 개체가 만들어집니다.  동일한 이름을 반복해서 지정하면 명명된 동일한 이벤트를 나타내는 여러 개체가 만들어집니다.  
  
 명명된 이벤트를 사용할 때는 주의해야 합니다.  이 이벤트는 시스템 전체에 적용되므로 같은 이름을 사용하는 다른 프로세스로 인해 예기치 않게 스레드가 블로킹될 수 있습니다.  같은 컴퓨터에서 실행되는 악의적인 코드가 이것을 서비스 거부 공격의 수단으로 사용할 수 있습니다.  
  
 명명된 이벤트를 나타내는 <xref:System.Threading.EventWaitHandle> 개체를 보호하려면 <xref:System.Security.AccessControl.EventWaitHandleSecurity> 개체를 지정하는 생성자를 통해 액세스 제어 보안을 사용합니다.  또한 <xref:System.Threading.EventWaitHandle.SetAccessControl%2A> 메서드를 사용하여 액세스 제어 보안을 적용할 수도 있지만 이렇게 하면 이벤트 대기 핸들이 만들어지는 시간과 보호가 시작되는 시간 중간에 공격 받을 수 있습니다.  액세스 제어 보안으로 이벤트를 보호하면 악의적인 공격을 막을 수 있지만 예상치 못한 이름 충돌 문제가 나타납니다.  
  
> [!NOTE]
>  <xref:System.Threading.EventWaitHandle> 클래스와 달리, 파생 클래스 <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.ManualResetEvent>는 로컬 대기 핸들만 나타낼 수 있으며  명명된 시스템 이벤트를 나타낼 수 없습니다.  
  
## 참고 항목  
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)