---
title: "스레드 동기화(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e42b1be6-c93c-479f-a148-be0759f1a4e1
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: f8d51aa1c50c097577a575be9b5da4b9e0effc55
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="thread-synchronization-c"></a>스레드 동기화(C#)
다음 섹션에서는 다중 스레드 응용 프로그램에서 리소스에 대한 액세스를 동기화 하는 데 사용할 수 있는 기능 및 클래스를 설명합니다.  
  
 응용 프로그램에서 여러 스레드를 사용하는 이점 중 하나는 각 스레드가 비동기적으로 실행된다는 것입니다. Windows 응용 프로그램의 경우 이렇게 하면 시간이 많이 걸리는 작업을 백그라운드에서 수행하는 동시에 응용 프로그램 창과 컨트롤의 응답성을 유지할 수 있습니다. 서버 응용 프로그램의 경우 다중 스레딩을 사용하면 들어오는 각 요청을 다른 스레드에서 처리할 수 있습니다. 다중 스레딩을 사용하지 않으면 이전 요청이 완전히 충족될 때까지 새로운 각 요청이 처리되지 않습니다.  
  
 그러나 스레드의 비동기 특성 때문에 파일 핸들, 네트워크 연결, 메모리 등의 리소스에 대한 액세스를 조정해야 합니다. 조정하지 않으면 둘 이상의 스레드가 다른 스레드의 작업을 모르는 상태로 같은 리소스에 동시에 액세스할 수 있습니다. 그 결과, 예측할 수 없는 데이터 손상이 발생합니다.  
  
 정수 계열 숫자 데이터 형식에 대한 간단한 작업을 위해 <xref:System.Threading.Interlocked> 클래스의 멤버를 사용하여 스레드를 동기화할 수 있습니다. 다른 모든 데이터 형식 및 스레드로부터 안전하지 않은 리소스의 경우 이 항목의 생성자를 사용해야만 다중 스레딩을 안전하게 수행할 수 있습니다.  
  
 다중 스레드 프로그래밍에 대한 배경 정보는 다음을 참조하세요.  
  
-   [관리되는 스레딩 기본 사항](../../../../standard/threading/managed-threading-basics.md)  
  
-   [스레드 및 스레딩 사용](../../../../standard/threading/using-threads-and-threading.md)  
  
-   [관리되는 스레딩을 구현하는 최선의 방법](../../../../standard/threading/managed-threading-best-practices.md)  
  
## <a name="the-lock-keyword"></a>lock 키워드  
 C# `lock` 문을 사용하여 코드 블록이 다른 스레드에 의해 중단되지 않고 완료될 때까지 실행되도록 할 수 있습니다. 이렇게 하려면 코드 블록 기간 동안 지정된 개체에 대한 상호 배타적 잠금을 얻습니다.  
  
 `lock` 문에 개체가 인수로 지정되고, 한 번에 하나의 스레드에 의해 실행되는 코드 블록이 뒤에 나옵니다. 예:  
  
```csharp  
public class TestThreading  
{  
    private System.Object lockThis = new System.Object();  
  
    public void Process()  
    {  
  
        lock (lockThis)  
        {  
            // Access thread-sensitive resources.  
        }  
    }  
  
}  
```  
  
 `lock` 키워드에 제공되는 인수는 참조 형식을 기반으로 하는 개체여야 하며, 잠금 범위를 정의하는 데 사용됩니다. 위의 예제에서는 `lockThis` 개체에 대한 참조가 함수 외부에 없기 때문에 잠금 범위가 이 함수로 제한됩니다. 이러한 참조가 있으면 잠금 범위가 해당 개체까지 확장됩니다. 엄격히 말해, 제공된 개체는 여러 스레드 간에 공유되는 리소스를 고유하게 식별하는 용도로만 사용되므로 임의의 클래스 인스턴스일 수 있습니다. 그러나 실제로 이 개체는 일반적으로 스레드 동기화가 필요한 리소스를 나타냅니다. 예를 들어 컨테이너 개체가 여러 스레드에서 사용되는 경우 컨테이너를 잠금으로 전달할 수 있으며, 잠금 뒤에 나오는 동기화된 코드 블록에서 컨테이너에 액세스합니다. 액세스하기 전에 다른 스레드가 동일한 컨테이너를 잠그기만 하면 개체 액세스가 안전하게 동기화됩니다.  
  
 일반적으로 응용 프로그램의 제어를 벗어난 `public` 형식 또는 개체 인스턴스에 대한 잠금은 피하는 것이 좋습니다. 예를 들어 `lock(this)`는 인스턴스를 공개적으로 액세스할 수 있는 경우 사용자의 제어를 벗어난 코드에서 개체를 잠글 수도 있기 때문에 문제가 될 수 있습니다. 이 경우 둘 이상의 스레드가 동일한 개체의 해제를 기다리는 교착 상태 상황이 생성될 수 있습니다. 개체가 아니라 공용 데이터 형식을 잠그는 경우 동일한 이유로 문제가 발생할 수 있습니다. 리터럴 문자열 잠금은 리터럴 문자열이 CLR(공용 언어 런타임)에 의해 *인턴 지정*되므로 특히 위험합니다. 즉, 지정된 문자열 리터럴 인스턴스가 전체 프로그램에 하나만 있고, 실행 중인 모든 응용 프로그램 도메인의 모든 스레드에서 똑같은 개체가 해당 리터럴을 나타냅니다. 그 결과, 응용 프로그램 프로세스의 어디든지 동일한 콘텐츠가 있는 문자열에 잠금을 설정하면 응용 프로그램에서 해당 문자열의 모든 인스턴스가 잠깁니다. 따라서 인턴 지정되지 않은 private 또는 protected 멤버를 잠그는 것이 좋습니다. 일부 클래스는 잠금을 위한 특수 멤버를 제공합니다. 예를 들어 <xref:System.Array> 형식은 <xref:System.Array.SyncRoot%2A>를 제공합니다. 많은 컬렉션 형식은 `SyncRoot` 멤버도 제공합니다.  
  
 `lock` 문에 대한 자세한 내용은 다음 항목을 참조하세요.  
  
-   [lock 문](../../../../csharp/language-reference/keywords/lock-statement.md)  
  
-   @System.Threading.Monitor  
  
## <a name="monitors"></a>모니터  
 `lock` 키워드와 마찬가지로, 모니터는 코드 블록이 여러 스레드에서 동시에 실행되지 않도록 합니다. <xref:System.Threading.Monitor.Enter%2A> 메서드를 사용하면 하나의 스레드만 다음 문으로 계속 진행할 수 있습니다. 다른 모든 스레드는 실행 중인 스레드가 <xref:System.Threading.Monitor.Exit%2A>를 호출할 때까지 차단됩니다. 이는 `lock` 키워드를 사용하는 것과 같습니다. 예:  
  
```csharp  
lock (x)  
{  
    DoSomething();  
}  
```  
  
 다음 코드와 동일합니다.  
  
```csharp  
System.Object obj = (System.Object)x;  
System.Threading.Monitor.Enter(obj);  
try  
{  
    DoSomething();  
}  
finally  
{  
    System.Threading.Monitor.Exit(obj);  
}  
```  
  
 `lock`이 더 간결할 뿐 아니라 `lock`은 보호된 코드에서 예외를 throw하는 경우에도 기본 모니터가 해제되도록 하기 때문에 일반적으로 <xref:System.Threading.Monitor> 클래스를 직접 사용하는 것보다 `lock` 키워드를 사용하는 것이 좋습니다. 이렇게 하려면 예외가 throw되는지 여부에 관계없이 관련된 코드 블록을 실행하는 `finally` 키워드를 사용합니다.  
  
## <a name="synchronization-events-and-wait-handles"></a>동기화 이벤트 및 대기 핸들  
 잠금 또는 모니터는 스레드가 중요한 코드 블록의 동시 실행을 방지하는 데 유용하지만 이러한 구문은 한 스레드가 다른 스레드에 이벤트를 전달할 수 있도록 허용하지 않습니다. 이렇게 하려면 스레드를 활성화하고 일시 중단하는 데 사용할 수 있는 두 상태(신호 알림 및 신호 알림 해제) 중 하나인 *동기화 이벤트* 개체가 필요합니다. 신호 알림이 해제된 동기화 이벤트에서 대기하도록 하여 스레드를 일시 중단하고, 이벤트 상태를 신호 알림으로 변경하여 스레드를 활성화할 수 있습니다. 스레드가 이미 신호 알림을 보낸 이벤트에서 대기하려고 하면 지연 없이 계속 실행됩니다.  
  
 동기화 이벤트에는 <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.ManualResetEvent>의 두 가지 종류가 있습니다. 두 가지 동기화 이벤트는 <xref:System.Threading.AutoResetEvent>가 스레드를 활성화할 때마다 자동으로 신호 알림에서 신호 알림 해제로 변경된다는 점만 다릅니다. 반대로, <xref:System.Threading.ManualResetEvent>는 개수와 관계없이 스레드가 신호 알림 상태에 의해 활성화될 수 있도록 하며, 해당 <xref:System.Threading.EventWaitHandle.Reset%2A> 메서드가 호출될 때만 신호 알림 해제 상태로 돌아갑니다.  
  
 <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, <xref:System.Threading.WaitHandle.WaitAll%2A> 등의 대기 메서드 중 하나를 호출하여 스레드가 이벤트에서 대기하도록 만들 수 있습니다. <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName>을 사용하면 단일 이벤트 신호 알림을 보낼 때까지 스레드가 대기하고, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName>을 사용하면 표시된 하나 이상의 이벤트 신호 알림을 보낼 때까지 스레드가 차단되고, <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName>을 사용하면 표시된 모든 이벤트 신호 알림을 보낼 때까지 스레드가 차단됩니다. 해당 <xref:System.Threading.EventWaitHandle.Set%2A> 메서드가 호출될 때 이벤트 신호를 보냅니다.  
  
 다음 예제에서는 `Main` 함수에 의해 스레드가 생성되고 시작됩니다. 새 스레드는 <xref:System.Threading.WaitHandle.WaitOne%2A> 메서드를 사용하여 이벤트에서 대기합니다. `Main` 함수를 실행하는 기본 스레드에서 이벤트 신호 알림을 보낼 때까지 스레드가 일시 중단됩니다. 이벤트 신호 알림을 보내면 보조 스레드가 반환됩니다. 이 경우 이벤트는 하나의 스레드 활성화에만 사용되므로 <xref:System.Threading.AutoResetEvent> 또는 <xref:System.Threading.ManualResetEvent> 클래스를 사용할 수 있습니다.  
  
```csharp  
using System;  
using System.Threading;  
  
class ThreadingExample  
{  
    static AutoResetEvent autoEvent;  
  
    static void DoWork()  
    {  
        Console.WriteLine("   worker thread started, now waiting on event...");  
        autoEvent.WaitOne();  
        Console.WriteLine("   worker thread reactivated, now exiting...");  
    }  
  
    static void Main()  
    {  
        autoEvent = new AutoResetEvent(false);  
  
        Console.WriteLine("main thread starting worker thread...");  
        Thread t = new Thread(DoWork);  
        t.Start();  
  
        Console.WriteLine("main thread sleeping for 1 second...");  
        Thread.Sleep(1000);  
  
        Console.WriteLine("main thread signaling worker thread...");  
        autoEvent.Set();  
    }  
}  
```  
  
## <a name="mutex-object"></a>뮤텍스 개체  
 *뮤텍스*는 모니터와 유사하며, 한 번에 둘 이상의 스레드가 코드 블록을 동시에 실행할 수 없도록 합니다. 실제로 "뮤텍스"란 이름은 "상호 배타적"이란 용어의 약식 형태입니다. 그러나 모니터와 달리 뮤텍스는 프로세스 간에 스레드를 동기화하는 데 사용할 수 있습니다. 뮤텍스는 <xref:System.Threading.Mutex> 클래스가 나타냅니다.  
  
 프로세스 간 동기화에 사용되는 경우 뮤텍스가 다른 응용 프로그램에서 사용되어 전역 또는 정적 변수를 통해 공유할 수 없기 때문에 *명명 된 뮤텍스*라고 합니다. 두 응용 프로그램이 모두 동일한 뮤텍스 개체에 액세스할 수 있도록 이름이 지정되어야 합니다.  
  
 프로세스 간 스레드 동기화에 뮤텍스를 사용할 수 있지만, 모니터가 .NET Framework용으로 특별히 설계되어 리소스를 더 효율적으로 사용하기 때문에 일반적으로 <xref:System.Threading.Monitor>를 사용하는 것이 좋습니다. 반면, <xref:System.Threading.Mutex> 클래스는 Win32 구문에 대한 래퍼입니다. 모니터보다 더 강력하지만, 뮤텍스는 <xref:System.Threading.Monitor> 클래스에 필요한 것보다 계산 비용이 더 큰 interop 전환이 필요합니다. 뮤텍스 사용 예제는 [뮤텍스](../../../../standard/threading/mutexes.md)를 참조하세요.  
  
## <a name="interlocked-class"></a>Interlocked 클래스  
 <xref:System.Threading.Interlocked> 클래스의 메서드를 사용하여 여러 스레드가 동일한 값을 동시에 업데이트하거나 비교하려고 할 때 발생할 수 있는 문제를 방지할 수 있습니다. 이 클래스의 메서드를 사용하면 모든 스레드의 값을 안전하게 증가, 감소, 교환 및 비교할 수 있습니다.  
  
## <a name="readerwriter-locks"></a>ReaderWriter 잠금  
 경우에 따라 데이터를 쓰고 있을 때만 리소스를 잠그고, 데이터를 업데이트하지 않을 때는 여러 클라이언트가 동시에 데이터를 읽을 수 있도록 허용할 수 있습니다. <xref:System.Threading.ReaderWriterLock> 클래스는 스레드가 리소스를 수정하는 동안에는 리소스에 대한 배타적 액세스를 적용하지만 리소스를 읽을 때는 비배타적 액세스를 허용합니다. ReaderWriter 잠금은 다른 스레드가 데이터를 업데이트할 필요가 없는 경우에도 해당 스레드가 대기하도록 하는 배타적 잠금의 유용한 대안입니다.  
  
## <a name="deadlocks"></a>교착 상태  
 스레드 동기화는 다중 스레드 응용 프로그램에서 중요하지만 항상 여러 스레드가 서로를 대기하여 응용 프로그램이 중단되는 `deadlock`이 발생할 위험이 있습니다. 교착 상태는 자동차가 교차로 일단 정지 지점에서 멈춰 있고 서로 지나가기를 기다리는 상황과 유사합니다. 교착 상태를 방지하는 것이 중요하며, 관건은 신중한 계획입니다. 대체로 코딩을 시작하기 전에 다중 스레드 응용 프로그램의 다이어그램을 작성하면 교착 상태 상황을 예측할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.WaitHandle.WaitOne%2A>   
 <xref:System.Threading.WaitHandle.WaitAny%2A>   
 <xref:System.Threading.WaitHandle.WaitAll%2A>   
 <xref:System.Threading.Thread.Join%2A>   
 <xref:System.Threading.Thread.Start%2A>   
 <xref:System.Threading.Thread.Sleep%2A>   
 <xref:System.Threading.Monitor>   
 <xref:System.Threading.Mutex>   
 <xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Interlocked>   
 <xref:System.Threading.WaitHandle>   
 <xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading>   
 <xref:System.Threading.EventWaitHandle.Set%2A>   
 [다중 스레드 응용 프로그램(C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)   
 [lock 문](../../../../csharp/language-reference/keywords/lock-statement.md)   
 [뮤텍스](../../../../standard/threading/mutexes.md)   
 @System.Threading.Monitor   
 [연동 작업](../../../../standard/threading/interlocked-operations.md)   
 [AutoResetEvent](../../../../standard/threading/autoresetevent.md)   
 [다중 스레딩을 위한 데이터 동기화](../../../../standard/threading/synchronizing-data-for-multithreading.md)
