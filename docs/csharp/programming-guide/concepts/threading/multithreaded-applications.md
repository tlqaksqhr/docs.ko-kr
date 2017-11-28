---
title: "다중 스레드 응용 프로그램(C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b7015cfb-d506-4eac-b2f8-b2caaa9cc977
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 48b056172e3260952155eb40a1a393d86da78344
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="multithreaded-applications-c"></a><span data-ttu-id="d9691-102">다중 스레드 응용 프로그램(C#)</span><span class="sxs-lookup"><span data-stu-id="d9691-102">Multithreaded Applications (C#)</span></span>
<span data-ttu-id="d9691-103">C#에서는 동시에 여러 작업을 수행하는 응용 프로그램을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-103">With C#, you can write applications that perform multiple tasks at the same time.</span></span> <span data-ttu-id="d9691-104">다른 작업을 지연시킬 수 있는 작업은 별도 스레드에서 실행할 수 있으며, 이 프로세스를 *다중 스레딩* 또는 *자유 스레딩*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-104">Tasks with the potential of holding up other tasks can execute on separate threads, a process known as *multithreading* or *free threading*.</span></span>  
  
 <span data-ttu-id="d9691-105">다중 스레딩을 사용하는 응용 프로그램은 프로세서를 많이 사용하는 작업이 별도 스레드에서 실행될 때 사용자 인터페이스가 활성 상태로 유지되기 때문에 사용자 입력에 더 빠르게 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-105">Applications that use multithreading are more responsive to user input because the user interface stays active as processor-intensive tasks execute on separate threads.</span></span> <span data-ttu-id="d9691-106">또한 다중 스레딩은 작업이 증가함에 따라 스레드를 추가할 수 있으므로 확장 가능한 응용 프로그램을 만들 때에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-106">Multithreading is also useful when you create scalable applications, because you can add threads as the workload increases.</span></span>  
  
## <a name="creating-and-using-threads"></a><span data-ttu-id="d9691-107">스레드 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="d9691-107">Creating and Using Threads</span></span>  
 <span data-ttu-id="d9691-108">응용 프로그램 스레드의 동작을 보다 강력하게 제어해야 하는 경우 직접 스레드를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-108">If you need more control over the behavior of your application's threads, you can manage the threads yourself.</span></span> <span data-ttu-id="d9691-109">그러나 올바른 다중 스레드 응용 프로그램을 작성하는 것은 어려울 수 있습니다. 응용 프로그램이 응답하지 않거나 경합 상태로 인해 일시적인 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-109">However, realize that writing correct multithreaded applications can be difficult: Your application may stop responding or experience transient errors caused by race conditions.</span></span> <span data-ttu-id="d9691-110">자세한 내용은 [스레드로부터 안전한 구성 요소](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9691-110">For more information, see [Thread-Safe Components](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).</span></span>  
  
 <span data-ttu-id="d9691-111"><xref:System.Threading.Thread> 형식의 변수를 선언하고 새 스레드에서 실행하려는 프로시저 또는 메서드의 이름을 지정해서 생성자를 호출하여 새 스레드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-111">You create a new thread by declaring a variable of type <xref:System.Threading.Thread> and calling the constructor, providing the name of the procedure or method that you want to execute on the new thread.</span></span> <span data-ttu-id="d9691-112">코드 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-112">The following code provides an example.</span></span>  
  
```csharp  
System.Threading.Thread newThread =  
    new System.Threading.Thread(AMethod);  
```  
  
### <a name="starting-and-stopping-threads"></a><span data-ttu-id="d9691-113">스레드 시작 및 중지</span><span class="sxs-lookup"><span data-stu-id="d9691-113">Starting and Stopping Threads</span></span>  
 <span data-ttu-id="d9691-114">새 스레드의 실행을 시작하려면 다음 코드와 같이 <xref:System.Threading.Thread.Start%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-114">To start the execution of a new thread, use the <xref:System.Threading.Thread.Start%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Start();  
```  
  
 <span data-ttu-id="d9691-115">스레드 실행을 중지하려면 다음 코드와 같이 <xref:System.Threading.Thread.Abort%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-115">To stop the execution of a thread, use the <xref:System.Threading.Thread.Abort%2A> method, as shown in the following code.</span></span>  
  
```csharp  
newThread.Abort();  
```  
  
 <span data-ttu-id="d9691-116">스레드 시작 및 중지 외에도 <xref:System.Threading.Thread.Sleep%2A> 또는 <xref:System.Threading.Thread.Suspend%2A> 메서드를 호출하여 스레드를 일시 중지하고, <xref:System.Threading.Thread.Resume%2A> 메서드를 사용하여 일시 중단된 스레드를 다시 시작하고, <xref:System.Threading.Thread.Abort%2A> 메서드를 사용하여 스레드를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-116">Besides starting and stopping threads, you can also pause threads by calling the <xref:System.Threading.Thread.Sleep%2A> or <xref:System.Threading.Thread.Suspend%2A> method, resume a suspended thread by using the <xref:System.Threading.Thread.Resume%2A> method, and destroy a thread by using the <xref:System.Threading.Thread.Abort%2A> method</span></span>  
  
### <a name="thread-methods"></a><span data-ttu-id="d9691-117">스레드 메서드</span><span class="sxs-lookup"><span data-stu-id="d9691-117">Thread Methods</span></span>  
 <span data-ttu-id="d9691-118">다음 표에서는 개별 스레드를 제어하는 데 사용할 수 있는 메서드 중 일부를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-118">The following table shows some of the methods that you can use to control individual threads.</span></span>  
  
|<span data-ttu-id="d9691-119">메서드</span><span class="sxs-lookup"><span data-stu-id="d9691-119">Method</span></span>|<span data-ttu-id="d9691-120">작업</span><span class="sxs-lookup"><span data-stu-id="d9691-120">Action</span></span>|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|<span data-ttu-id="d9691-121">스레드 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-121">Causes a thread to start to run.</span></span>|  
|<xref:System.Threading.Thread.Sleep%2A>|<span data-ttu-id="d9691-122">지정된 시간 동안 스레드를 일시 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-122">Pauses a thread for a specified time.</span></span>|  
|<xref:System.Threading.Thread.Suspend%2A>|<span data-ttu-id="d9691-123">안전한 시점에 도달하면 스레드를 일시 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-123">Pauses a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Abort%2A>|<span data-ttu-id="d9691-124">안전한 시점에 도달하면 스레드를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-124">Stops a thread when it reaches a safe point.</span></span>|  
|<xref:System.Threading.Thread.Resume%2A>|<span data-ttu-id="d9691-125">일시 중지된 스레드를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-125">Restarts a suspended thread</span></span>|  
|<xref:System.Threading.Thread.Join%2A>|<span data-ttu-id="d9691-126">현재 스레드에서 다른 스레드가 완료되기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-126">Causes the current thread to wait for another thread to finish.</span></span> <span data-ttu-id="d9691-127">시간 제한 값과 함께 사용할 경우 이 메서드는 스레드가 할당된 시간 내에 완료되면 `True`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-127">If used with a time-out value, this method returns `True` if the thread finishes in the allocated time.</span></span>|  
  
### <a name="safe-points"></a><span data-ttu-id="d9691-128">안전 지점</span><span class="sxs-lookup"><span data-stu-id="d9691-128">Safe Points</span></span>  
 <span data-ttu-id="d9691-129">이러한 메서드의 대부분은 이해하기 쉽지만 *안전 지점*은 생소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-129">Most of these methods are self-explanatory, but the concept of *safe points* may be new to you.</span></span> <span data-ttu-id="d9691-130">안전 지점은 공용 언어 런타임에서 사용되지 않은 변수를 해제하고 메모리를 회수하는 프로세스인 *가비지 수집*을 자동으로 수행해도 안전한 코드 내 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-130">Safe points are locations in code where it is safe for the common language runtime to perform automatic *garbage collection*, the process of releasing unused variables and reclaiming memory.</span></span> <span data-ttu-id="d9691-131">스레드의 <xref:System.Threading.Thread.Abort%2A> 또는 <xref:System.Threading.Thread.Suspend%2A> 메서드를 호출하는 경우 공용 언어 런타임은 코드를 분석하고 스레드 실행을 중지할 적절한 위치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-131">When you call the <xref:System.Threading.Thread.Abort%2A> or <xref:System.Threading.Thread.Suspend%2A> method of a thread, the common language runtime analyzes the code and determines the location of an appropriate location for the thread to stop running.</span></span>  
  
### <a name="thread-properties"></a><span data-ttu-id="d9691-132">스레드 속성</span><span class="sxs-lookup"><span data-stu-id="d9691-132">Thread Properties</span></span>  
 <span data-ttu-id="d9691-133">스레드에는 다음 표에 나와 있는 것처럼 여러 가지 유용한 속성도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-133">Threads also contain several useful properties, as shown in the following table:</span></span>  
  
|<span data-ttu-id="d9691-134">속성</span><span class="sxs-lookup"><span data-stu-id="d9691-134">Property</span></span>|<span data-ttu-id="d9691-135">값</span><span class="sxs-lookup"><span data-stu-id="d9691-135">Value</span></span>|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|<span data-ttu-id="d9691-136">스레드가 활성 상태인 경우 `True` 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-136">Contains the value `True` if a thread is active.</span></span>|  
|<xref:System.Threading.Thread.IsBackground%2A>|<span data-ttu-id="d9691-137">스레드가 백그라운드 스레드인지 또는 그래야 하는지를 나타내는 부울 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-137">Gets or sets a Boolean that indicates if a thread is or should be a background thread.</span></span> <span data-ttu-id="d9691-138">백그라운드 스레드는 포그라운드 스레드와 유사하지만 백그라운드 스레드의 경우 프로세스가 중지되도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-138">Background threads are like foreground threads, but a background thread does not prevent a process from stopping.</span></span> <span data-ttu-id="d9691-139">프로세스에 속하는 모든 포그라운드 스레드가 중지되면 공용 언어 런타임은 여전히 활성 상태인 백그라운드 스레드에 대해 <xref:System.Threading.Thread.Abort%2A> 메서드를 호출하여 프로세스를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-139">Once all foreground threads that belong to a process have stopped, the common language runtime ends the process by calling the <xref:System.Threading.Thread.Abort%2A> method on background threads that are still alive.</span></span>|  
|<xref:System.Threading.Thread.Name%2A>|<span data-ttu-id="d9691-140">스레드의 이름을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-140">Gets or sets the name of a thread.</span></span> <span data-ttu-id="d9691-141">대체로 디버그할 때 개별 스레드를 찾는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-141">Most frequently used to discover individual threads when you debug.</span></span>|  
|<xref:System.Threading.Thread.Priority%2A>|<span data-ttu-id="d9691-142">운영 체제에서 스레드 예약의 우선 순위를 지정하는 데 사용되는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-142">Gets or sets a value that is used by the operating system to prioritize thread scheduling.</span></span>|  
|<xref:System.Threading.Thread.ThreadState%2A>|<span data-ttu-id="d9691-143">스레드 상태를 설명하는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-143">Contains a value that describes a thread's state or states.</span></span>|  
  
## <a name="thread-priorities"></a><span data-ttu-id="d9691-144">스레드 우선 순위</span><span class="sxs-lookup"><span data-stu-id="d9691-144">Thread Priorities</span></span>  
 <span data-ttu-id="d9691-145">모든 스레드에는 실행할 수 있는 프로세서 시간 조각의 크기를 결정하는 우선 순위 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-145">Every thread has a priority property that determines how big or small a slice of processor time it has to execute.</span></span> <span data-ttu-id="d9691-146">운영 체제는 우선 순위가 높은 스레드에 더 긴 시간 조각을 할당하고 우선 순위가 낮은 스레드에는 더 짧은 시간 조각을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-146">The operating system allocates longer time slices to high-priority threads and shorter time slices to low-priority threads.</span></span> <span data-ttu-id="d9691-147">새 스레드는 `Normal` 값으로 생성되지만, <xref:System.Threading.Thread.Priority%2A> 속성을 <xref:System.Threading.ThreadPriority> 열거형의 임의 값으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-147">New threads are created with the value of `Normal`, but you can change the <xref:System.Threading.Thread.Priority%2A> property to any value in the <xref:System.Threading.ThreadPriority> enumeration.</span></span>  
  
 <span data-ttu-id="d9691-148">다양한 스레드 우선 순위에 대한 자세한 설명은 <xref:System.Threading.ThreadPriority>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9691-148">See <xref:System.Threading.ThreadPriority> for a detailed description of the various thread priorities.</span></span>  
  
## <a name="foreground-and-background-threads"></a><span data-ttu-id="d9691-149">포그라운드 및 백그라운드 스레드</span><span class="sxs-lookup"><span data-stu-id="d9691-149">Foreground and Background Threads</span></span>  
 <span data-ttu-id="d9691-150">*포그라운드 스레드*는 무기한 실행되는 반면, *백그라운드 스레드*는 마지막 포그라운드 스레드가 중지되는 즉시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-150">A *foreground thread* runs indefinitely, whereas a *background thread* stops as soon as the last foreground thread has stopped.</span></span> <span data-ttu-id="d9691-151"><xref:System.Threading.Thread.IsBackground%2A> 속성을 사용하여 스레드의 백그라운드 상태를 확인하거나 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9691-151">You can use the <xref:System.Threading.Thread.IsBackground%2A> property to determine or change the background status of a thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9691-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9691-152">See Also</span></span>  
 <xref:System.Threading.Thread>  
 [<span data-ttu-id="d9691-153">스레드 동기화(C#)</span><span class="sxs-lookup"><span data-stu-id="d9691-153">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)  
 [<span data-ttu-id="d9691-154">다중 스레드 프로시저의 매개 변수 및 반환 값(C#)</span><span class="sxs-lookup"><span data-stu-id="d9691-154">Parameters and Return Values for Multithreaded Procedures (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)  
 [<span data-ttu-id="d9691-155">스레딩(C#)</span><span class="sxs-lookup"><span data-stu-id="d9691-155">Threading (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/index.md)
