---
title: "스레드 풀링 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 33b89d261aa2d038926f8c7e1832436b0cd34019
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="thread-pooling-visual-basic"></a><span data-ttu-id="9690f-102">스레드 풀링 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9690f-102">Thread Pooling (Visual Basic)</span></span>
<span data-ttu-id="9690f-103">*스레드 풀*은 백그라운드에서 몇 가지 작업을 수행하는 데 사용할 수 있는 스레드 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="9690f-104">(참조 [스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) 배경 정보에 대 한 합니다.) 이렇게 하면 기본 스레드가 자유롭게 다른 작업을 비동기적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-104">(See [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="9690f-105">스레드 풀은 서버 응용 프로그램에서 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="9690f-106">기본 스레드를 구속하거나 후속 요청의 처리를 지연하지 않고 요청을 비동기적으로 처리할 수 있도록 들어오는 각 요청이 스레드 풀의 스레드에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="9690f-107">풀의 스레드가 해당 작업을 완료하면 대기 중인 스레드 큐로 반환되어 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="9690f-108">이렇게 다시 사용하면 응용 프로그램에서 각 작업에 대한 새 스레드를 만드는 비용을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="9690f-109">일반적으로 스레드 풀에는 최대 개수의 스레드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="9690f-110">모든 스레드가 사용 중인 경우 추가 작업이 스레드를 사용할 수 있게 되면 처리될 때까지 큐에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="9690f-111">고유한 스레드 풀을 구현할 수 있지만, <xref:System.Threading.ThreadPool> 클래스를 통해 .NET Framework에서 제공하는 스레드 풀을 사용하는 편이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="9690f-112">호출 스레드 풀링을 사용는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 프로시저에 대 한 대리자 메서드를 실행 하려면, 및 Visual Basic에서 스레드를 만들고 프로시저를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method with a delegate for the procedure you want to run, and Visual Basic creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="9690f-113">스레드 풀링 예제</span><span class="sxs-lookup"><span data-stu-id="9690f-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="9690f-114">다음 예제에서는 스레드 풀링을 사용하여 몇 가지 작업을 시작하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
```vb  
Public Sub DoWork()  
    ' Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf SomeLongTask))  
    ' Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        New System.Threading.WaitCallback(AddressOf AnotherLongTask))  
End Sub  
Private Sub SomeLongTask(ByVal state As Object)  
    ' Insert code to perform a long task.  
End Sub  
Private Sub AnotherLongTask(ByVal state As Object)  
    ' Insert code to perform another long task.  
End Sub  
```  
  
 <span data-ttu-id="9690f-115">스레드 풀링의 한 가지 장점은 상태 개체의 인수를 작업 프로시저에 전달할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="9690f-116">호출하는 프로시저에 둘 이상의 인수가 필요한 경우 구조체 또는 클래스 인스턴스를 `Object` 데이터 형식으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="9690f-117">스레드 풀 매개 변수 및 반환 값</span><span class="sxs-lookup"><span data-stu-id="9690f-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="9690f-118">스레드 풀 스레드에서 값을 반환하는 것은 간단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="9690f-119">`Sub` 프로시저가 스레드 풀에 대기될 수 있는 유일한 프로시저 형식이므로 함수 호출에서 값을 반환하는 표준 방법은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="9690f-120">한 가지 방법은 매개 변수를 제공 있고 반환 값은 반환 값 매개 변수를 래핑하고 및 래퍼에 메서드가 클래스에 설명 된 대로 [매개 변수 및 반환 값에 대 한 다중 스레드 프로시저 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="9690f-121">매개 변수 및 반환 값을 제공하는 보다 쉬운 방법은 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 메서드의 선택적 `ByVal` 상태 개체 변수를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="9690f-122">이 변수를 사용하여 클래스 인스턴스에 대한 참조를 전달하는 경우 인스턴스 멤버가 스레드 풀 스레드에 의해 수정되고 반환 값으로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="9690f-123">처음에는 값으로 전달된 변수가 참조하는 개체를 수정할 수 있는지 명확하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="9690f-124">이 작업은 개체 참조만 값으로 전달되기 때문에 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="9690f-125">개체 참조에서 참조된 개체의 멤버를 변경하는 경우 변경 내용이 실제 클래스 인스턴스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="9690f-126">구조체를 사용하여 상태 개체 내의 값을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="9690f-127">구조체는 값 형식이므로 비동기 프로세스를 통해 변경된 내용은 원래 구조체의 멤버를 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="9690f-128">반환 값이 필요하지 않은 경우 구조체를 사용하여 매개 변수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9690f-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9690f-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9690f-129">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="9690f-130">방법: 스레드 풀 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9690f-130">How to: Use a Thread Pool (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [<span data-ttu-id="9690f-131">스레딩(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9690f-131">Threading (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="9690f-132">다중 스레드 응용 프로그램(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9690f-132">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="9690f-133">스레드 동기화(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9690f-133">Thread Synchronization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)
