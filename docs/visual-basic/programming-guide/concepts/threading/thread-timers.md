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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9ea657482d4e8e1465d9bc6ae3f94915badee512
ms.lasthandoff: 03/13/2017

---
# <a name="thread-timers-visual-basic"></a>스레드 타이머 (Visual Basic)
<xref:System.Threading.Timer?displayProperty=fullName>클래스는 정기적으로 별도 스레드에서 작업을 실행 하는 데 유용 합니다.</xref:System.Threading.Timer?displayProperty=fullName> 예를 들어, 상태 및 데이터베이스의 무결성을 확인 하거나 중요 한 파일을 백업 하는 스레드 타이머를 사용할 수 있습니다.  
  
## <a name="thread-timer-example"></a>스레드 타이머 예제  
 다음 예에서는&2; 초 마다 작업을 시작 하 고 플래그를 사용 하 여 시작 하는 <xref:System.IDisposable.Dispose%2A>타이머를 중지 하는 메서드입니다.</xref:System.IDisposable.Dispose%2A> 이 예제에서는 출력 창에 상태를 게시합니다.  
  
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
  
 스레드 타이머는 특히 유용는 <xref:System.Windows.Forms.Timer?displayProperty=fullName>개체를 개발 하는 경우 콘솔 응용 프로그램 등을 사용할 수 없는.</xref:System.Windows.Forms.Timer?displayProperty=fullName>  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading></xref:System.Threading>   
 [다중 스레드 응용 프로그램 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
