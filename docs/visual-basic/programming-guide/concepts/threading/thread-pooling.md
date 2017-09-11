---
title: "스레드 풀링 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 4903fb7a-eaad-435a-9add-1d1b32de3b83
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: eea7c94dffe525bb36c677bf3414f25ed0210074
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="thread-pooling-visual-basic"></a><span data-ttu-id="b8b59-102">스레드 풀링 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8b59-102">Thread Pooling (Visual Basic)</span></span>
<span data-ttu-id="b8b59-103">A *스레드 풀* 백그라운드에서 몇 가지 작업을 수행 하는 데 사용할 수 있는 스레드의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="b8b59-104">(참조 [스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) 배경 정보입니다.) 이런 기본 스레드를 자유롭게 다른 작업을 비동기적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-104">(See [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="b8b59-105">스레드 풀 서버 응용 프로그램에서 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="b8b59-106">기본 스레드까지 기다리거나의 후속 요청 처리를 연기 하지 않고는 요청을 비동기적으로 처리할 수 있도록 스레드 풀에서 들어오는 각 요청 스레드에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="b8b59-107">스레드 풀에서 해당 작업을 완료 되 면 반환 됩니다 대기 중인 스레드의 큐에 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="b8b59-108">이 다시 사용이 하기에는 각 작업에 대 한 새 스레드를 만드는 비용을 방지 하려면 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="b8b59-109">스레드 풀에는 일반적으로 최대 스레드 수 있으며</span><span class="sxs-lookup"><span data-stu-id="b8b59-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="b8b59-110">모든 스레드를 사용 중이면 추가 작업 스레드를 사용할 수 있을 때 처리 될 때까지 큐에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="b8b59-111">고유한 스레드 풀을 구현할 수 있지만 <xref:System.Threading.ThreadPool>클래스</xref:System.Threading.ThreadPool> 를 통해.NET Framework에서 제공 하는 스레드 풀을 사용 하 여 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="b8b59-112">호출 스레드 풀링을 사용할 경우는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName>프로시저에 대 한 대리자와 메서드를 실행 하려면, 및 Visual Basic에서 스레드를 만들고 프로시저를 실행 합니다.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="b8b59-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=fullName> method with a delegate for the procedure you want to run, and Visual Basic creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="b8b59-113">스레드 풀링 예제</span><span class="sxs-lookup"><span data-stu-id="b8b59-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="b8b59-114">다음 예제에서는 몇 가지 작업을 시작 하려면 풀링 스레드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
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
  
 <span data-ttu-id="b8b59-115">스레드 풀링의 이점은 수에 전달 하는 인수 상태 개체에는 작업 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="b8b59-116">또는 구조체에는 클래스의 인스턴스를 캐스팅할 수 프로시저를 호출 하는 둘 이상의 인수가 필요한 경우는 `Object` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="b8b59-117">스레드 풀 매개 변수 및 반환 값</span><span class="sxs-lookup"><span data-stu-id="b8b59-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="b8b59-118">스레드 풀 스레드가에서 값을 반환 간단 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="b8b59-119">함수 호출에서 값을 반환 하는 표준 방법 이므로 허용 되지 않습니다 `Sub` 프로시저는 프로시저는 스레드 풀에 대기할 수 있는 유일한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="b8b59-120">한 가지 방법은 매개 변수를 제공 하 수 값은 반환 값 매개 변수를 사용 하 여 래퍼에 메서드가 클래스에 설명 된 대로 반환 [매개 변수 및 반환 값 (Visual Basic) 다중 스레드 프로시저에 대 한](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="b8b59-121">반환 값 매개 변수를 제공 하는 보다 쉽게 선택적인를 사용 하 여는 `ByVal` 의 상태 개체 변수는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>메서드.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="b8b59-121">An easer way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="b8b59-122">이 변수를 사용 하 여 클래스의 인스턴스에 대 한 참조를 전달 하는 경우 인스턴스의 멤버를 스레드 풀 스레드에 의해 수정 하 고 반환 값으로 사용 되는 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="b8b59-123">처음에 하기 어려울 수 있습니다 값으로 전달 되는 변수에서 참조 하는 개체를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="b8b59-124">개체 참조만 값으로 전달 되기 때문에이 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="b8b59-125">개체 참조에서 참조 하는 개체의 구성원을 변경한 경우 변경 내용을 실제 클래스 인스턴스에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="b8b59-126">상태 개체 내 값을 반환 하려면 구조를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="b8b59-127">구조는 값 형식 이므로 비동기 프로세스를 통해 변경 된 원래 구조체의 멤버를 변경 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b8b59-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="b8b59-128">구조를 사용 하 여 반환 값이 필요 하지 않은 경우 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b59-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8b59-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8b59-129">See Also</span></span>  
 <span data-ttu-id="b8b59-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="b8b59-130"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span></span>   
 <span data-ttu-id="b8b59-131"><xref:System.Threading></xref:System.Threading></span><span class="sxs-lookup"><span data-stu-id="b8b59-131"><xref:System.Threading></span></span>   
 <span data-ttu-id="b8b59-132"><xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="b8b59-132"><xref:System.Threading.ThreadPool></span></span>   
<span data-ttu-id="b8b59-133"> [방법: 스레드 풀 (Visual Basic)를 사용 하 여](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span><span class="sxs-lookup"><span data-stu-id="b8b59-133"> [How to: Use a Thread Pool (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md) </span></span>  
<span data-ttu-id="b8b59-134"> [스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="b8b59-134"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
<span data-ttu-id="b8b59-135"> [다중 스레드 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span><span class="sxs-lookup"><span data-stu-id="b8b59-135"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md) </span></span>  
<span data-ttu-id="b8b59-136"> [스레드 동기화 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="b8b59-136"> [Thread Synchronization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)</span></span>
