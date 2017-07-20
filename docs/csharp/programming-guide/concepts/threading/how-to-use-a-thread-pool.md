---
title: "방법: 스레드 풀 사용(C#) | Microsoft 문서"
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
ms.assetid: 210a9235-83a6-420b-af52-2d6a58e5133f
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
ms.openlocfilehash: 3814213389119f1fb6692fd57b0f5636a81025bb
ms.contentlocale: ko-kr
ms.lasthandoff: 05/10/2017

---
# <a name="how-to-use-a-thread-pool-c"></a>방법: 스레드 풀 사용(C#)
*스레드 풀링*은 스레드를 만들 때 자동으로 시작되고 작업이 큐에 추가되는 다중 스레딩의 한 형태입니다. 자세한 내용은 [스레드 풀링(C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)을 참조하세요.  
  
 다음 예제에서는 .NET Framework 스레드 풀을 사용하여 20에서 40 사이의 숫자 10개에 대한 `Fibonacci` 결과를 계산합니다. 각 `Fibonacci` 결과는 계산을 수행하는 `ThreadPoolCallback`이라는 메서드를 제공하는 `Fibonacci` 클래스로 표현됩니다. 각 `Fibonacci` 값을 나타내는 개체가 생성되고 `ThreadPoolCallback` 메서드가 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>에 전달되면, 여기서 풀에서 사용 가능한 스레드를 할당하여 메서드를 실행합니다.  
  
 각 `Fibonacci` 개체에 계산할 값이 반임의적으로 지정되고 각 스레드가 프로세서 시간을 경쟁하므로 10개 결과를 모두 계산하는 데 걸리는 기간을 미리 알 수 없습니다. 이 때문에 생성 중 각 `Fibonacci` 개체에 <xref:System.Threading.ManualResetEvent> 클래스 인스턴스가 전달됩니다. 해당 계산이 완료되면 각 개체가 제공된 이벤트 개체에 신호 알림을 보내며, 이렇게 하여 `Fibonacci` 개체 10개가 모두 결과를 계산할 때까지 기본 스레드에서 <xref:System.Threading.WaitHandle.WaitAll%2A>을 사용하여 실행을 차단할 수 있습니다. 그런 다음 `Main` 메서드가 각 `Fibonacci` 결과를 표시합니다.  
  
## <a name="example"></a>예제  
  
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
  
 다음은 출력의 예입니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Mutex>   
 <xref:System.Threading.WaitHandle.WaitAll%2A>   
 <xref:System.Threading.ManualResetEvent>   
 <xref:System.Threading.EventWaitHandle.Set%2A>   
 <xref:System.Threading.ThreadPool>   
 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>   
 <xref:System.Threading.ManualResetEvent>   
 [스레드 풀링(C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)   
 [스레딩(C#)](../../../../csharp/programming-guide/concepts/threading/index.md)   
 @System.Threading.Monitor   
 [보안](../../../../standard/security/index.md)
