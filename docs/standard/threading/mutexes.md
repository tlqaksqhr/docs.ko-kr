---
title: "뮤텍스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1d69c1b943d15b9ad8c80b4d7dbafebc54990ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="mutexes"></a>뮤텍스
사용할 수는 <xref:System.Threading.Mutex> 리소스에 대 한 단독 액세스를 제공 하는 개체입니다. <xref:System.Threading.Mutex> 보다 많은 시스템 리소스를 사용 하는 클래스는 <xref:System.Threading.Monitor> 클래스와 응용 프로그램 도메인 경계를 넘어 마샬링될 수, 여러 대기에 사용할 수 있으며 서로 다른 프로세스에서 스레드를 동기화에 사용할 수 있습니다. 관리되는 동기화 메커니즘의 비교는 [동기화 기본 형식 개요](../../../docs/standard/threading/overview-of-synchronization-primitives.md)를 참조하세요.  
  
 코드 예에 대 한 참조 설명서를 참조는 <xref:System.Threading.Mutex.%23ctor%2A> 생성자입니다.  
  
## <a name="using-mutexes"></a>뮤텍스 사용  
 호출 하면 스레드는 <xref:System.Threading.WaitHandle.WaitOne%2A> 뮤텍스의 소유권을 요청 하는 메서드. 호출은 뮤텍스를 사용할 수 있거나 선택적 시간 제한 간격이 경과할 때까지 차단합니다. 뮤텍스의 상태는 스레드가 소유하지 않는 경우 신호를 받습니다.  
  
 스레드가 뮤텍스를 호출 하 여 해제 해당 <xref:System.Threading.Mutex.ReleaseMutex%2A> 메서드. 뮤텍스에는 스레드 선호도가 있습니다. 즉, 뮤텍스를 소유하는 스레드에 의해서만 해제될 수 있습니다. 스레드가 소유 하지 않는 뮤텍스를 해제 하는 경우는 <xref:System.ApplicationException> 스레드에서 throw 됩니다.  
  
 때문에 <xref:System.Threading.Mutex> 클래스에서 파생 <xref:System.Threading.WaitHandle>, 정적을 호출할 수도 있습니다 <xref:System.Threading.WaitHandle.WaitAll%2A> 또는 <xref:System.Threading.WaitHandle.WaitAny%2A> 의 메서드 <xref:System.Threading.WaitHandle> 의 소유권을 요청 하는 <xref:System.Threading.Mutex> 상호 함께에서 대기 핸들입니다.  
  
 그러나 소유 하는 스레드는 <xref:System.Threading.Mutex>, 스레드 동일 지정 하는 <xref:System.Threading.Mutex> ; 실행을 차단 하지 않고 반복 되는 대기 요청 호출에서 해제 해야는 <xref:System.Threading.Mutex> 소유권을 해제 하려면 횟수 만큼 합니다.  
  
## <a name="abandoned-mutexes"></a>중단된 뮤텍스  
 스레드가 해제 하지 않고 종료 하는 경우는 <xref:System.Threading.Mutex>, 뮤텍스가 중단 됩니다. 뮤텍스가 보호하는 리소스가 일관성 없는 상태로 남을 수도 있으므로 이는 종종 심각한 프로그래밍 오류를 나타냅니다. .NET Framework 버전 2.0에에서는 <xref:System.Threading.AbandonedMutexException> 뮤텍스를 획득 하는 다음 스레드에서 throw 됩니다.  
  
> [!NOTE]
>  .NET Framework 버전 1.0 및 1.1에서는 중단 된 <xref:System.Threading.Mutex> 스레드 가져옵니다 소유권 대기 신호를 받은 상태와 다음으로 설정 합니다. 스레드가 대기 하는 경우는 <xref:System.Threading.Mutex> 신호를 받은 상태로 유지 됩니다. 예외가 throw되지 않습니다.  
  
 시스템 차원 뮤텍스의 경우 중단된 뮤텍스는 응용 프로그램이 갑자기 종료되었음을 나타낼 수 있습니다(예: Windows 작업 관리자를 사용하여).  
  
## <a name="local-and-system-mutexes"></a>로컬 및 시스템 뮤텍스  
 뮤텍스는 로컬 뮤텍스 및 명명된 시스템 뮤텍스로 두 가지 유형입니다. 만드는 경우는 <xref:System.Threading.Mutex> 개체 이름을 허용 하는 생성자를 사용 하 여 해당 이름 가진 운영 체제 개체에 연결 됩니다. 명명된 시스템 뮤텍스는 운영 체제 전체에서 볼 수 있으며 프로세스 작업을 동기화하는 데 사용될 수 있습니다. 여러 개 만들 수 있습니다 <xref:System.Threading.Mutex> 명명 된 시스템 뮤텍스를 동일한 나타내는 개체를 사용할 수 있습니다 및는 <xref:System.Threading.Mutex.OpenExisting%2A> 기존 여 메서드를 명명 된 시스템 뮤텍스가 합니다.  
  
 로컬 뮤텍스는 프로세스 내에만 존재합니다. 로컬에 대 한 참조 프로세스의 모든 스레드에서 사용할 수 있습니다 <xref:System.Threading.Mutex> 개체입니다. 각 <xref:System.Threading.Mutex> 개체는 별도 로컬 뮤텍스는 합니다.  
  
### <a name="access-control-security-for-system-mutexes"></a>시스템 뮤텍스에 대한 액세스 제어 보안  
 .NET Framework 버전 2.0은 명명된 시스템 개체에 대해 Windows 액세스 제어 보안을 쿼리 및 설정하는 기능을 제공합니다. 시스템 개체는 전역적이며 따라서 코드에서 잠글 수 있으므로 생성 순간부터 시스템 뮤텍스를 보호하는 것이 좋습니다.  
  
 뮤텍스에 대 한 액세스 제어 보안에 대 한 자세한 내용은 참조는 <xref:System.Security.AccessControl.MutexSecurity> 및 <xref:System.Security.AccessControl.MutexAccessRule> 클래스는 <xref:System.Security.AccessControl.MutexRights> 열거형은 <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A>, 및 <xref:System.Threading.Mutex.OpenExisting%2A> 의 메서드는 <xref:System.Threading.Mutex> 클래스 및는 <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29> 생성자입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.Mutex.%23ctor%2A>  
 <xref:System.Security.AccessControl.MutexSecurity>  
 <xref:System.Security.AccessControl.MutexAccessRule>  
 [스레딩](../../../docs/standard/threading/index.md)  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)  
 [모니터](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 [스레드 및 스레딩](../../../docs/standard/threading/threads-and-threading.md)
