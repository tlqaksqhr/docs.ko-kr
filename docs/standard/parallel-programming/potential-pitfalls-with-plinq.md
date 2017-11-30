---
title: "PLINQ에서 발생할 수 있는 문제"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: PLINQ queries, pitfalls
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7c971d2c039e6441669108e966eba472819fde5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="potential-pitfalls-with-plinq"></a><span data-ttu-id="2a3b0-102">PLINQ에서 발생할 수 있는 문제</span><span class="sxs-lookup"><span data-stu-id="2a3b0-102">Potential Pitfalls with PLINQ</span></span>
<span data-ttu-id="2a3b0-103">대부분의 경우에서 PLINQ 순차 LINQ to Objects 쿼리를 통해 성능 향상을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-103">In many cases, PLINQ can provide significant performance improvements over sequential LINQ to Objects queries.</span></span> <span data-ttu-id="2a3b0-104">그러나 쿼리 실행을 병렬화 작업 하는 순차적 코드 일반적이 지 또는 전혀 발생 하지 않는 문제를 초래할 수 있는 복잡성을 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-104">However, the work of parallelizing the query execution introduces complexity that can lead to problems that, in sequential code, are not as common or are not encountered at all.</span></span> <span data-ttu-id="2a3b0-105">이 항목에서는 PLINQ 쿼리를 작성 하는 경우를 방지 하기 위해 몇 가지 사례를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-105">This topic lists some practices to avoid when you write PLINQ queries.</span></span>  
  
## <a name="do-not-assume-that-parallel-is-always-faster"></a><span data-ttu-id="2a3b0-106">병렬이 항상 더 빠르다고 가정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-106">Do Not Assume That Parallel Is Always Faster</span></span>  
 <span data-ttu-id="2a3b0-107">경우에 따라 병렬화 PLINQ 쿼리 하는 개체는 LINQ 보다 느리게 실행 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-107">Parallelization sometimes causes a PLINQ query to run slower than its LINQ to Objects equivalent.</span></span> <span data-ttu-id="2a3b0-108">경험적으로 된가 사용 하는 쿼리가 몇 가지 소스 요소와 빠른 사용자 대리자 속도가 가능성이 훨씬 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-108">The basic rule of thumb is that queries that have few source elements and fast user delegates are unlikely to speedup much.</span></span> <span data-ttu-id="2a3b0-109">그러나 성능에는 여러 가지 요소는 관련 PLINQ를 사용할 것인지를 결정 하기 전에 실제 결과 측정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-109">However, because many factors are involved in performance, we recommend that you measure actual results before you decide whether to use PLINQ.</span></span> <span data-ttu-id="2a3b0-110">자세한 내용은 [PLINQ의 속도 향상 이해](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-110">For more information, see [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).</span></span>  
  
## <a name="avoid-writing-to-shared-memory-locations"></a><span data-ttu-id="2a3b0-111">공유 메모리 위치에 쓰기 방지</span><span class="sxs-lookup"><span data-stu-id="2a3b0-111">Avoid Writing to Shared Memory Locations</span></span>  
 <span data-ttu-id="2a3b0-112">순차적 코드에서는 정적 변수 또는 클래스 필드에서 읽거나 쓰는 것은 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-112">In sequential code, it is not uncommon to read from or write to static variables or class fields.</span></span> <span data-ttu-id="2a3b0-113">그러나 여러 스레드가 해당 변수에 동시에 액세스할 때마다 경합 상태가 발생할 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-113">However, whenever multiple threads are accessing such variables concurrently, there is a big potential for race conditions.</span></span> <span data-ttu-id="2a3b0-114">잠금을 사용하여 변수에 대한 액세스를 동기화할 수 있지만 동기화의 비용으로 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-114">Even though you can use locks to synchronize access to the variable, the cost of synchronization can hurt performance.</span></span> <span data-ttu-id="2a3b0-115">따라서를 방지 하거나 적어도 제한 하에서 PLINQ 쿼리 가능한 한 공유 된 상태에 대 한 액세스는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-115">Therefore, we recommend that you avoid, or at least limit, access to shared state in a PLINQ query as much as possible.</span></span>  
  
## <a name="avoid-over-parallelization"></a><span data-ttu-id="2a3b0-116">과도한 병렬화 방지</span><span class="sxs-lookup"><span data-stu-id="2a3b0-116">Avoid Over-Parallelization</span></span>  
 <span data-ttu-id="2a3b0-117">사용 하 여는 `AsParallel` 연산자를 오버 헤드 비용을 소스 컬렉션을 분할 하 고 작업자 스레드를 동기화 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-117">By using the `AsParallel` operator, you incur the overhead costs of partitioning the source collection and synchronizing the worker threads.</span></span> <span data-ttu-id="2a3b0-118">병렬화의 이점은 컴퓨터의 프로세서 수로 더 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-118">The benefits of parallelization are further limited by the number of processors on the computer.</span></span> <span data-ttu-id="2a3b0-119">하나의 프로세서에서 여러 계산 바인딩된 스레드를 실행하여 얻을 수 있는 속도 향상이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-119">There is no speedup to be gained by running multiple compute-bound threads on just one processor.</span></span> <span data-ttu-id="2a3b0-120">따라서, 과도 한 쿼리를 병렬화 하지 않도록 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-120">Therefore, you must be careful not to over-parallelize a query.</span></span>  
  
 <span data-ttu-id="2a3b0-121">가장 일반적인 시나리오에 다음 코드 조각에 나와 있는 것 처럼 중첩된 쿼리 중인 어떤 과도 하 게 병렬화 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-121">The most common scenario in which over-parallelization can occur is in nested queries, as shown in the following snippet.</span></span>  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 <span data-ttu-id="2a3b0-122">이 경우 다음 조건 중 하나 이상이 적용 되지 않으면 외부 데이터 원본 (고객)만 병렬화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-122">In this case, it is best to parallelize only the outer data source (customers) unless one or more of the following conditions apply:</span></span>  
  
-   <span data-ttu-id="2a3b0-123">내부 데이터 원본 (cust 합니다. 주문)이 매우 긴 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-123">The inner data source (cust.Orders) is known to be very long.</span></span>  
  
-   <span data-ttu-id="2a3b0-124">각 순서에서 비용이 많이 드는 계산을 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-124">You are performing an expensive computation on each order.</span></span> <span data-ttu-id="2a3b0-125">(이 예제에 나와 있는 작업은 비용이 많이 들지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="2a3b0-125">(The operation shown in the example is not expensive.)</span></span>  
  
-   <span data-ttu-id="2a3b0-126">대상 시스템은 `cust.Orders`에서 쿼리를 병렬화하여 생성될 스레드의 수를 처리할 충분한 프로세서를 가진 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-126">The target system is known to have enough processors to handle the number of threads that will be produced by parallelizing the query on `cust.Orders`.</span></span>  
  
 <span data-ttu-id="2a3b0-127">모든 경우에서 최적의 쿼리 형태를 결정하는 가장 좋은 방법은 테스트하고 측정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-127">In all cases, the best way to determine the optimum query shape is to test and measure.</span></span> <span data-ttu-id="2a3b0-128">자세한 내용은 참조 [하는 방법: PLINQ 쿼리 성능 측정](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-128">For more information, see [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md).</span></span>  
  
## <a name="avoid-calls-to-non-thread-safe-methods"></a><span data-ttu-id="2a3b0-129">스레드로부터 안전하지 않은 메서드에 대한 호출 방지</span><span class="sxs-lookup"><span data-stu-id="2a3b0-129">Avoid Calls to Non-Thread-Safe Methods</span></span>  
 <span data-ttu-id="2a3b0-130">Plinq에서 스레드로부터 안전 하지 않은 인스턴스 메서드를 쓰는 쿼리 프로그램에서 발견 되지 않을 수도 있습니다는 데이터 손상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-130">Writing to non-thread-safe instance methods from a PLINQ query can lead to data corruption which may or may not go undetected in your program.</span></span> <span data-ttu-id="2a3b0-131">예외가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-131">It can also lead to exceptions.</span></span> <span data-ttu-id="2a3b0-132">다음 예제에서는 여러 스레드 호출을 시도 합니다는 `Filestream.Write` 메서드 동시에 클래스에 의해 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-132">In the following example, multiple threads would be attempting to call the `Filestream.Write` method simultaneously, which is not supported by the class.</span></span>  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## <a name="limit-calls-to-thread-safe-methods"></a><span data-ttu-id="2a3b0-133">스레드로부터 안전한 메서드에 대한 호출 제한</span><span class="sxs-lookup"><span data-stu-id="2a3b0-133">Limit Calls to Thread-Safe Methods</span></span>  
 <span data-ttu-id="2a3b0-134">.NET Framework에서 대부분의 정적 메서드는 스레드로부터 안전하고 여러 스레드에서 동시에 호출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-134">Most static methods in the .NET Framework are thread-safe and can be called from multiple threads concurrently.</span></span> <span data-ttu-id="2a3b0-135">그러나 이러한 경우에도 관련된 동기화로 인해 쿼리 속도가 상당히 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-135">However, even in these cases, the synchronization involved can lead to significant slowdown in the query.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a3b0-136">테스트할 수 있습니다이 대 한 직접 호출을 몇 개를 삽입 하 여 <xref:System.Console.WriteLine%2A> 쿼리에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-136">You can test for this yourself by inserting some calls to <xref:System.Console.WriteLine%2A> in your queries.</span></span> <span data-ttu-id="2a3b0-137">설명서의 예제에서는 설명을 위해이 메서드를 사용 해도 PLINQ 쿼리에서 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-137">Although this method is used in the documentation examples for demonstration purposes, do not use it in PLINQ queries.</span></span>  
  
## <a name="avoid-unnecessary-ordering-operations"></a><span data-ttu-id="2a3b0-138">불필요 한 순서 지정 작업을 방지</span><span class="sxs-lookup"><span data-stu-id="2a3b0-138">Avoid Unnecessary Ordering Operations</span></span>  
 <span data-ttu-id="2a3b0-139">PLINQ 쿼리 병렬로 실행 될 때 소스 시퀀스를 여러 스레드에서 동시에 작업할 수는 파티션으로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-139">When PLINQ executes a query in parallel, it divides the source sequence into partitions that can be operated on concurrently on multiple threads.</span></span> <span data-ttu-id="2a3b0-140">기본적으로 파티션이 처리 되 고 결과가 전달 순서를 예측할 수 없습니다 (같은 연산자를 제외 하 고 `OrderBy`).</span><span class="sxs-lookup"><span data-stu-id="2a3b0-140">By default, the order in which the partitions are processed and the results are delivered is not predictable (except for operators such as `OrderBy`).</span></span> <span data-ttu-id="2a3b0-141">PLINQ 소스 시퀀스의 순서를 유지 하도록 지시할 수 있습니다 수 있지만 성능 저하에이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-141">You can instruct PLINQ to preserve the ordering of any source sequence, but this has a negative impact on performance.</span></span> <span data-ttu-id="2a3b0-142">최상의 방법은 가능한 경우 항상는 쿼리를 구성 되므로 순서 유지에 의존 하지 마십시오입니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-142">The best practice, whenever possible, is to structure queries so that they do not rely on order preservation.</span></span> <span data-ttu-id="2a3b0-143">자세한 내용은 [PLINQ에서 순서 유지](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-143">For more information, see [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md).</span></span>  
  
## <a name="prefer-forall-to-foreach-when-it-is-possible"></a><span data-ttu-id="2a3b0-144">ForAll 선호 하는 가능한 경우에 ForEach</span><span class="sxs-lookup"><span data-stu-id="2a3b0-144">Prefer ForAll to ForEach When It Is Possible</span></span>  
 <span data-ttu-id="2a3b0-145">PLINQ의 결과 사용할 경우 여러 스레드에서 쿼리를 실행 하지만 `foreach` 루프 (`For Each` Visual basic에서), 쿼리 결과 하나의 스레드로 다시 병합 하 고 열거자에 순차적으로 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-145">Although PLINQ executes a query on multiple threads, if you consume the results in a `foreach` loop (`For Each` in Visual Basic), then the query results must be merged back into one thread and accessed serially by the enumerator.</span></span> <span data-ttu-id="2a3b0-146">경우에 따라이 피할 수 없는; 그러나 가능한 경우 항상 사용 하 여는 `ForAll` 메서드 자체 결과 같은 스레드로부터 안전한 컬렉션에 기록 하 여 출력에 각 스레드를 사용 하도록 설정 하려면 <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-146">In some cases, this is unavoidable; however, whenever possible, use the `ForAll` method to enable each thread to output its own results, for example, by writing to a thread-safe collection such as <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="2a3b0-147">동일한 문제가 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>에 적용됩니다. 즉, 다음 코드보다 `source.AsParallel().Where().ForAll(...)`을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-147">The same issue applies to <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> In other words, `source.AsParallel().Where().ForAll(...)` should be strongly preferred to</span></span>  
  
 <span data-ttu-id="2a3b0-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-148">`Parallel.ForEach(source.AsParallel().Where(), ...)`.</span></span>  
  
## <a name="be-aware-of-thread-affinity-issues"></a><span data-ttu-id="2a3b0-149">스레드 선호도 문제 인식</span><span class="sxs-lookup"><span data-stu-id="2a3b0-149">Be Aware of Thread Affinity Issues</span></span>  
 <span data-ttu-id="2a3b0-150">STA(단일 스레드 아파트) 구성 요소에 대한 COM 상호 운용성, Windows Forms 및 WPF(Windows Presentation Foundation)와 같은 일부 기술은 특정 스레드에서 실행하는 코드를 필요로 하는 스레드 선호도 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-150">Some technologies, for example, COM interoperability for Single-Threaded Apartment (STA) components, Windows Forms, and Windows Presentation Foundation (WPF), impose thread affinity restrictions that require code to run on a specific thread.</span></span> <span data-ttu-id="2a3b0-151">예를 들어 Windows Forms 및 WPF에서 컨트롤은 작성된 스레드에서만 액세스될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-151">For example, in both Windows Forms and WPF, a control can only be accessed on the thread on which it was created.</span></span> <span data-ttu-id="2a3b0-152">PLINQ 쿼리에서 Windows Forms 컨트롤의 공유 상태에 액세스 하려고 하면 디버거에서 실행 하는 경우 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-152">If you try to access the shared state of a Windows Forms control in a PLINQ query, an exception is raised if you are running in the debugger.</span></span> <span data-ttu-id="2a3b0-153">(이 설정을 해제할 수 있습니다.) 그러나 쿼리를 UI 스레드에서에서 소비 하는 경우 다음 있습니다 컨트롤에 액세스할 수에서 `foreach` 루프에서 쿼리를 열거 하는 한 스레드에서 코드를 실행 하기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-153">(This setting can be turned off.) However, if your query is consumed on the UI thread, then you can access the control from the `foreach` loop that enumerates the query results because that code executes on just one thread.</span></span>  
  
## <a name="do-not-assume-that-iterations-of-foreach-for-and-forall-always-execute-in-parallel"></a><span data-ttu-id="2a3b0-154">ForEach, For 및 ForAll의 반복이 항상 병렬로 실행된다고 가정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-154">Do Not Assume that Iterations of ForEach, For and ForAll Always Execute in Parallel</span></span>  
 <span data-ttu-id="2a3b0-155">이에 해당 개별 반복을 염두에 중요는 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 또는 <xref:System.Linq.ParallelEnumerable.ForAll%2A> 년 5 월 반복 하지만 동시에 실행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-155">It is important to keep in mind that individual iterations in a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> or <xref:System.Linq.ParallelEnumerable.ForAll%2A> loop may but do not have to execute in parallel.</span></span> <span data-ttu-id="2a3b0-156">따라서 반복의 병렬 실행 또는 특정 순서로 반복 실행의 정확성에 의존하는 코드를 작성하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-156">Therefore, you should avoid writing any code that depends for correctness on parallel execution of iterations or on the execution of iterations in any particular order.</span></span>  
  
 <span data-ttu-id="2a3b0-157">예를 들어 다음 코드는 교착 상태의 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-157">For example, this code is likely to deadlock:</span></span>  
  
```vb  
Dim mre = New ManualResetEventSlim()  
    Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll(Sub(j)   
  
                                                     If j = Environment.ProcessorCount Then  
  
                                                         Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Set()  
  
                                                     Else  
  
                                                         Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Wait()  
                                                     End If  
    End Sub) ' deadlocks  
```  
  
```csharp  
ManualResetEventSlim mre = new ManualResetEventSlim();  
            Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll((j) =>  
            {  
                if (j == Environment.ProcessorCount)  
                {  
                    Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Set();  
                }  
                else  
                {  
                    Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Wait();  
                }  
            }); //deadlocks  
```  
  
 <span data-ttu-id="2a3b0-158">이 예제에서는 하나의 반복이 이벤트를 설정하고 다른 모든 반복은 이벤트를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-158">In this example, one iteration sets an event, and all other iterations wait on the event.</span></span> <span data-ttu-id="2a3b0-159">대기 중인 반복은 이벤트 설정 반복이 완료될 때까지 완료할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-159">None of the waiting iterations can complete until the event-setting iteration has completed.</span></span> <span data-ttu-id="2a3b0-160">그러나 대기 중인 반복은 이벤트 설정 반복이 실행될 기회를 갖기 전에 병렬 루프를 실행하는 데 사용되는 모든 스레드를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-160">However, it is possible that the waiting iterations block all threads that are used to execute the parallel loop, before the event-setting iteration has had a chance to execute.</span></span> <span data-ttu-id="2a3b0-161">이로 인해 교착 상태가 발생하고 이벤트 설정 반복은 실행되지 않으며 대기 중인 반복은 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-161">This results in a deadlock – the event-setting iteration will never execute, and the waiting iterations will never wake up.</span></span>  
  
 <span data-ttu-id="2a3b0-162">특히 병렬 루프의 하나의 반복은 다른 루프의 반복이 진행되기를 기다리면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-162">In particular, one iteration of a parallel loop should never wait on another iteration of the loop to make progress.</span></span> <span data-ttu-id="2a3b0-163">병렬 루프가 반대 순서로 순차적으로 반복되도록 결정하는 경우 교착 상태가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b0-163">If the parallel loop decides to schedule the iterations sequentially but in the opposite order, a deadlock will occur.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3b0-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a3b0-164">See Also</span></span>  
 [<span data-ttu-id="2a3b0-165">PLINQ(병렬 LINQ)</span><span class="sxs-lookup"><span data-stu-id="2a3b0-165">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
