---
title: EventWaitHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], EventWaitHandle class
- EventWaitHandle class
- event wait handles [.NET Framework]
- threading [.NET Framework], cross-process synchronization
ms.assetid: 11ee0b38-d663-4617-b793-35eb6c64e9fc
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1bd248133bd95ff05246eb36a8e250247fd7ed61
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="eventwaithandle"></a>EventWaitHandle
<xref:System.Threading.EventWaitHandle> 클래스를 사용 하면 스레드가 신호를 보내 및 신호 대기 하 여 서로 통신할 수 있습니다. 이벤트 대기 핸들 (라고도 단순히 이벤트)는 하나 이상의 대기 중인 스레드를 해제 하기 위해 신호를 보낼 수 있는 대기 핸들입니다. 신호를 받으면 이벤트 대기 핸들 수동 또는 자동으로 다시 설정 됩니다. <xref:System.Threading.EventWaitHandle> 명명된 된 시스템 이벤트 대기 핸들 (명명 된 이벤트 나 시스템 이벤트를 모든 프로세스에 표시) 또는 클래스 중 하나는 로컬 이벤트 대기 핸들 (로컬 이벤트)를 나타낼 수 있습니다.  
  
> [!NOTE]
>  이벤트 대기 핸들 일반적으로.NET Framework의 해당 단어가 의미 의미에서 이벤트를 나타내지는 않습니다. 없는 대리자 또는 이벤트 처리기 참여 한다고 합니다. 이벤트가 발생 했음을 일반적으로 되었습니다를 참조 했으며 운영 체제 이벤트로 하 고 act 대기 핸들이 신호를 대기 중인 스레드를 나타내기 때문에를 설명 하는 단어 "이벤트" 사용 됩니다.  
  
 모두 로컬 및 명명 된 이벤트 대기 핸들에 의해 보호 되는 시스템 동기화 개체를 사용 하 여 <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> 래퍼는 리소스를 해제 됩니다. 사용할 수는 <xref:System.Threading.WaitHandle.Dispose%2A> 메서드를 즉시 개체를 사용 하 여 완료 했을 때의 리소스를 해제 합니다.  
  
## <a name="event-wait-handles-that-reset-automatically"></a>자동으로 다시 설정 하는 이벤트 대기 핸들  
 지정 하 여 자동 재설정 이벤트를 만들 <xref:System.Threading.EventResetMode.AutoReset?displayProperty=nameWithType> 만들 때는 <xref:System.Threading.EventWaitHandle> 개체입니다. 이름에서 알 수 있듯이 단일 대기 중인 스레드를 해제 한 후 신호를 받으면이 동기화 이벤트 자동으로 초기화 합니다. 호출 하 여 이벤트 신호 해당 <xref:System.Threading.EventWaitHandle.Set%2A> 메서드.  
  
 자동 다시 설정 이벤트는 일반적으로 한 번에 단일 스레드에 대 한 리소스에 대 한 단독 액세스를 제공 하는 데 사용 됩니다. 호출 하 여 리소스를 요청 하는 스레드는 <xref:System.Threading.WaitHandle.WaitOne%2A> 메서드. 메서드가 반환 하는 경우 다른 스레드에서 대기 핸들을 보류 중인 `true` 호출 스레드는 리소스를 제어 하 고 있습니다.  
  
> [!IMPORTANT]
>  모든 동기화 메커니즘에서와 마찬가지로 모든 코드 경로 보호 된 리소스에 액세스 하기 전에 적절 한 대기 핸들에 대기 함을 확인 해야 합니다. 스레드 동기화는 협력 작업 합니다.  
  
 자동 재설정 이벤트 대기 중인 스레드가 없을 때 신호를 받는, 스레드가 대기 하려고 할 때까지 신호를 받은 유지 합니다. 이벤트는 스레드를 해제 하 고 즉시 다시 설정 되며, 이후 스레드를 차단 합니다.  
  
## <a name="event-wait-handles-that-reset-manually"></a>수동으로 다시 설정 하는 이벤트 대기 핸들  
 수동 다시 설정 이벤트를 지정 하 여 만들 <xref:System.Threading.EventResetMode.ManualReset?displayProperty=nameWithType> 만들 때는 <xref:System.Threading.EventWaitHandle> 개체입니다. 이름에서 알 수 있듯이 신호를 받은 후이 동기화 이벤트 수동으로 재설정 해야 합니다. 재설정를 호출 하 여 해당 <xref:System.Threading.EventWaitHandle.Reset%2A> 메서드, 이벤트 핸들을 대기 하는 스레드가 즉시 진행을 차단 하지 않고 있습니다.  
  
 수동 재설정는 블로킹의 문 처럼 이벤트 작동 합니다. 이벤트 신호를 받지 하는 경우에 블로킹 말 처럼 대기 중인 스레드를 차단 합니다. 호출 하 여 이벤트가 신호 때 해당 <xref:System.Threading.EventWaitHandle.Set%2A> 메서드를 대기 중인 모든 스레드는 처리 가능 합니다. 될 때까지 문제를 해결 되지 않은 해당 <xref:System.Threading.EventWaitHandle.Reset%2A> 메서드를 호출 합니다. 이렇게 하면 수동 다시 설정 이벤트 하나의 스레드가 작업을 완료할 때까지 대기 해야 하는 스레드를 보관 하기 위한 이상적인 방법입니다.  
  
 꺼낼 말, 처럼 해제 된 스레드가 운영 체제에서 일정 예약 및 실행을 계속 하려면는 시간이 걸립니다. 경우는 <xref:System.Threading.EventWaitHandle.Reset%2A> 모든 스레드의 실행이 다시 시작 되기 전에 메서드가 호출 되 면 다시 한 번 나머지 스레드를 차단 합니다. 어떤 스레드가 다시 시작 및 스레드 차단 되 바탕으로 스레드 수가 시스템에 부하 같은 임의 요소 대기 중인 스케줄러 등에 대 한 합니다. 가장 일반적인 사용 패턴, 신호를 보내면 이벤트 신호를 보내는 스레드가 종료 되는 경우에 문제가 되지 않습니다. 모든 새 작업을 시작 하려면 이벤트의 대기 스레드가 신호 스레드를 사용 하도록 하려는 경우 대기 중인 모든 스레드가 다시 시작 될 때까지 차단 되어야 합니다. 그렇지 않은 경우 경합 조건이 있는 경우 및 코드의 동작을 예측할 수 없습니다.  
  
## <a name="features-common-to-automatic-and-manual-events"></a>자동 및 수동 이벤트에 공통 된 기능  
 에 하나 이상의 스레드가 차단 되는 일반적으로 <xref:System.Threading.EventWaitHandle> 차단 되지 않은 스레드가 호출 될 때까지 <xref:System.Threading.EventWaitHandle.Set%2A> (자동 다시 설정 이벤트)의 경우 대기 중인 스레드 중 하나 또는 모두를 고정 하는 메서드 (수동의 경우 다시 설정 이벤트). 스레드를 표시할 수는 <xref:System.Threading.EventWaitHandle> 정적을 호출 하 여 원자성 작업으로,을 차단 <xref:System.Threading.WaitHandle.SignalAndWait%2A?displayProperty=nameWithType> 메서드.  
  
 <xref:System.Threading.EventWaitHandle>개체를 정적으로 사용할 수 <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> 및 <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> 메서드. 때문에 <xref:System.Threading.EventWaitHandle> 및 <xref:System.Threading.Mutex> 에서 파생 된 클래스는 모두 <xref:System.Threading.WaitHandle>, 이러한 방법으로 두 클래스를 사용할 수 있습니다.  
  
### <a name="named-events"></a>명명 된 이벤트  
 Windows 운영 체제 이름을 이벤트 대기 핸들 수 있습니다. 명명된 된 이벤트는 시스템 전체에 있습니다. 즉, 명명된 된 이벤트를 만든 후 모든 프로세스의 모든 스레드가 표시 됩니다. 따라서 스레드 뿐 아니라 프로세스의 활동을 동기화 할 명명 된 이벤트를 사용할 수 있습니다.  
  
 만들 수는 <xref:System.Threading.EventWaitHandle> 이벤트 이름을 지정 하는 생성자 중 하나를 사용 하 여 명명된 된 시스템 이벤트를 나타내는 개체입니다.  
  
> [!NOTE]
>  없기 때문에 명명 된 이벤트는 시스템 전체를 여러 개 <xref:System.Threading.EventWaitHandle> 동일한 나타내는 개체를 명명 된 이벤트입니다. 생성자를 호출할 때마다 또는 <xref:System.Threading.EventWaitHandle.OpenExisting%2A> 메서드, 새 <xref:System.Threading.EventWaitHandle> 개체가 만들어집니다. 이름이 같은 반복적으로 지정 하면 같은 명명 된 이벤트를 나타내는 개체가 여러 개 만들어집니다.  
  
 명명 된 이벤트를 사용 하 여 주의 해야 합니다. 시스템 전체 있기 때문에 동일한 이름을 사용 하는 다른 프로세스가 예기치 않게 스레드 차단할 수 있습니다. 그러면 동일 컴퓨터에서 실행되는 악성 코드가 이를 악용해 서비스 거부 공격을 수행할 수 있습니다.  
  
 액세스 제어 보안을 사용 하 여 보호 하는 <xref:System.Threading.EventWaitHandle> 가급적 지정 하는 생성자를 사용 하 여 명명된 된 이벤트를 나타내는 개체입니다는 <xref:System.Security.AccessControl.EventWaitHandleSecurity> 개체입니다. 사용 하 여 액세스 제어 보안을 적용할 수도 있습니다는 <xref:System.Threading.EventWaitHandle.SetAccessControl%2A> 메서드를 있지만 이렇게 하면 보호 되는 시간과 이벤트 대기 핸들을 만든 시간 사이 취약 합니다. 이벤트 보호 액세스 제어를 사용한 보안 악의적인 공격을 방지할 수 있지만 의도 하지 않은 이름 충돌 문제가 해결 되지 않습니다.  
  
> [!NOTE]
>  와 달리는 <xref:System.Threading.EventWaitHandle> 클래스, 파생 된 클래스 <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.ManualResetEvent> 나타내는 로컬 대기할 수 있는 핸들입니다. 명명 된 시스템 이벤트를 나타낼 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.EventWaitHandle>  
 <xref:System.Threading.WaitHandle>  
 <xref:System.Threading.AutoResetEvent>  
 <xref:System.Threading.ManualResetEvent>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
