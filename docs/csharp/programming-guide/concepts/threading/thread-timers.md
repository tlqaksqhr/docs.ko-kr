---
title: "스레드 타이머(C#) | Microsoft 문서"
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
ms.assetid: 52ed71e8-4fd9-43a4-ae40-04cce7cff23f
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1f91fde1340772c62f7779a2503bfb79aba7c3fb
ms.lasthandoff: 03/13/2017

---
# <a name="thread-timers-c"></a>스레드 타이머(C#)
<xref:System.Threading.Timer?displayProperty=fullName> 클래스는 별도 스레드에서 작업을 정기적으로 실행하는 데 유용합니다. 예를 들어 스레드 타이머를 사용하여 데이터베이스의 상태 및 무결성을 확인하거나 중요한 파일을 백업할 수 있습니다.  
  
## <a name="thread-timer-example"></a>스레드 타이머 예제  
 다음 예제에서는 2초마다 작업을 시작하고 플래그를 사용하여 타이머를 중지하는 <xref:System.IDisposable.Dispose%2A> 메서드를 시작합니다. 이 예제에서는 출력 창에 상태를 게시합니다.  
  
```csharp  
private class StateObjClass  
{  
    // Used to hold parameters for calls to TimerTask.  
    public int SomeValue;  
    public System.Threading.Timer TimerReference;  
    public bool TimerCanceled;  
}  
  
public void RunTimer()  
{  
    StateObjClass StateObj = new StateObjClass();  
    StateObj.TimerCanceled = false;  
    StateObj.SomeValue = 1;  
    System.Threading.TimerCallback TimerDelegate =  
        new System.Threading.TimerCallback(TimerTask);  
  
    // Create a timer that calls a procedure every 2 seconds.  
    // Note: There is no Start method; the timer starts running as soon as   
    // the instance is created.  
    System.Threading.Timer TimerItem =  
        new System.Threading.Timer(TimerDelegate, StateObj, 2000, 2000);  
  
    // Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem;    
  
    // Run for ten loops.  
    while (StateObj.SomeValue < 10)   
    {  
        // Wait one second.  
        System.Threading.Thread.Sleep(1000);    
    }  
  
    // Request Dispose of the timer object.  
    StateObj.TimerCanceled = true;    
}  
  
private void TimerTask(object StateObj)  
{  
    StateObjClass State = (StateObjClass)StateObj;  
    // Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(ref State.SomeValue);  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " + DateTime.Now.ToString());  
    if (State.TimerCanceled)      
    // Dispose Requested.  
    {  
        State.TimerReference.Dispose();  
        System.Diagnostics.Debug.WriteLine("Done  " + DateTime.Now.ToString());  
    }  
}  
```  
  
 스레드 타이머는 콘솔 응용 프로그램을 개발하는 경우 등 <xref:System.Windows.Forms.Timer?displayProperty=fullName> 개체를 사용할 수 없는 경우에 특히 유용합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading>   
 [다중 스레드 응용 프로그램(C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)
