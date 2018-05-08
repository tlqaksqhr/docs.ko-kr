---
title: '방법: 스레드 풀 (Visual Basic)를 사용 하 여'
ms.date: 07/20/2015
ms.assetid: 90a0bb24-39f8-41f5-a217-b52a7d4fed0b
ms.openlocfilehash: a61defc2e40662d7fdadb40693e757fa559adb6a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-thread-pool-visual-basic"></a>방법: 스레드 풀 (Visual Basic)를 사용 하 여
*스레드 풀링*은 스레드를 만들 때 자동으로 시작되고 작업이 큐에 추가되는 다중 스레딩의 한 형태입니다. 자세한 내용은 참조 [(Visual Basic) 풀링 스레드](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)합니다.  
  
 다음 예제에서는 .NET Framework 스레드 풀을 사용하여 20에서 40 사이의 숫자 10개에 대한 `Fibonacci` 결과를 계산합니다. 각 `Fibonacci` 결과는 계산을 수행하는 `ThreadPoolCallback`이라는 메서드를 제공하는 `Fibonacci` 클래스로 표현됩니다. 각 `Fibonacci` 값을 나타내는 개체가 생성되고 `ThreadPoolCallback` 메서드가 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>에 전달되면, 여기서 풀에서 사용 가능한 스레드를 할당하여 메서드를 실행합니다.  
  
 각 `Fibonacci` 개체에 계산할 값이 반임의적으로 지정되고 각 스레드가 프로세서 시간을 경쟁하므로 10개 결과를 모두 계산하는 데 걸리는 기간을 미리 알 수 없습니다. 이 때문에 생성 중 각 `Fibonacci` 개체에 <xref:System.Threading.ManualResetEvent> 클래스 인스턴스가 전달됩니다. 해당 계산이 완료되면 각 개체가 제공된 이벤트 개체에 신호 알림을 보내며, 이렇게 하여 `Fibonacci` 개체 10개가 모두 결과를 계산할 때까지 기본 스레드에서 <xref:System.Threading.WaitHandle.WaitAll%2A>을 사용하여 실행을 차단할 수 있습니다. 그런 다음 `Main` 메서드가 각 `Fibonacci` 결과를 표시합니다.  
  
## <a name="example"></a>예제  
  
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
 <xref:System.Threading.Monitor>  
 [스레드 풀링(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)  
 [스레딩(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)  
 [보안](../../../../standard/security/index.md)
