---
title: "스레드 동기화 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 04f485d1-8333-4510-9e72-c334e7427e7e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ec8fa89c8921eadee428a90971d9ae4ce305a109
ms.lasthandoff: 03/13/2017

---
# <a name="thread-synchronization-visual-basic"></a>스레드 동기화 (Visual Basic)
다음 섹션에서는 기능 및 다중 스레드 응용 프로그램의 리소스에 대 한 액세스를 동기화 하는 데 사용할 수 있는 클래스를 설명 합니다.  
  
 여러 스레드를 사용 하 여 응용 프로그램에서 이점 중 하나는 각 스레드에 비동기적으로 실행 합니다. Windows 응용 프로그램, 이렇게 하면 시간이 많이 걸리는 작업을 응용 프로그램 창의 하는 동안 백그라운드에서 수행 해야 하 고 컨트롤 응답성을 유지 합니다. 서버에 대 한 다중 스레딩 응용 프로그램을 서로 다른 스레드로 들어오는 각 요청을 처리 하는 기능을 제공 합니다. 그렇지 않으면 새로운 각 요청은 하지 처리를 시작할 수는 이전 요청이 완전히 처리 될 때까지 합니다.  
  
 그러나 파일 핸들, 네트워크 연결 및 메모리와 같은 리소스에 액세스 하는 스레드 의미의 비동기 특성 조정 되어야 합니다. 그렇지 않으면 두 개 이상의 스레드가 다른 스레드의 작업의 각 인식 하지 못하는 같은 시간에 같은 리소스에 액세스할 수 있습니다. 결과는 예측할 수 없는 데이터가 손상 되었습니다.  
  
 정수 계열 숫자 데이터 형식에 간단한 작업에 대 한 스레드를 동기화 할 수 <xref:System.Threading.Interlocked>클래스</xref:System.Threading.Interlocked> 의 멤버와 다른 모든 데이터에 대 한 형식 및 다중 스레딩을 스레드로부터 안전 하지 않은 리소스 에서만 안전 하 게 수행할 수 있는 생성을 사용 하 여이 항목의 합니다.  
  
 다중 스레드 프로그래밍에 대 한 배경 정보를 참조 하십시오.  
  
-   [관리 되는 스레딩 기본 사항](http://msdn.microsoft.com/library/b2944911-0e8f-427d-a8bb-077550618935)  
  
-   [스레드 및 스레딩 사용](http://msdn.microsoft.com/library/9b5ec2cd-121b-4d49-b075-222cf26f2344)  
  
-   [관리 되는 스레딩 모범 사례](http://msdn.microsoft.com/library/e51988e7-7f4b-4646-a06d-1416cee8d557)  
  
## <a name="the-lock-and-synclock-keywords"></a>Lock 및 SyncLock 키워드  
 Visual Basic `SyncLock` 다른 스레드에 의해 중단 없이 완료 될 때까지 코드 블록을 실행 하려면 사용할 수 문입니다. 이 코드 블록의 기간에 대 한 지정된 된 개체에 대 한 상호 배타적 잠금을 확보 하 여 수행 됩니다.  
  
 A `SyncLock` 문 개체를 인수로 지정 하며 한 번에 하나의 스레드에 의해 실행 되는 코드 블록 나옵니다. 예:  
  
```vb  
Public Class TestThreading  
    Dim lockThis As New Object  
  
    Public Sub Process()  
        SyncLock lockThis  
            ' Access thread-sensitive resources.  
        End SyncLock  
    End Sub  
End Class  
```  
  
 에 제공 되는 인수는 `SyncLock` 키워드는 참조 형식에 따라 개체 여야 하 고 잠금 범위를 정의 하는 데 사용 됩니다. 위의 예에서 잠금 범위는이 함수로 제한 때문에 개체에 대 한 참조가 없는 `lockThis` 함수 외부에 존재 합니다. 참조 되는 이러한가 존재 하는 경우 해당 개체에 잠금 범위 확장 합니다. 엄격히 말해서, 제공 된 개체는 임의의 클래스 인스턴스가 사용할 수 있도록 여러 스레드 간에 공유 되는 리소스를 고유 하 게 식별 하는 데에 사용 됩니다. 그러나 실제로,이 개체 일반적으로 나타냅니다 스레드 동기화가 필요한 리소스를. 예를 들어 컨테이너 개체를 여러 스레드에서 사용 될 경우 컨테이너를 잠그는로 전달 될 수 및 잠금 뒤에 나오는 동기화 된 코드 블록 컨테이너에 액세스 합니다. 개체에 대 한 액세스가 동기화 안전 하 게 한 다음,에 액세스 하기 전에 다른 스레드가 동일한 잠금으로 포함 합니다.  
  
 잠금을 사용 하지 않는 좋습니다 일반적으로 `public` 유형 또는 응용 프로그램의 제어를 벗어난 개체 인스턴스. 예를 들어 `lockThis` 도 개체에 감당 하기는 코드를 잠글 수 때문에 인스턴스를 공개적으로 액세스할 수 있는 경우에 문제가 될 수 있습니다. 이 교착 상태 상황 동일한 개체의 릴리스에 대 한 두 개 이상의 스레드가 대기 하는 위치를 만들 수 있습니다. 개체 아니라 공용 데이터 형식에 대해 잠금을 이와 같은 이유로 문제가 발생할 수 있습니다. 리터럴 문자열은 때문에 특히 위험는 리터럴 문자열에 잠금 *내부 풀에 추가* 에서 공용 언어 런타임 (CLR). 즉, 전체 프로그램에 대 한 리터럴 지정된 된 문자열의 인스턴스 하나는 정확 하 게 동일한 개체가 나타내는 모든 응용 프로그램 도메인, 모든 스레드에 대해 실행 합니다. 결과적으로, 잠금 내용이 동일한 문자열에 곳에 나 배치 응용 프로그램 프로세스 잠금 응용 프로그램에서 해당 문자열의 모든 인스턴스입니다. 결과적으로 되지 내부 풀에 추가 하는 private 또는 protected 멤버를 잠그는 것이 좋습니다. 일부 클래스는 잠금을 위한 특별 한 멤버를 제공합니다. <xref:System.Array>형식, 예를 들어 <xref:System.Array.SyncRoot%2A>.</xref:System.Array.SyncRoot%2A> 를 제공합니다 합니다.</xref:System.Array> 많은 컬렉션 형식은 제공는 `SyncRoot` 멤버도 있습니다.  
  
 에 대 한 자세한 내용은 `SyncLock` 문을 다음 항목을 참조 합니다.  
  
-   [SyncLock 문](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
  
-   @System.Threading.Monitor  
  
## <a name="monitors"></a>모니터  
 마찬가지로 `SyncLock` 키워드를 모니터 여러 스레드에서 동시에 실행에서 코드 블록을 방지 합니다. <xref:System.Threading.Monitor.Enter%2A>메서드를 사용 하면 하나의 스레드를 다음 문으로 계속 진행 하 고 다른 모든 스레드가 실행 되는 스레드 <xref:System.Threading.Monitor.Exit%2A>.</xref:System.Threading.Monitor.Exit%2A> 를 호출할 때까지 차단 됩니다</xref:System.Threading.Monitor.Enter%2A> 이 사용할 때 처럼는 `SyncLock` 키워드입니다. 예:  
  
```vb  
SyncLock x  
    DoSomething()  
End SyncLock  
```  
  
 이 다음과 같습니다.  
  
```vb  
Dim obj As Object = CType(x, Object)  
System.Threading.Monitor.Enter(obj)  
Try  
    DoSomething()  
Finally  
    System.Threading.Monitor.Exit(obj)  
End Try  
```  
  
 사용 하 여는 `SyncLock` 사용 하 여 키워드는 일반적으로 선호는 <xref:System.Threading.Monitor>클래스를 직접 때문에 `SyncLock` 는 더 간결 하 고 `SyncLock` 보호 되는 코드는 예외를 throw 하는 경우에 기본 모니터 해제 되도록 사용 하면.</xref:System.Threading.Monitor> 이 사용 하 여 수행 되는 `Finally` 예외가 throw 되는 여부에 관계 없이 해당 관련된 코드 블록을 실행 하는 키워드입니다.  
  
## <a name="synchronization-events-and-wait-handles"></a>동기화 이벤트 및 대기 핸들  
 잠금 또는 모니터를 사용 하 여 스레드 관련 코드 블록을 동시에 실행할 방지 하는 데 유용 하지만 이러한 구조를 다른 이벤트를 전달 하는 스레드 하나를 허용 하지 않습니다. 이 위해서는 *동기화 이벤트*, 두 상태 중 하나를 가진 개체는 신호를 받은 및 취소 신호를 사용할 수 있는 활성화 하 고 스레드를 일시 중단 합니다. 스레드는 동기화 되지 않은 이벤트에 신호를 대기 하 여 일시 중단할 수 및 이벤트 상태를 신호를 변경 하 여 활성화 될 수 있습니다. 스레드를 이미 신호를 받는 이벤트를 대기 하려고 하는 경우 지연 없이 실행 하는 스레드가 계속 합니다.  
  
 동기화 이벤트의 두 가지가: <xref:System.Threading.AutoResetEvent>, 및 <xref:System.Threading.ManualResetEvent>.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent> 만 다를 <xref:System.Threading.AutoResetEvent>의 변경 내용을 신호를 보내지 않은 자동으로 때마다 스레드를 활성화 합니다.</xref:System.Threading.AutoResetEvent> 반대로,는 <xref:System.Threading.ManualResetEvent>스레드는 신호를 받은 상태에 의해 활성화 될 수 있으며이 신호를 보내지 않은에 되돌아갑니다 하면 상태로 해당 <xref:System.Threading.EventWaitHandle.Reset%2A>메서드를 호출 합니다.</xref:System.Threading.EventWaitHandle.Reset%2A> </xref:System.Threading.ManualResetEvent>  
  
 스레드 수와 같은 대기 메서드 중 하나를 호출 하 여 이벤트를 대기할 <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, 또는 <xref:System.Threading.WaitHandle.WaitAll%2A>.</xref:System.Threading.WaitHandle.WaitAll%2A> </xref:System.Threading.WaitHandle.WaitAny%2A> </xref:System.Threading.WaitHandle.WaitOne%2A> <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName>단일 이벤트, 신호가 전달 될 때까지 대기 하는 스레드가 <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName>하나 이상의 지정 된 이벤트가, 신호가 전달 될 때까지 스레드를 차단 하 고 <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName>모든 표시 된 이벤트 신호가 전달 될 때까지 스레드를 차단 합니다.</xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> </xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName></xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName> 이벤트에 신호가 전달 하면 해당 <xref:System.Threading.EventWaitHandle.Set%2A>메서드를 호출 합니다.</xref:System.Threading.EventWaitHandle.Set%2A>  
  
 다음 예제에서는에서 스레드를 만들고 시작 하 여는 `Main` 함수입니다. 사용 하 여 이벤트에서 대기 하는 새 스레드는 <xref:System.Threading.WaitHandle.WaitOne%2A>메서드.</xref:System.Threading.WaitHandle.WaitOne%2A> 기본 스레드를 실행 하 여 이벤트에 신호가 전달 될 때까지 스레드가 일시 중단 되는 `Main` 함수입니다. 이벤트 신호를 받는 되 면 보조 스레드에서 반환 합니다. 이 경우 이벤트 사용 되기 때문에 한 스레드가 활성화 중 하나는 <xref:System.Threading.AutoResetEvent>또는 <xref:System.Threading.ManualResetEvent>클래스를 사용할 수 있습니다.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent>  
  
```vb  
Imports System.Threading  
  
Module Module1  
    Dim autoEvent As AutoResetEvent  
  
    Sub DoWork()  
        Console.WriteLine("   worker thread started, now waiting on event...")  
        autoEvent.WaitOne()  
        Console.WriteLine("   worker thread reactivated, now exiting...")  
    End Sub  
  
    Sub Main()  
        autoEvent = New AutoResetEvent(False)  
  
        Console.WriteLine("main thread starting worker thread...")  
        Dim t As New Thread(AddressOf DoWork)  
        t.Start()  
  
        Console.WriteLine("main thread sleeping for 1 second...")  
        Thread.Sleep(1000)  
  
        Console.WriteLine("main thread signaling worker thread...")  
        autoEvent.Set()  
    End Sub  
End Module  
```  
  
## <a name="mutex-object"></a>뮤텍스 개체  
 A *뮤텍스* 모니터; 비슷합니다 한 번에 둘 이상의 스레드가 코드 블록을 동시에 실행할 것입니다. 실제로 뮤텍스"이름"은 "함께 사용할 수 없습니다." 라는 용어의 축약 된 형식 그러나 모니터와 달리 뮤텍스는 데 사용할 수 프로세스 간에 스레드를 동기화 합니다. 뮤텍스 나타내는 <xref:System.Threading.Mutex>클래스가 있습니다.</xref:System.Threading.Mutex>  
  
 프로세스 간 동기화에 사용 하는 경우 뮤텍스 라고는 *명명 된 뮤텍스* 다른 응용 프로그램에서 사용할 수 있기 때문에 따라서 전역 또는 정적 변수를 사용 하 여 공유할 수 없습니다. 이 응용 프로그램을 모두 동일한 mutex 개체에 액세스할 수 있는 이름을 제공 되어야 합니다.  
  
 뮤텍스는 프로세스 내의 스레드 동기화에 사용할 수 있지만 사용 하 여 <xref:System.Threading.Monitor>모니터.NET Framework에 맞게 설계 된 때문에 일반적으로 선호 되 고 따라서 리소스를 더 효율적으로 사용 합니다.</xref:System.Threading.Monitor> 반면에 <xref:System.Threading.Mutex>클래스는 Win32 구문에 대 한 래퍼입니다.</xref:System.Threading.Mutex> 뮤텍스는 <xref:System.Threading.Monitor>클래스</xref:System.Threading.Monitor> 에서 필요한 것 보다 비용이 더 계산 하는 interop 전환이 필요 모니터 보다 더 강력 하지만, 뮤텍스를 사용 하는 예제를 참조 하십시오. [뮤텍스](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)합니다.  
  
## <a name="interlocked-class"></a>Interlocked 클래스  
 메서드를 사용할 수는 <xref:System.Threading.Interlocked>여러 스레드가 동시에 업데이트 하거나 동일한 값을 비교 하려고 하는 경우 발생할 수 있는 문제를 방지 하는 클래스입니다.</xref:System.Threading.Interlocked> 이 클래스의 메서드를 사용 하면 안전 하 게 증가, 감소, 교환, 및 모든 스레드의 값을 비교 합니다.  
  
## <a name="readerwriter-locks"></a>ReaderWriter 잠금  
 경우에 따라 데이터를 기록 하는 경우에 리소스를 잠글 여러 클라이언트가 동시에 데이터를 읽을 때 데이터가 업데이트 되지 않습니다 허용 하는 것이 좋습니다. <xref:System.Threading.ReaderWriterLock>클래스는 리소스를 수정 하는 스레드는 있지만 리소스를 읽을 때-단독 액세스를 허용 하는 동안 리소스에 대 한 단독 액세스를 적용 합니다.</xref:System.Threading.ReaderWriterLock> ReaderWriter 잠금은 단독 잠금 대기도 경우 이러한 스레드 않아도 데이터를 업데이트 하도록 다른 스레드를 대신 사용 하면 유용 합니다.  
  
## <a name="deadlocks"></a>교착 상태  
 스레드 동기화는 다중 스레드 응용 프로그램에 가장 유용 하지만 항상 발생할 위험이 있습니다는 `deadlock`, 여기서 서로 다른 여러 스레드가 대기 하 여 응용 프로그램이 중단 됩니다. 교착 상태는 자동차에서&4; 방향 중지를 중지 하 고 각자 다른 자동차가 기다리고 상황이 같습니다. 교착 상태 방지 하는 것이 중요 합니다. 키는 신중 하 게 계획 합니다. 다중 스레드 응용 프로그램 코딩을 시작 하기 전에 다이어그램을 작성 하면 교착 상태 상황을 자주 예측할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread></xref:System.Threading.Thread>   
 <xref:System.Threading.WaitHandle.WaitOne%2A></xref:System.Threading.WaitHandle.WaitOne%2A>   
 <xref:System.Threading.WaitHandle.WaitAny%2A></xref:System.Threading.WaitHandle.WaitAny%2A>   
 <xref:System.Threading.WaitHandle.WaitAll%2A></xref:System.Threading.WaitHandle.WaitAll%2A>   
 <xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A>   
 <xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A>   
 <xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A>   
 <xref:System.Threading.Monitor></xref:System.Threading.Monitor>   
 <xref:System.Threading.Mutex></xref:System.Threading.Mutex>   
 <xref:System.Threading.AutoResetEvent></xref:System.Threading.AutoResetEvent>   
 <xref:System.Threading.ManualResetEvent></xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.Interlocked></xref:System.Threading.Interlocked>   
 <xref:System.Threading.WaitHandle></xref:System.Threading.WaitHandle>   
 <xref:System.Threading.EventWaitHandle></xref:System.Threading.EventWaitHandle>   
 <xref:System.Threading></xref:System.Threading>   
 <xref:System.Threading.EventWaitHandle.Set%2A></xref:System.Threading.EventWaitHandle.Set%2A>   
 [다중 스레드 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)   
 [SyncLock 문](../../../../visual-basic/language-reference/statements/synclock-statement.md)   
 [뮤텍스](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)   
 @System.Threading.Monitor   
 [연동된 작업](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b)   
 [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18)   
 [에 대 한 데이터를 동기화 할 다중 스레딩](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)
