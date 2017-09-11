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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 240937905254120f777ce140049084279c35005c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="thread-synchronization-visual-basic"></a><span data-ttu-id="97077-102">스레드 동기화 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97077-102">Thread Synchronization (Visual Basic)</span></span>
<span data-ttu-id="97077-103">다음 섹션에서는 기능 및 다중 스레드 응용 프로그램의 리소스에 대 한 액세스를 동기화 하는 데 사용할 수 있는 클래스를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-103">The following sections describe features and classes that can be used to synchronize access to resources in multithreaded applications.</span></span>  
  
 <span data-ttu-id="97077-104">여러 스레드를 사용 하 여 응용 프로그램에서 이점 중 하나는 각 스레드에 비동기적으로 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-104">One of the benefits of using multiple threads in an application is that each thread executes asynchronously.</span></span> <span data-ttu-id="97077-105">Windows 응용 프로그램, 이렇게 하면 시간이 많이 걸리는 작업을 응용 프로그램 창의 하는 동안 백그라운드에서 수행 해야 하 고 컨트롤 응답성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-105">For Windows applications, this allows time-consuming tasks to be performed in the background while the application window and controls remain responsive.</span></span> <span data-ttu-id="97077-106">서버에 대 한 다중 스레딩 응용 프로그램을 서로 다른 스레드로 들어오는 각 요청을 처리 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-106">For server applications, multithreading provides the ability to handle each incoming request with a different thread.</span></span> <span data-ttu-id="97077-107">그렇지 않으면 새로운 각 요청은 하지 처리를 시작할 수는 이전 요청이 완전히 처리 될 때까지 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-107">Otherwise, each new request would not get serviced until the previous request had been fully satisfied.</span></span>  
  
 <span data-ttu-id="97077-108">그러나 파일 핸들, 네트워크 연결 및 메모리와 같은 리소스에 액세스 하는 스레드 의미의 비동기 특성 조정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-108">However, the asynchronous nature of threads means that access to resources such as file handles, network connections, and memory must be coordinated.</span></span> <span data-ttu-id="97077-109">그렇지 않으면 두 개 이상의 스레드가 다른 스레드의 작업의 각 인식 하지 못하는 같은 시간에 같은 리소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-109">Otherwise, two or more threads could access the same resource at the same time, each unaware of the other's actions.</span></span> <span data-ttu-id="97077-110">결과는 예측할 수 없는 데이터가 손상 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-110">The result is unpredictable data corruption.</span></span>  
  
 <span data-ttu-id="97077-111">정수 계열 숫자 데이터 형식에 간단한 작업에 대 한 스레드를 동기화 할 수 <xref:System.Threading.Interlocked>클래스</xref:System.Threading.Interlocked> 의 멤버와</span><span class="sxs-lookup"><span data-stu-id="97077-111">For simple operations on integral numeric data types, synchronizing threads can be accomplished with members of the <xref:System.Threading.Interlocked> class.</span></span> <span data-ttu-id="97077-112">다른 모든 데이터에 대 한 형식 및 다중 스레딩을 스레드로부터 안전 하지 않은 리소스 에서만 안전 하 게 수행할 수 있는 생성을 사용 하 여이 항목의 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-112">For all other data types and non thread-safe resources, multithreading can only be safely performed using the constructs in this topic.</span></span>  
  
 <span data-ttu-id="97077-113">다중 스레드 프로그래밍에 대 한 배경 정보를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="97077-113">For background information on multithreaded programming, see:</span></span>  
  
-   [<span data-ttu-id="97077-114">관리 되는 스레딩 기본 사항</span><span class="sxs-lookup"><span data-stu-id="97077-114">Managed Threading Basics</span></span>](http://msdn.microsoft.com/library/b2944911-0e8f-427d-a8bb-077550618935)  
  
-   [<span data-ttu-id="97077-115">스레드 및 스레딩 사용</span><span class="sxs-lookup"><span data-stu-id="97077-115">Using Threads and Threading</span></span>](http://msdn.microsoft.com/library/9b5ec2cd-121b-4d49-b075-222cf26f2344)  
  
-   [<span data-ttu-id="97077-116">관리 되는 스레딩 모범 사례</span><span class="sxs-lookup"><span data-stu-id="97077-116">Managed Threading Best Practices</span></span>](http://msdn.microsoft.com/library/e51988e7-7f4b-4646-a06d-1416cee8d557)  
  
## <a name="the-lock-and-synclock-keywords"></a><span data-ttu-id="97077-117">Lock 및 SyncLock 키워드</span><span class="sxs-lookup"><span data-stu-id="97077-117">The lock and SyncLock Keywords</span></span>  
 <span data-ttu-id="97077-118">Visual Basic `SyncLock` 다른 스레드에 의해 중단 없이 완료 될 때까지 코드 블록을 실행 하려면 사용할 수 문입니다.</span><span class="sxs-lookup"><span data-stu-id="97077-118">The Visual Basic `SyncLock` statement can be used to ensure that a block of code runs to completion without interruption by other threads.</span></span> <span data-ttu-id="97077-119">이 코드 블록의 기간에 대 한 지정된 된 개체에 대 한 상호 배타적 잠금을 확보 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97077-119">This is accomplished by obtaining a mutual-exclusion lock for a given object for the duration of the code block.</span></span>  
  
 <span data-ttu-id="97077-120">A `SyncLock` 문 개체를 인수로 지정 하며 한 번에 하나의 스레드에 의해 실행 되는 코드 블록 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="97077-120">A `SyncLock` statement is given an object as an argument, and is followed by a code block that is to be executed by only one thread at a time.</span></span> <span data-ttu-id="97077-121">예:</span><span class="sxs-lookup"><span data-stu-id="97077-121">For example:</span></span>  
  
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
  
 <span data-ttu-id="97077-122">에 제공 되는 인수는 `SyncLock` 키워드는 참조 형식에 따라 개체 여야 하 고 잠금 범위를 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97077-122">The argument provided to the `SyncLock` keyword must be an object based on a reference type, and is used to define the scope of the lock.</span></span> <span data-ttu-id="97077-123">위의 예에서 잠금 범위는이 함수로 제한 때문에 개체에 대 한 참조가 없는 `lockThis` 함수 외부에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-123">In the example above, the lock scope is limited to this function because no references to the object `lockThis` exist outside the function.</span></span> <span data-ttu-id="97077-124">참조 되는 이러한가 존재 하는 경우 해당 개체에 잠금 범위 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-124">If such a reference did exist, lock scope would extend to that object.</span></span> <span data-ttu-id="97077-125">엄격히 말해서, 제공 된 개체는 임의의 클래스 인스턴스가 사용할 수 있도록 여러 스레드 간에 공유 되는 리소스를 고유 하 게 식별 하는 데에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97077-125">Strictly speaking, the object provided is used solely to uniquely identify the resource being shared among multiple threads, so it can be an arbitrary class instance.</span></span> <span data-ttu-id="97077-126">그러나 실제로,이 개체 일반적으로 나타냅니다 스레드 동기화가 필요한 리소스를.</span><span class="sxs-lookup"><span data-stu-id="97077-126">In practice, however, this object usually represents the resource for which thread synchronization is necessary.</span></span> <span data-ttu-id="97077-127">예를 들어 컨테이너 개체를 여러 스레드에서 사용 될 경우 컨테이너를 잠그는로 전달 될 수 및 잠금 뒤에 나오는 동기화 된 코드 블록 컨테이너에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-127">For example, if a container object is to be used by multiple threads, then the container can be passed to lock, and the synchronized code block following the lock would access the container.</span></span> <span data-ttu-id="97077-128">개체에 대 한 액세스가 동기화 안전 하 게 한 다음,에 액세스 하기 전에 다른 스레드가 동일한 잠금으로 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-128">As long as other threads locks on the same contain before accessing it, then access to the object is safely synchronized.</span></span>  
  
 <span data-ttu-id="97077-129">잠금을 사용 하지 않는 좋습니다 일반적으로 `public` 유형 또는 응용 프로그램의 제어를 벗어난 개체 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="97077-129">Generally, it is best to avoid locking on a `public` type, or on object instances beyond the control of your application.</span></span> <span data-ttu-id="97077-130">예를 들어 `lockThis` 도 개체에 감당 하기는 코드를 잠글 수 때문에 인스턴스를 공개적으로 액세스할 수 있는 경우에 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-130">For example, `lockThis` can be problematic if the instance can be accessed publicly, because code beyond your control may lock on the object as well.</span></span> <span data-ttu-id="97077-131">이 교착 상태 상황 동일한 개체의 릴리스에 대 한 두 개 이상의 스레드가 대기 하는 위치를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-131">This could create deadlock situations where two or more threads wait for the release of the same object.</span></span> <span data-ttu-id="97077-132">개체 아니라 공용 데이터 형식에 대해 잠금을 이와 같은 이유로 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-132">Locking on a public data type, as opposed to an object, can cause problems for the same reason.</span></span> <span data-ttu-id="97077-133">리터럴 문자열은 때문에 특히 위험는 리터럴 문자열에 잠금 *내부 풀에 추가* 에서 공용 언어 런타임 (CLR).</span><span class="sxs-lookup"><span data-stu-id="97077-133">Locking on literal strings is especially risky because literal strings are *interned* by the common language runtime (CLR).</span></span> <span data-ttu-id="97077-134">즉, 전체 프로그램에 대 한 리터럴 지정된 된 문자열의 인스턴스 하나는 정확 하 게 동일한 개체가 나타내는 모든 응용 프로그램 도메인, 모든 스레드에 대해 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-134">This means that there is one instance of any given string literal for the entire program, the exact same object represents the literal in all running application domains, on all threads.</span></span> <span data-ttu-id="97077-135">결과적으로, 잠금 내용이 동일한 문자열에 곳에 나 배치 응용 프로그램 프로세스 잠금 응용 프로그램에서 해당 문자열의 모든 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="97077-135">As a result, a lock placed on a string with the same contents anywhere in the application process locks all instances of that string in the application.</span></span> <span data-ttu-id="97077-136">결과적으로 되지 내부 풀에 추가 하는 private 또는 protected 멤버를 잠그는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-136">As a result, it is best to lock a private or protected member that is not interned.</span></span> <span data-ttu-id="97077-137">일부 클래스는 잠금을 위한 특별 한 멤버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-137">Some classes provide members specifically for locking.</span></span> <span data-ttu-id="97077-138"><xref:System.Array>형식, 예를 들어 <xref:System.Array.SyncRoot%2A>.</xref:System.Array.SyncRoot%2A> 를 제공합니다 합니다.</xref:System.Array></span><span class="sxs-lookup"><span data-stu-id="97077-138">The <xref:System.Array> type, for example, provides <xref:System.Array.SyncRoot%2A>.</span></span> <span data-ttu-id="97077-139">많은 컬렉션 형식은 제공는 `SyncRoot` 멤버도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-139">Many collection types provide a `SyncRoot` member as well.</span></span>  
  
 <span data-ttu-id="97077-140">에 대 한 자세한 내용은 `SyncLock` 문을 다음 항목을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-140">For more information about the `SyncLock` statement, see the following topics:</span></span>  
  
-   [<span data-ttu-id="97077-141">SyncLock 문</span><span class="sxs-lookup"><span data-stu-id="97077-141">SyncLock Statement</span></span>](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
  
-   @System.Threading.Monitor  
  
## <a name="monitors"></a><span data-ttu-id="97077-142">모니터</span><span class="sxs-lookup"><span data-stu-id="97077-142">Monitors</span></span>  
 <span data-ttu-id="97077-143">마찬가지로 `SyncLock` 키워드를 모니터 여러 스레드에서 동시에 실행에서 코드 블록을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-143">Like the `SyncLock` keyword, monitors prevent blocks of code from simultaneous execution by multiple threads.</span></span> <span data-ttu-id="97077-144"><xref:System.Threading.Monitor.Enter%2A>메서드를 사용 하면 하나의 스레드를 다음 문으로 계속 진행 하 고 다른 모든 스레드가 실행 되는 스레드 <xref:System.Threading.Monitor.Exit%2A>.</xref:System.Threading.Monitor.Exit%2A> 를 호출할 때까지 차단 됩니다</xref:System.Threading.Monitor.Enter%2A></span><span class="sxs-lookup"><span data-stu-id="97077-144">The <xref:System.Threading.Monitor.Enter%2A> method allows one and only one thread to proceed into the following statements; all other threads are blocked until the executing thread calls <xref:System.Threading.Monitor.Exit%2A>.</span></span> <span data-ttu-id="97077-145">이 사용할 때 처럼는 `SyncLock` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="97077-145">This is just like using the `SyncLock` keyword.</span></span> <span data-ttu-id="97077-146">예:</span><span class="sxs-lookup"><span data-stu-id="97077-146">For example:</span></span>  
  
```vb  
SyncLock x  
    DoSomething()  
End SyncLock  
```  
  
 <span data-ttu-id="97077-147">이 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-147">This is equivalent to:</span></span>  
  
```vb  
Dim obj As Object = CType(x, Object)  
System.Threading.Monitor.Enter(obj)  
Try  
    DoSomething()  
Finally  
    System.Threading.Monitor.Exit(obj)  
End Try  
```  
  
 <span data-ttu-id="97077-148">사용 하 여는 `SyncLock` 사용 하 여 키워드는 일반적으로 선호는 <xref:System.Threading.Monitor>클래스를 직접 때문에 `SyncLock` 는 더 간결 하 고 `SyncLock` 보호 되는 코드는 예외를 throw 하는 경우에 기본 모니터 해제 되도록 사용 하면.</xref:System.Threading.Monitor></span><span class="sxs-lookup"><span data-stu-id="97077-148">Using the `SyncLock` keyword is generally preferred over using the <xref:System.Threading.Monitor> class directly, both because `SyncLock` is more concise, and because `SyncLock` insures that the underlying monitor is released, even if the protected code throws an exception.</span></span> <span data-ttu-id="97077-149">이 사용 하 여 수행 되는 `Finally` 예외가 throw 되는 여부에 관계 없이 해당 관련된 코드 블록을 실행 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="97077-149">This is accomplished with the `Finally` keyword, which executes its associated code block regardless of whether an exception is thrown.</span></span>  
  
## <a name="synchronization-events-and-wait-handles"></a><span data-ttu-id="97077-150">동기화 이벤트 및 대기 핸들</span><span class="sxs-lookup"><span data-stu-id="97077-150">Synchronization Events and Wait Handles</span></span>  
 <span data-ttu-id="97077-151">잠금 또는 모니터를 사용 하 여 스레드 관련 코드 블록을 동시에 실행할 방지 하는 데 유용 하지만 이러한 구조를 다른 이벤트를 전달 하는 스레드 하나를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-151">Using a lock or monitor is useful for preventing the simultaneous execution of thread-sensitive blocks of code, but these constructs do not allow one thread to communicate an event to another.</span></span> <span data-ttu-id="97077-152">이 위해서는 *동기화 이벤트*, 두 상태 중 하나를 가진 개체는 신호를 받은 및 취소 신호를 사용할 수 있는 활성화 하 고 스레드를 일시 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-152">This requires *synchronization events*, which are objects that have one of two states, signaled and un-signaled, that can be used to activate and suspend threads.</span></span> <span data-ttu-id="97077-153">스레드는 동기화 되지 않은 이벤트에 신호를 대기 하 여 일시 중단할 수 및 이벤트 상태를 신호를 변경 하 여 활성화 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-153">Threads can be suspended by being made to wait on a synchronization event that is unsignaled, and can be activated by changing the event state to signaled.</span></span> <span data-ttu-id="97077-154">스레드를 이미 신호를 받는 이벤트를 대기 하려고 하는 경우 지연 없이 실행 하는 스레드가 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-154">If a thread attempts to wait on an event that is already signaled, then the thread continues to execute without delay.</span></span>  
  
 <span data-ttu-id="97077-155">동기화 이벤트의 두 가지가: <xref:System.Threading.AutoResetEvent>, 및 <xref:System.Threading.ManualResetEvent>.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent></span><span class="sxs-lookup"><span data-stu-id="97077-155">There are two kinds of synchronization events: <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.ManualResetEvent>.</span></span> <span data-ttu-id="97077-156">만 다를 <xref:System.Threading.AutoResetEvent>의 변경 내용을 신호를 보내지 않은 자동으로 때마다 스레드를 활성화 합니다.</xref:System.Threading.AutoResetEvent></span><span class="sxs-lookup"><span data-stu-id="97077-156">They differ only in that <xref:System.Threading.AutoResetEvent> changes from signaled to unsignaled automatically any time it activates a thread.</span></span> <span data-ttu-id="97077-157">반대로,는 <xref:System.Threading.ManualResetEvent>스레드는 신호를 받은 상태에 의해 활성화 될 수 있으며이 신호를 보내지 않은에 되돌아갑니다 하면 상태로 해당 <xref:System.Threading.EventWaitHandle.Reset%2A>메서드를 호출 합니다.</xref:System.Threading.EventWaitHandle.Reset%2A> </xref:System.Threading.ManualResetEvent></span><span class="sxs-lookup"><span data-stu-id="97077-157">Conversely, a <xref:System.Threading.ManualResetEvent> allows any number of threads to be activated by its signaled state, and will only revert to an unsignaled state when its <xref:System.Threading.EventWaitHandle.Reset%2A> method is called.</span></span>  
  
 <span data-ttu-id="97077-158">스레드 수와 같은 대기 메서드 중 하나를 호출 하 여 이벤트를 대기할 <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, 또는 <xref:System.Threading.WaitHandle.WaitAll%2A>.</xref:System.Threading.WaitHandle.WaitAll%2A> </xref:System.Threading.WaitHandle.WaitAny%2A> </xref:System.Threading.WaitHandle.WaitOne%2A></span><span class="sxs-lookup"><span data-stu-id="97077-158">Threads can be made to wait on events by calling one of the wait methods, such as <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, or <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span> <span data-ttu-id="97077-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName>단일 이벤트, 신호가 전달 될 때까지 대기 하는 스레드가 <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName>하나 이상의 지정 된 이벤트가, 신호가 전달 될 때까지 스레드를 차단 하 고 <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName>모든 표시 된 이벤트 신호가 전달 될 때까지 스레드를 차단 합니다.</xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> </xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName></xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="97077-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=fullName> causes the thread to wait until a single event becomes signaled, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=fullName> blocks a thread until one or more indicated events become signaled, and <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=fullName> blocks the thread until all of the indicated events become signaled.</span></span> <span data-ttu-id="97077-160">이벤트에 신호가 전달 하면 해당 <xref:System.Threading.EventWaitHandle.Set%2A>메서드를 호출 합니다.</xref:System.Threading.EventWaitHandle.Set%2A></span><span class="sxs-lookup"><span data-stu-id="97077-160">An event becomes signaled when its <xref:System.Threading.EventWaitHandle.Set%2A> method is called.</span></span>  
  
 <span data-ttu-id="97077-161">다음 예제에서는에서 스레드를 만들고 시작 하 여는 `Main` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="97077-161">In the following example, a thread is created and started by the `Main` function.</span></span> <span data-ttu-id="97077-162">사용 하 여 이벤트에서 대기 하는 새 스레드는 <xref:System.Threading.WaitHandle.WaitOne%2A>메서드.</xref:System.Threading.WaitHandle.WaitOne%2A></span><span class="sxs-lookup"><span data-stu-id="97077-162">The new thread waits on an event using the <xref:System.Threading.WaitHandle.WaitOne%2A> method.</span></span> <span data-ttu-id="97077-163">기본 스레드를 실행 하 여 이벤트에 신호가 전달 될 때까지 스레드가 일시 중단 되는 `Main` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="97077-163">The thread is suspended until the event becomes signaled by the primary thread that is executing the `Main` function.</span></span> <span data-ttu-id="97077-164">이벤트 신호를 받는 되 면 보조 스레드에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-164">Once the event becomes signaled, the auxiliary thread returns.</span></span> <span data-ttu-id="97077-165">이 경우 이벤트 사용 되기 때문에 한 스레드가 활성화 중 하나는 <xref:System.Threading.AutoResetEvent>또는 <xref:System.Threading.ManualResetEvent>클래스를 사용할 수 있습니다.</xref:System.Threading.ManualResetEvent> </xref:System.Threading.AutoResetEvent></span><span class="sxs-lookup"><span data-stu-id="97077-165">In this case, because the event is only used for one thread activation, either the <xref:System.Threading.AutoResetEvent> or <xref:System.Threading.ManualResetEvent> classes could be used.</span></span>  
  
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
  
## <a name="mutex-object"></a><span data-ttu-id="97077-166">뮤텍스 개체</span><span class="sxs-lookup"><span data-stu-id="97077-166">Mutex Object</span></span>  
 <span data-ttu-id="97077-167">A *뮤텍스* 모니터; 비슷합니다 한 번에 둘 이상의 스레드가 코드 블록을 동시에 실행할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97077-167">A *mutex* is similar to a monitor; it prevents the simultaneous execution of a block of code by more than one thread at a time.</span></span> <span data-ttu-id="97077-168">실제로 뮤텍스"이름"은 "함께 사용할 수 없습니다." 라는 용어의 축약 된 형식</span><span class="sxs-lookup"><span data-stu-id="97077-168">In fact, the name "mutex" is a shortened form of the term "mutually exclusive."</span></span> <span data-ttu-id="97077-169">그러나 모니터와 달리 뮤텍스는 데 사용할 수 프로세스 간에 스레드를 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-169">Unlike monitors, however, a mutex can be used to synchronize threads across processes.</span></span> <span data-ttu-id="97077-170">뮤텍스 나타내는 <xref:System.Threading.Mutex>클래스가 있습니다.</xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="97077-170">A mutex is represented by the <xref:System.Threading.Mutex> class.</span></span>  
  
 <span data-ttu-id="97077-171">프로세스 간 동기화에 사용 하는 경우 뮤텍스 라고는 *명명 된 뮤텍스* 다른 응용 프로그램에서 사용할 수 있기 때문에 따라서 전역 또는 정적 변수를 사용 하 여 공유할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-171">When used for inter-process synchronization, a mutex is called a *named mutex* because it is to be used in another application, and therefore it cannot be shared by means of a global or static variable.</span></span> <span data-ttu-id="97077-172">이 응용 프로그램을 모두 동일한 mutex 개체에 액세스할 수 있는 이름을 제공 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-172">It must be given a name so that both applications can access the same mutex object.</span></span>  
  
 <span data-ttu-id="97077-173">뮤텍스는 프로세스 내의 스레드 동기화에 사용할 수 있지만 사용 하 여 <xref:System.Threading.Monitor>모니터.NET Framework에 맞게 설계 된 때문에 일반적으로 선호 되 고 따라서 리소스를 더 효율적으로 사용 합니다.</xref:System.Threading.Monitor></span><span class="sxs-lookup"><span data-stu-id="97077-173">Although a mutex can be used for intra-process thread synchronization, using <xref:System.Threading.Monitor> is generally preferred, because monitors were designed specifically for the .NET Framework and therefore make better use of resources.</span></span> <span data-ttu-id="97077-174">반면에 <xref:System.Threading.Mutex>클래스는 Win32 구문에 대 한 래퍼입니다.</xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="97077-174">In contrast, the <xref:System.Threading.Mutex> class is a wrapper to a Win32 construct.</span></span> <span data-ttu-id="97077-175">뮤텍스는 <xref:System.Threading.Monitor>클래스</xref:System.Threading.Monitor> 에서 필요한 것 보다 비용이 더 계산 하는 interop 전환이 필요 모니터 보다 더 강력 하지만,</span><span class="sxs-lookup"><span data-stu-id="97077-175">While it is more powerful than a monitor, a mutex requires interop transitions that are more computationally expensive than those required by the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="97077-176">뮤텍스를 사용 하는 예제를 참조 하십시오. [뮤텍스](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2)합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-176">For an example of using a mutex, see [Mutexes](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2).</span></span>  
  
## <a name="interlocked-class"></a><span data-ttu-id="97077-177">Interlocked 클래스</span><span class="sxs-lookup"><span data-stu-id="97077-177">Interlocked Class</span></span>  
 <span data-ttu-id="97077-178">메서드를 사용할 수는 <xref:System.Threading.Interlocked>여러 스레드가 동시에 업데이트 하거나 동일한 값을 비교 하려고 하는 경우 발생할 수 있는 문제를 방지 하는 클래스입니다.</xref:System.Threading.Interlocked></span><span class="sxs-lookup"><span data-stu-id="97077-178">You can use the methods of the <xref:System.Threading.Interlocked> class to prevent problems that can occur when multiple threads attempt to simultaneously update or compare the same value.</span></span> <span data-ttu-id="97077-179">이 클래스의 메서드를 사용 하면 안전 하 게 증가, 감소, 교환, 및 모든 스레드의 값을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-179">The methods of this class let you safely increment, decrement, exchange, and compare values from any thread.</span></span>  
  
## <a name="readerwriter-locks"></a><span data-ttu-id="97077-180">ReaderWriter 잠금</span><span class="sxs-lookup"><span data-stu-id="97077-180">ReaderWriter Locks</span></span>  
 <span data-ttu-id="97077-181">경우에 따라 데이터를 기록 하는 경우에 리소스를 잠글 여러 클라이언트가 동시에 데이터를 읽을 때 데이터가 업데이트 되지 않습니다 허용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-181">In some cases, you may want to lock a resource only when data is being written and permit multiple clients to simultaneously read data when data is not being updated.</span></span> <span data-ttu-id="97077-182"><xref:System.Threading.ReaderWriterLock>클래스는 리소스를 수정 하는 스레드는 있지만 리소스를 읽을 때-단독 액세스를 허용 하는 동안 리소스에 대 한 단독 액세스를 적용 합니다.</xref:System.Threading.ReaderWriterLock></span><span class="sxs-lookup"><span data-stu-id="97077-182">The <xref:System.Threading.ReaderWriterLock> class enforces exclusive access to a resource while a thread is modifying the resource, but it allows non-exclusive access when reading the resource.</span></span> <span data-ttu-id="97077-183">ReaderWriter 잠금은 단독 잠금 대기도 경우 이러한 스레드 않아도 데이터를 업데이트 하도록 다른 스레드를 대신 사용 하면 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-183">ReaderWriter locks are a useful alternative to exclusive locks, which cause other threads to wait, even when those threads do not need to update data.</span></span>  
  
## <a name="deadlocks"></a><span data-ttu-id="97077-184">교착 상태</span><span class="sxs-lookup"><span data-stu-id="97077-184">Deadlocks</span></span>  
 <span data-ttu-id="97077-185">스레드 동기화는 다중 스레드 응용 프로그램에 가장 유용 하지만 항상 발생할 위험이 있습니다는 `deadlock`, 여기서 서로 다른 여러 스레드가 대기 하 여 응용 프로그램이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97077-185">Thread synchronization is invaluable in multithreaded applications, but there is always the danger of creating a `deadlock`, where multiple threads are waiting for each other and the application comes to a halt.</span></span> <span data-ttu-id="97077-186">교착 상태는 자동차에서&4; 방향 중지를 중지 하 고 각자 다른 자동차가 기다리고 상황이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-186">A deadlock is analogous to a situation in which cars are stopped at a four-way stop and each person is waiting for the other to go.</span></span> <span data-ttu-id="97077-187">교착 상태 방지 하는 것이 중요 합니다. 키는 신중 하 게 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="97077-187">Avoiding deadlocks is important; the key is careful planning.</span></span> <span data-ttu-id="97077-188">다중 스레드 응용 프로그램 코딩을 시작 하기 전에 다이어그램을 작성 하면 교착 상태 상황을 자주 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97077-188">You can often predict deadlock situations by diagramming multithreaded applications before you start coding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97077-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97077-189">See Also</span></span>  
 <span data-ttu-id="97077-190"><xref:System.Threading.Thread></xref:System.Threading.Thread></span><span class="sxs-lookup"><span data-stu-id="97077-190"><xref:System.Threading.Thread></span></span>   
 <span data-ttu-id="97077-191"><xref:System.Threading.WaitHandle.WaitOne%2A></xref:System.Threading.WaitHandle.WaitOne%2A></span><span class="sxs-lookup"><span data-stu-id="97077-191"><xref:System.Threading.WaitHandle.WaitOne%2A></span></span>   
 <span data-ttu-id="97077-192"><xref:System.Threading.WaitHandle.WaitAny%2A></xref:System.Threading.WaitHandle.WaitAny%2A></span><span class="sxs-lookup"><span data-stu-id="97077-192"><xref:System.Threading.WaitHandle.WaitAny%2A></span></span>   
 <span data-ttu-id="97077-193"><xref:System.Threading.WaitHandle.WaitAll%2A></xref:System.Threading.WaitHandle.WaitAll%2A></span><span class="sxs-lookup"><span data-stu-id="97077-193"><xref:System.Threading.WaitHandle.WaitAll%2A></span></span>   
 <span data-ttu-id="97077-194"><xref:System.Threading.Thread.Join%2A></xref:System.Threading.Thread.Join%2A></span><span class="sxs-lookup"><span data-stu-id="97077-194"><xref:System.Threading.Thread.Join%2A></span></span>   
 <span data-ttu-id="97077-195"><xref:System.Threading.Thread.Start%2A></xref:System.Threading.Thread.Start%2A></span><span class="sxs-lookup"><span data-stu-id="97077-195"><xref:System.Threading.Thread.Start%2A></span></span>   
 <span data-ttu-id="97077-196"><xref:System.Threading.Thread.Sleep%2A></xref:System.Threading.Thread.Sleep%2A></span><span class="sxs-lookup"><span data-stu-id="97077-196"><xref:System.Threading.Thread.Sleep%2A></span></span>   
 <span data-ttu-id="97077-197"><xref:System.Threading.Monitor></xref:System.Threading.Monitor></span><span class="sxs-lookup"><span data-stu-id="97077-197"><xref:System.Threading.Monitor></span></span>   
 <span data-ttu-id="97077-198"><xref:System.Threading.Mutex></xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="97077-198"><xref:System.Threading.Mutex></span></span>   
 <span data-ttu-id="97077-199"><xref:System.Threading.AutoResetEvent></xref:System.Threading.AutoResetEvent></span><span class="sxs-lookup"><span data-stu-id="97077-199"><xref:System.Threading.AutoResetEvent></span></span>   
 <span data-ttu-id="97077-200"><xref:System.Threading.ManualResetEvent></xref:System.Threading.ManualResetEvent></span><span class="sxs-lookup"><span data-stu-id="97077-200"><xref:System.Threading.ManualResetEvent></span></span>   
 <span data-ttu-id="97077-201"><xref:System.Threading.Interlocked></xref:System.Threading.Interlocked></span><span class="sxs-lookup"><span data-stu-id="97077-201"><xref:System.Threading.Interlocked></span></span>   
 <span data-ttu-id="97077-202"><xref:System.Threading.WaitHandle></xref:System.Threading.WaitHandle></span><span class="sxs-lookup"><span data-stu-id="97077-202"><xref:System.Threading.WaitHandle></span></span>   
 <span data-ttu-id="97077-203"><xref:System.Threading.EventWaitHandle></xref:System.Threading.EventWaitHandle></span><span class="sxs-lookup"><span data-stu-id="97077-203"><xref:System.Threading.EventWaitHandle></span></span>   
 <span data-ttu-id="97077-204"><xref:System.Threading></xref:System.Threading></span><span class="sxs-lookup"><span data-stu-id="97077-204"><xref:System.Threading></span></span>   
 <span data-ttu-id="97077-205"><xref:System.Threading.EventWaitHandle.Set%2A></xref:System.Threading.EventWaitHandle.Set%2A></span><span class="sxs-lookup"><span data-stu-id="97077-205"><xref:System.Threading.EventWaitHandle.Set%2A></span></span>   
<span data-ttu-id="97077-206"> [다중 스레드 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="97077-206"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="97077-207"> [SyncLock 문](../../../../visual-basic/language-reference/statements/synclock-statement.md) </span><span class="sxs-lookup"><span data-stu-id="97077-207"> [SyncLock Statement](../../../../visual-basic/language-reference/statements/synclock-statement.md) </span></span>  
<span data-ttu-id="97077-208"> [뮤텍스](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2) </span><span class="sxs-lookup"><span data-stu-id="97077-208"> [Mutexes](http://msdn.microsoft.com/library/9dd06e25-12c0-4a9e-855a-452dc83803e2) </span></span>  
 @System.Threading.Monitor   
<span data-ttu-id="97077-209"> [연동된 작업](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b) </span><span class="sxs-lookup"><span data-stu-id="97077-209"> [Interlocked Operations](http://msdn.microsoft.com/library/cbda7114-c752-4f3e-ada1-b1e8dd262f2b) </span></span>  
<span data-ttu-id="97077-210"> [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18) </span><span class="sxs-lookup"><span data-stu-id="97077-210"> [AutoResetEvent](http://msdn.microsoft.com/library/6d39c48d-6b37-4a9b-8631-f2924cfd9c18) </span></span>  
<span data-ttu-id="97077-211"> [에 대 한 데이터를 동기화 할 다중 스레딩](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)</span><span class="sxs-lookup"><span data-stu-id="97077-211"> [Synchronizing Data for Multithreading](http://msdn.microsoft.com/library/b980eb4c-71d5-4860-864a-6dfe3692430a)</span></span>
