---
title: "스레드 타이머 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 809cba93-cc93-4e21-afda-f299f9a39818
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
ms.openlocfilehash: af184f6f061cfd95b767a95a6b34f18bd6ba4f2b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="thread-timers-visual-basic"></a><span data-ttu-id="41321-102">스레드 타이머 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41321-102">Thread Timers (Visual Basic)</span></span>
<span data-ttu-id="41321-103"><xref:System.Threading.Timer?displayProperty=fullName>클래스는 정기적으로 별도 스레드에서 작업을 실행 하는 데 유용 합니다.</xref:System.Threading.Timer?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="41321-103">The <xref:System.Threading.Timer?displayProperty=fullName> class is useful for periodically running a task on a separate thread.</span></span> <span data-ttu-id="41321-104">예를 들어, 상태 및 데이터베이스의 무결성을 확인 하거나 중요 한 파일을 백업 하는 스레드 타이머를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41321-104">For example, you could use a thread timer to check the status and integrity of a database or to back up critical files.</span></span>  
  
## <a name="thread-timer-example"></a><span data-ttu-id="41321-105">스레드 타이머 예제</span><span class="sxs-lookup"><span data-stu-id="41321-105">Thread Timer Example</span></span>  
 <span data-ttu-id="41321-106">다음 예에서는&2; 초 마다 작업을 시작 하 고 플래그를 사용 하 여 시작 하는 <xref:System.IDisposable.Dispose%2A>타이머를 중지 하는 메서드입니다.</xref:System.IDisposable.Dispose%2A></span><span class="sxs-lookup"><span data-stu-id="41321-106">The following example starts a task every two seconds and uses a flag to initiate the <xref:System.IDisposable.Dispose%2A> method that stops the timer.</span></span> <span data-ttu-id="41321-107">이 예제에서는 출력 창에 상태를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="41321-107">This example posts status to the output window.</span></span>  
  
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
  
 <span data-ttu-id="41321-108">스레드 타이머는 특히 유용는 <xref:System.Windows.Forms.Timer?displayProperty=fullName>개체를 개발 하는 경우 콘솔 응용 프로그램 등을 사용할 수 없는.</xref:System.Windows.Forms.Timer?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="41321-108">Thread timers are particularly useful when the <xref:System.Windows.Forms.Timer?displayProperty=fullName> object is unavailable, such as when you are developing console applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41321-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="41321-109">See Also</span></span>  
 <span data-ttu-id="41321-110"><xref:System.Threading></xref:System.Threading></span><span class="sxs-lookup"><span data-stu-id="41321-110"><xref:System.Threading></span></span>   
<span data-ttu-id="41321-111"> [다중 스레드 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)</span><span class="sxs-lookup"><span data-stu-id="41321-111"> [Multithreaded Applications (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)</span></span>
