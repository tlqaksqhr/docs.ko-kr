---
title: "방법: 스레드 풀 (Visual Basic)를 사용 하 여 | Microsoft 문서"
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
ms.assetid: 90a0bb24-39f8-41f5-a217-b52a7d4fed0b
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
ms.openlocfilehash: a86eabe40c91d96fc236c0a0de3ff668b855b9ab
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-use-a-thread-pool-visual-basic"></a><span data-ttu-id="e6c63-102">방법: 스레드 풀 (Visual Basic)를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="e6c63-102">How to: Use a Thread Pool (Visual Basic)</span></span>
<span data-ttu-id="e6c63-103">*스레드 풀링* 는 형태의 다중 스레딩의 작업 큐에 추가 되 고 자동으로 생성 된 스레드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c63-103">*Thread pooling* is a form of multithreading in which tasks are added to a queue and automatically started when threads are created.</span></span> <span data-ttu-id="e6c63-104">자세한 내용은 참조 [(Visual Basic)를 풀링 스레드](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c63-104">For more information, see [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md).</span></span>  
  
 <span data-ttu-id="e6c63-105">다음 예제에서는.NET Framework 스레드 풀을 사용 하 여 계산 하는 `Fibonacci` 20과 40 사이의 숫자를 10 개에 대 한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c63-105">The following example uses the .NET Framework thread pool to calculate the `Fibonacci` result for ten numbers between 20 and 40.</span></span> <span data-ttu-id="e6c63-106">각 `Fibonacci` 결과 나타내는 `Fibonacci` 라는 메서드를 제공 하는 클래스 `ThreadPoolCallback` 계산을 수행 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6c63-106">Each `Fibonacci` result is represented by the `Fibonacci` class, which provides a method named `ThreadPoolCallback` that performs the calculation.</span></span> <span data-ttu-id="e6c63-107">각각을 나타내는 개체입니다 `Fibonacci` 만들어지는 값 및 `ThreadPoolCallback` 전달 됩니다 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, 메서드를 실행 하는 풀에서 사용 가능한 스레드가 할당.</xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="e6c63-107">An object that represents each `Fibonacci` value is created, and the `ThreadPoolCallback` method is passed to <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>, which assigns an available thread in the pool to execute the method.</span></span>  
  
 <span data-ttu-id="e6c63-108">때문에 각 `Fibonacci` 개체 계산을 위해 어느 정도 임의적인 값이 지정 되 고 각 스레드는 프로세서 시간에 대 한 경쟁 합니다, 때문에 결과를 모두&10; 개의 계산 하는 데 걸리는 시간 할지 미리 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6c63-108">Because each `Fibonacci` object is given a semi-random value to compute, and because each thread will be competing for processor time, you cannot know in advance how long it will take for all ten results to be calculated.</span></span> <span data-ttu-id="e6c63-109">그건 각 `Fibonacci` 개체의 인스턴스가 전달 되는 <xref:System.Threading.ManualResetEvent>클래스를 생성 하는 동안.</xref:System.Threading.ManualResetEvent></span><span class="sxs-lookup"><span data-stu-id="e6c63-109">That is why each `Fibonacci` object is passed an instance of the <xref:System.Threading.ManualResetEvent> class during construction.</span></span> <span data-ttu-id="e6c63-110">각 개체에 제공된 된 이벤트 개체 신호 해당 계산이 완료 되 면, 기본 스레드를 사용 하 여 블록 실행을 허용 하는 <xref:System.Threading.WaitHandle.WaitAll%2A>10 모두까지 `Fibonacci` 개체에 결과 계산 했습니다.</xref:System.Threading.WaitHandle.WaitAll%2A></span><span class="sxs-lookup"><span data-stu-id="e6c63-110">Each object signals the provided event object when its calculation is complete, which allows the primary thread to block execution with <xref:System.Threading.WaitHandle.WaitAll%2A> until all ten `Fibonacci` objects have calculated a result.</span></span> <span data-ttu-id="e6c63-111">`Main` 메서드를 다음 각 표시 `Fibonacci` 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c63-111">The `Main` method then displays each `Fibonacci` result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6c63-112">예제</span><span class="sxs-lookup"><span data-stu-id="e6c63-112">Example</span></span>  
  
```vb  
Imports System.Threading  
  
Module Module1  
  
    Public Class Fibonacci  
        Private _n As Integer  
        Private _fibOfN  
        Private _doneEvent As ManualResetEvent  
  
        Public ReadOnly Property N() As Integer  
            Get  
                Return _n  
            End Get  
        End Property  
  
        Public ReadOnly Property FibOfN() As Integer  
            Get  
                Return _fibOfN  
            End Get  
        End Property  
  
        Sub New(ByVal n As Integer, ByVal doneEvent As ManualResetEvent)  
            _n = n  
            _doneEvent = doneEvent  
        End Sub  
  
        ' Wrapper method for use with the thread pool.  
        Public Sub ThreadPoolCallBack(ByVal threadContext As Object)  
            Dim threadIndex As Integer = CType(threadContext, Integer)  
            Console.WriteLine("thread {0} started...", threadIndex)  
            _fibOfN = Calculate(_n)  
            Console.WriteLine("thread {0} result calculated...", threadIndex)  
            _doneEvent.Set()  
        End Sub  
  
        Public Function Calculate(ByVal n As Integer) As Integer  
            If n <= 1 Then  
                Return n  
            End If  
            Return Calculate(n - 1) + Calculate(n - 2)  
        End Function  
  
    End Class  
  
    <MTAThread()>   
    Sub Main()  
        Const FibonacciCalculations As Integer = 9 ' 0 to 9  
  
        ' One event is used for each Fibonacci object  
        Dim doneEvents(FibonacciCalculations) As ManualResetEvent  
        Dim fibArray(FibonacciCalculations) As Fibonacci  
        Dim r As New Random()  
  
        ' Configure and start threads using ThreadPool.  
        Console.WriteLine("launching {0} tasks...", FibonacciCalculations)  
  
        For i As Integer = 0 To FibonacciCalculations  
            doneEvents(i) = New ManualResetEvent(False)  
            Dim f = New Fibonacci(r.Next(20, 40), doneEvents(i))  
            fibArray(i) = f  
            ThreadPool.QueueUserWorkItem(AddressOf f.ThreadPoolCallBack, i)  
        Next  
  
        ' Wait for all threads in pool to calculate.  
        WaitHandle.WaitAll(doneEvents)  
        Console.WriteLine("All calculations are complete.")  
  
        ' Display the results.  
        For i As Integer = 0 To FibonacciCalculations  
            Dim f As Fibonacci = fibArray(i)  
            Console.WriteLine("Fibonacci({0}) = {1}", f.N, f.FibOfN)  
        Next  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="e6c63-113">다음은 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="e6c63-113">Following is an example of the output.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6c63-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6c63-114">See Also</span></span>  
 <span data-ttu-id="e6c63-115"><xref:System.Threading.Mutex></xref:System.Threading.Mutex></span><span class="sxs-lookup"><span data-stu-id="e6c63-115"><xref:System.Threading.Mutex></span></span>   
 <span data-ttu-id="e6c63-116"><xref:System.Threading.WaitHandle.WaitAll%2A></xref:System.Threading.WaitHandle.WaitAll%2A></span><span class="sxs-lookup"><span data-stu-id="e6c63-116"><xref:System.Threading.WaitHandle.WaitAll%2A></span></span>   
 <span data-ttu-id="e6c63-117"><xref:System.Threading.ManualResetEvent></xref:System.Threading.ManualResetEvent></span><span class="sxs-lookup"><span data-stu-id="e6c63-117"><xref:System.Threading.ManualResetEvent></span></span>   
 <span data-ttu-id="e6c63-118"><xref:System.Threading.EventWaitHandle.Set%2A></xref:System.Threading.EventWaitHandle.Set%2A></span><span class="sxs-lookup"><span data-stu-id="e6c63-118"><xref:System.Threading.EventWaitHandle.Set%2A></span></span>   
 <span data-ttu-id="e6c63-119"><xref:System.Threading.ThreadPool></xref:System.Threading.ThreadPool></span><span class="sxs-lookup"><span data-stu-id="e6c63-119"><xref:System.Threading.ThreadPool></span></span>   
 <span data-ttu-id="e6c63-120"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span><span class="sxs-lookup"><span data-stu-id="e6c63-120"><xref:System.Threading.ThreadPool.QueueUserWorkItem%2A></span></span>   
 <span data-ttu-id="e6c63-121"><xref:System.Threading.ManualResetEvent></xref:System.Threading.ManualResetEvent></span><span class="sxs-lookup"><span data-stu-id="e6c63-121"><xref:System.Threading.ManualResetEvent></span></span>   
<span data-ttu-id="e6c63-122"> [스레드 풀링 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span><span class="sxs-lookup"><span data-stu-id="e6c63-122"> [Thread Pooling (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md) </span></span>  
<span data-ttu-id="e6c63-123"> [스레딩 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span><span class="sxs-lookup"><span data-stu-id="e6c63-123"> [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md) </span></span>  
 @System.Threading.Monitor   
<span data-ttu-id="e6c63-124"> [보안](http://msdn.microsoft.com/library/9a9621d7-8883-4a4f-a874-65e8e09e20a6)</span><span class="sxs-lookup"><span data-stu-id="e6c63-124"> [Security](http://msdn.microsoft.com/library/9a9621d7-8883-4a4f-a874-65e8e09e20a6)</span></span>
