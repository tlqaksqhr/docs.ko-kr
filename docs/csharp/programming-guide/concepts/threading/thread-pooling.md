---
title: 스레드 풀링(C#)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 98ae68c1-ace8-44b9-9317-8920ac9ef2b6
caps.latest.revision: 5
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 56fba1197fe81e60e27f300ec43879569d0a9d48
ms.sourcegitcommit: 68b60d38043e50104ccc90c76f8599b1ffe18346
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2018
---
# <a name="thread-pooling-c"></a><span data-ttu-id="323d8-102">스레드 풀링(C#)</span><span class="sxs-lookup"><span data-stu-id="323d8-102">Thread Pooling (C#)</span></span>
<span data-ttu-id="323d8-103">*스레드 풀*은 백그라운드에서 몇 가지 작업을 수행하는 데 사용할 수 있는 스레드 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-103">A *thread pool* is a collection of threads that can be used to perform several tasks in the background.</span></span> <span data-ttu-id="323d8-104">배경 정보는 [스레딩(C#)](../../../../csharp/programming-guide/concepts/threading/index.md)을 참조하세요. 이렇게 하면 기본 스레드가 자유롭게 다른 작업을 비동기적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-104">(See [Threading (C#)](../../../../csharp/programming-guide/concepts/threading/index.md) for background information.) This leaves the primary thread free to perform other tasks asynchronously.</span></span>  
  
 <span data-ttu-id="323d8-105">스레드 풀은 서버 응용 프로그램에서 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-105">Thread pools are often employed in server applications.</span></span> <span data-ttu-id="323d8-106">기본 스레드를 구속하거나 후속 요청의 처리를 지연하지 않고 요청을 비동기적으로 처리할 수 있도록 들어오는 각 요청이 스레드 풀의 스레드에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-106">Each incoming request is assigned to a thread from the thread pool, so that the request can be processed asynchronously, without tying up the primary thread or delaying the processing of subsequent requests.</span></span>  
  
 <span data-ttu-id="323d8-107">풀의 스레드가 해당 작업을 완료하면 대기 중인 스레드 큐로 반환되어 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-107">Once a thread in the pool completes its task, it is returned to a queue of waiting threads, where it can be reused.</span></span> <span data-ttu-id="323d8-108">이렇게 다시 사용하면 응용 프로그램에서 각 작업에 대한 새 스레드를 만드는 비용을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-108">This reuse enables applications to avoid the cost of creating a new thread for each task.</span></span>  
  
 <span data-ttu-id="323d8-109">일반적으로 스레드 풀에는 최대 개수의 스레드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-109">Thread pools typically have a maximum number of threads.</span></span> <span data-ttu-id="323d8-110">모든 스레드가 사용 중인 경우 추가 작업이 스레드를 사용할 수 있게 되면 처리될 때까지 큐에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-110">If all the threads are busy, additional tasks are put in queue until they can be serviced as threads become available.</span></span>  
  
 <span data-ttu-id="323d8-111">고유한 스레드 풀을 구현할 수 있지만, <xref:System.Threading.ThreadPool> 클래스를 통해 .NET Framework에서 제공하는 스레드 풀을 사용하는 편이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-111">You can implement your own thread pool, but it is easier to use the thread pool provided by the .NET Framework through the <xref:System.Threading.ThreadPool> class.</span></span>  
  
 <span data-ttu-id="323d8-112">스레드 풀링을 사용하는 경우 실행하려는 프로시저에 대한 대리자를 사용하여 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 메서드를 호출합니다. 그러면 C#에서 스레드를 만들고 프로시저를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-112">With thread pooling, you call the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> method with a delegate for the procedure you want to run, and C# creates the thread and runs your procedure.</span></span>  
  
## <a name="thread-pooling-example"></a><span data-ttu-id="323d8-113">스레드 풀링 예제</span><span class="sxs-lookup"><span data-stu-id="323d8-113">Thread Pooling Example</span></span>  
 <span data-ttu-id="323d8-114">다음 예제에서는 스레드 풀링을 사용하여 몇 가지 작업을 시작하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-114">The following example shows how you can use thread pooling to start several tasks.</span></span>  
  
```csharp  
public void DoWork()  
{  
    // Queue a task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(SomeLongTask));  
    // Queue another task.  
    System.Threading.ThreadPool.QueueUserWorkItem(  
        new System.Threading.WaitCallback(AnotherLongTask));  
}  
  
private void SomeLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
  
private void AnotherLongTask(Object state)  
{  
    // Insert code to perform a long task.  
}  
```  
  
 <span data-ttu-id="323d8-115">스레드 풀링의 한 가지 장점은 상태 개체의 인수를 작업 프로시저에 전달할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-115">One advantage of thread pooling is that you can pass arguments in a state object to the task procedure.</span></span> <span data-ttu-id="323d8-116">호출하는 프로시저에 둘 이상의 인수가 필요한 경우 구조체 또는 클래스 인스턴스를 `Object` 데이터 형식으로 캐스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-116">If the procedure you are calling requires more than one argument, you can cast a structure or an instance of a class into an `Object` data type.</span></span>  
  
## <a name="thread-pool-parameters-and-return-values"></a><span data-ttu-id="323d8-117">스레드 풀 매개 변수 및 반환 값</span><span class="sxs-lookup"><span data-stu-id="323d8-117">Thread Pool Parameters and Return Values</span></span>  
 <span data-ttu-id="323d8-118">스레드 풀 스레드에서 값을 반환하는 것은 간단하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-118">Returning values from a thread-pool thread is not straightforward.</span></span> <span data-ttu-id="323d8-119">`Sub` 프로시저가 스레드 풀에 대기될 수 있는 유일한 프로시저 형식이므로 함수 호출에서 값을 반환하는 표준 방법은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-119">The standard way of returning values from a function call is not allowed because `Sub` procedures are the only type of procedure that can be queued to a thread pool.</span></span> <span data-ttu-id="323d8-120">매개 변수 및 반환 값을 제공할 수 있는 한 가지 방법은 [다중 스레드 프로시저의 매개 변수 및 반환 값(C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)에 설명된 대로 매개 변수, 반환 값 및 메서드를 래퍼 클래스에 래핑하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-120">One way you can provide parameters and return values is by wrapping the parameters, return values, and methods in a wrapper class as described in [Parameters and Return Values for Multithreaded Procedures (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md).</span></span>  
  
 <span data-ttu-id="323d8-121">매개 변수 및 반환 값을 제공하는 보다 쉬운 방법은 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 메서드의 선택적 `ByVal` 상태 개체 변수를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-121">An easier way to provide parameters and return values is by using the optional `ByVal` state object variable of the <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> method.</span></span> <span data-ttu-id="323d8-122">이 변수를 사용하여 클래스 인스턴스에 대한 참조를 전달하는 경우 인스턴스 멤버가 스레드 풀 스레드에 의해 수정되고 반환 값으로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-122">If you use this variable to pass a reference to an instance of a class, the members of the instance can be modified by the thread-pool thread and used as return values.</span></span>  
  
 <span data-ttu-id="323d8-123">처음에는 값으로 전달된 변수가 참조하는 개체를 수정할 수 있는지 명확하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-123">At first it may not be obvious that you can modify an object referred to by a variable that is passed by value.</span></span> <span data-ttu-id="323d8-124">이 작업은 개체 참조만 값으로 전달되기 때문에 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-124">You can do this because only the object reference is passed by value.</span></span> <span data-ttu-id="323d8-125">개체 참조에서 참조된 개체의 멤버를 변경하는 경우 변경 내용이 실제 클래스 인스턴스에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-125">When you make changes to members of the object referred to by the object reference, the changes apply to the actual class instance.</span></span>  
  
 <span data-ttu-id="323d8-126">구조체를 사용하여 상태 개체 내의 값을 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-126">Structures cannot be used to return values inside state objects.</span></span> <span data-ttu-id="323d8-127">구조체는 값 형식이므로 비동기 프로세스를 통해 변경된 내용은 원래 구조체의 멤버를 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-127">Because structures are value types, changes that the asynchronous process makes do not change the members of the original structure.</span></span> <span data-ttu-id="323d8-128">반환 값이 필요하지 않은 경우 구조체를 사용하여 매개 변수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="323d8-128">Use structures to provide parameters when return values are not needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="323d8-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="323d8-129">See Also</span></span>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="323d8-130">방법: 스레드 풀 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="323d8-130">How to: Use a Thread Pool (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)  
 [<span data-ttu-id="323d8-131">스레딩(C#)</span><span class="sxs-lookup"><span data-stu-id="323d8-131">Threading (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="323d8-132">다중 스레드 응용 프로그램(C#)</span><span class="sxs-lookup"><span data-stu-id="323d8-132">Multithreaded Applications (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)  
 [<span data-ttu-id="323d8-133">스레드 동기화(C#)</span><span class="sxs-lookup"><span data-stu-id="323d8-133">Thread Synchronization (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)
