---
title: '방법: 스레드 풀 사용(C#)'
ms.date: 07/20/2015
ms.assetid: 210a9235-83a6-420b-af52-2d6a58e5133f
ms.openlocfilehash: c89093bcff82715482b2ddb822916cfa5ff8ed72
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-thread-pool-c"></a><span data-ttu-id="40450-102">방법: 스레드 풀 사용(C#)</span><span class="sxs-lookup"><span data-stu-id="40450-102">How to: Use a Thread Pool (C#)</span></span>
<span data-ttu-id="40450-103">*스레드 풀링*은 스레드를 만들 때 자동으로 시작되고 작업이 큐에 추가되는 다중 스레딩의 한 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="40450-103">*Thread pooling* is a form of multithreading in which tasks are added to a queue and automatically started when threads are created.</span></span> <span data-ttu-id="40450-104">자세한 내용은 [스레드 풀링(C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40450-104">For more information, see [Thread Pooling (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md).</span></span>  
  
 <span data-ttu-id="40450-105">다음 예제에서는 .NET Framework 스레드 풀을 사용하여 20에서 40 사이의 숫자 10개에 대한 `Fibonacci` 결과를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="40450-105">The following example uses the .NET Framework thread pool to calculate the `Fibonacci` result for ten numbers between 20 and 40.</span></span> <span data-ttu-id="40450-106">각 `Fibonacci` 결과는 계산을 수행하는 `ThreadPoolCallback`이라는 메서드를 제공하는 `Fibonacci` 클래스로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="40450-106">Each `Fibonacci` result is represented by the `Fibonacci` class, which provides a method named `ThreadPoolCallback` that performs the calculation.</span></span> <span data-ttu-id="40450-107">각 `Fibonacci` 값을 나타내는 개체가 생성되고 `ThreadPoolCallback` 메서드가 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>에 전달되면, 여기서 풀에서 사용 가능한 스레드를 할당하여 메서드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="40450-107">An object that represents each `Fibonacci` value is created, and the `ThreadPoolCallback` method is passed to <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, which assigns an available thread in the pool to execute the method.</span></span>  
  
 <span data-ttu-id="40450-108">각 `Fibonacci` 개체에 계산할 값이 반임의적으로 지정되고 각 스레드가 프로세서 시간을 경쟁하므로 10개 결과를 모두 계산하는 데 걸리는 기간을 미리 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40450-108">Because each `Fibonacci` object is given a semi-random value to compute, and because each thread will be competing for processor time, you cannot know in advance how long it will take for all ten results to be calculated.</span></span> <span data-ttu-id="40450-109">이 때문에 생성 중 각 `Fibonacci` 개체에 <xref:System.Threading.ManualResetEvent> 클래스 인스턴스가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="40450-109">That is why each `Fibonacci` object is passed an instance of the <xref:System.Threading.ManualResetEvent> class during construction.</span></span> <span data-ttu-id="40450-110">해당 계산이 완료되면 각 개체가 제공된 이벤트 개체에 신호 알림을 보내며, 이렇게 하여 `Fibonacci` 개체 10개가 모두 결과를 계산할 때까지 기본 스레드에서 <xref:System.Threading.WaitHandle.WaitAll%2A>을 사용하여 실행을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40450-110">Each object signals the provided event object when its calculation is complete, which allows the primary thread to block execution with <xref:System.Threading.WaitHandle.WaitAll%2A> until all ten `Fibonacci` objects have calculated a result.</span></span> <span data-ttu-id="40450-111">그런 다음 `Main` 메서드가 각 `Fibonacci` 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="40450-111">The `Main` method then displays each `Fibonacci` result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40450-112">예</span><span class="sxs-lookup"><span data-stu-id="40450-112">Example</span></span>  
  
```csharp  
using System;  
using System.Threading;  
  
public class Fibonacci  
{  
    private int _n;  
    private int _fibOfN;  
    private ManualResetEvent _doneEvent;  
  
    public int N { get { return _n; } }  
    public int FibOfN { get { return _fibOfN; } }  
  
    // Constructor.  
    public Fibonacci(int n, ManualResetEvent doneEvent)  
    {  
        _n = n;  
        _doneEvent = doneEvent;  
    }  
  
    // Wrapper method for use with thread pool.  
    public void ThreadPoolCallback(Object threadContext)  
    {  
        int threadIndex = (int)threadContext;  
        Console.WriteLine("thread {0} started...", threadIndex);  
        _fibOfN = Calculate(_n);  
        Console.WriteLine("thread {0} result calculated...", threadIndex);  
        _doneEvent.Set();  
    }  
  
    // Recursive method that calculates the Nth Fibonacci number.  
    public int Calculate(int n)  
    {  
        if (n <= 1)  
        {  
            return n;  
        }  
  
        return Calculate(n - 1) + Calculate(n - 2);  
    }  
}  
  
public class ThreadPoolExample  
{  
    static void Main()  
    {  
        const int FibonacciCalculations = 10;  
  
        // One event is used for each Fibonacci object.  
        ManualResetEvent[] doneEvents = new ManualResetEvent[FibonacciCalculations];  
        Fibonacci[] fibArray = new Fibonacci[FibonacciCalculations];  
        Random r = new Random();  
  
        // Configure and start threads using ThreadPool.  
        Console.WriteLine("launching {0} tasks...", FibonacciCalculations);  
        for (int i = 0; i < FibonacciCalculations; i++)  
        {  
            doneEvents[i] = new ManualResetEvent(false);  
            Fibonacci f = new Fibonacci(r.Next(20, 40), doneEvents[i]);  
            fibArray[i] = f;  
            ThreadPool.QueueUserWorkItem(f.ThreadPoolCallback, i);  
        }  
  
        // Wait for all threads in pool to calculate.  
        WaitHandle.WaitAll(doneEvents);  
        Console.WriteLine("All calculations are complete.");  
  
        // Display the results.  
        for (int i= 0; i<FibonacciCalculations; i++)  
        {  
            Fibonacci f = fibArray[i];  
            Console.WriteLine("Fibonacci({0}) = {1}", f.N, f.FibOfN);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="40450-113">다음은 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="40450-113">Following is an example of the output.</span></span>  
  
```  
launching 10 tasks...  
thread 0 started...  
thread 1 started...  
thread 1 result calculated...  
thread 2 started...  
thread 2 result calculated...  
thread 3 started...  
thread 3 result calculated...  
thread 4 started...  
thread 0 result calculated...  
thread 5 started...  
thread 5 result calculated...  
thread 6 started...  
thread 4 result calculated...  
thread 7 started...  
thread 6 result calculated...  
thread 8 started...  
thread 8 result calculated...  
thread 9 started...  
thread 9 result calculated...  
thread 7 result calculated...  
All calculations are complete.  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(25) = 75025  
Fibonacci(22) = 17711  
Fibonacci(38) = 39088169  
Fibonacci(29) = 514229  
Fibonacci(29) = 514229  
Fibonacci(38) = 39088169  
Fibonacci(21) = 10946  
Fibonacci(27) = 196418  
```  
  
## <a name="see-also"></a><span data-ttu-id="40450-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40450-114">See Also</span></span>  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.WaitHandle.WaitAll%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.EventWaitHandle.Set%2A>  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="40450-115">스레드 풀링(C#)</span><span class="sxs-lookup"><span data-stu-id="40450-115">Thread Pooling (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)  
 [<span data-ttu-id="40450-116">스레딩(C#)</span><span class="sxs-lookup"><span data-stu-id="40450-116">Threading (C#)</span></span>](../../../../csharp/programming-guide/concepts/threading/index.md)  
 [<span data-ttu-id="40450-117">보안</span><span class="sxs-lookup"><span data-stu-id="40450-117">Security</span></span>](../../../../standard/security/index.md)
