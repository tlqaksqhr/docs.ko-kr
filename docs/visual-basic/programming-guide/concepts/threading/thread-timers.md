---
title: 스레드 타이머 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 809cba93-cc93-4e21-afda-f299f9a39818
ms.openlocfilehash: 019b8372be63b9a9fdbcee134834a34f6bef2b74
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646898"
---
# <a name="thread-timers-visual-basic"></a><span data-ttu-id="e65ba-102">스레드 타이머 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e65ba-102">Thread Timers (Visual Basic)</span></span>
<span data-ttu-id="e65ba-103"><xref:System.Threading.Timer?displayProperty=nameWithType> 클래스는 별도 스레드에서 정기적으로 작업을 실행하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e65ba-103">The <xref:System.Threading.Timer?displayProperty=nameWithType> class is useful for periodically running a task on a separate thread.</span></span> <span data-ttu-id="e65ba-104">예를 들어 스레드 타이머를 사용하여 데이터베이스의 상태 및 무결성을 확인하거나 중요한 파일을 백업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e65ba-104">For example, you could use a thread timer to check the status and integrity of a database or to back up critical files.</span></span>  
  
## <a name="thread-timer-example"></a><span data-ttu-id="e65ba-105">스레드 타이머 예제</span><span class="sxs-lookup"><span data-stu-id="e65ba-105">Thread Timer Example</span></span>  
 <span data-ttu-id="e65ba-106">다음 예제에서는 2초마다 작업을 시작하고 플래그를 사용하여 타이머를 중지하는 <xref:System.IDisposable.Dispose%2A> 메서드를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e65ba-106">The following example starts a task every two seconds and uses a flag to initiate the <xref:System.IDisposable.Dispose%2A> method that stops the timer.</span></span> <span data-ttu-id="e65ba-107">이 예제에서는 출력 창에 상태를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="e65ba-107">This example posts status to the output window.</span></span>  
  
```vb  
Private Class StateObjClass  
    ' Used to hold parameters for calls to TimerTask.  
    Public SomeValue As Integer  
    Public TimerReference As System.Threading.Timer  
    Public TimerCanceled As Boolean  
End Class  
  
Public Sub RunTimer()  
    Dim StateObj As New StateObjClass  
    StateObj.TimerCanceled = False  
    StateObj.SomeValue = 1  
    Dim TimerDelegate As New System.Threading.TimerCallback(AddressOf TimerTask)  
    ' Create a timer that calls a procedure every 2 seconds.  
    ' Note: There is no Start method; the timer starts running as soon as   
    ' the instance is created.  
    Dim TimerItem As New System.Threading.Timer(TimerDelegate, StateObj,  
                                                2000, 2000)  
    ' Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem  
  
    ' Run for ten loops.  
    While StateObj.SomeValue < 10  
        ' Wait one second.  
        System.Threading.Thread.Sleep(1000)  
    End While  
  
    ' Request Dispose of the timer object.  
    StateObj.TimerCanceled = True  
End Sub  
  
Private Sub TimerTask(ByVal StateObj As Object)  
    Dim State As StateObjClass = CType(StateObj, StateObjClass)  
    ' Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(State.SomeValue)  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " & Now.ToString)  
    If State.TimerCanceled Then  
        ' Dispose Requested.  
        State.TimerReference.Dispose()  
        System.Diagnostics.Debug.WriteLine("Done  " & Now)  
    End If  
End Sub  
```  
  
 <span data-ttu-id="e65ba-108">스레드 타이머는 콘솔 응용 프로그램을 개발하는 경우 등 <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> 개체를 사용할 수 없는 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e65ba-108">Thread timers are particularly useful when the <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> object is unavailable, such as when you are developing console applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e65ba-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e65ba-109">See Also</span></span>  
 <xref:System.Threading>  
 [<span data-ttu-id="e65ba-110">다중 스레드 응용 프로그램(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e65ba-110">Multithreaded Applications (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
