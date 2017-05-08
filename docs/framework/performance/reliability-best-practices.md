---
title: "최선의 안정성 구현 방법 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "비동기 예외 처리"
  - "취소 코드"
  - "블록, 안정성"
  - "catch 블록"
  - "CER"
  - "정리 작업"
  - "제약이 있는 실행 영역"
  - "응용 프로그램 도메인 간 공유 상태"
  - "서비스 거부 공격"
  - "파이버"
  - "종료자, 안정성"
  - "finally 절"
  - "GC.KeepAlive 메서드"
  - "잠금 식별"
  - "가장"
  - "누수된 리소스[.NET Framework]"
  - "잠금, 안정성"
  - "관리되는 스레드"
  - "잠금 표시"
  - "메모리, 안정성"
  - "프로세스 차원 도메인 공유 상태"
  - "데이터베이스 다시 부팅"
  - "안정성[.NET Framework]"
  - "안정성 계약[.NET Framework]"
  - "SafeHandle 클래스, 안정성"
  - "공유 상태"
  - "단일 스레드 COM 구성 요소"
  - "느린 누수"
  - "SQL Server[.NET Framework], 안정성"
  - "STA 종속 기능"
  - "스레드 일시 중단"
  - "동기화, 안정성"
  - "스레딩[.NET Framework], 안정성"
  - "관리되지 않는 메모리"
  - "안정적인 코드 작성"
ms.assetid: cf624c1f-c160-46a1-bb2b-213587688da7
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# 최선의 안정성 구현 방법
다음 안정성 규칙은 SQL Server 서버에 대한 규칙이지만 호스트 기반 서버 응용 프로그램에도 적용됩니다.  SQL Server와 같은 서버는 리소스가 누수되거나 다운되어서는 안 됩니다.  그러나 이를 위해 개체의 상태를 변경하는 모든 메서드에 대해 백아웃 코드를 작성할 수는 없습니다.  목표는 백아웃 코드를 사용하는 모든 위치에서 모든 오류를 복구하는 완전히 신뢰할 수 있는 관리 코드를 작성하지 것이 아닙니다.  이는 성공할 가능성이 희박한 어려운 작업입니다.  CLR\(공용 언어 런타임\)을 사용해도 관리 코드에서 완벽한 코드를 작성하기는 쉽지 않습니다.  SQL Server는 ASP.NET과 달리 적정 시간 동안 데이터베이스를 검색하여 재활용할 수 없는 하나의 프로세스만 사용합니다.  
  
 이처럼 보장 기능이 약하고 단일 프로세스에서 실행될 뿐 아니라, 필요한 경우 스레드 또는 재활용 응용 프로그램 도메인을 종료하고 핸들 또는 메모리와 같은 운영 체제 리소스가 누수되지 않도록 예방함으로써 안정성을 확보할 수 있습니다.  이러한 간단한 안정성 제약 조건 외에 다음과 같은 중요한 안정성 요구 사항도 있습니다.  
  
-   운영 체제 리소스가 누수되어서는 안 됩니다.  
  
-   모든 CLR 형식에서 관리되는 잠금을 모두 식별합니다.  
  
-   <xref:System.AppDomain> 재활용 기능이 원활하게 수행될 수 있도록 응용 프로그램 간 도메인 공유 상태를 해제하지 않습니다.  
  
 이론적으로는 관리 코드를 작성하여 <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> 및 <xref:System.OutOfMemoryException> 예외를 처리할 수 있지만 개발자가 전체 응용 프로그램에서 이처럼 견고한 코드를 작성하는 것은 비합리적입니다.  이러한 이유로, out\-of\-band 예외가 발생하면 실행 중인 스레드가 종료되며 종료된 스레드가 공유 상태를 편집하고 있는 경우 <xref:System.AppDomain>이 언로드됩니다. 종료된 스레드의 공유 상태 편집 여부는 스레드가 잠금을 유지하는지 여부로 확인할 수 있습니다.  공유 상태를 편집하는 메서드가 종료되면 공유 상태 업데이트를 위한 신뢰할 수 있는 백아웃 코드를 작성할 수 없어 해당 상태가 손상됩니다.  
  
 .NET Framework 버전 2.0의 경우 안정성이 필요한 호스트는 SQL Server뿐입니다.  어셈블리가 SQL Server에서 실행되는 경우 해당 어셈블리의 모든 부분에 대해 안정성 작업을 수행해야 하며, 데이터베이스에서 실행될 때 비활성화되는 특정 기능이 있는 경우에도 해당됩니다.  이는 코드 분석 엔진이 어셈블리 수준에서 코드를 검사하고 비활성화된 코드를 구분할 수 없기 때문에 필요합니다.  SQL Server 프로그래밍에서는 모든 SQL Server 작업이 단일 프로세스에서 실행되며 메모리 및 운영 체제 핸들과 같은 모든 리소스를 정리하는 데 <xref:System.AppDomain> 재활용을 사용한다는 점을 고려해야 합니다.  
  
 종료자 또는 소멸자나 백아웃 코드의 `try/finally` 블록의 경우  중단되거나 호출되지 않을 수 있으므로 의존해서는 안 됩니다.  
  
 모든 컴퓨터 명령의 예기치 못한 위치에서 <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> 및 <xref:System.OutOfMemoryException>과 같은 비동기 예외가 throw될 수 있습니다.  
  
 관리 스레드는 SQL의 Win32 스레드가 아닌 파이버일 수도 있습니다.  
  
 프로세스 전체 또는 응용 프로그램 간 도메인의 변경 가능한 공유 상태는 안전하게 변경하기가 매우 어려우므로 가능한 변경해서는 안 됩니다.  
  
 SQL Server에서는 메모리 부족 현상이 흔히 발생합니다.  
  
 SQL Server에 호스팅된 라이브러리가 해당 공유 상태를 올바르게 업데이트하지 않는 경우 일반적으로 데이터베이스를 다시 시작해야 코드가 복구됩니다.  또한 일부 극단적인 상황에서는 이로 인해 SQL Server 프로세스가 실패하여 데이터베이스가 다시 부팅될 수 있습니다.  데이터베이스를 다시 부팅하면 웹 사이트가 다운되거나 회사 업무에 지장을 주어 가용성이 떨어집니다.  메모리 또는 핸들과 같은 운영 체제 리소스가 천천히 누수되는 경우에도 결국 서버에서 핸들 할당에 실패하여 복구할 수 없거나, 서버 성능이 천천히 저하되고 고객의 응용 프로그램 가용성이 저하될 수 있습니다.  따라서 이런 상황이 발생하지 않도록 해야 합니다.  
  
## 최선의 규칙 구현 방법  
 앞의 소개 부분에서는 프레임워크의 안정성을 향상시키기 위해 서버에서 실행되는 관리 코드에 대한 코드 검사를 통해 파악해야 하는 내용에 대해 설명했습니다.  이러한 모든 확인 사항은 일반적으로 유용한 방법이며 서버에서는 반드시 필요한 사항입니다.  
  
 교착 상태 또는 리소스 제약 조건이 발생하는 경우 SQL Server는 스레드를 중단하거나 <xref:System.AppDomain>을 중지합니다.  이러한 경우 CER\(제약이 있는 실행 영역\)의 백아웃 코드만 실행될 수 있습니다.  
  
### SafeHandle을 사용하여 리소스 누수 방지  
 <xref:System.AppDomain>을 언로드하는 경우 실행되는 종료자 또는 `finally` 블록에 의존할 수 없습니다. 따라서 <xref:System.IntPtr>, <xref:System.Runtime.InteropServices.HandleRef> 또는 유사한 클래스가 아닌 <xref:System.Runtime.InteropServices.SafeHandle> 클래스를 통해 모든 운영 체제 리소스 액세스를 추출해야 합니다.  이것은 CLR을 추적 하고 심지어 <xref:System.AppDomain> 경우에서 처리를 닫게 합니다. <xref:System.Runtime.InteropServices.SafeHandle>는 CLR를 항상 실행 하게 하는 결정적 종료자 입니다.  
  
 운영 체제 핸들은 만들어진 시점부터 해제되는 시점까지 안전한 핸들에 저장됩니다.  <xref:System.Threading.ThreadAbortException>이 발생하여 핸들이 누수되는 경우는 없습니다.  또한 플랫폼 호출이 핸들에 대한 참조 카운트를 수행하여 핸들의 수명을 면밀히 추적할 수 있게 되므로 `Dispose`와 현재 핸들을 사용하는 메서드 간의 경합 상태 관련 보안 문제를 예방합니다.  
  
 현재 종료자를 사용하여 운영 체제 핸들을 간단히 정리하는 대부분의 클래스에는 더 이상 종료자가 필요하지 않게 됩니다.  대신 종료자는 <xref:System.Runtime.InteropServices.SafeHandle> 파생 클래스에 있습니다.  
  
 <xref:System.Runtime.InteropServices.SafeHandle>이 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName>를 대체하는 것은 아닙니다.  여전히 잠재적인 리소스 경합과, 운영 체제 리소스를 명시적으로 삭제할 수 있는 성능상의 이점이 있습니다.  리소스를 명시적으로 삭제하는 `finally` 블록은 완료될 때까지 실행되지 않을 수 있습니다.  
  
 <xref:System.Runtime.InteropServices.SafeHandle>을 사용하면 운영 체제 핸들 해제 루틴으로 상태를 전달하거나 루프에서 핸들 집합을 해제하는 등 핸들 해제 작업을 수행하는 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 메서드를 직접 구현할 수 있습니다.  CLR에서 이 메서드를 실행할 수 있습니다.  <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 구현 작성자는 모든 상황에서 핸들이 해제되도록 해야 합니다.  핸들이 해제되지 않으면 핸들이 누수되어 일반적으로 핸들과 관련된 네이티브 리소스까지 누수됩니다.  따라서 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 구현 시 호출 시점에서 사용할 수 없는 리소스를 할당하지 않아도 되도록 <xref:System.Runtime.InteropServices.SafeHandle> 파생 클래스를 구성해야 합니다.  사용자 코드에서 해당 실패를 처리할 수 있고 네이티브 핸들을 해제하는 계약을 완료하는 경우 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>의 구현에서 실패할 수 있는 메서드를 호출할 수 있습니다.  <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>에는 디버깅 목적을 위해 리소스 해제를 막는 치명적인 오류가 발생하는 경우 `false`로 설정될 수 있는 <xref:System.Boolean> 반환 값이 있습니다.  [releaseHandleFailed](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md) MDA를 사용할 수 있는 경우 이렇게 하면 이 MDA가 활성화되어 문제를 식별하는 데 도움이 됩니다.  다른 방법으로는 런타임에 영향을 주지 않습니다. 즉, 동일한 리소스에 대해 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A>이 다시 호출되지 않으며 결과적으로 핸들이 누수됩니다.  
  
 <xref:System.Runtime.InteropServices.SafeHandle>은 특정 컨텍스트에는 적합하지 않습니다.  <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle%2A> 메서드는 <xref:System.GC> 종료자 스레드에서 실행될 수 있으므로 특정 스레드에서 해제되어야 하는 모든 핸들은 <xref:System.Runtime.InteropServices.SafeHandle>에서 래핑되어서는 안 됩니다.  
  
 RCW\(런타임 호출 가능 래퍼\)는 CLR에서 추가 코드 없이 정리할 수 있습니다.  사용 하는 코드에 대한 플랫폼 호출 및 COM 개체를 처리한 `IUnknown*` 또는 <xref:System.IntPtr>, RCW를 사용 하 여 코드를 다시 작성 해야 합니다. <xref:System.Runtime.InteropServices.SafeHandle>는 관리 되지 않는 해제 메서드를 다시 관리 코드로 호출할 수 있기 때문에 적절한 시나리오일 수 있습니다.  
  
#### 코드 분석 규칙  
 운영 체제 리소스를 캡슐화하려면 <xref:System.Runtime.InteropServices.SafeHandle>을 사용합니다.  <xref:System.IntPtr> 형식의 필드나 <xref:System.Runtime.InteropServices.HandleRef>를 사용해서는 안 됩니다.  
  
### 종료자를 실행하지 않아도 운영 체제 리소스 누수를 막을 수 있도록 확인  
 종료자가 실행되지 않더라도 종료자를 주의 깊게 확인하여 중요한 운영 체제 리소스가 누수되지 않는지 확인합니다.  응용 프로그램이 안정적인 상태에서 실행되거나 SQL Server와 같은 서버가 종료되는 시점의 일반적인 <xref:System.AppDomain> 언로드와 달리 갑작스런 <xref:System.AppDomain> 언로드에서는 개체가 종결되지 않습니다.  응용 프로그램의 정확성을 보장할 수 없지만 리소스 누수를 막아 서버의 무결성을 유지해야 하므로 갑작스런 언로드의 경우 리소스가 누수되지 않는지 확인합니다.  운영 체제 리소스를 해제하려면 <xref:System.Runtime.InteropServices.SafeHandle>을 사용합니다.  
  
### finally 절을 실행하지 않아도 운영 체제 리소스 누수를 막을 수 있도록 확인  
 `finally` 절은 항상 CER 외부에서 실행되는 것은 아니므로 라이브러리 개발자는 관리되지 않는 리소스를 해제하기 위해 `finally` 블록 내부의 코드에 의존해서는 안 됩니다.  권장되는 해결 방법은 <xref:System.Runtime.InteropServices.SafeHandle>을 사용하는 것입니다.  
  
#### 코드 분석 규칙  
 운영 체제 리소스를 정리하려면 `Finalize` 대신 <xref:System.Runtime.InteropServices.SafeHandle>을 사용합니다.  <xref:System.IntPtr>를 사용해서는 안 됩니다. 리소스를 캡슐화하려면 <xref:System.Runtime.InteropServices.SafeHandle>을 사용합니다.  finally 절을 실행해야 하는 경우 CER에 삽입합니다.  
  
### 모든 잠금은 관리되는 기존 잠금 코드를 통과해야 함  
 CLR에서 코드가 잠금에 포함되는 시점을 파악하여 단지 스레드를 중단하는 것이 아닌 <xref:System.AppDomain>을 중단하는 것임을 알아야 합니다.  스레드를 중단하는 경우 스레드에 의해 작동되는 데이터가 일관성이 없는 상태가 될 수 있으므로 위험할 수 있습니다.  따라서 전체 <xref:System.AppDomain>을 재활용해야 합니다.  잠금을 식별하는 데 실패하는 경우 교착 상태 또는 잘못된 결과가 발생할 수 있습니다.  잠금 영역을 식별하려면 <xref:System.Threading.Thread.BeginCriticalRegion%2A> 및 <xref:System.Threading.Thread.EndCriticalRegion%2A> 메서드를 사용합니다.  이 메서드는 현재 스레드에만 적용되는 <xref:System.Threading.Thread> 클래스의 정적 메서드로서, 하나의 스레드가 다른 스레드의 잠금 횟수를 편집하지 못하게 합니다.  
  
 <xref:System.Threading.Monitor.Enter%2A> 및 <xref:System.Threading.Monitor.Exit%2A>에는 이 CLR 알림이 기본적으로 제공되므로 이 메서드를 사용하는 [lock 문](../Topic/lock%20Statement%20\(C%23%20Reference\).md)과 함께 사용하는 것이 좋습니다.  
  
 스핀 잠금 및 <xref:System.Threading.AutoResetEvent>와 같은 다른 잠금 메커니즘은 이러한 메서드를 호출하여 임계 영역이 시작되고 있음을 CLR에 알립니다.  이러한 메서드는 어떠한 잠금도 사용하지 않으며, 코드가 임계 영역에서 실행되고 있으므로 스레드를 중단하면 공유 상태가 일관성이 없는 상태가 될 수 있음을 알립니다.  사용자 지정 <xref:System.Threading.ReaderWriterLock> 클래스와 같은 고유한 잠금 형식을 정의한 경우 이 잠금 횟수 메서드를 사용합니다.  
  
#### 코드 분석 규칙  
 <xref:System.Threading.Thread.BeginCriticalRegion%2A> 및 <xref:System.Threading.Thread.EndCriticalRegion%2A>을 사용하여 모든 잠금을 표시하고 식별합니다.  <xref:System.Threading.Interlocked.CompareExchange%2A>, <xref:System.Threading.Interlocked.Increment%2A> 및 <xref:System.Threading.Interlocked.Decrement%2A>를 루프에서 사용하면 안 됩니다.  이 메서드의 Win32 변형에 대한 플랫폼 호출을 수행하면 안 됩니다.  <xref:System.Threading.Thread.Sleep%2A>을 루프에서 사용하면 안 됩니다.  volatile 필드를 사용하면 안 됩니다.  
  
### 정리 코드는 catch 다음이 아닌 finally 또는 catch 블록 내부에 있어야 함  
 정리 코드는 `catch` 블록 다음이 아닌 `finally` 또는 `catch` 블록 내부에 있어야 합니다.  이 규칙은 일반적으로 유용한 방법입니다.  `finally` 블록은 예외가 throw될 때와 `try` 블록의 끝이 정상적으로 표시될 때 모두 동일한 코드를 실행하므로 일반적으로 선호됩니다.  예를 들어, <xref:System.Threading.ThreadAbortException>과 같이 예기치 않은 예외가 throw되는 경우 정리 코드가 실행되지 않습니다.  `finally`에서 정리하는 모든 관리되지 않는 리소스는 <xref:System.Runtime.InteropServices.SafeHandle>에서 래핑되어야 누수를 막을 수 있습니다.  C\# `using` 키워드를 효과적으로 사용하면 핸들을 포함하여 개체를 삭제할 수 있습니다.  
  
 <xref:System.AppDomain>을 재활용하여 종료자 스레드에서 리소스를 정리할 수도 있지만 이 경우 정리 코드를 올바른 위치에 삽입해야 합니다.  스레드에서 잠금을 유지하지 않고 비동기 예외가 발생하는 경우 CLR은 <xref:System.AppDomain>을 재활용하지 않고 자체적으로 스레드 종료를 시도합니다.  리소스를 미리 정리하는 경우 보다 많은 리소스를 사용할 수 있고 수명을 보다 효과적으로 관리할 수 있어 유용합니다.  일부 오류 코드 경로에서 파일에 대한 핸들을 명시적으로 닫지 않고 <xref:System.Runtime.InteropServices.SafeHandle> 종료자가 코드를 정리하도록 기다리는 경우, 종료자가 실행되지 않은 상태에서 다음에 코드가 실행되면 동일한 파일에 대한 액세스에 실패할 수 있습니다.  따라서 필수 사항은 아니더라도 정리 코드가 존재하며 올바르게 작동하는지 확인함으로써 실패를 보다 명확하고 빠르게 복구하는 데 도움이 됩니다.  
  
#### 코드 분석 규칙  
 `catch` 다음의 정리 코드는 `finally` 블록에 포함되어야 합니다.  finally 블록에서 처리하기 위해 호출 합니다. `catch`블록은 throw 하거나 다시 throw 해야 합니다.  네트워크 연결을 설정할 수 있는지 여부를 확인하는 코드와 같이 여러 예외가 발생할 수 있는 경우 일반적인 상황에서 여러 예외를 catch해야 하는 코드는 코드의 성공 여부를 확인하기 위한 테스트를 수행해야 함을 나타내야 합니다.  
  
### 응용 프로그램 도메인 간의 프로세스 전체 변경 가능 공유 상태를 제거하거나 제약이 있는 실행 영역을 사용해야 함  
 앞의 소개 부분에서 설명한 대로, 응용 프로그램 도메인에 걸쳐 프로세스 차원의 공유 상태를 모니터링하는 관리 코드를 안전하게 작성하기는 매우 어렵습니다.  프로세스 전체 공유 상태는 응용 프로그램 도메인 간에 공유되는 데이터 구조의 유형으로서 Win32 코드, CLR 내부 또는 원격을 사용하는 관리 코드에 포함됩니다.  변경 가능한 고유 상태는 관리 코드에서 정확히 작성하기가 매우 어려우므로 정적 공유 상태를 수행하려면 세심한 주의를 기울여야 합니다.  프로세스 전체 또는 시스템 전체 공유 상태가 있는 경우 해당 상태를 제거할 방법을 찾거나 CER\(제약이 있는 실행 영역\)를 사용하여 공유 상태를 보호합니다.  라이브러리에 식별 및 수정되지 않은 공유 상태가 있는 경우 SQL Server와 같이 정리된 <xref:System.AppDomain> 언로드가 필요한 호스트에서 장애가 발생할 수 있습니다.  
  
 코드에서 COM 개체를 사용하는 경우 응용 프로그램 도메인 간에 해당 COM 개체를 공유하지 않도록 해야 합니다.  
  
### 프로세스 전체 또는 응용 프로그램 도메인 간에 잠금이 작동하지 않음  
 과거에는 <xref:System.Threading.Monitor.Enter%2A> 및 [lock 문](../Topic/lock%20Statement%20\(C%23%20Reference\).md)을 사용하여 전역 프로세스 잠금을 만들었습니다.  예를 들어, 공유되지 않는 어셈블리의 <xref:System.Type> 인스턴스와 같은 <xref:System.AppDomain> 활성 클래스, <xref:System.Threading.Thread> 개체, 내부 풀에 추가된 문자열 및 원격을 사용하는 응용 프로그램 도메인에 걸쳐 공유되는 일부 문자열을 잠글 때 발생합니다.  이러한 잠금은 더 이상 프로세스 전체에 적용되지 않습니다.  프로세스 전체의 응용 프로그램 간 도메인 잠금이 존재하는지 식별하려면 잠금 내 코드가 디스크의 파일 또는 데이터베이스와 같은 외부 지속 리소스를 사용하는지 여부를 확인합니다.  
  
 보호된 코드가 외부 리소스를 사용하는 경우 해당 코드가 여러 응용 프로그램 도메인에서 동시에 실행될 수 있으므로 <xref:System.AppDomain> 내부에서 잠금을 사용할 때 문제가 발생할 수 있습니다.  이는 하나의 로그 파일에 쓰거나 전체 프로세스에 대한 로켓에 바인딩할 때 문제가 될 수 있습니다.  이러한 변경은 명명된 <xref:System.Threading.Mutex> 또는 <xref:System.Threading.Semaphore> 인스턴스를 사용하지 않고 관리 코드를 사용하여 프로세스 전역 잠금을 쉽게 가져올 수 없는 경우 의미가 있습니다.  두 가지 응용 프로그램 도메인에서 동시에 실행되지 않는 코드를 만들거나 <xref:System.Threading.Mutex> 또는 <xref:System.Threading.Semaphore> 클래스를 사용합니다.  기존 코드를 변경할 수 없는 경우 이 동기화를 달성하기 위해 Win32 명명 뮤텍스를 사용해서는 안 됩니다. 파이버 모드에서 실행하는 경우 동일한 운영 체제 스레드에서 뮤텍스를 가져오고 해제하는 것으로 보장할 수 없기 때문입니다.  비관리 코드를 사용하여 잠금을 동기화하는 대신 CLR에서 인식하는 방식으로 코드 잠금을 동기화하려면 관리되는 <xref:System.Threading.Mutex> 클래스나 명명된 <xref:System.Threading.ManualResetEvent>, <xref:System.Threading.AutoResetEvent> 또는 <xref:System.Threading.Semaphore>를 사용해야 합니다.  
  
#### 잠금 방지\(typeof\(MyType\)\)  
 모든 응용 프로그램 도메인에서 하나의 코드 복사본만 공유되는 공유 어셈블리의 전용 및 공용 <xref:System.Type> 개체에도 문제가 발생합니다.  공유 어셈블리의 경우 프로세스당 <xref:System.Type>의 인스턴스가 하나만 있으며 이는 여러 응용 프로그램 도메인이 동일한 <xref:System.Type> 인스턴스를 공유함을 의미합니다.  <xref:System.Type> 인스턴스의 잠금을 사용하면 <xref:System.AppDomain>은 물론 전체 프로세스에 영향을 주는 잠금을 사용하게 됩니다.  하나의 <xref:System.AppDomain>에서 <xref:System.Type> 개체의 잠금을 사용하는 경우 해당 스레드는 갑자기 중단되어 잠금을 해제하지 않습니다.  이 잠금으로 인해 다른 응용 프로그램 도메인에 교착 상태가 발생할 수 있습니다.  
  
 정적 메서드의 잠금을 사용하는 올바른 방법 중 하나는 코드에 정적 내부 동기화 개체를 추가하는 것입니다.  이 방법은 클래스 생성자가 있는 경우 해당 생성자에서 초기화될 수 있으며 생성자가 없는 경우에는 다음과 같이 초기화될 수 있습니다.  
  
```  
private static Object s_InternalSyncObject;  
private static Object InternalSyncObject   
{  
    get   
    {  
        if (s_InternalSyncObject == null)   
        {  
            Object o = new Object();  
            Interlocked.CompareExchange(  
                ref s_InternalSyncObject, o, null);  
        }  
        return s_InternalSyncObject;  
    }  
}  
```  
  
 그런 다음 잠금을 사용할 때 `InternalSyncObject` 속성을 사용하여 잠글 개체를 가져옵니다.  클래스 생성자에서 내부 동기화 개체를 초기화한 경우 이 속성을 사용하지 않아도 됩니다.  잠금 초기화 코드를 다시 확인하면 다음 예제와 같이 표시되어야 합니다.  
  
```  
public static MyClass SingletonProperty   
{  
    get   
    {  
        if (s_SingletonProperty == null)   
        {  
            lock(InternalSyncObject)   
            {  
                // Do not use lock(typeof(MyClass))   
                if (s_SingletonProperty == null)   
                {  
                    MyClass tmp = new MyClass(…);     
                    // Do all initialization before publishing  
                    s_SingletonProperty = tmp;  
                }  
            }  
        }  
        return s_SingletonProperty;  
    }  
}  
```  
  
#### 잠금에 대한 참고 사항  
 일반적으로 공개적으로 액세스할 수 있는 개별 개체의 잠금을 사용할 수 있습니다.  그러나 해당 개체가 전체 하위 시스템에 교착 상태를 발생시킬 수 있는 singleton 개체인 경우 위의 설계 패턴 사용을 고려해야 합니다.  예를 들어, 하나의 <xref:System.Security.SecurityManager> 개체에 대한 잠금으로 <xref:System.AppDomain>에 교착 상태가 발생하여 전체 <xref:System.AppDomain>을 사용할 수 없게 될 수 있습니다.  공개적으로 액세스할 수 있는 이러한 형식의 개체에는 잠금을 사용하지 않는 것이 좋습니다.  그러나 일반적으로 개별 컬렉션이나 배열에 대한 잠금으로 문제가 발생하지는 않습니다.  
  
#### 코드 분석 규칙  
 응용 프로그램 도메인에 걸쳐 사용될 수 있거나 ID를 쉽게 식별할 수 없는 형식에는 잠금을 사용하면 안 됩니다.  <xref:System.Type>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.PropertyInfo>, <xref:System.String>, <xref:System.ValueType>, <xref:System.Threading.Thread> 또는 <xref:System.MarshalByRefObject>의 모든 파생 개체에서 <xref:System.Threading.Monitor.Enter%2A>를 호출해서는 안 됩니다.  
  
### GC.KeepAlive 호출 제거  
 기존 코드 중 상당 부분에서 <xref:System.GC.KeepAlive%2A>를 사용해야 할 때 사용하지 않거나 적합하지 않은 경우에 사용합니다.  <xref:System.Runtime.InteropServices.SafeHandle>로 변환한 후에는 클래스에서 <xref:System.GC.KeepAlive%2A>를 호출하지 않아도 됩니다. 해당 클래스에 종료자는 없지만 <xref:System.Runtime.InteropServices.SafeHandle>에 의존하여 운영 체제 핸들을 종결하는 것으로 가정하기 때문입니다.  <xref:System.GC.KeepAlive%2A>에 대한 호출을 유지하기 위한 성능 비용은 무시할 수 있지만 <xref:System.GC.KeepAlive%2A>에 대한 호출이 더 이상 존재하지 않는 수명 문제를 해결하는 데 반드시 필요하거나 문제 해결에 도움이 되는지 여부에 대한 인식으로 코드를 유지 관리하기가 더욱 어렵습니다.  그러나 COM interop CLR RCW\(런타임 호출 가능 래퍼\)를 사용하는 경우에도 코드에서 계속 <xref:System.GC.KeepAlive%2A>가 필요합니다.  
  
#### 코드 분석 규칙  
 <xref:System.GC.KeepAlive%2A>를 제거합니다.  
  
### 호스트 보호 특성 사용  
 HPA\(<xref:System.Security.Permissions.HostProtectionAttribute>\)는 선언적 보안 동작을 사용하여 호스트 보호 요구 사항을 확인함으로써 호스트에서 완전하게 신뢰할 수 있는 코드라도 해당 호스트에 적합하지 않은 <xref:System.Environment.Exit%2A> 또는 <xref:System.Windows.Forms.MessageBox.Show%2A>\(SQL Server\)와 같은 특정 메서드를 호출하지 못하게 할 수 있습니다.  
  
 HPA는 공용 언어 런타임을 호스트하고 호스트 보호를 구현하는 SQL Server와 같은 관리되지 않는 응용 프로그램에만 영향을 줍니다.  보안 동작이 수행되면 클래스나 메서드가 노출하는 호스트 리소스에 따라 링크 요청이 작성됩니다.  코드가 클라이언트 응용 프로그램 또는 호스트가 보호되지 않는 서버에서 실행되면 특성이 "사라져" 발견되지 않으므로 적용되지도 않습니다.  
  
> [!IMPORTANT]
>  이 특성의 목적은 보안 동작이 아닌 호스트 특정 프로그래밍 모델 지침을 적용하는 것입니다.  링크 요청은 프로그래밍 모델 요구 사항에 대한 적합성을 확인하는 데 사용되지만 <xref:System.Security.Permissions.HostProtectionAttribute>는 보안 권한이 아닙니다.  
  
 호스트에 프로그래밍 모델 요구 사항이 없으면 링크 요청이 발생하지 않습니다.  
  
 이 특성은 다음을 식별합니다.  
  
-   호스트 프로그래밍 모델에 맞지 않지만 다른 면에서는 양호한 메서드나 클래스  
  
-   호스트 프로그래밍 모델에 맞지 않아 서버에서 관리하는 사용자 코드를 불안정하게 만들 수 있는 메서드나 클래스  
  
-   호스트 프로그래밍 모델에 맞지 않아 서버 프로세스 자체를 불안정하게 만들 수 있는 메서드나 클래스  
  
> [!NOTE]
>  호스트가 보호되는 환경에서 실행될 수 있는 응용 프로그램에서 호출할 클래스 라이브러리를 만드는 경우 <xref:System.Security.Permissions.HostProtectionResource> 리소스 범주를 노출하는 멤버에 이 특성을 적용해야 합니다.  이 특성을 .NET Framework 클래스 라이브러리 멤버에 적용하면 직접 실행 호출자만 확인됩니다.  라이브러리 멤버 또한 동일한 방식으로 해당 직접 실행 호출자를 확인해야 합니다.  
  
 HPA에 대한 자세한 내용은 <xref:System.Security.Permissions.HostProtectionAttribute>를 참조하십시오.  
  
#### 코드 분석 규칙  
 SQL Server의 경우 동기화 또는 스레딩을 소개하는 데 사용되는 모든 메서드는 HPA를 사용하여 식별해야 합니다.  여기에는 상태를 공유하거나 동기화되거나 외부 프로세스를 관리하는 메서드가 포함됩니다.  SQL Server에 영향을 주는 <xref:System.Security.Permissions.HostProtectionResource> 값은 <xref:System.Security.Permissions.HostProtectionResource>, <xref:System.Security.Permissions.HostProtectionResource> 및 <xref:System.Security.Permissions.HostProtectionResource>입니다.  그러나 <xref:System.Security.Permissions.HostProtectionResource>를 노출하는 모든 메서드는 SQL에 영향을 주는 리소스를 사용하는 코드가 아닌 HPA로 식별해야 합니다.  
  
### 비관리 코드에서 무기한 차단하지 않음  
 관리 코드가 아닌 비관리 코드에서 차단하는 경우 CLR이 스레드를 중단할 수 없어 서비스 공격이 거부될 수 있습니다.  차단된 스레드는 일부 위험한 작업을 수행하지 않고도 CLR에서 <xref:System.AppDomain>을 언로드하지 않도록 막을 수 있습니다.  Win32 동기화 기본 형식을 사용한 차단은 허용되지 않습니다.  소켓에서 `ReadFile`에 대한 호출 차단은 가능한 수행해서는 안 됩니다. Win32 API는 이러한 작업의 시간을 제한하기 위한 메커니즘을 제공해야 합니다.  
  
 네이티브로 호출되는 메서드는 적절한 유한 시간 제한이 설정된 Win32 호출을 사용해야 합니다.  사용자가 시간 제한을 지정할 수 있는 경우라도 특정 보안 권한 없이 무한 시간 제한을 지정할 수 있도록 허용해서는 안 됩니다.  예를 들어, 메서드가 10초 넘게 차단되는 경우 시간 제한을 지원하는 버전을 사용하거나 추가 CLR 지원이 필요합니다.  
  
 다음은 문제를 일으킬 수 있는 몇 가지 API 예제입니다.  시간 제한을 사용하여 익명 및 명명된 파이프를 만들 수 있지만 코드에서 NMPWAIT\_WAIT\_FOREVER를 사용하여 `CreateNamedPipe` 또는 `WaitNamedPipe`를 호출하지 않도록 해야 합니다.  또한 시간 제한을 지정해도 예기치 않은 차단이 발생할 수 있습니다.  익명 파이프에 대한 `WriteFile` 호출은 모든 바이트를 쓸 때까지 차단됩니다. 즉, 버퍼에 읽지 않은 데이터가 있으면 판독기가 파이프 버퍼에서 사용 가능한 공간을 늘릴 때까지 `WriteFile` 호출이 차단됩니다.  소켓은 항상 시간 제한 메커니즘을 준수하는 API를 사용해야 합니다.  
  
#### 코드 분석 규칙  
 비관리 코드에서 시간 제한 없이 차단하는 것은 서비스 공격을 거부하는 것입니다.  `WaitForSingleObject`, `WaitForSingleObjectEx`, `WaitForMultipleObjects`, `MsgWaitForMultipleObjects` 및 `MsgWaitForMultipleObjectsEx`에서는 P\/Invoke 호출을 수행하면 안 됩니다.  NMPWAIT\_WAIT\_FOREVER를 사용해서는 안 됩니다.  
  
### STA 종속 기능 식별  
 COM STA\(Single\-Threaded Apartment\)를 사용하는 코드를 식별합니다.  SQL Server 프로세스에서는 STA가 비활성화됩니다.  성능 카운터나 클립보드와 같이 `CoInitialize`에 의존하는 기능은 SQL Server에서 비활성화되어야 합니다.  
  
### 종료자에 동기화 문제가 없는지 확인  
 .NET Framework의 후속 버전에는 여러 개의 종료자 스레드가 있을 수 있습니다. 이 경우 동일한 형식의 다른 인스턴스에 대한 종료자가 동시에 실행됩니다.  이러한 종료자는 스레드로부터 완전히 안전하지 않아도 되며 가비지 수집기가 하나의 스레드만 해당 개체 인스턴스에 대한 종료자를 실행하도록 보장합니다.  그러나 서로 다른 여러 개체 인스턴스에서 동시에 종료자를 실행하는 경우 경합 상태와 교착 상태가 발생하지 않도록 종료자를 코딩해야 합니다.  종료자에서 로그 파일에 쓰기와 같이 외부 상태를 사용하는 경우 스레딩 문제를 처리해야 합니다.  종료에 의존하여 스레드 안전을 제공해서는 안 됩니다.  종료자 스레드에 대한 상태를 저장하기 위해 네이티브 또는 관리되는 스레드 로컬 저장소를 사용해서는 안 됩니다.  
  
#### 코드 분석 규칙  
 종료자에는 동기화 문제가 없어야 합니다.  종료자에서 정적 변경 가능 상태를 사용해서는 안 됩니다.  
  
### 가능한 경우 관리되지 않는 메모리를 사용하지 않음  
 관리되지 않는 메모리는 운영 체제 핸들과 같이 누수될 수 있습니다.  가능한 경우 [stackalloc](../Topic/stackalloc%20\(C%23%20Reference\).md)을 사용하여 스택에서 메모리를 사용하거나 byte\[\]를 사용하여 [fixed 문](../Topic/fixed%20Statement%20\(C%23%20Reference\).md) 또는 <xref:System.Runtime.InteropServices.GCHandle>과 같은 관리되는 고정 개체를 사용합니다.  <xref:System.GC>가 이러한 메모리나 개체를 정리합니다.  그러나 관리되지 않는 메모리를 할당해야 하는 경우 <xref:System.Runtime.InteropServices.SafeHandle>의 파생 클래스를 사용하여 메모리 할당을 래핑할 수 있습니다.  
  
 <xref:System.Runtime.InteropServices.SafeHandle>이 적합하지 않은 경우도 있습니다.  메모리를 할당하거나 해제하는 COM 메서드 호출의 경우 일반적으로 하나의 DLL이 `CoTaskMemAlloc`을 통해 메모리를 할당한 다음 다른 DLL이 `CoTaskMemFree`를 사용하여 해당 메모리를 해제합니다.  이러한 경우 <xref:System.Runtime.InteropServices.SafeHandle>은 다른 DLL이 메모리 수명을 제어하도록 허용하는 대신 관리되지 않는 메모리의 수명과 <xref:System.Runtime.InteropServices.SafeHandle>의 수명을 연결하려고 시도하므로 사용해서는 안 됩니다.  
  
### 모든 catch\(예외\) 용례 확인  
 하나의 특정 예외가 아닌 모든 예외를 catch하는 catch 블록은 이제 비동기 예외도 catch합니다.  모든 catch\(예외\) 블록을 검사하여, 중요한 리소스 해제 또는 건너뛸 수 있는 백아웃 코드가 없는지 또한 catch 블록에서 <xref:System.Threading.ThreadAbortException>, <xref:System.StackOverflowException> 또는 <xref:System.OutOfMemoryException>을 처리하기 위한 잠재적으로 잘못될 수 있는 동작이 있는지 찾습니다.  이 코드는 특정 예외만 확인할 수 있거나 예외가 발생할 때마다 명확한 한 가지 특정 이유로 실패한다는 일부 가정을 기록하거나 작성할 수 있습니다.  이러한 가정은 <xref:System.Threading.ThreadAbortException>을 포함하도록 업데이트되어야 합니다.  
  
 예를 들어, 모든 예외를 catch하는 모든 위치를 문자열 형식 지정 메서드의 <xref:System.FormatException>과 같이 throw될 특정 형식의 예외 catch로 변경하는 것을 고려합니다.  이를 통해 catch 블록에 예기치 않은 예외가 발생하지 않고, 예기치 않은 예외를 catch함으로써 코드에서 버그를 숨기지 않을 수 있습니다.  일반 규칙은 라이브러리 코드 즉, 사용자가 호출하는 코드의 설계상의 결점을 나타내는 예외를 catch해야 하는 코드의 예외를 처리하지 않습니다.  경우에 따라 예외를 catch하여 추가 데이터를 제공할 수 있는 다른 예외 형식을 throw할 수 있습니다.  이 경우 중첩된 예외를 사용하여 새 예외의 <xref:System.Exception.InnerException%2A> 속성에 실패의 실제 원인을 저장합니다.  
  
#### 코드 분석 규칙  
 모든 개체를 catch하거나 모든 예외를 catch하는 모든 catch 블록을 관리 코드에서 확인합니다.  C\#의 경우 이 작업은 `catch` {}와 `catch(Exception)` {}에 모두 플래그를 지정하는 것을 의미합니다.  예외 형식을 매우 구체적으로 표시하거나, 예기치 않은 예외 형식을 catch하는 경우 코드가 잘못 작동하지 않는지 확인합니다.  
  
### 관리되는 스레드를 파이버가 아닌 Win32 스레드로 가정하지 않음  
 관리되는 스레드 로컬 저장소를 사용할 수 없는 경우 관리되지 않는 스레드 로컬 저장소를 사용할 수 없거나 현재 운영 체제 스레드에서 다시 코드가 실행될 것으로 가정할 수 없습니다.  스레드 로캘과 같은 설정은 변경할 수 없습니다.  `InitializeCriticalSection` 또는 `CreateMutex`의 경우 잠금을 시작하는 운영 체제 스레드가 또한 해당 잠금을 종료해야 하므로 플랫폼 호출을 통해 호출해서는 안 됩니다.  이는 파이버를 사용하는 경우가 아니므로 Win32 임계 영역과 뮤텍스를 SQL에서 직접 사용할 수 없습니다.  관리되는 <xref:System.Threading.Mutex> 클래스는 이러한 스레드 선호도 문제를 처리하지 않습니다.  
  
 관리되는 스레드 로컬 저장소와 스레드의 현재 UI 문화권을 포함하여 관리되는 <xref:System.Threading.Thread> 개체에 대한 대부분의 상태를 안전하게 사용할 수 있습니다.  <xref:System.ThreadStaticAttribute>를 사용하여, 현재 관리되는 스레드만 기존 정적 변수 값에 액세스할 수 있도록 할 수도 있습니다. 이 방법은 CLR에서 파이버 로컬 저장을 수행하는 다른 방법이기도 합니다.  프로그래밍 모델 관련 이유로, SQL에서 실행할 때는 스레드의 현재 문화권을 변경할 수 없습니다.  
  
#### 코드 분석 규칙  
 SQL Server는 파이버 모드에서 실행되므로 스레드 로컬 저장소를 사용해서는 안 됩니다.  또한 `TlsAlloc`, `TlsFree`, `TlsGetValue` 및 `TlsSetValue.`에 대한 P\/Invoke 호출을 수행해서는 안 됩니다.  
  
### SQL Server의 가장 처리 허용  
 가장은 스레드 수준에서 작동하고 SQL은 파이버 모드에서 실행될 수 있으므로 관리 코드는 사용자를 가장해서는 안 되며 `RevertToSelf`를 호출해서는 안 됩니다.  
  
#### 코드 분석 규칙  
 SQL Server에서 가장을 처리하도록 합니다.  `RevertToSelf`, `ImpersonateAnonymousToken`, `DdeImpersonateClient`, `ImpersonateDdeClientWindow`, `ImpersonateLoggedOnUser`, `ImpersonateNamedPipeClient`, `ImpersonateSelf`, `RpcImpersonateClient`, `RpcRevertToSelf`, `RpcRevertToSelfEx` 또는 `SetThreadToken`을 사용해서는 안 됩니다.  
  
### 스레드::일시 중단을 호출하지 않음  
 스레드를 일시 중단하는 기능은 간단한 작업처럼 보일 수 있지만 교착 상태가 발생할 수 있습니다.  동일한 잠금을 시도 잠금을 두 번째 스레드가 및 두 번째 스레드가 일시 중단을 보유 하는 스레드 교착 상태가 발생 합니다. 현재 보안, 클래스 로드, 원격 및 리플렉션으로 <xref:System.Threading.Thread.Suspend%2A>방해할 수 있습니다.  
  
#### 코드 분석 규칙  
 <xref:System.Threading.Thread.Suspend%2A>를 호출해서는 안 됩니다.  대신 <xref:System.Threading.Semaphore> 또는 <xref:System.Threading.ManualResetEvent>와 같은 실제 동기화 기본 형식을 사용할 수 있습니다.  
  
### 제약이 있는 실행 영역 및 안정성 계약을 사용한 중요 작업 보호  
 공유 상태를 업데이트하거나 완전한 성공 또는 실패 여부를 확인해야 하는 복잡한 작업을 수행하는 경우 CER\(제약이 있는 실행 영역\)로 해당 작업을 보호해야 합니다.  이를 통해 갑작스런 스레드 중단 또는 갑작스런 <xref:System.AppDomain> 언로드를 포함한 어떠한 경우라도 코드가 실행될 수 있습니다.  
  
 CER는 <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions%2A>에 대한 호출 바로 뒤에 오는 특정 `try/finally` 블록입니다.  
  
 이 경우 JIT\(Just\-In\-Time\) 컴파일러가 `try` 블록을 실행하기 전에 finally 블록의 모든 코드를 준비하도록 지시합니다.  이렇게 함으로써 finally 블록의 코드가 빌드되어 모든 경우에 실행될 수 있습니다.  CER에는 일반적으로 비어 있는 `try` 블록이 없습니다.  CER를 사용하면 비동기 스레드 중단과 메모리 부족 예외를 방지할 수 있습니다.  하위 코드에 대한 스택 오버플로를 추가로 처리하는 CER의 형삭을 보려면 <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup%2A>을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Runtime.ConstrainedExecution>   
 [SQL Server 프로그래밍 및 호스트 보호 특성](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)