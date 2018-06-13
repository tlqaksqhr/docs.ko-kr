---
title: 스레드 동기화 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 04f485d1-8333-4510-9e72-c334e7427e7e
ms.openlocfilehash: 9922230e1c7f2bd30c575bd66387feb4850a298b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655093"
---
# <a name="thread-synchronization-visual-basic"></a><span data-ttu-id="31b7e-102">스레드 동기화 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31b7e-102">Thread Synchronization (Visual Basic)</span></span>
<span data-ttu-id="31b7e-103">다음 섹션에서는 다중 스레드 응용 프로그램에서 리소스에 대한 액세스를 동기화 하는 데 사용할 수 있는 기능 및 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-103">The following sections describe features and classes that can be used to synchronize access to resources in multithreaded applications.</span></span>  
  
 <span data-ttu-id="31b7e-104">응용 프로그램에서 여러 스레드를 사용하는 이점 중 하나는 각 스레드가 비동기적으로 실행된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-104">One of the benefits of using multiple threads in an application is that each thread executes asynchronously.</span></span> <span data-ttu-id="31b7e-105">Windows 응용 프로그램의 경우 이렇게 하면 시간이 많이 걸리는 작업을 백그라운드에서 수행하는 동시에 응용 프로그램 창과 컨트롤의 응답성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-105">For Windows applications, this allows time-consuming tasks to be performed in the background while the application window and controls remain responsive.</span></span> <span data-ttu-id="31b7e-106">서버 응용 프로그램의 경우 다중 스레딩을 사용하면 들어오는 각 요청을 다른 스레드에서 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-106">For server applications, multithreading provides the ability to handle each incoming request with a different thread.</span></span> <span data-ttu-id="31b7e-107">다중 스레딩을 사용하지 않으면 이전 요청이 완전히 충족될 때까지 새로운 각 요청이 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-107">Otherwise, each new request would not get serviced until the previous request had been fully satisfied.</span></span>  
  
 <span data-ttu-id="31b7e-108">그러나 스레드의 비동기 특성 때문에 파일 핸들, 네트워크 연결, 메모리 등의 리소스에 대한 액세스를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-108">However, the asynchronous nature of threads means that access to resources such as file handles, network connections, and memory must be coordinated.</span></span> <span data-ttu-id="31b7e-109">조정하지 않으면 둘 이상의 스레드가 다른 스레드의 작업을 모르는 상태로 같은 리소스에 동시에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-109">Otherwise, two or more threads could access the same resource at the same time, each unaware of the other's actions.</span></span> <span data-ttu-id="31b7e-110">그 결과, 예측할 수 없는 데이터 손상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-110">The result is unpredictable data corruption.</span></span>  
  
 <span data-ttu-id="31b7e-111">정수 계열 숫자 데이터 형식에 대한 간단한 작업을 위해 <xref:System.Threading.Interlocked> 클래스의 멤버를 사용하여 스레드를 동기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-111">For simple operations on integral numeric data types, synchronizing threads can be accomplished with members of the <xref:System.Threading.Interlocked> class.</span></span> <span data-ttu-id="31b7e-112">다른 모든 데이터 형식 및 스레드로부터 안전하지 않은 리소스의 경우 이 항목의 생성자를 사용해야만 다중 스레딩을 안전하게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-112">For all other data types and non thread-safe resources, multithreading can only be safely performed using the constructs in this topic.</span></span>  
  
 <span data-ttu-id="31b7e-113">다중 스레드 프로그래밍에 대한 배경 정보는 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31b7e-113">For background information on multithreaded programming, see:</span></span>  
  
-   [<span data-ttu-id="31b7e-114">관리되는 스레딩 기본 사항</span><span class="sxs-lookup"><span data-stu-id="31b7e-114">Managed Threading Basics</span></span>](../../../../standard/threading/managed-threading-basics.md)  
  
-   [<span data-ttu-id="31b7e-115">스레드 및 스레딩 사용</span><span class="sxs-lookup"><span data-stu-id="31b7e-115">Using Threads and Threading</span></span>](../../../../standard/threading/using-threads-and-threading.md)  
  
-   [<span data-ttu-id="31b7e-116">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="31b7e-116">Managed Threading Best Practices</span></span>](../../../../standard/threading/managed-threading-best-practices.md)  
  
## <a name="the-lock-and-synclock-keywords"></a><span data-ttu-id="31b7e-117">잠금 및 SyncLock 키워드</span><span class="sxs-lookup"><span data-stu-id="31b7e-117">The lock and SyncLock Keywords</span></span>  
 <span data-ttu-id="31b7e-118">Visual Basic `SyncLock` 다른 스레드에서 코드 블록을 중단 없이 완료 될 때까지 실행 되도록 사용할 수 문입니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-118">The Visual Basic `SyncLock` statement can be used to ensure that a block of code runs to completion without interruption by other threads.</span></span> <span data-ttu-id="31b7e-119">이렇게 하려면 코드 블록 기간 동안 지정된 개체에 대한 상호 배타적 잠금을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-119">This is accomplished by obtaining a mutual-exclusion lock for a given object for the duration of the code block.</span></span>  
  
 <span data-ttu-id="31b7e-120">`SyncLock` 문에 개체가 인수로 지정되고, 한 번에 하나의 스레드에 의해 실행되는 코드 블록이 뒤에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-120">A `SyncLock` statement is given an object as an argument, and is followed by a code block that is to be executed by only one thread at a time.</span></span> <span data-ttu-id="31b7e-121">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="31b7e-121">For example:</span></span>  
  
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
  
 <span data-ttu-id="31b7e-122">`SyncLock` 키워드에 제공되는 인수는 참조 형식을 기반으로 하는 개체여야 하며, 잠금 범위를 정의하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-122">The argument provided to the `SyncLock` keyword must be an object based on a reference type, and is used to define the scope of the lock.</span></span> <span data-ttu-id="31b7e-123">위의 예제에서는 `lockThis` 개체에 대한 참조가 함수 외부에 없기 때문에 잠금 범위가 이 함수로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-123">In the example above, the lock scope is limited to this function because no references to the object `lockThis` exist outside the function.</span></span> <span data-ttu-id="31b7e-124">이러한 참조가 있으면 잠금 범위가 해당 개체까지 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-124">If such a reference did exist, lock scope would extend to that object.</span></span> <span data-ttu-id="31b7e-125">엄격히 말해, 제공된 개체는 여러 스레드 간에 공유되는 리소스를 고유하게 식별하는 용도로만 사용되므로 임의의 클래스 인스턴스일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-125">Strictly speaking, the object provided is used solely to uniquely identify the resource being shared among multiple threads, so it can be an arbitrary class instance.</span></span> <span data-ttu-id="31b7e-126">그러나 실제로 이 개체는 일반적으로 스레드 동기화가 필요한 리소스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-126">In practice, however, this object usually represents the resource for which thread synchronization is necessary.</span></span> <span data-ttu-id="31b7e-127">예를 들어 컨테이너 개체가 여러 스레드에서 사용되는 경우 컨테이너를 잠금으로 전달할 수 있으며, 잠금 뒤에 나오는 동기화된 코드 블록에서 컨테이너에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-127">For example, if a container object is to be used by multiple threads, then the container can be passed to lock, and the synchronized code block following the lock would access the container.</span></span> <span data-ttu-id="31b7e-128">액세스하기 전에 다른 스레드가 동일한 컨테이너를 잠그기만 하면 개체 액세스가 안전하게 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-128">As long as other threads locks on the same contain before accessing it, then access to the object is safely synchronized.</span></span>  
  
 <span data-ttu-id="31b7e-129">일반적으로 응용 프로그램의 제어를 벗어난 `public` 형식 또는 개체 인스턴스에 대한 잠금은 피하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-129">Generally, it is best to avoid locking on a `public` type, or on object instances beyond the control of your application.</span></span> <span data-ttu-id="31b7e-130">예를 들어 `lockThis`는 인스턴스를 공개적으로 액세스할 수 있는 경우 사용자의 제어를 벗어난 코드에서 개체를 잠글 수도 있기 때문에 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-130">For example, `lockThis` can be problematic if the instance can be accessed publicly, because code beyond your control may lock on the object as well.</span></span> <span data-ttu-id="31b7e-131">이 경우 둘 이상의 스레드가 동일한 개체의 해제를 기다리는 교착 상태 상황이 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-131">This could create deadlock situations where two or more threads wait for the release of the same object.</span></span> <span data-ttu-id="31b7e-132">개체가 아니라 공용 데이터 형식을 잠그는 경우 동일한 이유로 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-132">Locking on a public data type, as opposed to an object, can cause problems for the same reason.</span></span> <span data-ttu-id="31b7e-133">리터럴 문자열 잠금은 리터럴 문자열이 CLR(공용 언어 런타임)에 의해 *인턴 지정*되므로 특히 위험합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-133">Locking on literal strings is especially risky because literal strings are *interned* by the common language runtime (CLR).</span></span> <span data-ttu-id="31b7e-134">즉, 지정된 문자열 리터럴 인스턴스가 전체 프로그램에 하나만 있고, 실행 중인 모든 응용 프로그램 도메인의 모든 스레드에서 똑같은 개체가 해당 리터럴을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-134">This means that there is one instance of any given string literal for the entire program, the exact same object represents the literal in all running application domains, on all threads.</span></span> <span data-ttu-id="31b7e-135">그 결과, 응용 프로그램 프로세스의 어디든지 동일한 콘텐츠가 있는 문자열에 잠금을 설정하면 응용 프로그램에서 해당 문자열의 모든 인스턴스가 잠깁니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-135">As a result, a lock placed on a string with the same contents anywhere in the application process locks all instances of that string in the application.</span></span> <span data-ttu-id="31b7e-136">따라서 인턴 지정되지 않은 private 또는 protected 멤버를 잠그는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-136">As a result, it is best to lock a private or protected member that is not interned.</span></span> <span data-ttu-id="31b7e-137">일부 클래스는 잠금을 위한 특수 멤버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-137">Some classes provide members specifically for locking.</span></span> <span data-ttu-id="31b7e-138">예를 들어 <xref:System.Array> 형식은 <xref:System.Array.SyncRoot%2A>를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-138">The <xref:System.Array> type, for example, provides <xref:System.Array.SyncRoot%2A>.</span></span> <span data-ttu-id="31b7e-139">많은 컬렉션 형식은 `SyncRoot` 멤버도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-139">Many collection types provide a `SyncRoot` member as well.</span></span>  
  
 <span data-ttu-id="31b7e-140">`SyncLock` 문에 대한 자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31b7e-140">For more information about the `SyncLock` statement, see the following topics:</span></span>  
  
-   [<span data-ttu-id="31b7e-141">SyncLock 문</span><span class="sxs-lookup"><span data-stu-id="31b7e-141">SyncLock Statement</span></span>](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
  
-   <xref:System.Threading.Monitor>  
  
## <a name="monitors"></a><span data-ttu-id="31b7e-142">모니터</span><span class="sxs-lookup"><span data-stu-id="31b7e-142">Monitors</span></span>  
 <span data-ttu-id="31b7e-143">`SyncLock` 키워드와 마찬가지로, 모니터는 코드 블록이 여러 스레드에서 동시에 실행되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-143">Like the `SyncLock` keyword, monitors prevent blocks of code from simultaneous execution by multiple threads.</span></span> <span data-ttu-id="31b7e-144"><xref:System.Threading.Monitor.Enter%2A> 메서드를 사용하면 하나의 스레드만 다음 문으로 계속 진행할 수 있습니다. 다른 모든 스레드는 실행 중인 스레드가 <xref:System.Threading.Monitor.Exit%2A>를 호출할 때까지 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-144">The <xref:System.Threading.Monitor.Enter%2A> method allows one and only one thread to proceed into the following statements; all other threads are blocked until the executing thread calls <xref:System.Threading.Monitor.Exit%2A>.</span></span> <span data-ttu-id="31b7e-145">이는 `SyncLock` 키워드를 사용하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-145">This is just like using the `SyncLock` keyword.</span></span> <span data-ttu-id="31b7e-146">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="31b7e-146">For example:</span></span>  
  
```vb  
SyncLock x  
    DoSomething()  
End SyncLock  
```  
  
 <span data-ttu-id="31b7e-147">다음 코드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-147">This is equivalent to:</span></span>  
  
```vb  
Dim obj As Object = CType(x, Object)  
System.Threading.Monitor.Enter(obj)  
Try  
    DoSomething()  
Finally  
    System.Threading.Monitor.Exit(obj)  
End Try  
```  
  
 <span data-ttu-id="31b7e-148">`SyncLock`이 더 간결할 뿐 아니라 `SyncLock`은 보호된 코드에서 예외를 throw하는 경우에도 기본 모니터가 해제되도록 하기 때문에 일반적으로 <xref:System.Threading.Monitor> 클래스를 직접 사용하는 것보다 `SyncLock` 키워드를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-148">Using the `SyncLock` keyword is generally preferred over using the <xref:System.Threading.Monitor> class directly, both because `SyncLock` is more concise, and because `SyncLock` insures that the underlying monitor is released, even if the protected code throws an exception.</span></span> <span data-ttu-id="31b7e-149">이렇게 하려면 예외가 throw되는지 여부에 관계없이 관련된 코드 블록을 실행하는 `Finally` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-149">This is accomplished with the `Finally` keyword, which executes its associated code block regardless of whether an exception is thrown.</span></span>  
  
## <a name="synchronization-events-and-wait-handles"></a><span data-ttu-id="31b7e-150">동기화 이벤트 및 대기 핸들</span><span class="sxs-lookup"><span data-stu-id="31b7e-150">Synchronization Events and Wait Handles</span></span>  
 <span data-ttu-id="31b7e-151">잠금 또는 모니터는 스레드가 중요한 코드 블록의 동시 실행을 방지하는 데 유용하지만 이러한 구문은 한 스레드가 다른 스레드에 이벤트를 전달할 수 있도록 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-151">Using a lock or monitor is useful for preventing the simultaneous execution of thread-sensitive blocks of code, but these constructs do not allow one thread to communicate an event to another.</span></span> <span data-ttu-id="31b7e-152">이렇게 하려면 스레드를 활성화하고 일시 중단하는 데 사용할 수 있는 두 상태(신호 알림 및 신호 알림 해제) 중 하나인 *동기화 이벤트* 개체가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-152">This requires *synchronization events*, which are objects that have one of two states, signaled and un-signaled, that can be used to activate and suspend threads.</span></span> <span data-ttu-id="31b7e-153">신호 알림이 해제된 동기화 이벤트에서 대기하도록 하여 스레드를 일시 중단하고, 이벤트 상태를 신호 알림으로 변경하여 스레드를 활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-153">Threads can be suspended by being made to wait on a synchronization event that is unsignaled, and can be activated by changing the event state to signaled.</span></span> <span data-ttu-id="31b7e-154">스레드가 이미 신호 알림을 보낸 이벤트에서 대기하려고 하면 지연 없이 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-154">If a thread attempts to wait on an event that is already signaled, then the thread continues to execute without delay.</span></span>  
  
 <span data-ttu-id="31b7e-155">동기화 이벤트에는 <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.ManualResetEvent>의 두 가지 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-155">There are two kinds of synchronization events: <xref:System.Threading.AutoResetEvent>, and <xref:System.Threading.ManualResetEvent>.</span></span> <span data-ttu-id="31b7e-156">두 가지 동기화 이벤트는 <xref:System.Threading.AutoResetEvent>가 스레드를 활성화할 때마다 자동으로 신호 알림에서 신호 알림 해제로 변경된다는 점만 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-156">They differ only in that <xref:System.Threading.AutoResetEvent> changes from signaled to unsignaled automatically any time it activates a thread.</span></span> <span data-ttu-id="31b7e-157">반대로, <xref:System.Threading.ManualResetEvent>는 개수와 관계없이 스레드가 신호 알림 상태에 의해 활성화될 수 있도록 하며, 해당 <xref:System.Threading.EventWaitHandle.Reset%2A> 메서드가 호출될 때만 신호 알림 해제 상태로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-157">Conversely, a <xref:System.Threading.ManualResetEvent> allows any number of threads to be activated by its signaled state, and will only revert to an unsignaled state when its <xref:System.Threading.EventWaitHandle.Reset%2A> method is called.</span></span>  
  
 <span data-ttu-id="31b7e-158"><xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, <xref:System.Threading.WaitHandle.WaitAll%2A> 등의 대기 메서드 중 하나를 호출하여 스레드가 이벤트에서 대기하도록 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-158">Threads can be made to wait on events by calling one of the wait methods, such as <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.WaitHandle.WaitAny%2A>, or <xref:System.Threading.WaitHandle.WaitAll%2A>.</span></span> <span data-ttu-id="31b7e-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>을 사용하면 단일 이벤트 신호 알림을 보낼 때까지 스레드가 대기하고, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType>을 사용하면 표시된 하나 이상의 이벤트 신호 알림을 보낼 때까지 스레드가 차단되고, <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType>을 사용하면 표시된 모든 이벤트 신호 알림을 보낼 때까지 스레드가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-159"><xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType> causes the thread to wait until a single event becomes signaled, <xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType> blocks a thread until one or more indicated events become signaled, and <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType> blocks the thread until all of the indicated events become signaled.</span></span> <span data-ttu-id="31b7e-160">해당 <xref:System.Threading.EventWaitHandle.Set%2A> 메서드가 호출될 때 이벤트 신호를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-160">An event becomes signaled when its <xref:System.Threading.EventWaitHandle.Set%2A> method is called.</span></span>  
  
 <span data-ttu-id="31b7e-161">다음 예제에서는 `Main` 함수에 의해 스레드가 생성되고 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-161">In the following example, a thread is created and started by the `Main` function.</span></span> <span data-ttu-id="31b7e-162">새 스레드는 <xref:System.Threading.WaitHandle.WaitOne%2A> 메서드를 사용하여 이벤트에서 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-162">The new thread waits on an event using the <xref:System.Threading.WaitHandle.WaitOne%2A> method.</span></span> <span data-ttu-id="31b7e-163">`Main` 함수를 실행하는 기본 스레드에서 이벤트 신호 알림을 보낼 때까지 스레드가 일시 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-163">The thread is suspended until the event becomes signaled by the primary thread that is executing the `Main` function.</span></span> <span data-ttu-id="31b7e-164">이벤트 신호 알림을 보내면 보조 스레드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-164">Once the event becomes signaled, the auxiliary thread returns.</span></span> <span data-ttu-id="31b7e-165">이 경우 이벤트는 하나의 스레드 활성화에만 사용되므로 <xref:System.Threading.AutoResetEvent> 또는 <xref:System.Threading.ManualResetEvent> 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-165">In this case, because the event is only used for one thread activation, either the <xref:System.Threading.AutoResetEvent> or <xref:System.Threading.ManualResetEvent> classes could be used.</span></span>  
  
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
  
## <a name="mutex-object"></a><span data-ttu-id="31b7e-166">뮤텍스 개체</span><span class="sxs-lookup"><span data-stu-id="31b7e-166">Mutex Object</span></span>  
 <span data-ttu-id="31b7e-167">*뮤텍스*는 모니터와 유사하며, 한 번에 둘 이상의 스레드가 코드 블록을 동시에 실행할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-167">A *mutex* is similar to a monitor; it prevents the simultaneous execution of a block of code by more than one thread at a time.</span></span> <span data-ttu-id="31b7e-168">실제로 "뮤텍스"란 이름은 "상호 배타적"이란 용어의 약식 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-168">In fact, the name "mutex" is a shortened form of the term "mutually exclusive."</span></span> <span data-ttu-id="31b7e-169">그러나 모니터와 달리 뮤텍스는 프로세스 간에 스레드를 동기화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-169">Unlike monitors, however, a mutex can be used to synchronize threads across processes.</span></span> <span data-ttu-id="31b7e-170">뮤텍스는 <xref:System.Threading.Mutex> 클래스가 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-170">A mutex is represented by the <xref:System.Threading.Mutex> class.</span></span>  
  
 <span data-ttu-id="31b7e-171">프로세스 간 동기화에 사용되는 경우 뮤텍스가 다른 응용 프로그램에서 사용되어 전역 또는 정적 변수를 통해 공유할 수 없기 때문에 *명명 된 뮤텍스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-171">When used for inter-process synchronization, a mutex is called a *named mutex* because it is to be used in another application, and therefore it cannot be shared by means of a global or static variable.</span></span> <span data-ttu-id="31b7e-172">두 응용 프로그램이 모두 동일한 뮤텍스 개체에 액세스할 수 있도록 이름이 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-172">It must be given a name so that both applications can access the same mutex object.</span></span>  
  
 <span data-ttu-id="31b7e-173">프로세스 간 스레드 동기화에 뮤텍스를 사용할 수 있지만, 모니터가 .NET Framework용으로 특별히 설계되어 리소스를 더 효율적으로 사용하기 때문에 일반적으로 <xref:System.Threading.Monitor>를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-173">Although a mutex can be used for intra-process thread synchronization, using <xref:System.Threading.Monitor> is generally preferred, because monitors were designed specifically for the .NET Framework and therefore make better use of resources.</span></span> <span data-ttu-id="31b7e-174">반면, <xref:System.Threading.Mutex> 클래스는 Win32 구문에 대한 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-174">In contrast, the <xref:System.Threading.Mutex> class is a wrapper to a Win32 construct.</span></span> <span data-ttu-id="31b7e-175">모니터보다 더 강력하지만, 뮤텍스는 <xref:System.Threading.Monitor> 클래스에 필요한 것보다 계산 비용이 더 큰 interop 전환이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-175">While it is more powerful than a monitor, a mutex requires interop transitions that are more computationally expensive than those required by the <xref:System.Threading.Monitor> class.</span></span> <span data-ttu-id="31b7e-176">뮤텍스 사용 예제는 [뮤텍스](../../../../standard/threading/mutexes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31b7e-176">For an example of using a mutex, see [Mutexes](../../../../standard/threading/mutexes.md).</span></span>  
  
## <a name="interlocked-class"></a><span data-ttu-id="31b7e-177">Interlocked 클래스</span><span class="sxs-lookup"><span data-stu-id="31b7e-177">Interlocked Class</span></span>  
 <span data-ttu-id="31b7e-178"><xref:System.Threading.Interlocked> 클래스의 메서드를 사용하여 여러 스레드가 동일한 값을 동시에 업데이트하거나 비교하려고 할 때 발생할 수 있는 문제를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-178">You can use the methods of the <xref:System.Threading.Interlocked> class to prevent problems that can occur when multiple threads attempt to simultaneously update or compare the same value.</span></span> <span data-ttu-id="31b7e-179">이 클래스의 메서드를 사용하면 모든 스레드의 값을 안전하게 증가, 감소, 교환 및 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-179">The methods of this class let you safely increment, decrement, exchange, and compare values from any thread.</span></span>  
  
## <a name="readerwriter-locks"></a><span data-ttu-id="31b7e-180">ReaderWriter 잠금</span><span class="sxs-lookup"><span data-stu-id="31b7e-180">ReaderWriter Locks</span></span>  
 <span data-ttu-id="31b7e-181">경우에 따라 데이터를 쓰고 있을 때만 리소스를 잠그고, 데이터를 업데이트하지 않을 때는 여러 클라이언트가 동시에 데이터를 읽을 수 있도록 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-181">In some cases, you may want to lock a resource only when data is being written and permit multiple clients to simultaneously read data when data is not being updated.</span></span> <span data-ttu-id="31b7e-182"><xref:System.Threading.ReaderWriterLock> 클래스는 스레드가 리소스를 수정하는 동안에는 리소스에 대한 배타적 액세스를 적용하지만 리소스를 읽을 때는 비배타적 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-182">The <xref:System.Threading.ReaderWriterLock> class enforces exclusive access to a resource while a thread is modifying the resource, but it allows non-exclusive access when reading the resource.</span></span> <span data-ttu-id="31b7e-183">ReaderWriter 잠금은 다른 스레드가 데이터를 업데이트할 필요가 없는 경우에도 해당 스레드가 대기하도록 하는 배타적 잠금의 유용한 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-183">ReaderWriter locks are a useful alternative to exclusive locks, which cause other threads to wait, even when those threads do not need to update data.</span></span>  
  
## <a name="deadlocks"></a><span data-ttu-id="31b7e-184">교착 상태</span><span class="sxs-lookup"><span data-stu-id="31b7e-184">Deadlocks</span></span>  
 <span data-ttu-id="31b7e-185">스레드 동기화는 다중 스레드 응용 프로그램에서 중요하지만 항상 여러 스레드가 서로를 대기하여 응용 프로그램이 중단되는 `deadlock`이 발생할 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-185">Thread synchronization is invaluable in multithreaded applications, but there is always the danger of creating a `deadlock`, where multiple threads are waiting for each other and the application comes to a halt.</span></span> <span data-ttu-id="31b7e-186">교착 상태는 자동차가 교차로 일단 정지 지점에서 멈춰 있고 서로 지나가기를 기다리는 상황과 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-186">A deadlock is analogous to a situation in which cars are stopped at a four-way stop and each person is waiting for the other to go.</span></span> <span data-ttu-id="31b7e-187">교착 상태를 방지하는 것이 중요하며, 관건은 신중한 계획입니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-187">Avoiding deadlocks is important; the key is careful planning.</span></span> <span data-ttu-id="31b7e-188">대체로 코딩을 시작하기 전에 다중 스레드 응용 프로그램의 다이어그램을 작성하면 교착 상태 상황을 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31b7e-188">You can often predict deadlock situations by diagramming multithreaded applications before you start coding.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b7e-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31b7e-189">See Also</span></span>  
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
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="31b7e-190">다중 스레드 응용 프로그램(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="31b7e-190">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="31b7e-191">SyncLock 문</span><span class="sxs-lookup"><span data-stu-id="31b7e-191">SyncLock Statement</span></span>](../../../../visual-basic/language-reference/statements/synclock-statement.md)  
 [<span data-ttu-id="31b7e-192">뮤텍스</span><span class="sxs-lookup"><span data-stu-id="31b7e-192">Mutexes</span></span>](../../../../standard/threading/mutexes.md)  
 [<span data-ttu-id="31b7e-193">연동 작업</span><span class="sxs-lookup"><span data-stu-id="31b7e-193">Interlocked Operations</span></span>](../../../../standard/threading/interlocked-operations.md)  
 [<span data-ttu-id="31b7e-194">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="31b7e-194">AutoResetEvent</span></span>](../../../../standard/threading/autoresetevent.md)  
 [<span data-ttu-id="31b7e-195">다중 스레딩을 위한 데이터 동기화</span><span class="sxs-lookup"><span data-stu-id="31b7e-195">Synchronizing Data for Multithreading</span></span>](../../../../standard/threading/synchronizing-data-for-multithreading.md)
